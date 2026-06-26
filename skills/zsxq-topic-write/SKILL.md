---
name: zsxq-topic-write
version: 1.4.0
description: "知识星球主题写入与管理：创建、编辑、删除主题，设置精华和标签。当用户需要发帖、改帖、删帖、设置精华/标签时使用。"
metadata:
  requires:
    bins: ["zsxq-cli"]
  cliHelp: "zsxq-cli topic --help"
  operations:
    - "+create"
    - "+edit"
    - "api raw DELETE /v2/topics/<topic_id>"
    - "set_topic_digested"
    - "set_topic_tags"
  keywords:
    - "主题"
    - "创建"
    - "发布"
    - "编辑"
    - "删除"
    - "精华"
    - "标签"
    - "写入"
  readOnly: false
  relatedSkills:
    - "zsxq-shared"
    - "zsxq-group"
    - "zsxq-topic-read"
    - "zsxq-topic-interact"
---

# topic-write

> 首次使用或遇到认证错误（401 / token 过期 / `not logged in`）时，先读 [`../zsxq-shared/SKILL.md`](../zsxq-shared/SKILL.md) 了解登录与 API 调用约定。本 skill 包含写入与删除操作，执行前必须向用户确认意图与目标。日常调用已登录账户时无需每次重读。

## Core Concepts

- **主题（Topic）**：星球内的内容单元，由 `topic_id` 唯一标识。
- **精华（Digested）**：星主可将优质主题设为精华，在星球内突出展示。
- **标签（Hashtag）**：为主题设置分类标签，便于检索。

## Resource Relationships

```
Group (group_id)
└── Topic (topic_id)
    └── Hashtag 标签列表
```

## Shortcuts（推荐优先使用）

| Shortcut | 说明 |
|----------|------|
| [`+create`](references/zsxq-topic-create.md) | 在指定星球发布新主题（仅支持 talk 类型），需确认内容后执行 |
| [`+edit`](references/zsxq-topic-edit.md) | 编辑自己发布的主题（正文、附件），需确认内容后执行 |

## API（通过 `zsxq-cli api call` 直接调用）

| 工具 | 参数 | 说明 |
|------|------|------|
| `set_topic_digested` | `topic_id`, `digested` | 设置/取消精华（星主权限） |
| `set_topic_tags` | `topic_id`, `titles` | 为主题设置标签（标签名数组） |

## 原始 HTTP 调用（`zsxq-cli api raw`）

| 操作 | 命令模板 | 说明 |
|------|----------|------|
| [删除主题](references/zsxq-topic-delete.md) | `api raw --method DELETE --path /v2/topics/<topic_id>` | 删除主题，不可恢复 |

## 安全提示

所有写入与删除操作都会影响线上内容。执行前请确认：

1. 目标星球 / 主题（`group_id` / `topic_id`）
2. 操作的具体内容
3. 用户明确同意执行

详见 [`zsxq-shared` 安全规则](../zsxq-shared/SKILL.md#安全规则)。

## 相关操作

- 查找/查看主题、获取评论：见 [zsxq-topic-read](../zsxq-topic-read/SKILL.md)。
- 发表评论、回答提问：见 [zsxq-topic-interact](../zsxq-topic-interact/SKILL.md)。
