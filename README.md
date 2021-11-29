# yarn-nm-pnp

- run `yarn install && cd nm-packages/angular && yarn install && cd ../..`
- open `nm-packages/angular/src/app/app.component.ts` in vscode and notice that `TestService` cannot be auto imported. `ChangeDetectorRef` can be auto imported however.

Logged in tsserver.log:

```
Err 604728[13:39:57.089] Exception on executing command {"seq":357,"type":"request","command":"getCodeFixes","arguments":{"file":"/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/nm-packages/angular/src/app/app.component.ts","startLine":11,"startOffset":36,"endLine":11,"endOffset":47,"errorCodes":[2304]}}:

    Cannot read property 'findPackageLocator' of null

    TypeError: Cannot read property 'findPackageLocator' of null
        at tryGetModuleNameAsNodeModule (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:117203:38)
        at computeModuleSpecifiers (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:116872:33)
        at Object.getModuleSpecifiersWithCacheInfo (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:116840:26)
        at getModuleSpecifiers (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:145686:72)
        at /Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:145689:26
        at Object.flatMap (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:519:25)
        at getNewImportFixes (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:145688:28)
        at getFixesForAddImport (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:145709:66)
        at getImportFixes (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:145557:63)
        at /Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:145832:24
        at getIterator (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:573:23)
        at Object.flatMapIterator (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:556:27)
        at getFixesInfoForNonUMDImport (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:145830:41)
        at getFixesInfo (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:145722:50)
        at Object.getCodeActions (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:145333:28)
        at /Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:142936:77
        at Object.flatMap (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:519:25)
        at Object.getFixes (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:142936:23)
        at /Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:157319:35
        at Object.flatMap (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:519:25)
        at Object.getCodeFixesAtPosition (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:157317:23)
        at IOSession.Session.getCodeFixes (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:168835:64)
        at Session.handlers.ts.Map.ts.getEntries._a.<computed> (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:167473:61)
        at /Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:169148:88
        at IOSession.Session.executeWithRequestId (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:169139:28)
        at IOSession.Session.executeCommand (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:169148:33)
        at IOSession.Session.onMessage (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:169174:35)
        at IOSession.onMessage (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/sdks/typescript/lib/tsserver.js:161:32)
        at Interface.<anonymous> (/Users/andreialecu/Work/contrib/repro-yarn-nm-pnp/.yarn/cache/typescript-patch-d95d140154-bd629ad0da.zip/node_modules/typescript/lib/tsserver.js:171787:31)
        at Interface.emit (events.js:315:20)
        at Interface._onLine (readline.js:337:10)
        at Interface._normalWrite (readline.js:482:12)
        at Socket.ondata (readline.js:194:10)
        at Socket.emit (events.js:315:20)
        at addChunk (internal/streams/readable.js:309:12)
        at readableAddChunk (internal/streams/readable.js:284:9)
        at Socket.Readable.push (internal/streams/readable.js:223:10)
        at Pipe.onStreamRead (internal/stream_base_commons.js:188:23)
```