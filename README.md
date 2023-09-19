# Training GitHub Actions

### Estructura de un action.yml

- **name:** todo empieza por darle un nombre a aesta action. Esto va a darle un nombre al workflow
- **on:** (**********trigger**********) esto le indica a github cuando debe ejecutar este workflow.
    - workflow_dispatch: este evento se asegura de que podamos activar manualmente el workflow. Espera que inicie manualmente el usuario
- **jobs:** indica que deberia hacerse. la primer linea debajo y con sangria indica el nombre del job
    - identificar del job, ej first-job
        - ****************runs-on:**************** declara donde se van a ejecutar los diferentes steps de este job

Runners: github actions proporciona multiples entornos que podemos utilizar, con entornos configurados como windows server 2022, 2019, ubuntu 22.04, macos monterey, big sur, etc. Para buscar los labels que deberiamos utilizar, podemos revisar la pagina https://docs.github.com/es/actions/using-github-hosted-runners/about-github-hosted-runners#supported-runners-and-hardware-resources 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/3546ede7-4589-48fc-a4f2-4ce0fccbaec0/4a68513c-2ee5-42e4-8cca-e91cecd5db53/Untitled.png)

sige de jobs:

- **steps:** esta palabra clave la vamos a usar para definir los pasos que se deben ejecutar
    - Los steps se definen con un lineamiento de pasos, por tanto se debe ingresar un guion medio luego de la identacion, esto se define con un par de pares key-value que describen este paso y los pasos multiples definen guiones multiples.
        - **name:** necesario para identificar el paso que se va a ejecutar
        - **run:** para definir el comando que debe ejecutar en la linea de comandos o actions predefinidas
            - Para ejecutar multilineas de comando se puede usar pipe para idicarle que va a ejecutar varias lineas

```yaml
name: first workflow
on: workflow_dispatch
jobs:
  first-job:
    runs-on: ubuntu-latest
    step:
      - name: Print greeting
        run: echo "hello you""
      - name: Print goodbye
        run: |
          echo "Done"
          ecjo "goodbay you!"
```

Una vez commiteado este cambio, se debe ir a action darle run workflows.


[![Node.js CI](https://github.com/morewings/cra-template-npm-library/actions/workflows/merge-jobs.yml/badge.svg)](https://github.com/morewings/cra-template-npm-library/actions/workflows/merge-jobs.yml)
[![npm version](https://badge.fury.io/js/cra-template-npm-library.svg)](https://www.npmjs.com/package/cra-template-npm-library)
[![npm](https://img.shields.io/npm/dm/cra-template-npm-library)](http://npm-stats.org/#/cra-template-npm-library)

# NPM library Create React App template

[Create React App](https://github.com/facebook/create-react-app) (CRA) template to build and publish NPM libraries with **rollup**, **eslint** and **stylelint** configurations. See [full documentation](https://morewings.github.io/cra-template-npm-library).

## Usage

```shell script
npx create-react-app %PROJECT_NAME% --template npm-library
``` 
Or
```shell script
yarn create react-app %PROJECT_NAME% --template npm-library
```

Then

```shell script
cd %PROJECT_NAME%
yarn start
```

## Features

- Handles all modern JS features.
- Bundles `commonjs` and `es` module formats.
- [Husky](https://github.com/typicode/husky) for git hooks.
- [Eslint](https://eslint.org/) and [stylelint](https://stylelint.io/).
- [Rollup](https://rollupjs.org/guide/en/) for bundling.
- [Babel](https://babeljs.io/) for transpiling.
- [Jest](https://jestjs.io/) and [react-testing-library](https://testing-library.com/docs/react-testing-library/intro) for testing.
- Supports CSS modules, SASS/SCSS and PostCSS.
- [Storybook](https://storybook.js.org/) for documentation and demo.
- And [much more](https://cra-template-npm-library.netlify.com/).

## Contributors

@morewings, @sky0matic
