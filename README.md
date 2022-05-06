# **Simple** E2E test suite with Cypress

## :gear: Setup

1. `git clone https://github.com/jrgcubano/cypress-example.git`
2. cd to `cypress-example` folder and run `npm install`

## :heavy_check_mark: Run tests

- If you installed Cypress via npm: 
    - cypress test runner (cypress __open__):
      - **`npm run cy:open:web`** OR `cypress open --env device=web` (change web to mob to switch to mobile view)
    
    - cypress __headless mode__ (cypress run):
      - `npm run cy:run:web` OR `cypress run --env device=web`
- If you installed Cypress zip:
    - import **`cypress-example`** folder and you are good to go

## :bulb: Information
#### :test_tube: Tests:
:file_folder: Tests are located in `cypress/integration` folder

:file_folder: Custom commands are located in `cypress/support` folder (`.cmd.js` suffix)


#### :hammer_and_wrench: Configuration
Config files:
1. `cypress.json` - Main config file where default behavior of Cypress can be modified. [More info](https://docs.cypress.io/guides/references/configuration#cypress-json)
2. `plugins/index.js` - Plugins file is where we can programmatically alter the resolved configuration [More info](https://docs.cypress.io/guides/tooling/plugins-guide#Use-Cases)

This test suite is supporting multiple viewports (mobile and desktop). 

One solution is to use [cy.viewport()](https://docs.cypress.io/api/commands/viewport) command inside the test, to change the viewports, but very often websites also check user agent to get the device information(and show the mobile view). Since user agent is something [we can't change in the middle of the test](https://github.com/cypress-io/cypress/issues/2100), we need to pass config value when launching tests. In `cypress.json` we have a `device` parameter and in plugins file `index.js`, we decide viewports and user agent parameter values based on device value.

#### :diamond_shape_with_a_dot_inside: IDE setup and recommended extensions
- [VS Code](https://code.visualstudio.com/download) with following extensions:
    - [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) - to keep your code tidy
    - [Add Only](https://marketplace.visualstudio.com/items?itemName=ub1que.add-only) - enables to add/remove `.only` with one click
    - [VScode-icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons)

## :link: References

Original source: https://github.com/helenanull/cypress-example 
