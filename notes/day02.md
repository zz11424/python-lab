# Day 2 · 循环与条件

日期：2026-11-14

## 今天做了什么

- 复习 D1 的四个概念
- 学习 `for` / `range` / `if` / `continue`
- 区分 `continue` 与 `break`

## 语法

```python
for i in range(1, 11):
    if i == 7:
        continue
    print(i, i * i)
```

- `range(1, 11)`：1 到 10，**左闭右开**。
- 冒号不能少，`if`、`for`、`def` 后面都要跟英文冒号。
- 循环体缩进 4 个空格，这是语法不是格式。
- `continue` 跳过本轮，`break` 结束整个循环。

## 踩过的坑

1. `if i == 7` 漏了英文冒号，VS Code 用波浪线提示 → 补 `:` 解决。
2. 把运行命令 `python d2_loop.py` 写进了 `.py` 文件，报 SyntaxError
   → 命令在终端敲，编辑器里只写 Python 语句。
3. 在错误目录运行，报 `[Errno 2] No such file or directory`
   → 先 `cd C:\Users\z\python-lab`。

## 练习

- 打印 1—20 中的偶数
- 计算 1+2+…+100 = 5050
