# Protractor (Ubuntu 14.04)
本教學將說明如和安裝 Protractor。

## Node.js 安裝
首先，先安裝 `Node.js`，而 `Node.js` 安裝部分有以下兩種方式進行安裝。

### 1. Package 安裝
使用 `wget` 取得 Node.js 官方 v4.2.4 LTS 安裝套件。

```sh
$ wget https://nodejs.org/dist/v4.2.4/node-v4.2.4.tar.gz
```

將下載的套件透過 `tar xvf` 指令進行解壓縮。

```sh
$ tar xvf node-v4.2.4.tar.gz
```

解壓縮後，進入 node-v4.2.4 資料夾中透過 `make` & `make install` 指令進行編譯與安裝。

```
$ make & make install
```
> 1. 問題：`Makefile:56: *** stale config.gypi ... stop.` 訊息，請先執行 `./configure` 指令。
> 2. 問題：`g++ command not found` 訊息，請使用 `sudo apt-get install g++` 命令安裝套件。

使用 `node  --version` 指令驗證是否安裝成功與查看版本。

```
$ node --version
v4.2.4 //成功可以看到版本
```

### 2. apt 安裝
Node.js 版本 >= 4.x

```sh
$ curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -
$ sudo apt-get install -y nodejs
```

Node.js 版本 >= 5.x

```sh
$ curl -sL https://deb.nodesource.com/setup_5.x | sudo -E bash -
$ sudo apt-get install -y nodejs
```

### 3. 其他作業系統安裝方式
若作業系統不為 `Ubuntu` ，請參考以下網址：[Node.js 官方網站](https://nodejs.org/en/download/)

## jdk 安裝
使用 `apt-get install default-jdk` 指令安裝 jdk 套件。

```sh
$ apt-get install default-jdk
```

透過 `java -version` 指令驗證是否安裝成功與查看版本。

```sh
$ java -version
java version "1.7.0_91" //成功可以看到版本
```

## Protractor 安裝
使用 `npm install -g protractor` 指令安裝 Protractor 套件。

```sh
$ npm install -g protractor
```

安裝完後，分別執行 `webdriver-manager update` 、 `webdriver-manager start` 進行更新與啟動。

```sh
$ webdriver-manager update
$ webdriver-manager start
```

> 可以進入 SeleniumHQ [官方網站](http://www.seleniumhq.org/download/)下載不同瀏覽器的 browser driver。

### 執行 Protractor

透過 protractor conf.js 指令執行 e2e 測試。

```sh
$ protractor conf.js
```

> 此處 conf.js 依照使用者配置檔命名有所不同。

## 參考

[Protractor 官方安裝教學與測試範例](https://angular.github.io/protractor/#/)
