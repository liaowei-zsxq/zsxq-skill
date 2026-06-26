---
name: zsxq-topic-read
version: 1.4.0
description: "知识星球主题读查：搜索主题、查看详情、获取评论、查看自己/他人提问记录。当用户需要查找/查看主题、获取 topic_id、看评论或提问记录时使用。"
metadata:
  requires:
    bins: ["zsxq-cli"]
  cliHelp: "zsxq-cli topic --help"
  operations:
    - "+search"
    - "+detail"
    - "get_topic_comments"
    - "get_self_question_topics"
    - "get_self_answer_topics"
  keywords:
    - "主题"
    - "topic_id"
    - "搜索"
    - "详情"
    - "评论"
    - "提问"
    - "精华"
    - "标签"
  readOnly: true
  relatedSkills:
    - "zsxq-shared"
    - "zsxq-group"
    - "zsxq-topic-write"
    - "zsxq-topic-interact"
---

# topic-read

> 首次使用或遇到认证错误（401 / token 过期 / `not logged in`）时，先读 [`../zsxq-shared/SKILL.md`](../zsxq-shared/SKILL.md) 了解登录与 API 调用约定。日常调用已登录账户时无需每次重读。

## Core Concepts

- **主题（Topic）**：星球内的内容单元，由 `topic_id` 唯一标识。类型：
  - `talk`：普通帖子（图文）
  - `q&a`：提问，可被星主回答
  - `task`：作业题目
  - `solution`：作业答案
- **评论（Comment）**：主题下的回复，由 `comment_id` 标识，支持楼中楼（`replied_comment_id`）。
- **精华（Digested）**：星主可将优质主题设为精华，在星球内突出展示。

## Resource Relationships

```
Group (group_id)
└── Topic (topic_id) — talk / q&a / task / solution
    ├── Comment (comment_id)
    │   └── 楼中楼 Reply (replied_comment_id)
    ├── Answer（q&a 类型专属）
    └── Hashtag 标签列表
```

## Shortcuts（推荐优先使用）

| Shortcut | 说明 |
|----------|------|
| [`+search`](references/zsxq-topic-search.md) | 在星球内全文搜索主题，返回 topic_id / 类型 / 标题 / 时间表格 |
| [`+detail`](references/zsxq-topic-detail.md) | 获取单条主题的完整详情（内容、评论数、点赞数、标签等） |

## API（通过 `zsxq-cli api call` 直接调用）

Shortcut 未覆盖的只读操作：

| 工具 | 参数 | 说明 |
|------|------|------|
| `get_topic_comments` | `topic_id`, `limit`, `index` | 获取主题评论列表（分页） |
| `get_self_question_topics` | `topic_filter`, `count`, `end_time` | 查看自己发起的提问（`unanswered`/`answered`） |
| `get_self_answer_topics` | `topic_filter`, `count`, `end_time` | 查看别人向我发起的提问（`unanswered`/`answered`） |

## 相关操作

- 创建、编辑、删除主题，以及设置精华/标签：见 [zsxq-topic-write](../zsxq-topic-write/SKILL.md)。
- 发表评论、回答提问：见 [zsxq-topic-interact](../zsxq-topic-interact/SKILL.md)。
