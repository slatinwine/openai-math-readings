---
layout: default
title: "One Rational Matrix Hitting Point for Noncommutative Formulas"
family: "116"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | One Rational Matrix Hitting Point for Noncommutative Formulas

> 结果族 116：Uniform black-box noncommutative identity testing across characteristics　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
在特征零的一切域上，确定性算法仅凭变量数 \(n\) 与公式规模 \(s\)，在多项式比特时间内构造一组维度 \(\le2ns^2\) 的有理矩阵，使每个规模 \(\le s\) 的非零非交换公式代入后非零——单个矩阵元组即构成多项式大小的黑盒打击集。

## 问题背景
非交换多项式恒等测试（polynomial identity testing, PIT）中变量取矩阵值，标量代入无法区分 \(x_1x_2-x_2x_1\) 与零。白盒方面，Raz–Shpilka（2005）对给出描述的非交换公式与分支程序已有确定性多项式时间算法；黑盒方面，Bogdanov–Wee（2005）给出带次数界的随机化矩阵代入测试，Forbes–Shpilka（2013）构造了拟多项式大小的确定性矩阵打击集（hitting set），其域基数条件在特征零下自动满足。把有限打击集用块对角和拼成单一元组虽可行，维度却等于各成员维度之和，故仍止步于拟多项式。能否只用规模参数就生成一个多项式维度的"万能"代入点，此前在特征零下未解。本文肯定作答，且不施加深度、齐次性或稀疏性限制——小公式展开后可有指数多个单项式：\(k\) 个 \(x_1+x_2\) 的有序积只有 \(4k-1\) 个门却有 \(2^k\) 个字。

## 主要结果
定理 1.1：存在确定性算法，输入 \(n,s\ge1\)，构造元组 \(\mathbf T_{n,s}\in\Mat_d(\mathbb Q)^n\)，\(d\le2ns^2\)，构造时间为关于 \(n,s\) 的多项式比特时间；各元素分子分母的比特长为 \(O(\log(ns+1)+ns^2\log(n+1))\)。对每个特征零域 \(F\) 与每个非零 \(f\in\mathsf{Form}_{n,s}(F)\)（由规模至多 \(s\) 的公式计算的多项式），经嵌入 \(\mathbb Q\hookrightarrow F\) 把同一元组视为 \(F\) 上矩阵，有 \(f(\mathbf T_{n,s})\ne0\)。于是对承诺落在 \(\mathsf{Form}_{n,s}(F)\) 中的多项式，一次精确矩阵求值即可判定是否为零。命题还把构造推广到 \(m\) 顶点的无圈代数分支程序（acyclic algebraic branching program），维度 \((n-1)\binom m2+m\)，从而在特征零下改进了此前拟多项式的打击集界。对任意共享子式的电路并无相应断言。

## 证明思路
难点在于小公式可能含指数多个字，必须用忠实编码保住全部字，再用公式的紧凑表示控制截断长度。第一步用迭代积分（iterated integrals）编码：定义 \(\mathcal J_i(a)(z)=\int_0^z\frac{a(t)}{t+i}\,dt\)（按形式幂级数逐项积分），令 \(h_\epsilon=1\)、\(h_{iw}=\mathcal J_i(h_w)\)——这类函数属经典超对数（hyperlogarithm）理论。论文证明 \(\{h_w\}\) 在一切特征零域上线性无关：先在 \(\mathbb C\) 上做三角形单值（monodromy）论证，把级数族组装成取值于截断自由代数 \(E_D\) 的微分方程解 \(U\)；绕极点 \(-i\) 的回路值满足 \(Q_i=1+\tau X_i\pmod{\mathfrak m^2}\)（\(\tau=2\pi\sqrt{-1}\)），有序乘积族 \(C_w=(Q_{i_1}-1)\cdots(Q_{i_b}-1)\) 在按字长排序的基下呈三角、对角元为 \(\tau^{|w|}\)，故回路值张成 \(E_D\)，任何线性关系必为零；再取一个非零的有理系数子式，经 \(\mathbb Q\hookrightarrow F\) 把无关性转移到任意特征零域。于是 \(f\mapsto h_f=\sum_wf_wh_w\) 是单射，编码不丢失任何非零多项式。

第二步把公式压缩为微分系统。沿用 Nisan 的公式到路径程序构造：规模 \(s\) 的公式给出至多 \(2s\) 个顶点的无圈图，消去标量边后得到 \(m\le2s\)、严格上三角的 \(B_i\) 与 \(u,v\)，使每个字的系数 \(f_w=uB_wv\)。令 \(G(z)=\sum_{|w|<m}B_wh_w\)，则 \(G(0)=I_m\)、\(G'=\bigl(\sum_i\frac{B_i}{z+i}\bigr)G\)，且 \(uGv=h_f\ne0\)；系统的分母 \(q(z)=\prod_{i=1}^n(z+i)\) 满足 \(q(0)=n!\ne0\)、分子次数 \(\deg P\le n-1\)。第三步是量化核心——Moura 的重数估计（multiplicity estimate）：对满足 \(G'=(P/q)G\)、\(q(0)\ne0\)、\(\deg q=n\)、\(\deg P\le n-1\) 的 \(m\) 维系统，非零标量分量满足 \(\ord_0(uGv)\le(n-1)\binom m2+m-1\le2ns^2-1\)；论文用形式 Wronskian 判据与导数行极大子式的最低阶给出自足证明，界与一切系数取值无关。最后取 \(d=2ns^2\)，把积分算子实现为 \(d\) 维 Taylor 系数空间上的显式有理矩阵：\((T_i)_{r,q}=\frac{(-1)^{r-q-1}}{r\,i^{r-q}}\)（当 \(q<r\)，其余为 \(0\)，呈严格下三角）。于是 \(f(T_1,\ldots,T_n)e_0=\pi_d(h_f)\ne0\)，即矩阵值本身非零。构造只涉及分子为 \(\pm1\)、分母为 \(r\,i^{r-q}\) 的分数，预计算幂表 \(i,i^2,\ldots\) 后，总比特成本为 \(O(nd^2B^2)\)。

## 可信度与备注
本文暂无形式化证明，按 OpenAI 官方声明，"未经形式化的结果可能有问题"，请以社区核验为准。它是本族三篇的枢纽：特征零、无除法情形由此单个打击点解决；正特征姊妹篇把迭代积分换成乘法位移以进入任意 \(\mathbb F_p\)；含逆门的有理公式姊妹篇则把它推广为多项式大小的打击列表，三者共享"字级数 + 紧凑表示 + 次数界 + 截断"的同一逻辑骨架。

{% endraw %}
