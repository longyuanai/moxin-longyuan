# moxin-longyuan · ARCHITECTURE

核实日期：2026-10-15。依据本地README、构建清单和实际入口；本文件不把文档计划当成运行时验收。

## 目标与范围

通过终端界面和现有模拟器运行固件，复用 Arduino Uno 与 STM32F405 的既有仿真路径。

GitHub：[longyuanai/moxin-longyuan](https://github.com/longyuanai/moxin-longyuan)。知识笔记：Vault内 `03_Projects/moxin-longyuan/moxin-longyuan - Git关联.md`。

## 组件与代码入口

| 实际路径 | 责任边界 |
| --- | --- |
| [src](src) | 主要实现 |
| [bridge](bridge) | 仿真桥接 |
| [scripts](scripts) | 作者/运维工具 |
| [docs](docs) | 工程规范与说明 |

## 数据与控制流

以下链路对应README/规范描述；实现覆盖以代码入口和适用验证为准。

```mermaid
flowchart LR
    N0["终端操作"]
    N1["bridge"]
    N2["simavr或QEMU"]
    N3["GPIO/UART事件"]
    N4["终端面板"]
    N0 --> N1
    N1 --> N2
    N2 --> N3
    N3 --> N4
```

## 构建与依赖依据

按README和各子目录清单运行；文档/静态/脚本项目不额外引入构建框架。

## 验证边界

分别记录两类仿真器版本、GPIO/UART输入与输出；这轮不进行实体硬件烧录。

## 现行依据

- [README.md](README.md)
