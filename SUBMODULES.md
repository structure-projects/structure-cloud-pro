# 子模块列表

本项目使用 Git 子模块管理多个组件。以下仅列出**开源（公开）子模块**；SaaS 产品为闭源商业化解决方案，以私有仓库形式维护，不通过子模块公开，详见 [Structure Docs · SaaS 产品](https://github.com/structure-projects/structure-docs)。

## 基础框架

| 子模块 | 说明 | 最新版本 |
|--------|------|---------|
| structure-boot | Spring Boot 快速开发框架 | 1.5.0 |
| structure-cloud | 微服务依赖 | — |
| structure-security | 安全认证授权框架 | 1.1.5 |

## 服务组件

| 子模块 | 说明 | 最新版本 |
|--------|------|---------|
| structure-gateway | API 网关 | 1.0.6 |
| structure-job | 调度中心 | 2.0.1 |
| structure-message | 消息中心 | — |
| structure-admin | 管理中心后端 | — |
| structure-admin-ui | 管理中心前端 | — |

## 前端

| 子模块 | 说明 |
|--------|------|
| structure-sso | 统一登录前端 |

## 工具与文档

| 子模块 | 说明 | 最新版本 |
|--------|------|---------|
| somcli | 容器管理工具 | v0.1.2-alpha |
| structure-docs | 文档 | — |

## AI 工具

| 子模块 | 说明 |
|--------|------|
| structure-agent | AI 智能体 |

## 子模块管理命令

```bash
# 初始化并拉取所有子模块
git submodule update --init --recursive

# 查看子模块状态
git submodule status

# 更新子模块到远程最新版本
git submodule update --remote
```