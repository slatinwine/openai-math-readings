---
layout: default
title: "Unconditional time lower bounds for Weisfeiler–Leman equivalence"
family: "133"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Unconditional time lower bounds for Weisfeiler–Leman equivalence

> 结果族 133：The computational complexity of Weisfeiler–Leman refinement　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
本文无条件证明：对每个足够大的固定 \(k\)，任何判定两张 \(n\) 顶点图是否 \(k\) 维 Weisfeiler–Leman 等价的确定性串行算法，最坏情形需要 \(n^{\Omega(k)}\) 时间；不依赖 ETH 等任何复杂性假设，且在直径至多 2 的简单连通无色图上已成立。

## 问题背景
固定 \(k\) 时，\(k\)-WL 等价的朴素判定耗时 \(n^{O(k)}\)。要证明任何算法——哪怕根本不执行细化——都逃不开随 \(k\) 线性增长的指数，现有工具都不够用：Cai–Fürer–Immerman 的奇偶构造及 Grohe–Lichter–Neuen–Schweitzer 的压缩版本给出的是"需要多少轮细化"的下界，只约束细化过程本身；变维数下的 coNP 艰难与 EXPTIME 完全结果（Seppelt；Lichter–Raßmann–Schweitzer 等）量词不同，推不出固定维数的时间指数；Berkholz 关于存在博弈（existential pebble game）的无条件下界对应的是另一种博弈规则。因此本文自足地证明所需的博弈对应与完整归约。

## 主要结果
定理：存在绝对常数 \(c>0\) 与 \(k_0\)，使得对每个固定整数 \(k\ge k_0\) 与每个正确的确定性判定器 \(A\)，存在 \(n_0(A,k)\)，使 \(T_A(n)\ge n^{ck}\) 对每个整数 \(n\ge n_0\) 成立。要点：指数常数 \(c\) 与程序和 \(k\) 都无关；下界在每个足够大的图阶上都成立，而非只在无穷多个阶上——这排除了算法在稀疏的任意大阶上异常快的可能；模型覆盖多带图灵机与顺序对数字长 RAM（地址与字长 \(O(\log(n+2))\) 位，每条指令可在字长多项式时间内实现）；输入为显式邻接矩阵；即使算法只被要求在直径至多 2 的简单连通无色图上正确、且最坏时间只按该类输入计，下界依旧成立。joint 与 separate 两种替换约定都在结论之内。由此排除任何形如 \(f(k)n^{g(k)}\)、\(g(k)=o(k)\) 的运行时间界。

## 证明思路
证明按五级接口展开。第一步固定双射博弈（bijective game）对应：joint 约定的 \(k\)-WL 等价恰对应 Duplicator 在 \(k+1\) 个对槽的双射博弈中获胜，separate 约定对应 \(k\) 个对槽。第二步是压缩一致性归约：考虑变量按地址 \(\mathbf a\in[m]^r\) 下标、取值于 \(\mathbb F_2^{d_P}\) 的实例，逐边弧一致（individual-edge arc consistency）指存在非空集合 \(Q_{P,\mathbf a}\) 使每条比较 \(\phi_{e,0}(Q_{P,\mathbf a})=\phi_{e,1}(Q_{R,\boldsymbol\sigma_e(\mathbf a)})\) 逐条成立；定理把这类实例转成两张同阶、连通、直径至多 2、阶为 \(O(m^6)\) 的无色图，使 Duplicator 获胜当且仅当弧一致成立。技术核心：位点块与方块只记录两个相邻坐标，只有凑满一整圈 \(r\) 个块的"缠绕"子集才暴露一个完整地址；Duplicator 的策略用"组件位移+角势"表示平移，非缠绕组件上的位移改变可被角势吸收而读出值不变，精确投影引理 \(\mathcal H_U|_V=\mathcal H_V\) 保证保留块逐块延拓。
第三步编码计算：单调电路用私有两坐标缓冲 \(\{(z,z'):z+z'\in D\}\) 实现单向传播——目的地被压成单点不会反向限制假源；再用 Cook 式局部更新规则把单带图灵机的时空表编码为按 \(m\) 进制数字寻址的电路，时间与位置的移位通过进位/借位分解写成有界多个乘积模式，得到"机器接受当且仅当两图不等价"，且图可从 \(O(m)\) 条一坐标表在 \(O(n^4)\) 时间内构造，无需枚举完整地址。
第四步是对角语言：沿 Hennie–Stearns 的填充对角化构造显式语言 \(H_s\)，它有固定的单带判定器在 \(O(m^{20s})\) 步内可解，而任何正确的单带判定器在每个足够大的长度上最坏时间严格大于 \(m^s\)。第五步是截断迁移：对长度 \(m\) 的词尝试区间 \([m^{20},(m+1)^{20})\) 内的一切图阶，每阶给候选算法 \(m^p\) 步截断；若某个阶 \(n\) 上 \(T_A(n)<n^{c_0k}\)，则所有长度 \(m\) 的词都能在截断内完成，拼出一个 \(m^{D+50p}<m^s\) 时间的 \(H_s\) 单带判定器，与第四步矛盾。参数取 \(s=\lfloor r/1000\rfloor\)、\(p=\lfloor s/1000\rfloor\)、\(c_0=10^{-9}\)，两个严格缝隙恰好容纳全部构造与模拟开销。

## 可信度与备注
本文为无条件结果，但未经形式化验证，请以社区核验为准。作者明确指出局限：为达到直径 2 而引入的通用枢纽顶点度数无界，本文不主张有界度数承诺；当 \(r\) 随输入增长时压缩构造不给出多项式编译。它与族 133 的姊妹篇互补：本文主定理取代 ETH 条件下界篇的条件性结论，而识别篇处理的是另一量词（识别）的 EXPTIME 完全性。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
