---
layout: default
title: "Exact derandomization of logarithmic space: L = RL = BPL"
family: "103"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Exact derandomization of logarithmic space: L = RL = BPL

> 结果族 103：Exact derandomization of logarithmic space: `@@M@@\mathsf L=\mathsf{RL}=\mathsf{BPL}@@`　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 `@@M@@\mathsf L=\mathsf{RL}=\mathsf{BPL}@@`：多项式时间的对数空间随机计算，无论单侧错误还是双侧错误，都能被确定性对数空间 (logarithmic space) 机器等价模拟，并给出带显式多项式时间界的有效编译器，彻底解决该去随机化 (derandomization) 问题。

## 问题背景

复杂性理论用 `@@M@@\mathsf L@@`、`@@M@@\mathsf{RL}@@`、`@@M@@\mathsf{BPL}@@` 分别刻画确定性、单侧错误 (one-sided error) 与双侧错误 (two-sided error) 的对数空间多项式时间计算。平凡包含 `@@M@@\mathsf L\subseteq\mathsf{RL}\subseteq\mathsf{BPL}@@` 成立，真正的难题在反方向：随机硬币究竟能否省掉。与 `@@M@@\mathsf{P}@@` 对 `@@M@@\mathsf{BPP}@@` 的经典问题不同，空间版本此前连把 `@@M@@\mathsf{BPL}@@` 压回 `@@M@@O(\log n)@@` 都做不到，通用技术只能给出略大的确定性空间上界。近年 Pyne–Raz–Zhan 提出的"普适确定性估计"路线，给出一台能统一逼近分支程序 (branching program) 接受概率的确定性算法；本文明确以它为先声，并把这条路线推进到终点。

## 主要结果

主定理：`@@M@@\mathsf L=\mathsf{RL}=\mathsf{BPL}@@`。核心是"固定逆多项式精度"的概率逼近定理：对每个固定的随机对数空间多项式时间机器 `@@M@@\mathcal M@@` 与精度指数 `@@M@@d\ge 1@@`，存在统一的确定性转换器 (transducer)，在每个长度 `@@M@@n@@` 的输入上输出 dyadic 有理数 (dyadic rational) `@@M@@z_x\in[0,1]@@`，使 `@@M@@|z_x-p_{\mathcal M}(x)|\le(n+2)^{-d}@@`，其中 `@@M@@p_{\mathcal M}(x)@@` 是接受概率；转换器只用 `@@M@@O(\log(n+2))@@` 工作空间与多项式时间。取 `@@M@@d=3@@`，误差 `@@M@@\le 1/8@@`，与阈值 `@@M@@1/2@@` 比较即可在 `@@M@@1/3@@` 与 `@@M@@2/3@@` 的接受概率间隙上正确判定，故 `@@M@@\mathsf{BPL}\subseteq\mathsf L@@`；另两个包含是平凡的（确定性机器可忽略硬币，`@@M@@\mathsf{RL}@@` 重复两次即放大成 `@@M@@\mathsf{BPL}@@`）。论文进一步证明承诺问题 (promise problem) 版 `@@M@@\mathsf{PromiseBPL}=\mathsf{PromiseL}@@`，精度可作为输入的一部分给出，并且当 `@@M@@p_{\mathcal M}(x)\ge(n+2)^{-c}@@` 时能在对数空间输出经过认证的接受计算。最后是有效编译器定理：给定机器描述 `@@M@@M@@` 与正整数 `@@M@@a,b@@`，算法输出确定性机器 `@@M@@D_M@@` 及显式常数 `@@M@@K,H,c@@`——只要 `@@M@@M@@` 满足声明的 `@@M@@(n+2)^a@@` 步与 `@@M@@b\lceil\log(n+2)\rceil@@` 比特界，`@@M@@D_M@@` 就判定同一语言，且每次执行至多用 `@@M@@K\log(n+2)@@` 个工作比特与 `@@M@@H(n+2)^c@@` 次基本位操作。

## 证明思路

证明是一条自下而上的长链。第一步，把随机机器在输入 `@@M@@x@@` 上的运行写成有限配置图 (configuration graph)：转移矩阵 `@@M@@S@@` 严格前向（`@@M@@S(x,y)=0@@` 除非 `@@M@@x<y@@`）、行和不超过 1，接受概率是线性方程组的解 `@@M@@p_0=(I-S)^{-1}e@@`，于是去随机化等价于在对数空间内确定性逼近这个数。第二步是纠正—复制层级 (correction and copy hierarchy)：利用恒等式 `@@M@@I-D=(I+E)(I-C)@@`，每阶段构造修正项 (correction) `@@M@@E@@` 把转移质量搬入奖励 (reward)，使残余矩阵 `@@M@@D=C-E+EC@@` 的元素在"好列"上大幅缩小；再用 `@@M@@D_0@@` 份复制 (copies) 把残余大项分流，全部元素从 `@@M@@f@@` 压到 `@@M@@f/2^H@@`，而活跃顶点数每阶段至多翻倍。`@@M@@L=O(\log n)@@` 步后转移行和降到 `@@M@@1/16@@` 以下，搬运出的奖励 `@@M@@W_L@@` 便逼近 `@@M@@p_0@@`。修正项需要知道哪些列"过载"，这由随机探测器 (detector)——对采样行的秩统计量取期望——判定。第三步，整个随机环境只需 `@@M@@O(\log n)@@` 个随机比特：若干独立的秩通道 (rank channel) 是有限域 `@@M@@\mathbb F_P@@` 上随机矩阵实现的哈希，顶点 `@@M@@y@@` 在速率 `@@M@@a@@` 被保留的概率 `@@M@@\pi_a@@` 与 `@@M@@a@@` 同阶；论文构造原子 (atom) 表（分箱、修正、探测器得分），使其在保留事件下的条件期望 (conditional expectation) 恰好等于层级中的精确量，且行门与入门保证每行、每列只有常数个非零端口。第四步是递归估计：每个任务带统计预算 `@@M@@M@@`，误差以对环境的 8 阶积分矩度量并按 `@@M@@C_b2^{-p}@@` 归纳控制；关键技巧是"加法调度"——不做一次长平均，而是对相邻预算估计之差施以长度递增的条件平均随机游走 (conditional walk)，其谱隙 (spectral gap) 一致，条件均值伸缩相消、噪声指数衰减，过细的贡献则整体省略。最后收尾：条件化到指定起点损失因子 `@@M@@N=2^{O(\log n)}@@`，由 8 阶矩加 Markov 不等式支付；随后穷举全部 `@@M@@2^{O(\log n)}@@` 个环境编码（原始盐比特串与域矩阵元素），逐个确定性算出估计值的 dyadic 数码再取中位数 (median)——因超过四分之三的环境足够准，中位数必落在误差 `@@M@@(n+2)^{-d}@@` 之内。编译器一节补上显式界：先造自带时间与空间上限的固定解释器 (interpreter) `@@M@@U@@`，把逼近定理作用于 `@@M@@U@@` 得到固定的确定性判定库 `@@M@@A@@`；对每个源机器用长度 `@@M@@N_{\mathrm{pad}}=2^{PB_n}@@` 的虚拟填充输入把它无损嵌入 `@@M@@U@@` 的上限（接受概率精确不变），`@@M@@D_M@@` 靠回调从真实输入按需重生成虚拟符号；最后用构型计数 (configuration counting) 导出空间与时间的显式联立界。

## 可信度与备注

本结果暂无形式化证明，OpenAI 官方亦声明"未经形式化的结果可能有问题"，请以社区核验为准。该手稿（2026 年 9 月 23 日版）是结果族 103 中唯一一篇，没有族内姊妹篇互相支撑；其正确性依赖"环境—层级—原子—估计—指纹—算术—实现—编译器"这一内部自洽的长链条，任何一环（尤其是论文中按严格顺序选择的众多固定常数）出错都会波及主定理，读者宜以同行评议结论为准。

{% endraw %}
