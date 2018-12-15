# Training 培训系统

## 系统概述
培训系统，界面类似[慕课网](https://www.imooc.com/)，功能包含需求，课程，用户中心，社区等。

## 作者
甘培康 费青松 季海峰 富裕华 夏久聪 唐靖 郭俊 戴豪 张敏

## 项目配置
- 通过git下载项目(平时开发模块时只需要training-parent(父项目),training-core（工具类项目）,training-register（注册中心项目）,training-对应模块（业务开发项目），traning-web（前端页面项目）)
- 在elipse中打开各项目,配置为 maven项目,elipse会自动下载maven依赖。
- 按顺序运行项目中的启动类，先运行training-register中的TrainingRegisterApplication.java，再执行training-模块 中的 模块Application.java(如training-test1中的Test1Application.java),启动前端项目(前端项目启动方法详见前端工程中的readme.md)。

## 主要业务逻辑
1. 用户登录系统后，可提交需求申请。
2. 管理员可查看提的需求，驳回或拆分或合并需求生成出课程，指定讲师或讲师招募。
3. 讲师收到课程通知可指定时间、上课形式、上传材料。
4. 用户可查看课程，关注课程，对课程打分，评论。
5. 用户可在社区发帖，或回复帖子。

## 功能点拆分（待补充）

### 用户
- 注册
- 登录
- 账户绑定
- 个人信息
- 操作记录
- 我的收藏
- 我的需求
- 我的课程
- 私信 
- 通知

### 需求(待补充)
- 我要提需求
- 需求列表
- 需求合并拆分
- 从需求创建课程，指定讲师

### 课程
- 课程列表（最热，最新）
- 课程详情
- 课程评分
- 课程搜索
- 新增课程

### 社区(待补充)
- 手记
- 猿问

### 搜索

## 技术选型

### 后端
springboot springcloud mybatis redis mq es druid swaggerui activemq

### 前端
vue vue-cli elementui nodejs es6 webpack

### 数据库
mysql

## 系统模块介绍

| 模块名称 | 说明 | 端口 | 备注 | 负责人 |
| :---: | :---: | :---: | :---: | :---: |
| training-parent | 父项目 | 无 | 打包所有项目，控制jar包版本 |  |
| training-core | 项目基础 | 无 | 封装框架所需的基础配置，工具类和运行机制等 |  |
| training-register | 注册中心 | 8999 | eureka注册中心 |  |
| training-gateway | 网关 | 8000 | 转发，资源权限校验，请求号生成等 |  |
| training-config | 配置中心服务器 | 8001 | 配置集中管理 |  |
| training-logger | 日志服务 | 8002 | 消费并存储日志 |  |
| training-monitor | 监控中心 | 8003 | 监控服务运行状况 |  |
| training-user | 用户服务 | 9001 | 提供用户，资源，权限等接口 | 唐靖 |
| training-req | 需求服务 | 9002 | 需求服务 | 富钰华，戴豪 |
| training-course | 课程服务 | 9003 | 课程服务 | 夏久聪，张敏 |
| training-community | 社区服务 | 9004 | 共享服务 | 郭俊 |
| training-search | 搜索服务 | 9005 | 搜索服务 | 费青松 |
| training-web | 前端 | 80 | 网页端 | 季海峰 |
| training-webcrawler | 爬虫服务 | 9010 | 爬取网上资源 |  |

## 项目规范
- groupid：com.dothings.training
- artifactId：各模块名称（如：training-parent)
- 包名： com.dothings.training
- 包结构 config:配置信息，dao：实体类，service：服务层，service.impl：实现类，entity：实体类
- 提交代码时：啥需求 修改点 修改人
- 类上方法上加注释：说明 作者 时间

## 版本信息
- jdk:1.8
- 编码集:utf-8
- springboot:2.0.1.RELEASE
- springcloud:Finchley.RELEASE
- druid:1.1.6
- swagger:2.7.0


