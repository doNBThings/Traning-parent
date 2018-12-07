# Training 培训系统

## 系统概述
培训系统，界面类似[慕课网](https://www.imooc.com/)，功能包含需求，课程，用户中心，社区等。
## 作者
甘培康 费青松 季海峰 富裕华 夏久聪 唐靖 郭俊

## 主要业务逻辑
1. 用户登录系统后，可提交需求申请。
2. 管理员可查看提的需求，驳回或拆分或合并需求生成出课程，指定讲师或讲师招募。
3. 讲师收到课程通知可指定时间、上课形式、上传材料。
4. 用户可查看课程，关注课程，对课程打分，评论。
5. 用户可在社区发帖，或回复帖子。

## 功能点拆分（待补充）

### 用户
- 个人设置
- 经验
- 我的课程

### 需求
- 我要提需求
- 需求列表

### 课程
- 课程列表

### 共享中心

### 通知

### 私信

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
| training-req | 需求服务 | 9002 | 需求服务 | 富钰华 |
| training-course | 课程服务 | 9003 | 课程服务 | 夏久聪 |
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


