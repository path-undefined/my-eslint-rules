# My ESLint Rules

To initialized the ESLint for a project:

```console
$ npm i -D eslint @stylistic/eslint-plugin @typescript-eslint/parser @typescript-eslint/eslint-plugin
```

Install this package using following command:

```console
$ npm i -D https://github.com/path-undefined/my-eslint-rules
```

An example of the `eslint.config.mjs` file:

```js
import stylisticEslintPlugin from "@stylistic/eslint-plugin";
import typescriptEslintPlugin from "@typescript-eslint/eslint-plugin";
import typescriptEslintParser from "@typescript-eslint/parser";
import myEslintRules from "my-eslint-rules";

export default [
  {
    files: [
      "src/**/*.ts",
      "eslint.config.mjs",
    ],

    plugins: {
      "@typescript-eslint": typescriptEslintPlugin,
      "@stylistic": stylisticEslintPlugin,
    },

    languageOptions: {
      parser: typescriptEslintParser,
      parserOptions: {
        project: "./tsconfig.json",
        sourceType: "module",
      },
    },

    rules: {
      ...myEslintRules,
    },
  },
];
```