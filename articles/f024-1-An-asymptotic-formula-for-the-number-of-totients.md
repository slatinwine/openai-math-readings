---
layout: default
title: "An asymptotic formula for the number of totients"
family: "024"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An asymptotic formula for the number of totients

> 结果族 024：An asymptotic formula for the number of totients　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文给出欧拉函数不同取值个数 \(V(x)\) 的显式渐近等价 \(V(x)\sim\frac{x}{\log x}G_mA(1;\theta)\)，系数是有限算术数据的一致极限；并证明 \(V(cx)/V(x)\to c\)，正面回答了 Erdős 与 Hall 1976 年提出的固定伸缩问题。

## 问题背景

欧拉函数（Euler's totient function）\(\varphi(n)\) 计数 \(1\) 到 \(n\) 中与 \(n\) 互素的整数个数，\(V(x)\) 统计 \(\varphi\) 在 \([1,x]\) 内取到的不同值的个数。计数取值比计数具有给定分解的整数更难：不同整数可以有相同的函数值，而这一差别在渐近公式层面是决定性的。Pillai 1929 年证明取值集密度为零，其后 Erdős、Erdős–Hall 与 Pomerance 逐步推进，Maier 与 Pomerance 1988 年定出主部 \(V(x)=\frac{x}{\log x}\exp\{(C_0+o(1))(\log_3x)^2\}\)，Ford 1998 年又将其精化为只差一个有界乘性因子的估计。卡点在于这个有界因子可能随相位（phase）振荡，上下界夹逼失效。Erdős 与 Hall 1976 年在文末问道：固定 \(c>1\)，是否 \(V(cx)/V(x)\to c\)？Ford 只证得 \(V(cx)-V(x)\asymp_cV(x)\)，极限比值多年悬而未决。

## 主要结果

记 \(\log_j\) 为 \(j\) 重迭代对数。设 \(a_j=\int_j^{j+1}\log t\,\mathrm dt\)，\(\rho\in(0,1)\) 为 \(\sum_{j\ge1}a_j\rho^j=1\) 的唯一根，\(\lambda=\log(1/\rho)\)，\(g_j\) 为更新序列（renewal sequence）\(g_j=\sum_{d\le j}a_dg_{j-d}\)。令 \(B=\log_2x\)，\(m=\lfloor(\log B-\log_2B)/\lambda\rfloor\)，相位 \(\theta\in[0,1)\) 为其小数部分，\(G_j=\frac{B^j}{j!\prod_{i\le j}g_i}\)；\(\frac{x}{\log x}G_m\) 正是 Ford 的计数尺度。

**主定理**：存在 \([0,1)\) 上正的有界函数 \(A(1;\cdot)\)，使得 \(V(x)\sim\frac{x}{\log x}G_mA(1;\theta)\)，且对每个固定实数 \(c>0\) 有 \(V(cx)/V(x)\to c\)。系数是有限算术公式 \(A_H(1;s)\) 当 \(H\to\infty\) 的一致极限，其定义不使用 \(V\)：固定相位 \(s\)，一个尾部见证（tail witness）\(\eta\) 是满足规定双对数带条件与大小界的一组素数 \(Q_h\)（\(P\le h<H\)）及整数 \(a\)，令 \(w(\eta)=a\prod_hQ_h\)；对每个取值 \(d\) 收集满足 \(\varphi(w(\eta))=d\) 的见证集合（固定 \(H\) 时整体有限），对一族独立指数随机变量的尾事件取并集概率，经容斥（inclusion–exclusion）化为绝对收敛的显式指数级数，再配上前因子 \(\rho^{H(H-1)/2}(\gamma/\alpha_s)^H\) 即得 \(A_H\)。

**伴随定理（最小原像）**：设 \(\ell(v)=\min\{n\ge1:\varphi(n)=v\}\)，\(N_k(x)\) 计数满足 \(v\le x\) 且 \(kx<\ell(v)\le(k+1)x\) 的取值个数，则 \(N_k(x)=\frac{x}{\log x}G_m(A(f_k;\theta)+o(1))\)，且二择一：若存在取值 \(d\) 使 \(\ell(d)>kd\)，则 \(N_k(x)\asymp_kV(x)\)；否则 \(N_k(x)\) 恒为零。\(k=1,2\) 属第一种情形；是否对一切 \(k\) 成立，等价于 \(\ell(d)/d\) 无界这一公开问题。

## 证明思路

证明分三步。先提取长素数前缀：把原像的素因子从大到小排列为 \(p_0\ge p_1\ge\cdots\)，Ford 的结构定理（定理 10、16）断言，几乎所有取值的每一个原像都使双对数坐标 \(u_i=\log_2p_i\) 落在中心为 \(b_i=\alpha h_i\rho^{-h_i}\) 的窄带内，且满足单纯形约束 \(\sum_{r>i}a_{r-i}u_r\le\xi_iu_i\)。在两处不同位置切刀 \(R=m-H\) 与 \(L=m-P\)（\(P=\lfloor\log\log H\rfloor\)）：长前缀 \(p_0,\ldots,p_R\) 交由连续体积计数，短尾 \(p_{R+1},\ldots,p_L\) 与余因子 \(a\) 保留精确的离散算术，固定 \(H\) 时尾部整体有界；极限次序为先 \(x\to\infty\)（\(H\) 固定）、再 \(H\to\infty\)。

再控制前缀碰撞：不同长前缀给出同一取值的有序配对总数必须可忽略。抵消公共前缀后得到移位素数乘积的恒等式，证明沿用 Maier–Pomerance 的分层移位素数比较法，并把 Ford 的比较引理改写到本文所需的一组假设之下：先对齐两侧 \(p_i-1\) 的最大素因子（素数带彼此分离保证对齐位置唯一），再由单纯形的严格松弛取得指数节省 \(\exp(-cB_y/h^4)\)，它足以吸收从残余因子中恢复元组数据的全部代价。随后一个初等的有限映射计数引理把"元组数"转换为"取值数"；并且典型取值的**所有**原像共享同一前缀，由此得到最小原像的乘法分解 \(\ell(v)=p_0\cdots p_R\ell(d)\)。

最后数最大素数并取体积极限：对 \(p_0\) 用素数定理，且 \(t=x\) 与 \(t=x/c\) 共用同一质量 \(M_1(x;H)\) 与同一 \(G_m\)，两式相减时未知质量直接消去，立刻得到 \(V(cx)/V(x)\to c\)——这一路完全不需要系数的连续性。再把前缀的倒数素数和换成"尾部见证所允许区域之并"的体积，交集体积是显式的单纯形体积，容斥后令 \(x\to\infty\)，恰收敛到 \(A_H\) 中的指数项与前因子；一致收敛则借助与 \(H\) 无关的比较量 \(V(x)\log x/(xG_m)\)（Ford 的双侧估计给出上下界）与"精确相位序列"论证。绕开难点的关键在于：不把尾部平均化，而是精确保留离散尾部，让相位依赖的算术系数从有限容差中显式浮现。

## 可信度与备注

本文暂无 Lean 形式化证明：发布包内 lean/docs/024.md 及比较器文件 TotientAsymptotic.lean 只给出主定理的陈述并留有 sorry，形式化是作为挑战命题而非已完成证明给出的，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。论文的结构性起点与尺度估计直接引用 Ford 2013 年修订版（定理 10、16 与双侧估计），而碰撞控制、体积极限与系数构造等关键新步骤均在文内自证。文中引用的同批姊妹结果（存在满足 \(\#\{n:\varphi(n)=v\}>v^{1-\varepsilon}\) 的极大纤维）研究单个纤维的大小，与本文的取值计数相互独立，并非本文证明的输入。

{% endraw %}
