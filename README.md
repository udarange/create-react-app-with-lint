# Setup ESLint + Prettier with Create React App (default)

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## How to start
### Creating a TypeScript app
```
npx create-react-app my-app
cd my-app
```

### Extending or replacing the default ESLint config

Goto `package.json` and replace `eslintConfig` section
```
"eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ],
    "rules": {},
    "overrides": [
      {
        "files": [
          "**/*.ts?(x)"
        ],
        "rules": {}
      }
    ]
  }
```


### Formatting Code Automatically

Prettier is a code formatter
```
npm install --save husky lint-staged prettier
```
Add the following field to the `package.json`
```
"husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  }
```

```
"lint-staged": {
    "src/**/*.{js,jsx,ts,tsx,json,css,scss,md}": [
      "prettier --write"
    ]
  }
```


Add this new script to `package.json` file under `scripts`
```
"format": "prettier --write src/**/*.{js,jsx,ts,tsx,json,css,scss,md}"
```
Now you can simply format all files by executing the below command.
```
npm run format
```


**Note: Don't forget to run `npm run format` before starting the project.

In the project directory, you can run:
1. `npm run start`
2. `npm run build`

To learn React, check out the [React documentation](https://reactjs.org/).

