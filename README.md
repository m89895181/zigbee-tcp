﻿# zigbee-tcp

## 启动

```javascript
npm start   //本地环境,其他环境查看package.json或者config/config.js
```

## 服务

- 端口: `4003`(localhost)

## 配置

| 名称      |     描述 |
| :-------- | :--------|
| redis(本地环境)    |   `redis://localhost:6379` |
| mongodb(本地环境)  |   `mongodb://localhost/zigbee` |

## 日志

| 名称      |     描述 |
| :-------- | :--------|
| 进程    |   主进程和子进程启动停止日志 |
| 服务    |   tcp服务启动和停止日志 |
| 错误    |   错误日志 |

>提示: 日志在`log/txt`文件夹下以记事本的形式存储.


## 目录

```javascript
.
├── config                      # 配置
│   ├── config.js               # 参数配置
│   └── index.config.js         # 导出配置
├── server                      # 服务
│   ├── constants               # 常量
│   ├── controllers             # 逻辑
│   ├── logs                    # 日志
│   ├── models                  # 数据
│   ├── pubs                    # 发布
│   ├── subs                    # 订阅
│   └── server.js               # tcp服务脚本
└── app.js                      # 启动脚本
```

## 问题

| 类型      |    说明  |
| :-------- | :--------|
| redis发布和订阅|   redis发布和订阅必须开启两个客户端，同一个客户端不能同时发布和订阅 |
| redis数据发送   |   发送时需要JSON.stringif()封装，接收使用JSON.parse()解封对象 |
| 多进程和程序异常捕获   |  最终版本开启，目前开启虽然会产生异常日志，但是日志的说明不是很清楚，还是让程序异常中断查看error，不然不利于编程 |


## 进度记录

| 日期      |     进度 |
| :-------- | :--------|
| 2016/11/06    |   模拟socket连接和断开成功,redis缓存socket列表,redis发布成功 |
| 2016/11/07    |   增加基站数据字段 |
| 2016/12/07    |   windows环境下重新配置和测试 |
| 2016/12/27    |   redis订阅成功，通过TCP发送数据给基站成功 |

