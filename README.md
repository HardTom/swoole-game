# swoole-h5game

* 基于Swoole扩展开发游戏服务器框架

## 一，概述

* 该框架主要用于开发h5游戏服务器，简化游戏前后端开发，框架主要实现了前后端，封包解包，协议解析，压缩，粘包，路由等功能。
 
## 二，示例图

![游戏demo1](images/demo1.jpg)
![游戏demo2](images/demo2.jpg)
![游戏demo3](images/demo3.png)
![游戏demo4](images/demo4.jpg)
![客户端交互测试工具](images/demo5.png)

 

## 三，特性

* 对websocket协议进行封装，异步处理任务
* 实现前后端二进制封包解包，采用的是msgpack扩展，msgpack对数据进行了压缩，并实现粘包处理
* 数据采用固定包头，包头4个字节存包体长度，包体前2个字节分别为cmd(主命令字)，scmd(子命令字)，后面为包体内容
* 采用策略模式解耦游戏中的每个协议逻辑
* 实现定义游戏开发cmd(主命令字)和scmd(子命令字)定义，cmd和scmd主要用来路由到游戏协议逻辑处理
* 代码里有个JokerPoker类是一个款小游戏算法类，是一个示例，如示例图1,2,3,4
* 代码主要是用框架实现小游戏JokerPoker例子，服务端代码开源，客户端代码暂不开源，但是提供客户端交互测试工具，见示例图5。
* 可以方便的把JokerPoker范例去除，只使用框架功能定制开发开发自己的游戏功能


备注：注意此范例数字都是默认值， 为存储， 运行不需要数据库，数据库配置只是测试用
        
   
## 四，环境依赖
    
* php 5.6 最好以上
* php扩展：
* swoole 1.8以上版本
* msgpack
    
    
## 五，开始使用

* 1，目录说明：

```
./bin 服务启动目录
./client 客户端交互测试工具
./core 框架服务器核心代码
./lib 游戏协议逻辑处理代码
./log  日志目录

``` 
         

* 2，进入bin目录，启动服务器 ：

```
./poker  start   启动服务 
./poker  stop    关闭服务 
./poker  reload   服务重载， 优雅载入， 不需要启动服务， 可以载入所修改的逻辑

``` 
   

* 3 ，H5游戏客户端代码由于公司限制，暂不开启， 但是提供了一个客户端交互测试工具，直接把client目录放入web服务器， 修改配置websocket链接就能运行。


## 六，联系方式

* qq：251413215