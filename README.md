# yarn-nm-pnp

- run `yarn install && cd nm-packages/angular && yarn install && cd ../..`
- `yarn start:nm` or `yarn start:nm2` from the root doesn't work:

```
[error] Error: the specified module doesn't seem to be part of the dependency tree
    at getModuleLocator (/home/aandrei/projects/repros/yarn-nm-pnp/nm-packages/angular/node_modules/pnp-webpack-plugin/index.js:21:11)
    at Object.module.exports.moduleLoader (/home/aandrei/projects/repros/yarn-nm-pnp/nm-packages/angular/node_modules/pnp-webpack-plugin/index.js:140:23)
    at Object.getCommonConfig (/home/aandrei/projects/repros/yarn-nm-pnp/nm-packages/angular/node_modules/@angular-devkit/build-angular/src/angular-cli-files/models/webpack-configs/common.js:390:40)
    at webpackPartialGenerator (/home/aandrei/projects/repros/yarn-nm-pnp/nm-packages/angular/node_modules/@angular-devkit/build-angular/src/browser/index.js:59:27)
    at generateWebpackConfig (/home/aandrei/projects/repros/yarn-nm-pnp/nm-packages/angular/node_modules/@angular-devkit/build-angular/src/utils/webpack-browser-config.js:63:22)
    at async generateBrowserWebpackConfigFromContext (/home/aandrei/projects/repros/yarn-nm-pnp/nm-packages/angular/node_modules/@angular-devkit/build-angular/src/utils/webpack-browser-config.js:154:20)
    at async Object.generateI18nBrowserWebpackConfigFromContext (/home/aandrei/projects/repros/yarn-nm-pnp/nm-packages/angular/node_modules/@angular-devkit/build-angular/src/utils/webpack-browser-config.js:95:20)
    at async setup (/home/aandrei/projects/repros/yarn-nm-pnp/nm-packages/angular/node_modules/@angular-devkit/build-angular/src/dev-server/index.js:78:47)
```

- manually running `cd nm-packages/angular && yarn start` in the terminal does work
