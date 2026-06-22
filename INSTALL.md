# 知识星球 Skill 安装指南

本文档供 AI Agent 阅读并执行，帮助用户完成知识星球 Skill 的安装与配置。

## 前置条件

- Node.js >= 18（执行 `node -v` 检查）

## 安装步骤

### 1. 安装 CLI 工具

```bash
npm install -g zsxq-cli
```

### 2. 安装 Skill

优先使用 GitHub（海外用户）：

```bash
npx skills add https://github.com/unnoo/zsxq-skill --yes --global
```

如果 GitHub 不可达，使用 Gitee 备用通道（国内用户）：

```bash
npx skills add https://gitee.com/unnoo/zsxq-skill --yes --global
```

### 3. 登录知识星球账号

```bash
zsxq-cli auth login
```

执行后终端会输出授权链接与设备验证码。将链接提供给用户，让用户在浏览器中打开并确认授权。等待用户确认后即可开始使用。

## 网络受限时的备选方案

如果上述地址均不可达，可从以下地址下载离线包手动安装：

```
https://garden.zsxq.com/skill/zsxq-skills.zip
```

下载解压后执行：

```bash
npx skills add ./zsxq-skill --yes
```

## 安装完成

安装并登录后，AI Agent 即可调用以下技能：

| 技能 | 用途 |
|------|------|
| `zsxq-group` | 浏览星球、搜索成员 |
| `zsxq-topic` | 搜索、发布、编辑主题，评论回答 |
| `zsxq-note` | 创建、编辑、管理笔记 |
| `zsxq-user` | 查看用户信息与足迹 |
| `zsxq-shared` | 认证授权、通用工具 |
