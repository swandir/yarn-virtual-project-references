https://github.com/yarnpkg/berry/issues/3829

```sh
yarn
yarn tsc -b workspaces/a

# .yarn/__virtual__/b-virtual-0b8cdd16e3/1/workspaces/b/index.ts:5:19 - error TS7019: Rest parameter 'args' implicitly has an 'any[]' type.
#
# 5 export const b = (...args) => args;
#                     ~~~~~~~
#
#
# Found 1 error.

yarn tsc -b workspaces/a --clean
yarn config set nodeLinker node-modules
yarn
yarn tsc -b workspaces/a

# No errors!
```
