# Instruction Set Architecture(ISA)

指令集结构是描述计算机的抽象模型, 它有时也被成为计算机体系结构. ISA 定义了在该计算机上进行编程的一切行为. ISA 包含一系列的 opcode即操作码(机器语言), 以及由特定处理器执行的基本命令.

EVM 指令集按照功能分类, 可分为如下几个部分:

- `0x00 ~ 0x0f`: 用于终止和算术的指令
- `0x10 ~ 0x1f`: 用于算术比较和位操作的指令
- `0x20 ~ 0x2f`: 用于计算 SHA3 的指令
- `0x30 ~ 0x3f`: 用于获取环境信息的指令
- `0x40 ~ 0x4f`: 用于获取区块信息的指令
- `0x50 ~ 0x5f`: 用于内存与存储读写和控制流程的指令
- `0x60 ~ 0x7f`: 用于数据入栈的指令
- `0x80 ~ 0x8f`: 用于栈内数据复制的指令
- `0x90 ~ 0x9f`: 用于栈内数据交换的指令
- `0xa0 ~ 0xaf`: 用于记录日志的指令
- `0xf0 ~ 0xff`: 用于系统调用的指令

描述一个指令最少需要以下几个部分:

| Value | Mnemonic | $\delta$ | $\alpha$ | Description |
|-------|----------|----------|----------|-------------|
| 值 | 助记词 | 出栈数 | 入栈数 | 描述 |

以四则运算指令为例:

| Value | Mnemonic | $\delta$ | $\alpha$ | Description |
|-------|----------|----------|----------|-------------|
| 0x01  | ADD | 2 | 1 | Addition operation. $\mu_s^\prime[0] \equiv \mu_s[0] + \mu_s[1]$ |
| 0x02  | MUL | 2 | 1 | Multiplication operation. $\mu_s^\prime[0] \equiv \mu_s[0] * \mu_s[1]$ |
| 0x03  | SUB | 2 | 1 | Subtraction operation. $\mu_s^\prime[0] \equiv \mu_s[0] - \mu_s[1]$ |
| 0x04  | DIV | 2 | 1 | Integer division operation. $\mu_s^\prime[0] \equiv \mu_s[0] / \mu_s[1]$ |


> $\mu$ 表示当前栈, $\mu^\prime$ 表示执行之后的栈

EVM 全部操作码非常的多, 相信阅读黄皮书比看我的中文二手货更值当.
