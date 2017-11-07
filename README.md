## 1 秒杀系统系统环境搭建

### 1.1 秒杀系统特点

- 人多商品少
- 时间短流量高
- 外挂机器

### 1.2 技术要点

- 瞬时高并发的处理能力
- 多层次的分布式处理能力
- 人机交互与对抗（验证码）

### 1.3 技术选型分析

- Linux + Nginx + PHP + MySQL + redis
- 开源，免费
- 大众普及
- CDN，智能DNS
- 分布式缓存，全国多节点
- 多线路接入
- 负载均衡LVS
- 大型Web集群
- 高效稳定

### 1.4 开发环境

- 开发工具：Eclipse for PHP Developers / PhpStorm / EditPlus
- 部署开发环境：XAMPP / macos brew安装工具 / Linux yum
- 代码管理员：Git / SVN

### 1.5 MySQL 封装类

- 更安全的PDO组件
- 封装常用的增删改查
- 详见class目录

### 1.6 Redis 封装类

- PHP客户端：phpredis / Predis
- 封装基本的redis资源连接和命令
- 详见class文件目录
- [Redis介绍](https://redis.io/documentation)
- [Redis手册](https://redis.io/commands)

### 1.7 调式封装类

- 封装资源类调用：mysql，redis，curl等
- 定制日志，调式日志等
- 详见项目代码

## 2 系统设计

### 2.1 基本功能和流程

- 后台：活动管理/商品管理/订单管理/日志管理
- 前台：商品展示/秒杀/购物车/我的订单
- 安全：验证码/问答

### 2.2 基本功能和流程

![秒杀](seckill.png)

### 2.3 数据库设计

- 活动信息表

```
CREATE TABLE `ms_active`(
`id` int(10) unsigned NOT NULL AUTO_INCREMENT COMMENT '活动ID',
`title` varchar(255) NOT NULL COMMENT '活动名称',
`time_begin` int(10) unsigned NOT NULL DEFAULT '0' COMMENT '开始时间',
`time_end` int(10) unsigned NOT NULL DEFAULT '0' COMMENT '结束时间',
`sys_dateline` int(10) unsigned NOT NULL DEFAULT '0' COMMENT '创建时间',
`sys_lastmodify` int(10) unsigned NOT NULL DEFAULT '0' COMMENT '最后修改时间',
`sys_status` int(10) unsigned NOT NULL DEFAULT '0' COMMENT '状态,0待上线，1已上线，2已下线',
`sys_ip` varchar(50) NOT NULL COMMENT '创建人IP',
PRIMARY KEY(`id`)
)ENGING=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=utf8 COMMENT='活动信息表';
```