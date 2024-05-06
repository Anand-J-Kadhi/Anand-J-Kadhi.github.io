---
title:  Node deasync installation issue with windows
date: 2021-12-28 11:50:00 +0800
categories: [Technical, Node]
tags: [node]
---
Error I was facing while learning node modules insallation

I was always getting error for deasync with no specific reason like 

> info run deasync@0.1.29 install node_modules/deasync node ./build.js
> info run deasync@0.1.29 install { code: 1, signal: null }
> timing reify:rollback:createSparse Completed in 175ms
> timing reify:rollback:retireShallow Completed in 0ms
> timing command:i Completed in 5105ms
> verbose stack Error: command failed
> verbose stack     at ChildProcess.<anonymous> (directory\node_modules\npm\node_modules\@npmcli\promise-spawn\index.js:64:27)
> verbose stack     at ChildProcess.emit (node:events:527:28)
> verbose stack     at maybeClose (node:internal/child_process:1092:16)
> verbose stack     at Process.ChildProcess._handle.onexit (node:internal/child_process:302:5)
> verbose pkgid deasync@0.1.29
> verbose cwd \directory\
> verbose Windows_NT 10.0.19045
> verbose argv "directory\\NodeJs\\node.exe" "directory\\NodeJs\\node_modules\\npm\\bin\\npm-cli.js" "i" "deasync"
> verbose node v16.15.0
> verbose npm  v8.5.5
> error code 1
> error path \directory\node_modules\deasync
> error command failed
> error command bash -c node ./build.js
> verbose exit 1


I was frustrated and tried muliple node versions , I thought its some issue with the nodee versions as online seaerchong doesnt brough 
much answers when I searched the logs it showed one line of bash I wondereed where this bash is coming from as windows uses cmd not bash . 
I searched .nprmc and found this line

```
script-shell=bash
python=python3.10.7
```

Hola removing this I was able to install deasync

A:\Installations\Programming\workspace\practice>npm i deasync@0.1.29

added 4 packages, and audited 5 packages in 2s

found 0 vulnerabilities

