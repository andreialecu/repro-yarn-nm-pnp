# yarn-nm-pnp

- run `yarn install && cd nm-packages/app && yarn install && cd ../..`
- `yarn start:nm` or `yarn start:nm2` from the root doesn't work:

```
index.ts:1:17 - error TS2307: Cannot find module 'lodash/add' or its corresponding type declarations.

1 import add from "lodash/add";
                  ~~~~~~~~~~~~


Found 1 error.
```

- manually running `cd nm-packages/app && yarn start` in the terminal does work
