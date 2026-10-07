---
layout: default
title: "Deterministic Polynomial Factorization over Prime Fields"
family: "142"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Deterministic Polynomial Factorization over Prime Fields

> 结果族 142：Deterministic polynomial factorization over prime fields　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文给出一致确定性算法，在 \((n+1)\log p\) 的多项式位复杂度内完全分解素域 \(\mathbf F_p\) 上任一 \(n\) 次多项式（含重数）；不使用随机数、整数分解或原根预言机，也不依赖 GRH，唯一的解析输入是姊妹篇的一致 Hecke \(L\) 函数零点自由定理。

## 问题背景

有限域多项式分解是计算代数的基本构造性问题。Berlekamp 于 1967 年把线性代数推到台前：商代数 \(\mathbf F_p[X]/h\) 中 Frobenius 不动元构成的线性空间编码了全部不可约因子；Cantor–Zassenhaus 类随机算法靠随机抽取分离元素达到期望多项式时间。确定性情形却卡了几十年：Shoup 的算法对特征有 \(p^{1/2+o(1)}\) 依赖；Rónyai 在 GRH 假设下处理因子个数有界的情形；Evdokimov 的一般确定性界 \((n^{\log n}\log p)^{O(1)}\) 对次数只是拟多项式。门槛在于：素数 \(p\) 以二进制给出，复杂度必须同时是 \(n\) 与 \(\log p\) 的多项式——对 \(p\) 本身多项式的算法不算数；而随机分离元素要有确定性的替身，往往需要额外的算术信息。本文正是把这份信息从解析数论中取来。

## 主要结果

主定理（Theorem 1.1）：存在一致确定性算法，输入二进制素数 \(p\) 与稠密系数表给出的非零多项式 \(f\in\mathbf F_p[x]\)（\(n=\deg f\)），输出首项系数 \(c\) 与全部互异首一不可约因子 \(g_i\) 及重数 \(e_i\)，使 \(f=c\prod_i g_i^{e_i}\)，位运算量为 \(O(((n+1)\lceil\log_2p\rceil)^{10^{12}})\)。指数刻意放宽，要点是对一切次数与特征有一致的多项式界；不使用随机性、整数分解预言机（oracle）、原根预言机，也不假设广义黎曼猜想（GRH）。结构上，论文先证归约定理（Theorem 1.2）：只要为每个素数 \(q\le n\) 配一个辅助素数 \(\ell\)——满足 \(\ell\equiv1\pmod{12q}\) 且 \(p^{(\ell-1)/q}\not\equiv1\pmod\ell\)，即 \(p\) 模 \(\ell\) 不是 \(q\) 次幂——且诸 \(\ell\) 的数值被 \(B\) 的固定幂控制（\(B=20+(n+1)(L+1)\)，\(L=\lceil\log_2p\rceil\)），代数部分便多项式时间完成；第 10 节再用姊妹篇的定理无条件造出这样的小辅助素数。

## 证明思路

整体是"先归约、再分裂、后补解析"三步走。

先归约：递归驱动器以 \(h=g^p\) 与 \(\gcd(h,h')\) 剥离 \(p\) 次幂与重数，Berlekamp 代数的维数 \(r\) 给出因子个数；若 \(r\ge2\)，取一组基 \(b_0,\dots,b_{r-1}\)，令 \(b(t)=\sum_j t^jb_j\)，使任两分量重合的坏参数少于 \(r^3\) 个，特征大时逐一试验 \(t\)，即得完全分裂且无平方的特征多项式 \(F_t\)——问题化归为分裂一个根全在域中却未知的 \(F\)。计算在积代数 \(A=k[T]/(F)\simeq\prod_i k\) 里同时执行（动态求值，dynamic evaluation）：零测试一旦在不同分量分叉，\(\gcd\) 立即产出真因子。

偶次 \(N\) 用 Rónyai 式锦标赛论证：由 \(\mathbf F_p^*\) 的 2-准素子群（2-primary subgroup）生成元给根的两两差定向，每个无序对恰选中一个方向；若各行得分全等，公共值必为 \((N-1)/2\)，偶数下不是整数——得分不同即得分裂。

奇次 \(N\) 是实质贡献。取奇素数 \(q\mid N\)，记 \(r=v_q(N)\)、\(m=1+(q-1)r\)，构造循环覆盖曲线 \(C:\ Y^q=F(X)\)（亏格 \((q-1)(N-2)/2\)）：其分歧点 \(P_i=(x_i,0)\) 恰对应未知根，另有 \(q\) 个无穷远点。令 \(\sigma(X,Y)=(X,\zeta_qY)\)、\(\lambda=1-\sigma\)。核心不对称在于：\(\lambda\) 在几何雅可比（Jacobian）\(J\) 上满射，在无穷远点格 \(\Lambda\simeq\mathbf Z[\xi]\) 上却单而不满。先把每个类 \([P_i-\infty_0]\) 连续作 \(\lambda\)-除法提升 \(m-1\) 次；一组滤过模 \(T_t\) 与 Frobenius 论证保证提升链全部有理于 \(q^r\) 次扩张 \(k\) 上，扩张次数始终多项式有界。再对诸提升求和得 \(d_m\)，满足 \(\lambda^m d_m=[Ne]\)。最后依次做标签测试 \(l_{i,t}=v_{P_i}(D_t)-\log_\zeta(h_t(P_i)/\gamma_t)\pmod q\)：若每次测试标签都全同，格元素 \(Ne\) 就能再多被 \(\lambda\) 整除一次，与 \(Ne\in\lambda^{m-1}\Lambda\setminus\lambda^m\Lambda\)（因 \(N=q^ra\)、\(q\nmid a\)）矛盾，故必有一次测试区分两个根。\(\lambda\)-除法的算法实现化为 \(k(C)/k(X)\) 的范数方程（norm equation）：在分裂循环代数中构造极大阶，以秩一幂等元经线性代数求解；Riemann–Roch 约化控制除子规模，大系数的无穷除子用加法–倍乘电路存储。

后补解析：辅助素数的界 \(\ell\le c_0B^{20000000}\) 出自姊妹篇的一致零点自由定理——固定宽度 \(\delta=10^{-6}\) 的无零点带给出平滑素理想估计，比较 \(K=\mathbb Q(\mu_{12q})\) 与 \(M=K(p^{1/q})\) 的素理想计数：若无辅助素数，相应一次素理想在 \(M\) 中完全分裂、两侧贡献恰好抵消，与主项矛盾。GRH 亦给出同样的带，故归约在 GRH 下独立成立，姊妹篇把这最后一步变成无条件。小特征 \(p\le B^{200000}\) 时直接枚举标量，代价仍是 \(B\) 的多项式。

## 可信度与备注

论文主结果暂无形式化证明，请以社区核验为准。文章把代数归约与解析输入严格隔离：全文仅第 10 节引用姊妹篇《Primitive roots for every admissible integer base》的零点自由定理，两篇需一并审读；即便搁置该定理，GRH 下的多项式界仍独立成立。注意 OpenAI 官方声明：未经形式化的结果可能有问题。指数 \(10^{12}\) 只求一致多项式，远非实用。

{% endraw %}
