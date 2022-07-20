# Web UI Components

[![Storybook](https://github.com/storybookjs/brand/blob/master/badge/badge-storybook.svg)](https://storybook.js.org/)


> Starting monorepo with React UI components following Atomic Design principles


A template of a monorepo to create a react application.

## :books: Table of Contents

- [Features](#features)
- [Commands](#keyboard-commands)
- [License](#scroll-license)

## Features

- [x] Monorepo tooling ([Yarn workspaces](https://classic.yarnpkg.com/en/docs/workspaces/) and [Lerna](https://github.com/lerna/lerna))
- [x] Precommit validation ([Husky](https://github.com/typicode/husky) and [Lint-staged](https://github.com/okonet/lint-staged))
- [x] Linting with recommended rules ([Eslint](https://github.com/eslint/eslint),[Prettier](https://github.com/prettier/prettier) and [Stylelint](https://github.com/stylelint/stylelint))
- [x] Github actions (test, lint, etc)
- [x] Storybook (with HMR)
- [x] CSS in Js ([Emotion](https://github.com/emotion-js/emotion))
- [x] HMR on packages ([React fast refresh](https://github.com/pmmmwh/react-refresh-webpack-plugin))
- [x] App running in CSR and SSR
- [x] Unit testing ([Jest](https://github.com/facebook/jest) and [React testing library](https://github.com/testing-library/react-testing-library))
- [x] Bundling ([Webpack 5](https://github.com/webpack/webpack))
- [x] Prevent duplicated versions of packages ([Dedubcheck](https://github.com/innovatrics/dedubcheck))
- [x] HTTP requests on server/client Isomorphic and state management ([Apollo/client](https://github.com/apollographql/apollo-client))
- [x] Deployed to production ([Heroku](https://dashboard.heroku.com/))
- [x] End 2 End tests ([Cypress](https://github.com/cypress-io/cypress))
- [x] Auto update typescript project references([Update-ts-references](https://github.com/eBayClassifiedsGroup/update-ts-references))
- [x] Generator to create packages in the monorepo ([Hygen](https://github.com/jondot/hygen))
- [x] Graphql schema validation and type checking ([eslint-plugin-graphql](https://github.com/apollostack/eslint-plugin-graphql)) and ([apollo-tooling](https://github.com/apollographql/apollo-tooling))
- [ ] Automatic create and validate the graphql schema on pipeline
- [ ] Jest shared configs easily
- [ ] Jest with recommend rules for react/node projects
- [x] Tsconfig with recommend rules for react/node projects ([tsconfig/bases](https://github.com/tsconfig/bases))
- [ ] Package Manager ([Yarn 2](https://yarnpkg.com/getting-started/migration))
- [ ] Multiple team project handling tool (Codeowners and Merge bot)
- [ ] Document how to handle peerdependencies on the monorepo
- [ ] Load tests ([Artillary](https://github.com/artilleryio/artillery))


## :keyboard: Commands

Run all the commands from the root folder
The monorepo is built in a way where you don't need to change from the root to run any command

### Install dependencies
```
yarn
```

### Start dev server
```
yarn start
```

### Start production server (SSR)
```
yarn start:server
```

### Typescript build
```
yarn build
```

### Typescript watch
```
yarn watch
```

### Lint all the project
```
yarn lint
```

### Test all the project
```
yarn test
```

### Find duplicated dependencies on the project
```
yarn test:dependencies
```

### Start storybook
```
yarn storybook
```

### Test E2E
```
yarn test:e2e
```

note: you need to start the client

### Heroku deploy
On your project do this steps:

Login in your heroku account
```
heroku login
```

This will create a project in the heroku account you loggedin previously
```
heroku create
```

Can be master or main the next command depending on your repo
```
git push heroku master
```

Note: This part requires you to have a heroku account

## Typescript references

They are updated automatically as soon as you do `yarn`


## License

- [GPL-3.0-or-later](https://github.com/IberaSoft/web-ui-components/blob/master/LICENSE)
- Copyright 2022 © <a href="https://iberasoft.com" target="_blank">IberaSoft</a>.