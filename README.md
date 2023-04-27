## ESLint ES6

`package.json`

```json
"scripts": {
    "lint": "eslint \"**/*.js\" --ignore-pattern node_modules/ --config .eslintrc.json --fix --cache"
}
```

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
        "spaced-comment": ["error",
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
        "no-duplicate-imports": [
            "error", {
                "includeExports": true
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
        "eqeqeq": ["error", "smart"],
        "linebreak-style": ["error", "windows"],
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
        "valid-jsdoc": "error"
    },
    "parserOptions": {
        "ecmaVersion": 2022
    }
}
```
