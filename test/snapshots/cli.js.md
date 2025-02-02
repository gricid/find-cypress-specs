# Snapshot report for `test/cli.js`

The actual snapshot is saved in `cli.js.snap`.

Generated by [AVA](https://avajs.dev).

## prints tags

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      Tag     Tests␊
      ------  -----␊
      @alpha  1    ␊
      @main   2    ␊
      @user   2␊
      -------␊
    `

## prints test names

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      cypress/e2e/spec.cy.js (2 tests)␊
      └─ parent suite [@main]␊
        ├─ works well enough␊
        └─ inner suite␊
          └─ shows something! [@user]␊
    ␊
      cypress/e2e/featureA/user.cy.ts (2 tests, 1 pending)␊
      ├─ works [@user]␊
      └⊙ needs to be written [@alpha]␊
    ␊
      found 2 specs (4 tests, 1 pending)␊
      -------␊
    `

## prints test tagged @alpha

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      cypress/e2e/featureA/user.cy.ts␊
      -------␊
    `

## prints test tagged @user

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      cypress/e2e/spec.cy.js,cypress/e2e/featureA/user.cy.ts␊
      -------␊
    `

## prints test tagged @main

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      cypress/e2e/spec.cy.js␊
      -------␊
    `

## prints test tagged @main and @alpha

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      cypress/e2e/spec.cy.js,cypress/e2e/featureA/user.cy.ts␊
      -------␊
    `

## prints only the skipped tests

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      cypress/e2e/featureA/user.cy.ts (1 test, 1 pending)␊
      └⊙ needs to be written [@alpha]␊
    ␊
      found 1 spec (1 test, 1 pending)␊
      -------␊
    `

## prints only the skipped test count

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      1␊
      -------␊
    `

## --pending is an alias to --skipped

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      cypress/e2e/featureA/user.cy.ts (1 test, 1 pending)␊
      └⊙ needs to be written [@alpha]␊
    ␊
      found 1 spec (1 test, 1 pending)␊
      -------␊
    `

## jsx components

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      test-components/comp1.cy.js (1 test)␊
      └─ Counter␊
        └─ works␊
    ␊
      test-components/comp2.cy.ts (1 test)␊
      └─ mock component suite 2␊
        └─ works␊
    ␊
      found 2 specs (2 tests)␊
      -------␊
    `

## exclusive tests

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      cypress/integration/spec1.js (2 tests)␊
      ├> runs by itself␊
      └─ another test␊
    ␊
      found 1 spec (2 tests)␊
      -------␊
    `

## prints test file names --tagged @alpha

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      cypress/e2e/featureA/user.cy.ts␊
      -------␊
    `

## prints test file names --tagged @alpha,@main,@user

> Snapshot 1

    `  code: 0␊
      stdout:␊
      -------␊
      cypress/e2e/featureA/user.cy.ts␊
      -------␊
    `
