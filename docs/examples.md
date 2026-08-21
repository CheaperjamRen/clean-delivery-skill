# 示例：同一件事，交付面可以很干净

先看带残留的写法，再看可复制的干净写法。

## 代码注释

### 带残留

```python
def process_data(data):
    # 原本加入额外校验，用户要求删除，所以这里不加
    return cleaned_data
```

### 干净交付

```python
def process_data(data):
    return cleaned_data
```

边界理由确实重要时，写成事实：

```python
# Keep the original order because downstream reconciliation is positional.
```

## 报告标题与正文

### 带残留

```text
季度总结报告-去除多余数据分析版

根据用户要求，本节不包含详细竞品分析，原计划的图表已删除。
```

### 干净交付

```text
季度总结报告

核心结论如下：……
```

## PR

### 带残留

```text
标题：feat: export CSV（无额外校验版）

根据反馈移除了额外校验；原先考虑的进度条和空状态也已放弃。
```

### 干净交付

```text
标题：feat: export filtered records as CSV

为筛选结果添加 CSV 导出入口，并保留现有筛选条件。
验证：pytest；npm run lint。
```

## 文件名

### 带残留

```text
求职报告_精简修订版_v2_删除竞品风险图表_2026-08-21.docx
```

### 干净交付

```text
求职报告_2026-08-21.docx
```

## PPT 与办公文件

### 带残留

```text
项目汇报（按要求更新版）
第 3 页：根据用户要求删除竞品页
```

### 干净交付

```text
项目汇报
第 3 页：用户决策与下一步动作
```

审计需要完整变更记录时，把记录放入 `review-notes.md` 或平台的审计区，主文件保持可直接使用。
