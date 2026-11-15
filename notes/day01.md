# Day 1 · 环境与基础语法

日期：2026-11-13

## 今天做了什么

- 打通 Python 环境（卸载 3.15.2，改装 3.12.4）
- 第一批语法：变量、print、input、f-string
- 跑通 `d1_hello.py`

## 语法

```python
name = "赵嘉俊"
print(f"你好，{name}")

age = int(input("年龄："))
print(f"我今年 {age} 岁")
```

**要点**：`input()` 拿到的永远是字符串，要参与计算必须先 `int()` 或 `float()`。

## 踩过的坑

1. Python 3.15.2 太新，numpy 没有对应 wheel，报
   `No matching distribution found` → 降到 3.12.4 解决。
2. 清华镜像解析不到包（`from versions: none`）→ 换阿里云镜像正常。
3. 命令行 `python` 指向 WindowsApps 占位符，会跳微软商店
   → 关闭「应用执行别名」，并把真实解释器目录加入用户 PATH。

## 自测

- 打印「我今年 N 岁」
- 输入两个数求和
- 用 `f"{sec:.1f}"` 保留一位小数
