# 头脑王者

本项目仅作为学习`anyproxy`之用，请问用于非法用途，否则后果自负

## 功能

+ [x] 题目爬取
+ [x] 答题匹配 && 自动入库

## 开始

1. 安装mysql，新建数据库`tnwz`，建表语句
    ```sql
    CREATE TABLE tnwz.question
    (
        id int(11) PRIMARY KEY NOT NULL AUTO_INCREMENT,
        question varchar(100),
        a varchar(20),
        b varchar(20),
        c varchar(20),
        d varchar(20),
        answer int(11),
        createdAt datetime NOT NULL,
        updatedAt datetime NOT NULL
    );
    ```
2. config.json为数据库配置 
3. 安装`anyproxy` => `npm install anyproxy -g`
4. 生成证书`anyproxy -i`
5. 手机接入代理，代理地址`电脑IP:8001`

## 题库获取

1. 登录两个微信号获取到uid和token之后填入auth.json
2. `node question-fetcher.js`,如果出现401，请重新登录

## 排位系统

1. `npm run fight`开启代理
2. 手机接入代理
3. 开始排位，终端会提示`开始匹配`，系统会将正确答案添加上`###`

## 适用系统

+ Android && iOS
+ iOS11.3 已通过测试