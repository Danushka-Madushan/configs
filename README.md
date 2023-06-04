#### ESLint ES6 CommonJS

`package.json`

```json
"scripts": {
    "lint": "eslint \"**/*.js\" --ignore-pattern node_modules/ --config .eslintrc.json --fix --cache"
}
```

#### ESLint ES2022 (Module) TypeScript

`package.json`

```json
"main": "./dist/index.js",
"type": "module",
"scripts": {
    "build": "tsc",
    "dev": "nodemon",
    "start": "node ./dist/index.js",
    "lint": "eslint \"./src/**/*.ts\" --ignore-pattern node_modules/ --config .eslintrc.json --fix --cache",
    "postinstall": "npm run build"
},
```

#### TypeScript Dev Dependancies + ESLint

```sh
npm init -y && npm i typescript && npm i -D nodemon tsc-watch eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser
```

#### NodeMon

`nodemon.json`

```json
{
    "exec": "index.js",
    "ignore": ["node_modules"],
    "ext": ".js,.json",
    "env": {
        "NODE_ENV": "development"
    }
}
```

```json
{
    "exec": "tsc-watch --onSuccess \"node ./dist/index.js\"",
    "ignore": ["node_modules"],
    "ext": ".ts,.json",
    "env": {
        "NODE_ENV": "development"
    }
}
```

#### ES2022 TypeScript

`.eslintrc.json`

```json5
/* eslint-env node */
{
    "env": {
        "node": true,
        "es6": true,
        "mongo": true
    },
    "extends": [
        "eslint:recommended",
        "plugin:@typescript-eslint/recommended",
        "plugin:@typescript-eslint/recommended-requiring-type-checking"
    ],
    "plugins": ["@typescript-eslint"],
    "parser": "@typescript-eslint/parser",
    /* TypeScript (Ignore -dist-) */
    "ignorePatterns": ["**/dist/*"],
    "parserOptions": {
        "project": true,
        "tsconfigRootDir": "__dirname",
        "ecmaVersion": 2022
    },
    "root": true,
    "rules": {
        "no-unused-vars": [
            "error", {
                "vars": "all",
                "args": "none",
                "ignoreRestSiblings": false
            }
        ],
        "space-before-function-paren": [
            "error", {
                "anonymous": "always",
                "named": "always",
                "asyncArrow": "always"
            }
        ],
        "space-infix-ops": [
            "error", {
                "int32Hint": false
            }
        ],
        "space-unary-ops": [
            2, {
                "words": true,
                "nonwords": false,
                "overrides": {
                    "new": false,
                    "++": true
                }
            }
        ],
        "spaced-comment": [ "error",
            "always", {
                "line": {
                    "markers": ["/"],
                    "exceptions": ["-", "+"]
                },
                "block": {
                    "markers": ["!"],
                    "exceptions": ["*"],
                    "balanced": true
                }
            }
        ],
        "no-irregular-whitespace" : [
            "error", {
                "skipStrings": true,
                "skipComments": true,
                "skipRegExps": true,
                "skipTemplates": true
            }
        ],
        "keyword-spacing": [ 
            "error", {
                "before": true,
                "after": true
            }
        ],
        "key-spacing": [
            "error", {
                "mode": "strict",
                "afterColon": true,
                "beforeColon": false
            }
        ],
        "no-duplicate-imports": [
            "error", {
                "includeExports": true
            }
        ],
        "arrow-spacing": [
            "error", {
                "before": true,
                "after": true
            }
        ],
        "comma-spacing": [
            "error", {
                "before": false,
                "after": true
            }
        ],
        "prefer-destructuring": [
            "error", {
                "array": false,
                "object": true
            },{
                "enforceForRenamedProperties": false
            }
        ],
        "array-bracket-spacing": [ "error",
            "always", {
                "singleValue": false,
                "arraysInArrays": false,
                "objectsInArrays": false
            }
        ],
        "brace-style": [ "error",
            "1tbs", {
                "allowSingleLine": true
            }
        ],
        "curly": ["error", "all"],
        "eqeqeq": ["error", "smart"],
        "linebreak-style": ["error", "windows"],
        "object-curly-spacing": ["error", "always"],
        "template-curly-spacing": ["error", "always"],
        "no-whitespace-before-property": "error",
        "no-mixed-spaces-and-tabs": "error",
        "no-prototype-builtins": "off",
        "no-case-declarations": "off",
        "space-before-blocks": "error",
        "block-scoped-var" : "error",
        "no-regex-spaces": "error",
        "no-multi-spaces": "error",
        "no-else-return" : "error",
        "no-fallthrough": "error",
        "valid-jsdoc": "error",
        "prefer-const": "error",
        "no-var": "error",
        /* TypeScript */
        "@typescript-eslint/no-misused-promises": [
            "error", {
                "checksVoidReturn": {
                    "arguments": false
                }
            }
        ]
    }
}
```

#### ES6 CommonJS

`.eslintrc.json`

```json
{
    "env": {
        "node": true,
        "commonjs": true,
        "es6": true
    },
    "extends": "eslint:recommended",
    "rules": {
        "no-unused-vars": [
            "error", {
                "vars": "all",
                "args": "none",
                "ignoreRestSiblings": false
            }
        ],
        "space-before-function-paren": [
            "error", {
                "anonymous": "always",
                "named": "always",
                "asyncArrow": "always"
            }
        ],
        "space-infix-ops": [
            "error", {
                "int32Hint": false
            }
        ],
        "space-unary-ops": [
            2, {
                "words": true,
                "nonwords": false,
                "overrides": {
                    "new": false,
                    "++": true
                }
            }
        ],
        "spaced-comment": [ "error",
            "always", {
                "line": {
                    "markers": ["/"],
                    "exceptions": ["-", "+"]
                },
                "block": {
                    "markers": ["!"],
                    "exceptions": ["*"],
                    "balanced": true
                }
            }
        ],
        "no-irregular-whitespace" : [
            "error", {
                "skipStrings": true,
                "skipComments": true,
                "skipRegExps": true,
                "skipTemplates": true
            }
        ],
        "keyword-spacing": [ 
            "error", {
                "before": true,
                "after": true
            }
        ],
        "key-spacing": [
            "error", {
                "mode": "strict",
                "afterColon": true,
                "beforeColon": false
            }
        ],
        "no-duplicate-imports": [
            "error", {
                "includeExports": true
            }
        ],
        "arrow-spacing": [
            "error", {
                "before": true,
                "after": true
            }
        ],
        "comma-spacing": [
            "error", {
                "before": false,
                "after": true
            }
        ],
        "prefer-destructuring": [
            "error", {
                "array": false,
                "object": true
            },{
                "enforceForRenamedProperties": false
            }
        ],
        "array-bracket-spacing": [ "error",
            "always", {
                "singleValue": false,
                "arraysInArrays": false,
                "objectsInArrays": false
            }
        ],
        "brace-style": [ "error",
            "1tbs", {
                "allowSingleLine": true
            }
        ],
        "curly": ["error", "all"],
        "eqeqeq": ["error", "smart"],
        "linebreak-style": ["error", "windows"],
        "object-curly-spacing": ["error", "always"],
        "template-curly-spacing": ["error", "always"],
        "no-whitespace-before-property": "error",
        "no-mixed-spaces-and-tabs": "error",
        "no-prototype-builtins": "off",
        "no-case-declarations": "off",
        "space-before-blocks": "error",
        "block-scoped-var" : "error",
        "no-regex-spaces": "error",
        "no-multi-spaces": "error",
        "no-else-return" : "error",
        "no-fallthrough": "error",
        "valid-jsdoc": "error",
        "prefer-const": "error",
        "no-var": "error"
    },
    "parserOptions": {
        "ecmaVersion": 2022
    }
}
```
