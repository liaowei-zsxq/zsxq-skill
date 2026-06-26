---
name: zsxq-topic-interact
version: 1.4.0
description: "知识星球主题互动：发表评论、楼中楼回复、回答提问。当用户需要评论主题、回复评论或回答 q&a 提问时使用。"
metadata:
  requires:
    bins: ["zsxq-cli"]
  cliHelp: "zsxq-cli topic --help"
  operations:
    - "+reply"
    - "+answer"
  keywords:
    - "主题"
    - "评论"
    - "回复"
    - "楼中楼"
    - "回答"
    - "q&a"
    - "互动"
  readOnly: false
  relatedSkills:
    - "zsxq-shared"
    - "zsxq-topic-read"
    - "zsxq-topic-write"
---

# topic-interact

> 首次使用或遇到认证错误（401 / token 过期 / `not logged in`）时，先读 [`../zsxq-shared/SKILL.md`](../zsxq-shared/SKILL.md) 了解登录与 API 调用约定。本 skill 包含写入操作，执行前必须向用户确认意图与目标。日常调用已登录账户时无需每次重读。

## Core Concepts

- **评论（Comment）**：主题下的回复，由 `comment_id` 标识，支持楼中楼（`replied_comment_id`）。
- **回答（Answer）**：`q&a` 类型主题的官方回答，每个问题只能回答一次。

## Resource Relationships

```
Group (group_id)
└── Topic (topic_id)
    ├── Comment (comment_id)
    │   └── 楼中楼 Reply (replied_comment_id)
    └── Answer（q&a 类型专属）
```

## Shortcuts（推荐优先使用）

| Shortcut | 说明 |
|----------|------|
| [`+reply`](references/zsxq-topic-reply.md) | 对主题发表评论，支持楼中楼回复，需确认内容后执行 |
| [`+answer`](references/zsxq-topic-answer.md) | 对提问类主题（q&a）发布官方回答，需确认内容后执行 |

## 安全提示

评论与回答均为公开写入操作。执行前请确认：

1. 目标主题（`topic_id`）
2. 评论/回答的具体内容
3. `+answer` 每个问题只能回答一次，回答后无法修改

详见 [`zsxq-shared` 安全规则](../zsxq-shared/SKILL.md#安全规则)。

## 相关操作

- 查找/查看主题、获取评论：见 [zsxq-topic-read](../zsxq-topic-read/SKILL.md)。
- 创建、编辑、删除主题：见 [zsxq-topic-write](../zsxq-topic-write/SKILL.md)。
