# Development settings

back to [main project page][mainpage]

## JEST

- [jest-Extended](https://github.com/jest-community/jest-extended)
- [Jest Cheat Sheet](https://github.com/sapegin/jest-cheat-sheet)
- [jest-mock-process](https://github.com/EpicEric/jest-mock-process)

## ESLINT

- [Typescript-Eslint :: Getting started](https://github.com/typescript-eslint/typescript-eslint/blob/master/docs/getting-started/linting/README.md)
- [Eslint-jest plugin](https://www.npmjs.com/package/eslint-plugin-jest)

## local installation

Locally install the package (using a symlink!).

**Warning**: Use at your own risk! the npm link/unlink seems to cause troubles sometimes... see note and refs below.

### install/link

To bind the package in the **local npm repository** i.e. to make the libraries and the CLI available globaly on the local dev machine, one can **link** the package:

```shell
> npm run dev:publish
```

### uninstall/unlink

To uninstall the locally deployed package i.e. to **unlink** the package from the **local npm repository**, one can use:

```shell
> npm run dev:unpublish
```

note: uninstalling may break the package integrity (at least on windows os). In this case, the "node_modules" and "package.lock.json" need to be re-created. This is implemented in the "dev:unpublish" script.

## Addendum

The npm script "**copyts**" (in the root `package.json`) may cause some problem, depending on the paths used in the project (e.g. when paths are containing space charcters). In this case, the paths should be put in double quotes, like:

```json
{
  "copyts": "copyfiles -u 2 \"src/lib/**/*\" -e \"**/*.spec.ts\" lib/ts"
}
```

instead of the simple

```json
{
  "copyts": "copyfiles -u 2 src/lib/**/* -e **/*.spec.ts lib/ts"
}
```

## References

- [Publishing Node modules with TypeScript and ES modules](https://blog.logrocket.com/publishing-node-modules-typescript-es-modules/)
- [npm-link](https://docs.npmjs.com/cli/link)
- [ES6 modules in depth](https://ponyfoo.com/articles/es6-modules-in-depth)
- [create a node cli package](https://medium.com/netscape/a-guide-to-create-a-nodejs-command-line-package-c2166ad0452e)

[mainpage]: ../README.md
