# dr caroline min

The frontend codebase using nuxt 3, vue 3, and vuetify 3.

- [Nuxt 3 documentation](https://nuxt.com/docs/getting-started/introduction)
- [Vuetify 3 documentation](https://vuetifyjs.com/en/)

## Generate static site

https://nuxt.com/docs/getting-started/deployment#crawl-based-pre-rendering

```bash 
npx nuxi generate

npx serve .output/public
```

## Setup

Make sure to install the dependencies:

```bash
# yarn
yarn install

# npm
npm install

# pnpm
pnpm install
```

## Development Server

Start the development server on http://localhost:8080. The default port of 3000 is changed in `package.json` with this: `"dev": "nuxt dev --port=8080",`.

```bash
yarn dev
```

## Production

Build the application for production:

```bash
yarn build
```

Locally preview production build:

```bash
yarn preview
```

Check out the [deployment documentation](https://nuxt.com/docs/getting-started/deployment) for more information.

## Husky and Commitlint

https://github.com/conventional-changelog/commitlint

You can follow the `yarn` commands here, and use the linked article as a reference.

https://dev.to/sohandutta/make-everyone-in-your-project-write-beautiful-commit-messages-using-commitlint-and-commitizen-1amn

Install Husky

```bash
npx husky-init && yarn
```

Next, install commitlint

```bash
yarn add -D @commitlint/cli @commitlint/config-conventional
```

Add `commitlint` as a git hook

```bash
yarn husky add .husky/commit-msg 'yarn commitlint --edit "$1"'
```

**Note:** husky by default creates a pre-commit file, which runs npm test. If you don't have a test script defined in your package.json it will throw an error. You can remove the npm test line from the pre-commit file or add a valid test script.

Add `commitizen` cli for composing commit messages

```bash
yarn add -D commitizen cz-customizable
```

Add a `commitizen` config to your package.json.

```
{
  ....
  "devDependencies": {
    ...,
  },
  "config": {
    "commitizen": {
      "path": "cz-customizable"
    }
  }
}
```

Add a npm script to run `commitizen` cli.

```
{
  "scripts": {
    ...,
    "cm": "cz"
  },
  "dependencies": {
    ...
  }
}
```

Review the `cz-config.js` file.

## VueUse

This collection of utilities https://vueuse.org/ comes in very handy.

## Pinia

[Pinia](https://pinia.vuejs.org/ssr/nuxt.html) is a lightweight store that allows state to be shared across pages, etc.
