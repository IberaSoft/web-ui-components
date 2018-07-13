# Web UI Components

[![Storybook](https://github.com/storybookjs/brand/blob/master/badge/badge-storybook.svg)](https://storybook.js.org/)

> Starting project with Next.js, React.js, TypeScript and Storybook


## Quick Start

1- Open your terminal and clone the repository on your disk

```
git clone https://github.com/IberaSoft/web-ui-components.git
```

2- Remove the .git folder

```
cd web-ui-components
rm -rf .git
```

3- Install all of the node dependencies and packages required by the project.

```
yarn install
```

4- Run Storybook.

```
yarn storybook
```

## Step by step guide from scratch

### Create a base project
```
mkdir my-app
cd my-app
yarn init -y
yarn add react react-dom next
mkdir page
```

Then, open the `package.json` file in the root directory and replace scripts with the following

```
"scripts": {
  "dev": "next",
  "build": "next build",
  "start": "next start"
}
```

Create a page to render in `pages/index.tsx` and copy the following code:
```
const Home = () => <h1>Hello world!</h1>;
export default Home;
```

### Add TypeScript and Types
```
yarn add -D typescript @types/react @types/node
```

Test your app starting the server with:
```
yarn dev
```
> note: you will get a warning `We detected TypeScript in your project and created a tsconfig.json file for you` and a tsconfig.json file will be created in the root of your project.

> optional: you can change the `strict` to `true` in `tsconfig.json` if you prefer.

### Add Storybook
```
yarn add -D @storybook/react @babel/core babel-loader babel-preset-react-app
```

Add the storybook script to the `package.json` file:
```
{
  ...
  "scripts": {
    ...
    "storybook": "start-storybook -p 6006 -c .storybook"
  }
}
```

Now create a `.storybook`folder on the root of your app:
```
mkdir .storybook
cd .storybook
touch config.js webpack.config.js
```

Go to config.js file:
```
import { configure } from '@storybook/react';
// automatically import all files ending in *.stories.tsx
configure(require.context('../src/stories', true, /\.stories\.tsx?$/), module);
```

Go to webpack.config.js file:
```
module.exports = ({ config }) => {
  config.module.rules.push({
    test: /\.(ts|tsx)$/,
    loader: require.resolve('babel-loader'),
    options: {
      presets: [require.resolve('babel-preset-react-app')],
    },
  });

  config.resolve.extensions.push('.ts', '.tsx');
  return config;
};
```

### Create a story

Create a button component inside src/components so that we can see if storybook is working properly.
```
cd src
mkdir components
cd components
touch Button.tsx
```

And copy the following code:
```
import * as React from 'react';

type Props = {
  text: string;
};

export default ({ text }: Props) => <button>{text}</button>;
```

Create a folder for your stories
```
mkdir src
cd src
mkdir stories
cd stories
touch Button.stories.tsx
```

And copy the following code:
```
import * as React from 'react';
import { storiesOf } from '@storybook/react';
import Button from '../components/Button';

storiesOf('Button', module).add('with text', () => {
  return <Button text="Click Me" />;
});
```

Start storybook:
```
yarn storybook
```

## License

- [MIT license](https://github.com/IberaSoft/web-ui-components/blob/master/LICENSE)
- Copyright 2018 © <a href="http://iberasoft.com" target="_blank">IberaSoft</a>.