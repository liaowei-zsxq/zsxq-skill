# Skill 操作索引

本文件按操作意图汇总所有 skill 提供的 Shortcut、`api call` 工具与 `api raw` 模板，方便 AI 工具在不阅读各 `SKILL.md` 正文的情况下快速定位目标 skill 与 reference。

| 操作意图 | 命令 / 工具 | Skill | Reference / 说明 |
|----------|-------------|-------|------------------|
| 登录 / 重新登录 | `zsxq-cli auth login` | [zsxq-shared](zsxq-shared/SKILL.md) | [认证](zsxq-shared/SKILL.md#认证) |
| 查看登录状态 | `zsxq-cli auth status` | [zsxq-shared](zsxq-shared/SKILL.md) | [认证](zsxq-shared/SKILL.md#认证) |
| 退出登录 | `zsxq-cli auth logout` | [zsxq-shared](zsxq-shared/SKILL.md) | [认证](zsxq-shared/SKILL.md#认证) |
| 诊断 CLI 配置 | `zsxq-cli doctor` | [zsxq-shared](zsxq-shared/SKILL.md) | [Commands](zsxq-shared/SKILL.md#commands) |
| 查看当前配置 | `zsxq-cli config show` | [zsxq-shared](zsxq-shared/SKILL.md) | [Commands](zsxq-shared/SKILL.md#commands) |
| 列出所有底层接口 | `zsxq-cli api list` | [zsxq-shared](zsxq-shared/SKILL.md) | [直接调用 API](zsxq-shared/SKILL.md#直接调用-api) |
| 调用底层接口 | `zsxq-cli api call <tool>` | [zsxq-shared](zsxq-shared/SKILL.md) | [直接调用 API](zsxq-shared/SKILL.md#直接调用-api) |
| 原始 HTTP 调用 | `zsxq-cli api raw ...` | [zsxq-shared](zsxq-shared/SKILL.md) | [直接调用 API](zsxq-shared/SKILL.md#直接调用-api) |
| 拼接主题/星球链接 | 链接模板 | [zsxq-shared](zsxq-shared/SKILL.md) | [链接拼接](zsxq-shared/SKILL.md#链接拼接) |
| 列出加入/创建的星球 | `group +list` | [zsxq-group](zsxq-group/SKILL.md) | [zsxq-group-list](zsxq-group/references/zsxq-group-list.md) |
| 浏览星球最新主题 | `group +topics` | [zsxq-group](zsxq-group/SKILL.md) | [zsxq-group-topics](zsxq-group/references/zsxq-group-topics.md) |
| 列出星球标签 | `group +hashtags` | [zsxq-group](zsxq-group/SKILL.md) | [zsxq-group-hashtags](zsxq-group/references/zsxq-group-hashtags.md) |
| 搜索星球 | `api call search_groups` | [zsxq-group](zsxq-group/SKILL.md) | [SKILL.md API 表](zsxq-group/SKILL.md#api通过-zsxq-cli-api-call-直接调用) |
| 搜索星球成员 | `api call search_group_members` | [zsxq-group](zsxq-group/SKILL.md) | [SKILL.md API 表](zsxq-group/SKILL.md#api通过-zsxq-cli-api-call-直接调用) |
| 查看标签下主题 | `api call get_hashtag_topics` | [zsxq-group](zsxq-group/SKILL.md) | [SKILL.md API 表](zsxq-group/SKILL.md#api通过-zsxq-cli-api-call-直接调用) |
| 搜索主题 | `topic +search` | [zsxq-topic-read](zsxq-topic-read/SKILL.md) | [zsxq-topic-search](zsxq-topic-read/references/zsxq-topic-search.md) |
| 查看主题详情 | `topic +detail` | [zsxq-topic-read](zsxq-topic-read/SKILL.md) | [zsxq-topic-detail](zsxq-topic-read/references/zsxq-topic-detail.md) |
| 获取主题评论列表 | `api call get_topic_comments` | [zsxq-topic-read](zsxq-topic-read/SKILL.md) | [SKILL.md API 表](zsxq-topic-read/SKILL.md#api通过-zsxq-cli-api-call-直接调用) |
| 查看自己发起的提问 | `api call get_self_question_topics` | [zsxq-topic-read](zsxq-topic-read/SKILL.md) | [SKILL.md API 表](zsxq-topic-read/SKILL.md#api通过-zsxq-cli-api-call-直接调用) |
| 查看别人向我发起的提问 | `api call get_self_answer_topics` | [zsxq-topic-read](zsxq-topic-read/SKILL.md) | [SKILL.md API 表](zsxq-topic-read/SKILL.md#api通过-zsxq-cli-api-call-直接调用) |
| 发布主题 | `topic +create` | [zsxq-topic-write](zsxq-topic-write/SKILL.md) | [zsxq-topic-create](zsxq-topic-write/references/zsxq-topic-create.md) |
| 编辑主题 | `topic +edit` | [zsxq-topic-write](zsxq-topic-write/SKILL.md) | [zsxq-topic-edit](zsxq-topic-write/references/zsxq-topic-edit.md) |
| 删除主题 | `api raw --method DELETE --path /v2/topics/<topic_id>` | [zsxq-topic-write](zsxq-topic-write/SKILL.md) | [zsxq-topic-delete](zsxq-topic-write/references/zsxq-topic-delete.md) |
| 设置/取消精华 | `api call set_topic_digested` | [zsxq-topic-write](zsxq-topic-write/SKILL.md) | [SKILL.md API 表](zsxq-topic-write/SKILL.md#api通过-zsxq-cli-api-call-直接调用) |
| 设置主题标签 | `api call set_topic_tags` | [zsxq-topic-write](zsxq-topic-write/SKILL.md) | [SKILL.md API 表](zsxq-topic-write/SKILL.md#api通过-zsxq-cli-api-call-直接调用) |
| 发表评论 / 楼中楼回复 | `topic +reply` | [zsxq-topic-interact](zsxq-topic-interact/SKILL.md) | [zsxq-topic-reply](zsxq-topic-interact/references/zsxq-topic-reply.md) |
| 回答提问类主题 | `topic +answer` | [zsxq-topic-interact](zsxq-topic-interact/SKILL.md) | [zsxq-topic-answer](zsxq-topic-interact/references/zsxq-topic-answer.md) |
| 创建笔记 | `note +create` | [zsxq-note](zsxq-note/SKILL.md) | [zsxq-note-create](zsxq-note/references/zsxq-note-create.md) |
| 查看笔记列表 | `note +list` | [zsxq-note](zsxq-note/SKILL.md) | [zsxq-note-list](zsxq-note/references/zsxq-note-list.md) |
| 查看笔记详情 | `note +detail` | [zsxq-note](zsxq-note/SKILL.md) | [zsxq-note-detail](zsxq-note/references/zsxq-note-detail.md) |
| 编辑笔记 | `note +edit` | [zsxq-note](zsxq-note/SKILL.md) | [zsxq-note-edit](zsxq-note/references/zsxq-note-edit.md) |
| 删除笔记 | `note +delete` | [zsxq-note](zsxq-note/SKILL.md) | [zsxq-note-delete](zsxq-note/references/zsxq-note-delete.md) |
| 查看当前用户信息 | `user +info` | [zsxq-user](zsxq-user/SKILL.md) | [zsxq-user-info](zsxq-user/references/zsxq-user-info.md) |
| 查看跨星球主题足迹 | `user +footprints` | [zsxq-user](zsxq-user/SKILL.md) | [zsxq-user-footprints](zsxq-user/references/zsxq-user-footprints.md) |
| 提交 NPS 反馈 | `user +nps` | [zsxq-user](zsxq-user/SKILL.md) | [zsxq-user-nps](zsxq-user/references/zsxq-user-nps.md) |
