自动生成自签名HTTPS服务器，快速安装ipa、apk，基于[ios-ipa-server](https://github.com/bumaociyuan/ios-ipa-server)开发

# 支持
* OS X
* Ubuntu
* 其他平台未测试

# 需要
* [nodejs](https://nodejs.org/)

# 安装
```
$ npm install -g ipapk-server
```

# 用法
```
Usage: ipapk-server [option] [dir]

Options:

-h, --help                output usage information
-V, --version             output the version number
-p, --port <port-number>  set port for server (defaults is 1234)
```
## 准备
- 创建如下结构目录

```
___path-of-ipa-and-apk
|____ipa
|____apk
```
- ipa文件放于ipa文件夹内
- apk文件放于apk文件夹内

## 开启服务
```
$ cd path-of-ipa-and-apk
$ ipapk-server

# or

$ ipapk-server path-of-ipa-and-apk

# open https://ip:port/download on your iphone
# 推荐使用pm2等进程管理运行服务
```
## 包上传
* 可直接放入上述文件夹内
* 通过api上传 `curl 'https://ip:port/upload' -F "package=@文件路径" --insecure`，不能去掉`@`。

### 安装app
* 手机使用浏览器(iOS必须使用Safari)打开`https://ip:port/download`页面
* 第一次打开会弹出警告`无法验证服务器`，请点击`详细信息`按钮安装证书，按指示一直点击下一步和完成(**强烈推荐使用静态IP，避免每次重新安装证书**)
* 点击`下载`在线安装`ipa`

![simulator screen shot jun 22 2016 2 45 19 pm 2](https://cloud.githubusercontent.com/assets/4977911/16257320/66c5ff7e-388a-11e6-827a-b5708b86e272.png)
# 效果图
![screeshot](screeshot.png)

# TODO
- 显示icon
- 解析包信息
