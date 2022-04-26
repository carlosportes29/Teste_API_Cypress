# Teste_API_cypress

1 - npm init --yes (package.json e package_lock.json)

2 - npm install cypress@9.5.1 ou npm install cypress (instalar o cypress na última versão: https://docs.cypress.io/)

3 -npm install --save-dev cypress-cucumber-preprocessor (https://www.npmjs.com/package/cypress-cucumber-preprocessor)


Adicionar dados no arquivos a seguir:

**support/index.js**

const cucumber = require('cypress-cucumber-preprocessor').default

module.exports = (on, config) => {
  on('file:preprocessor', cucumber())
}

**cypress.json**

"testFiles": "**/*.feature"

**Adicionar o cucumber no package-json**

  "cypress-cucumber-preprocessor": {
    "nonGlobalStepDefinitions": false,
    "step_definitions": "cypress/support/steps",
    "cucumberJson": {
      "generate": true,
      "outputFolder": "cypress/cucumber-json",
      "filePrefix": "",
      "fileSuffix": ".json"
    }
	
_e depois rodar o npm update e logo em seguida.. executar o cypress chamando a função arquivo.feature com a finalidade de dar sucesso ao step definition
