# Day 4 · 读 CSV 与统计

日期：2026-11-16

## 今天做了什么

- 学会用 `csv.DictReader` 读表
- 把「字符串」转成数字再做统计
- 算出条数、平均耗时、最慢、失败总数
- 按任务汇总平均耗时

## 数据文件 `actions.csv`

```csv
任务,耗时秒,失败次数
抓取,42.5,1
递送,35.0,0
开门,58.2,2
抓取,39.8,0
递送,33.4,1
开门,61.0,3
```

## 核心代码

```python
import csv

rows = []
with open("actions.csv", "r", encoding="utf-8") as f:
    for row in csv.DictReader(f):
        rows.append({
            "task": row["任务"],
            "sec": float(row["耗时秒"]),
            "fail": int(row["失败次数"]),
        })

secs = [r["sec"] for r in rows]

print("条数：", len(rows))
print("平均耗时：%.1f 秒" % (sum(secs) / len(secs)))
print("最慢：", max(secs), "秒")
print("失败总数：", sum(r["fail"] for r in rows))
```

输出：

```
条数： 6
平均耗时： 45.0 秒
最慢： 61.0 秒
失败总数： 7
```

## 按任务汇总

```python
total = {}
count = {}

for r in rows:
    t = r["task"]
    total[t] = total.get(t, 0) + r["sec"]
    count[t] = count.get(t, 0) + 1

for t in total:
    print(t, round(total[t] / count[t], 1))
```

输出：

```
抓取 41.2
递送 34.2
开门 59.6
```

## 关键点

- `DictReader` 把第一行当表头，之后每行是字典；
- **所有值都是字符串**，`float()` / `int()` 必须转；
- `total.get(t, 0)` 是「取不到就给 0」，避免 `KeyError`；
- `round(x, 1)` 保留一位小数。

## 踩坑备忘

| 报错 | 原因 | 修法 |
|---|---|---|
| `FileNotFoundError` | 目录不对或文件名错 | `cd` 到项目目录，`dir` 确认 |
| `KeyError: 任务` | 表头有空格或全角逗号 | 用记事本看第一行 |
| `ValueError: could not convert string to float` | 单元格是空值或带单位 | 确认该列只有数字 |

## 下一步

D5：用 pandas 读同一份 CSV，把上面 20 行代码缩成 3 行。
