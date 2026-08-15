# website-guangzhou 环境描述

`website-guangzhou` 是一台阿里云 ECS 云服务器，用于托管个人网站。

## 托管站点

| 站点 | 说明 |
|------|------|
| Barnett 个人主页 | Barnett 的个人主页 |
| Lorene 个人主页 | 女儿 Lorene 的个人主页 |

## 基本信息

| 字段 | 值 |
|------|-----|
| 云厂商 | 阿里云 ECS |
| 实例名 | website-guangzhou-20251122 |
| 地域/可用区 | 华南3（广州）B |
| 规格 | ecs.e-c1m1.large（2 vCPU / 2 GiB） |
| 系统 | Ubuntu 22.04 64位 |
| 系统盘 | ESSD Entry 40 GiB |
| 公网 IP | 不在此记录，前往 [ECS 控制台](https://ecs.console.aliyun.com) 查询 |
| 私网 IP | `<PRIVATE_IP>` |
| 公网带宽 | 3 Mbps（按固定带宽计费） |
| 用途 | 托管个人主页（Barnett 和 Lorene） |

## 计费与续费

| 字段 | 值 |
|------|-----|
| 付费类型 | 包年包月 |
| 到期时间 | 2026-11-22 |
| 自动续费 | 已开启（1 年） |
| 创建时间 | 2025-11-22 |

## 已安装工具

| 工具 | 用途 |
|------|------|
| git | 版本控制 |
| curl / wget | 网络请求与下载 |
| nginx | Web 服务器，托管网站 |
