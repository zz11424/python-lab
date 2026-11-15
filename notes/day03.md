# Day 3 · 函数、字典、文件

日期：2026-11-15

## 函数

```python
def add(a, b):
    return a + b

print(add(3, 5))
```

定义时不执行，调用时才执行；函数体缩进 4 空格。

## 字典

```python
cost = {"抓取": 42.5, "递送": 35.0, "开门": 58.2}
print(cost["抓取"])
cost["整理"] = 30.0
print(cost.get("清洁", 0))   # 键不存在时返回默认值，不报错
```

列表靠位置取值，字典靠名字取值；统计类任务用字典更方便。

## 文件读写

```python
with open("note.txt", "w", encoding="utf-8") as f:
    f.write("抓取 42 秒\n")

with open("note.txt", "r", encoding="utf-8") as f:
    lines = f.readlines()

print(len(lines))
```

- `"w"` 写入会覆盖，`"r"` 读取；
- `encoding="utf-8"` 必写，否则中文可能乱码；
- 每行末尾带 `\n`，处理时用 `line.strip()` 去掉。

## 练习

1. `add(a, b)` 返回两数之和
2. 字典存三个任务耗时，算平均
3. 逐行读取并加序号输出：

```
1 抓取 42 秒
2 递送 35 秒
3 开门 58 秒
```

提示：`for i, line in enumerate(lines, 1):` 配合 `line.strip()`。

## 状态

题 1 已完成；题 2、题 3 待补。
