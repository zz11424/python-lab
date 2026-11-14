# python-lab

湘潭理工学院 · 车辆工程 · 2028 届
实习期（2026.11—2027.02）Python 学习记录

## 目标

3 个月内，能用 pandas 把实习采集的动作数据做成「指标表 + 图表 + 周报」，
而不是学完一门 Python 课。

## 环境

- Python 3.12.4（`C:\Python312`）
- numpy 2.5.4 / pandas 3.1.1 / matplotlib / openpyxl
- pip 源：阿里云镜像

## 7 天计划

| 天 | 文件 | 内容 | 跑通标准 |
|---|---|---|---|
| D1 | `d1_hello.py` | print、变量、input、f-string | 输入名字打印问候 |
| D2 | `d2_loop.py` | if、for、while、列表 | 打印 1—10 平方，跳过 7 |
| D3 | `d3_file.py` | 函数、字典、读写 txt | 读一个 txt 并统计行数 |
| D4 | `d4_csv.py` | csv 模块读表、算均值/最大/计数 | 用自己的动作卡数据算出 3 个数 |
| D5 | `d5_pandas.py` | pandas 读表、选列、过滤 | 筛出失败次数 > 0 的行 |
| D6 | `d6_groupby.py` | groupby 算每类任务平均耗时 | 输出按任务汇总的表 |
| D7 | `d7_plot.py` | matplotlib 画柱状图 | 生成 `chart.png` |

## 今日记录 · 2026-11-13

**完成**

- 打通 Python 环境：卸载 3.15.2，改装 3.12.4
- 装齐 numpy / pandas / matplotlib / openpyxl，验证 import 通过
- 跑通 `d1_hello.py`

**踩过的坑**

1. Python 3.15.2 太新，numpy 没有对应 wheel，`pip install` 报
   `No matching distribution found` → 降到 3.12.4 解决。
2. 清华镜像在这台机器上解析不到包（`from versions: none`），
   换个源到阿里云后正常。
3. 命令行 `python` 指向 WindowsApps 占位符，跳到微软商店 →
   关闭「应用执行别名」并把真实解释器目录加进用户 PATH。

**明天**

- D2：循环与条件
- 面试（长沙，具身智能机器人实习）

## 今日记录 · 2026-11-14

**完成**

- D1 复习：变量、print、input、f-string，三道自测跑通
- D2：`for` / `range` / `if` / `continue`，理解了 `break` 与 `continue` 的区别

**踩过的坑**

4. `if i == 7` 漏了英文冒号，VS Code 用波浪线提示 → 补上 `:` 解决。
5. 把运行命令 `python d2_loop.py` 写进了 `.py` 文件，报 SyntaxError
   → 命令在终端敲，编辑器里只写 Python 语句。
6. 在错误目录运行，报 `[Errno 2] No such file or directory`
   → 先 `cd C:\Users\z\python-lab`，或在 VS Code 里打开文件夹。

**明天**

- D3：函数、字典、读写 txt
