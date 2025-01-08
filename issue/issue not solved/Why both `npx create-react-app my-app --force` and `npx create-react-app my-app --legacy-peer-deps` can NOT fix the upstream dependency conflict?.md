# issue
Why both `npx create-react-app my-app --force` and `npx create-react-app my-app --legacy-peer-deps` can NOT fix the upstream dependency conflict?

## details  
I'm a newbie to ReatJS and npx. I want to create a ReactJS project with npx command , steps are followed by [`Getting Started` (ReactJS official docs)](https://create-react-app.dev/docs/getting-started/).

But I got npm error

```
npm error Fix the upstream dependency conflict, or retry
npm error this command with --force or --legacy-peer-deps
npm error to accept an incorrect (and potentially broken) dependency resolution.
```

which points there is an upstream dependency conflict.

Then, I try these commands `npx create-react-app my-app --force` and `npx create-react-app my-app --legacy-peer-deps` according to the command-line prompt says (as above).

However, I still got similar error

```
npm error Fix the upstream dependency conflict, or retry
npm error this command with --force or --legacy-peer-deps
npm error to accept an incorrect (and potentially broken) dependency resolution.
```

I don't know how to solve it?

## Demo
### `npx create-react-app my-app --force`
[Demo of `npx create-react-app my-app --force`](https://i.sstatic.net/bZaVGdDU.png)

#### log file
In `C:\Users\Jay\AppData\Local\npm-cache\_logs\2025-01-08T15_01_44_621Z-debug-0.log` file

```
0 verbose cli C:\Program Files\nodejs\node.exe C:\Program Files\nodejs\node_modules\npm\bin\npm-cli.js
1 info using npm@10.9.0
2 info using node@v22.11.0
3 silly config load:file:C:\Program Files\nodejs\node_modules\npm\npmrc
4 silly config load:file:C:\Users\Jay\Desktop\CSS\example\ex13 -- media\demos\color-scheme-toggle-demo-4\my-app\.npmrc
5 silly config load:file:C:\Users\Jay\.npmrc
6 silly config load:file:C:\Users\Jay\AppData\Roaming\npm\etc\npmrc
7 verbose title npm install @testing-library/jest-dom@^5.14.1 @testing-library/react@^13.0.0 @testing-library/user-event@^13.2.1 web-vitals@^2.1.0
8 verbose argv "install" "--no-audit" "--save" "@testing-library/jest-dom@^5.14.1" "@testing-library/react@^13.0.0" "@testing-library/user-event@^13.2.1" "web-vitals@^2.1.0"
9 verbose logfile logs-max:10 dir:C:\Users\Jay\AppData\Local\npm-cache\_logs\2025-01-08T15_01_44_621Z-
10 verbose logfile C:\Users\Jay\AppData\Local\npm-cache\_logs\2025-01-08T15_01_44_621Z-debug-0.log
11 silly logfile start cleaning logs, removing 1 files
12 silly packumentCache heap:4345298944 maxSize:1086324736 maxEntrySize:543162368
13 silly logfile done cleaning log files
14 silly idealTree buildDeps
15 silly fetch manifest @testing-library/jest-dom@^5.14.1
16 silly packumentCache full:https://registry.npmjs.org/@testing-library%2fjest-dom cache-miss
17 http fetch GET 200 https://registry.npmjs.org/@testing-library%2fjest-dom 691ms (cache updated)
18 silly packumentCache full:https://registry.npmjs.org/@testing-library%2fjest-dom set size:undefined disposed:false
19 silly fetch manifest @testing-library/react@^13.0.0
20 silly packumentCache full:https://registry.npmjs.org/@testing-library%2freact cache-miss
21 http fetch GET 200 https://registry.npmjs.org/@testing-library%2freact 208ms (cache updated)
22 silly packumentCache full:https://registry.npmjs.org/@testing-library%2freact set size:undefined disposed:false
23 silly fetch manifest react@^19.0.0
24 silly packumentCache full:https://registry.npmjs.org/react cache-miss
25 http fetch GET 200 https://registry.npmjs.org/react 10ms (cache hit)
26 silly packumentCache full:https://registry.npmjs.org/react set size:5317255 disposed:false
27 silly fetch manifest react@^18.0.0
28 silly packumentCache full:https://registry.npmjs.org/react cache-miss
29 http fetch GET 200 https://registry.npmjs.org/react 8ms (cache hit)
30 silly packumentCache full:https://registry.npmjs.org/react set size:5317255 disposed:false
31 verbose stack Error: unable to resolve dependency tree
31 verbose stack     at #failPeerConflict (C:\Program Files\nodejs\node_modules\npm\node_modules\@npmcli\arborist\lib\arborist\build-ideal-tree.js:1363:25)
31 verbose stack     at #loadPeerSet (C:\Program Files\nodejs\node_modules\npm\node_modules\@npmcli\arborist\lib\arborist\build-ideal-tree.js:1329:33)
31 verbose stack     at async #buildDepStep (C:\Program Files\nodejs\node_modules\npm\node_modules\@npmcli\arborist\lib\arborist\build-ideal-tree.js:904:11)
31 verbose stack     at async Arborist.buildIdealTree (C:\Program Files\nodejs\node_modules\npm\node_modules\@npmcli\arborist\lib\arborist\build-ideal-tree.js:181:7)
31 verbose stack     at async Promise.all (index 1)
31 verbose stack     at async Arborist.reify (C:\Program Files\nodejs\node_modules\npm\node_modules\@npmcli\arborist\lib\arborist\reify.js:131:5)
31 verbose stack     at async Install.exec (C:\Program Files\nodejs\node_modules\npm\lib\commands\install.js:150:5)
31 verbose stack     at async Npm.exec (C:\Program Files\nodejs\node_modules\npm\lib\npm.js:207:9)
31 verbose stack     at async module.exports (C:\Program Files\nodejs\node_modules\npm\lib\cli\entry.js:74:5)
32 error code ERESOLVE
33 error ERESOLVE unable to resolve dependency tree
34 error
35 error While resolving: my-app@0.1.0
35 error Found: react@19.0.0[2m[22m
35 error [2mnode_modules/react[22m
35 error   react@"^19.0.0" from the root project
35 error
35 error Could not resolve dependency:
35 error [95mpeer[39m react@"^18.0.0" from @testing-library/react@13.4.0[2m[22m
35 error [2mnode_modules/@testing-library/react[22m
35 error   @testing-library/react@"^13.0.0" from the root project
35 error
35 error Fix the upstream dependency conflict, or retry
35 error this command with --force or --legacy-peer-deps
35 error to accept an incorrect (and potentially broken) dependency resolution.
36 error
36 error
36 error For a full report see:
36 error C:\Users\Jay\AppData\Local\npm-cache\_logs\2025-01-08T15_01_44_621Z-eresolve-report.txt
37 silly unfinished npm timer reify 1736348504951
38 silly unfinished npm timer reify:loadTrees 1736348504952
39 silly unfinished npm timer idealTree:buildDeps 1736348505223
40 silly unfinished npm timer idealTree:#root 1736348505223
41 verbose cwd C:\Users\Jay\Desktop\CSS\example\ex13 -- media\demos\color-scheme-toggle-demo-4\my-app
42 verbose os Windows_NT 10.0.26100
43 verbose node v22.11.0
44 verbose npm  v10.9.0
45 verbose exit 1
46 verbose code 1
47 error A complete log of this run can be found in: C:\Users\Jay\AppData\Local\npm-cache\_logs\2025-01-08T15_01_44_621Z-debug-0.log
```

### `npx create-react-app my-app  --legacy-peer-deps`
[Demo `npx create-react-app my-app  --legacy-peer-deps`](https://i.sstatic.net/XWhTDiwc.png)

#### log file
In `C:\Users\Jay\AppData\Local\npm-cache\_logs\2025-01-08T15_08_26_234Z-debug-0.log` file

```
0 verbose cli C:\Program Files\nodejs\node.exe C:\Program Files\nodejs\node_modules\npm\bin\npm-cli.js
1 info using npm@10.9.0
2 info using node@v22.11.0
3 silly config load:file:C:\Program Files\nodejs\node_modules\npm\npmrc
4 silly config load:file:C:\Users\Jay\Desktop\CSS\example\ex13 -- media\demos\color-scheme-toggle-demo-4\my-app\.npmrc
5 silly config load:file:C:\Users\Jay\.npmrc
6 silly config load:file:C:\Users\Jay\AppData\Roaming\npm\etc\npmrc
7 verbose title npm install @testing-library/jest-dom@^5.14.1 @testing-library/react@^13.0.0 @testing-library/user-event@^13.2.1 web-vitals@^2.1.0
8 verbose argv "install" "--no-audit" "--save" "@testing-library/jest-dom@^5.14.1" "@testing-library/react@^13.0.0" "@testing-library/user-event@^13.2.1" "web-vitals@^2.1.0"
9 verbose logfile logs-max:10 dir:C:\Users\Jay\AppData\Local\npm-cache\_logs\2025-01-08T15_08_26_234Z-
10 verbose logfile C:\Users\Jay\AppData\Local\npm-cache\_logs\2025-01-08T15_08_26_234Z-debug-0.log
11 silly logfile start cleaning logs, removing 1 files
12 silly packumentCache heap:4345298944 maxSize:1086324736 maxEntrySize:543162368
13 silly logfile done cleaning log files
14 silly idealTree buildDeps
15 silly fetch manifest @testing-library/jest-dom@^5.14.1
16 silly packumentCache full:https://registry.npmjs.org/@testing-library%2fjest-dom cache-miss
17 http fetch GET 200 https://registry.npmjs.org/@testing-library%2fjest-dom 1297ms (cache updated)
18 silly packumentCache full:https://registry.npmjs.org/@testing-library%2fjest-dom set size:undefined disposed:false
19 silly fetch manifest @testing-library/react@^13.0.0
20 silly packumentCache full:https://registry.npmjs.org/@testing-library%2freact cache-miss
21 http fetch GET 200 https://registry.npmjs.org/@testing-library%2freact 188ms (cache updated)
22 silly packumentCache full:https://registry.npmjs.org/@testing-library%2freact set size:undefined disposed:false
23 silly fetch manifest react@^19.0.0
24 silly packumentCache full:https://registry.npmjs.org/react cache-miss
25 http fetch GET 200 https://registry.npmjs.org/react 18ms (cache hit)
26 silly packumentCache full:https://registry.npmjs.org/react set size:5317255 disposed:false
27 silly fetch manifest react@^18.0.0
28 silly packumentCache full:https://registry.npmjs.org/react cache-miss
29 http fetch GET 200 https://registry.npmjs.org/react 9ms (cache hit)
30 silly packumentCache full:https://registry.npmjs.org/react set size:5317255 disposed:false
31 verbose stack Error: unable to resolve dependency tree
31 verbose stack     at #failPeerConflict (C:\Program Files\nodejs\node_modules\npm\node_modules\@npmcli\arborist\lib\arborist\build-ideal-tree.js:1363:25)
31 verbose stack     at #loadPeerSet (C:\Program Files\nodejs\node_modules\npm\node_modules\@npmcli\arborist\lib\arborist\build-ideal-tree.js:1329:33)
31 verbose stack     at async #buildDepStep (C:\Program Files\nodejs\node_modules\npm\node_modules\@npmcli\arborist\lib\arborist\build-ideal-tree.js:904:11)
31 verbose stack     at async Arborist.buildIdealTree (C:\Program Files\nodejs\node_modules\npm\node_modules\@npmcli\arborist\lib\arborist\build-ideal-tree.js:181:7)
31 verbose stack     at async Promise.all (index 1)
31 verbose stack     at async Arborist.reify (C:\Program Files\nodejs\node_modules\npm\node_modules\@npmcli\arborist\lib\arborist\reify.js:131:5)
31 verbose stack     at async Install.exec (C:\Program Files\nodejs\node_modules\npm\lib\commands\install.js:150:5)
31 verbose stack     at async Npm.exec (C:\Program Files\nodejs\node_modules\npm\lib\npm.js:207:9)
31 verbose stack     at async module.exports (C:\Program Files\nodejs\node_modules\npm\lib\cli\entry.js:74:5)
32 error code ERESOLVE
33 error ERESOLVE unable to resolve dependency tree
34 error
35 error While resolving: my-app@0.1.0
35 error Found: react@19.0.0[2m[22m
35 error [2mnode_modules/react[22m
35 error   react@"^19.0.0" from the root project
35 error
35 error Could not resolve dependency:
35 error [95mpeer[39m react@"^18.0.0" from @testing-library/react@13.4.0[2m[22m
35 error [2mnode_modules/@testing-library/react[22m
35 error   @testing-library/react@"^13.0.0" from the root project
35 error
35 error Fix the upstream dependency conflict, or retry
35 error this command with --force or --legacy-peer-deps
35 error to accept an incorrect (and potentially broken) dependency resolution.
36 error
36 error
36 error For a full report see:
36 error C:\Users\Jay\AppData\Local\npm-cache\_logs\2025-01-08T15_08_26_234Z-eresolve-report.txt
37 silly unfinished npm timer reify 1736348906582
38 silly unfinished npm timer reify:loadTrees 1736348906583
39 silly unfinished npm timer idealTree:buildDeps 1736348906858
40 silly unfinished npm timer idealTree:#root 1736348906859
41 verbose cwd C:\Users\Jay\Desktop\CSS\example\ex13 -- media\demos\color-scheme-toggle-demo-4\my-app
42 verbose os Windows_NT 10.0.26100
43 verbose node v22.11.0
44 verbose npm  v10.9.0
45 verbose exit 1
46 verbose code 1
47 error A complete log of this run can be found in: C:\Users\Jay\AppData\Local\npm-cache\_logs\2025-01-08T15_08_26_234Z-debug-0.log
```

### version
#### npm
`npm --version` => `10.9.0`
#### NodeJS
`node --version` => `v22.11.0`

#### npx
`npx --version` => `10.9.0`

[`--version in command-line prompt`](https://i.sstatic.net/bZyHJuuU.png)

## appreciation 
Any replies or tips will be highly appreciated.


## What did I try?

1. As state above.

```
Then, I try these commands `npx create-react-app my-app --force` and `npx create-react-app my-app --legacy-peer-deps` according to the command-line prompt says (as above).
```

2. I have read articles on stackoverflow.

+ [`Fix the upstream dependency conflict installing NPM packages`](https://stackoverflow.com/questions/64936044/fix-the-upstream-dependency-conflict-installing-npm-packages)

## What was I expecting?
I want to solve this issue to create a ReactJS project.
