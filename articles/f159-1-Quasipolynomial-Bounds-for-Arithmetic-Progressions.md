---
layout: default
title: "Quasipolynomial Bounds for Arithmetic Progressions"
family: "159"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Quasipolynomial Bounds for Arithmetic Progressions

> 结果族 159：Erdős's reciprocal-sum conjecture and quasipolynomial Szemerédi bounds　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了 Erdős 1974 年的倒数和猜想：倒数和发散的正整数集必含任意有限长度的非平凡等差数列；定量上对每个固定 \(k\ge 3\) 给出拟多项式界 \(r_k(N)\le C_kN\exp(-c_k(\log N)^{\varepsilon_k})\)，这是首个对所有长度都可逐二进段求和的 Szemerédi 型界。

## 问题背景
1974 年 Erdős 提出猜想：凡正整数集 \(A\) 满足 \(\sum_{a\in A}1/a=\infty\)，就包含任意有限长度的非平凡等差数列（arithmetic progression）。它源自 Erdős–Turán 1936 年开创的密度问题：Roth 1953 年用傅里叶分析证明 3 项情形的 \(r_3(N)=o(N)\)，Szemerédi 1975 年证明一般情形，Furstenberg 随后给出遍历论证明。但定性估计 \(r_k(N)=o(N)\) 不足以解决倒数和问题——证明需要更强的可求和条件 \(\sum_m r_k(2^m)/2^m<\infty\)。此前仅 3 项情形达标：Bloom–Sisask 2020 年的 \(r_3(N)\ll N/(\log N)^{1+c}\) 跨过求和阈值，Kelley–Meka 2023 年进一步给出 \(\exp(-c(\log N)^{1/12})\) 型界；而对 \(k\ge 5\)，Leng–Sah–Sawhney 的界 \(r_k(N)\ll_k N\exp(-(\log\log N)^{c_k})\) 不满足求和性。卡点在于密度增量（density increment）迭代时区间长度的对数损失会随轮数累积失控。

## 主要结果
主定理（论文 Theorem 1.1）：对每个固定整数 \(k\ge 3\)，存在常数 \(C_k,c_k,\varepsilon_k>0\)，使得对一切 \(N\ge2\) 有 \(r_k(N)\le C_kN\exp(-c_k(\log N)^{\varepsilon_k})\)，其中 \(r_k(N)\) 是 \(\{1,\ldots,N\}\) 中不含非常数 \(k\) 项等差数列的子集的最大规模。等价的阈值形式说：密度 \(\alpha\) 的子集只要 \(\log N\ge A_k(2+\log(1/\alpha))^{A_k}\) 就必含 \(k\) 项数列。立即得到核心推论：倒数和发散的集合含任意有限长度数列——对二进区间 \([2^m,2^{m+1})\) 求和即 \(\sum 2^{-m}r_k(2^m)\le\sum C_k\exp(-c_k(m\log2)^{\varepsilon_k})<\infty\)。论文还给出更强的加权判据（\(\sum_{a\in A}(\log(2+a))^B/a=\infty\) 即可）、重现 Green–Tao 的素数定理，并导出染色数上界 \(W_r(k)\le\lceil\exp(A_k(2+\log r)^{A_k})\rceil\)，与姊妹篇的下界配合，证明对固定 \(k\) 该数随颜色数的增长超多项式但不超拟多项式。

## 证明思路
整体是密度增量框架：数列缺失强迫密度在更小的结构化区域上提升，固定倍率的增益只能用 \(O_k(1+\log(1/\alpha))\) 次，故全部增量的对数长度损失总和必须是 \(2+\log(1/\alpha)\) 的多项式。论文的关键创新是增量区域的形状与预算制度。区域取为三角多项式胞腔（triangular polynomial cell）：空间变量 \(u\) 权重为 1，整块 \(b_h\) 权重为 \(h\)，逐层由约束 \(\|b_h-C_h(u,b_{<h})-l_h\|_\infty\le w_h\) 决定，窄宽度 \(w_h\le1/32\) 保证整块唯一，记精度 \(Q_h=\log(2/w_h)\)。核心的"三角增量定理"规定：新胞腔在权重 \(h\) 处的新增精度只依赖于维度数据、密度参数 \(p\) 及**严格更高**权重的精度，绝不依赖当前或更低的 \(Q\)——否则多项式度会在逐轮代入中不断升高，正是此前方法失效之处。由于权重层数 \(D\) 固定，自上而下的归纳保证所有维度与精度在 \(T=O_k(p)\) 轮迭代后仍为多项式。

增量的来源分两步。第一步是"绝对增量"：先用 Leng–Sah–Sawhney 的拟多项式逆定理（inverse theorem），把大的均匀度范数（uniformity norm）转化为与 nilsequence（紧幂零流形上的多项式轨道与 Lipschitz 函数）的相关性；再用平移比较定理（改造 Kelley–Meka 的失衡与筛选技术，配合 Schoen–Sisask 对半径敏感的殆周期性定理）从结构性测试过渡到正的数列计数；高阶比较则借助 Green–Tao 与 Leng 的多项式轨道等分布定理消去最高次频率。由此得到的引理给出与维度无关的新坐标数：新添加的整数槽至多 \(d_0=(2+p)^{C_k}\) 个，与所处盒子的维数无关。第二步是"返回原胞腔"：在采样盒上找到的增量必须换回原变量，且旧的决定方程必须精确保持——把整数槽原样代入后续所有多项式，误差才不会逐层传播。权重高于 \(s=k-2\) 的层是被动层，用 Conlon–Fox–Zhao 稠密化的立方体版本处理稀疏因子；最后 \(s\) 个主动层用精确投影保持旧方程。证明主线是：先做秩切割准备，再沿受约束路径下降到终端盒，应用绝对增量，然后逐层返回，提取新三角胞腔，最后闭合预算并迭代；约 \(O_k(p)\) 轮后阈值超过 1，而 \(fB^-\le B^+\) 逐点成立，阈值 \(\ge1\) 的证书不可能，矛盾。其中前向质量比较只要求证书的严格不等式、不计其盈余的逆，这也是能迭代到底的要点之一。

## 可信度与备注
本论文主结果暂无形式化证明，OpenAI 官方亦声明"未经形式化的结果可能有问题"，请以社区核验为准。论文的两大外部解析输入——Leng–Sah–Sawhney 逆定理与 Schoen–Sisask 殆周期性定理——均在正文引用处注明精确假设，且框图与接口表逐项列出各分析命题的完整证明位置。族内姊妹篇给出互补的 van der Waerden 数下界 \(W_r(k)>\exp((\log r)^2/(64\log2))\)（\(r\ge256\)），与本文上界共同夹出拟多项式增长；本文自陈未改进 3 项情形的指数，贡献在于全长度、可求和的界。

{% endraw %}
