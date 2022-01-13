# find-cypress-specs ![cypress version](https://img.shields.io/badge/cypress-9.2.0-brightgreen)

> Find Cypress spec files using the config settings

```bash
$ npx find-cypress-specs
# prints all spec files separated by a comma
cypress/e2e/spec.js,cypress/e2e/featureA/user.js
```

## Test names

You can print each spec file with the suite and test names inside of it (found using [find-test-names](https://github.com/bahmutov/find-test-names))

```bash
$ npx find-cypress-specs --names
# prints something like

cypress/e2e/spec.js (2 tests)
└─ parent suite [@main]
  ├─ works well enough
  └─ inner suite
    └─ shows something [@user]

cypress/e2e/featureA/user.js (2 tests, 1 pending)
├─ works
└⊙ needs to be written

found 2 specs (4 tests, 1 pending)
```

Where the tags are listed inside `[ ... ]` (see [cypress-grep](https://github.com/cypress-io/cypress-grep)) and the [pending tests](https://glebbahmutov.com/blog/cypress-test-statuses/) are marked with `⊙` character.

## Test tags

You can count tags attached to the individual tests using `--tags` arguments

```
$ npx find-cypress-specs --tags
# prints the tags table sorted by tag

Tag    Tests
-----  ----------
@sign  1
@user  2
```

Each tag count includes the tests that use the tag directly, and the _effective_ tags applied from the parent suites.

## Details

Cypress uses the resolved [configuration values](https://on.cypress.io/configuration) to find the spec files to run. It searches the `integrationFolder` for all patterns listed in `testFiles` and removes any files matching the `ignoreTestFiles` patterns.

You can see how Cypress finds the specs using `DEBUG=cypress:cli,cypress:server:specs` environment variable to see verbose logs. The logic should be in the file `packages/server/lib/util/specs.ts` in the repo [cypress-io/cypress](https://github.com/cypress-io/cypress)

## Debugging

Run the utility with environment variable `DEBUG=find-cypress-specs` to see the verbose logs

## Small print

Author: Gleb Bahmutov &lt;gleb.bahmutov@gmail.com&gt; &copy; 2022

- [@bahmutov](https://twitter.com/bahmutov)
- [glebbahmutov.com](https://glebbahmutov.com)
- [blog](https://glebbahmutov.com/blog)
- [videos](https://www.youtube.com/glebbahmutov)
- [presentations](https://slides.com/bahmutov)
- [cypress.tips](https://cypress.tips)

License: MIT - do anything with the code, but don't blame me if it does not work.

Support: if you find any problems with this module, email / tweet /
[open issue](https://github.com/bahmutov/find-cypress-specs/issues) on Github

## MIT License

Copyright (c) 2022 Gleb Bahmutov &lt;gleb.bahmutov@gmail.com&gt;

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the "Software"), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.
