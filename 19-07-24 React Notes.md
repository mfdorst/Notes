# React

## Installing create-react-app

```
$ npm i -g create-react-app
```

## Creating a new react app

```
$ npm init react-app <app-name>
```

## ESLint and Prettier

A specific version of `eslint` comes preinstalled, _do not install your own - things will break._

```
$ npm i prettier eslint-config-prettier eslint-plugin-prettier husky lint-staged pretty-quick -D
```

### Configuring ESLint and Prettier

Create a file named `.eslintrc` in the root directory of the app. It should contain:

```json
{
  "extends": ["react-app", "plugin:prettier/recommended"]
}
```

#### Automatic linting on git commit

In `package.json`, under `scripts`, add:

```json
"precommit": "pretty-quick --staged"
```
