# 沉淀与学习

> 模式二「沉淀与学习」时读取。

## 两个阶段：沉淀 ≠ 学习

- **沉淀**：把 `00-Inbox/待沉淀/` 里的资料消化成结构化笔记，写入 `10-Areas/{领域}/`（读 → 判断归属 → 写笔记 → 放入 Area）。
- **学习**：沉淀完成后，询问用户「要不要学习这篇」，要则用 `learn-anything-fast` 深度学习这篇笔记。

沉淀是「整理」，学习是「真正掌握」。不是每篇笔记都必须学习，由用户决定。

## 学习卡片格式（Compress 模式，默认）

学习产出的成果，追加到原 Areas 笔记（或生成学习卡片），包含：

1. **一句话定义** —— 用自己的话转述，不是原文照搬
2. **关键概念** —— 3–5 个
3. **具体例子** —— 至少 1 个
4. **常见错误** —— 至少 2 个
5. **自测题** —— 3–5 个

## learn-anything-fast 的调用

按用户意图选择模式：

| 用户意图 | 调用模式 |
|---------|---------|
| 快速学习（默认） | Compress：压成一张卡片 |
| 想深度学习某主题 | Full loop：完整学习循环（map→focus→retrieve→correct→compress→teach→verify） |
| 想验证是否掌握 | Teach-back：费曼检验，让用户用自己的话复述 |

## 降级说明

宿主没有 `learn-anything-fast` 技能时，用等价学习循环，产出格式一致：

```text
map（拆解主题）→ focus（找核心 20%）→ compress（压成卡片）→ teach-back（费曼自检）
```

## 打勾与状态记录

两处各记各的，不要混：

**原文**（还在 `00-Inbox/待沉淀/`）——沉淀完就打勾，表示已处理、不再被扫描：

- 文件名末尾加 `√`，如 `原文√.md`
- frontmatter 标 `outcome: digested`

**Areas 笔记**——用 frontmatter 记录实际发生了什么：

```yaml
status: learned            # 学了标 learned，只沉淀没学标 digested
output: 30-Output/ing/xxx/ # 做过输出才有这一行
```

## 做成输出（可选）

沉淀完的 Areas 笔记可以直接走成输出：读 `40-Skills/知识视频创作专家/kidd-content-expert.md`，按它的 7 步工作流把笔记扩成视频 / 文章脚本，产物写入 `30-Output/ing/{选题}/`，完成后在 Areas 笔记 frontmatter 补 `output` 字段。

学习和输出是两件独立的事：只学不输出、只输出不学、两者都做都行。

## Obsidian 适配

学习卡片和笔记都用 Obsidian 原生格式：

- **frontmatter**：`tags`、`created`、`type`、`status`
- **双向链接**：笔记顶部链接原文资料、关联相关笔记
- **callout**：需要强调时用 `> [!note]` / `> [!tip]` / `> [!warning]`
