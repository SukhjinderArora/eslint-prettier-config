# ESLint and Prettier Configuration for React Applications.

To use this config:

* Copy `.eslintignore`, `.eslintrc.js`, `.prettierignore` and `.prettierrc.js` files to the root of your project directory.

* Install `eslint-config-airbnb` using `npx install-peerdeps --dev eslint-config-airbnb`.

    * It will install all required peer dependencies  such as `eslint`, `eslint-plugin-import`, `eslint-plugin-react`, `eslint-plugin-react-hooks`, and `eslint-plugin-jsx-a11y`

* Install `prettier` using `yarn add -D prettier` or `npm install --save-dev prettier`

* Install `eslint-config-prettier` using `yarn add -D eslint-config-prettier` or `npm install --save-dev eslint-config-prettier`

* Install `eslint-plugin-prettier` using `yarn add -D eslint-plugin-prettier` or `npm install --save-dev eslint-plugin-prettier`

* Install `eslint-plugin-jest` if you're using `jest` using `yarn add -D eslint-plugin-jest` or `npm install --save-dev eslint-plugin-jest`

* Install `eslint-plugin-testing-library` if you're using `react-testing-library` using `yarn add -D eslint-plugin-testing-library` or `npm install --save-dev eslint-plugin-testing-library`

* Install `husky` and `lint-staged` to lint and format files before `git commit` using `yarn add -D husky lint-staged` or `npm install --save-dev husky lint-staged`

* Remove `"eslintConfig"` property from `package.json`, if you are using `create-react-app`.

* Add these scripts in the `packages.json` scripts section:
    
```json
  "lint": "eslint .",
  "lint:fix": "eslint --fix .",
  "format": "prettier --write \"**/*.+(js|jsx|json|css|md)\""
```

* Add this section below the `package.json` scripts section:

```json
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "*.+(js|jsx)": [
      "eslint --fix",
      "git add"
    ],
    "*.+(json|css|md)": [
      "prettier --write",
      "git add"
    ]
  },
```