# vue project init doc
----
## project init

### 1. install nodejs
> * [nodejs install website](http://nodejs.cn)

### 2. install cnpm
> * npm install -g cnpm --registry=https://registry.npm.taobao.org   *ps.cnpm contains a large quantities of package by using npm mirroring, which makes downloading quickly*

### 3. git install
> * [git install website](https://git-scm.cn)    *ps.it is recommanded that install gitbash as a substitute of windows cmd* 

### 4. vue-cli install global
> * cnpm install -g vue-cli

### 5. vue project init
``` c++
vue init webpack my-project //create a 'my-project' based on 'webpack' template
cd my-project
cnpm install 
cnpm run dev // debugging locallly
cnpm run build // package release
```
## some problems

### 1. some packages not install correctly
> * cnpm install --save packagename

### 2. ShasumNotMatchError solution
> * cnpm install --save --no-cache packagename
