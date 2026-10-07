---
layout: default
title: "A power saving for intersective polynomial differences with an exponent depending only on the degree"
family: "182"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A power saving for intersective polynomial differences with an exponent depending only on the degree

> 结果族 182：Power savings for intersective polynomial differences and prime arguments　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了：对每个次数 \(k\ge2\) 存在指数 \(c_k>0\)，凡避开固定 \(k\) 次交集多项式 \(h\) 一切非零取值之差的集合都满足 \(|A|=O_h(N^{1-c_k})\)，且幂节省指数只依赖次数。这把一般多项式差集的上界首次从对数级、亚指数级推进到固定幂级。

## 问题背景

这类问题始于 1977–1978 年 Furstenberg（遍历方法）与 Sárközy（Fourier 方法）独立的平方差定理：正上密度的整数集必含两个元素，其差为非零平方。Kamae 与 Mendès France 随后把定性结论推广到"交集多项式"（intersective polynomial），即模每个正整数 \(q\) 都有根的整系数多项式；该局部条件也是回避集密度必趋于零的充要条件。定量方面，Lucier、Rice、Arala 相继给出对数型界，Green–Sawhney（2025）对平方差得到 \(N\exp(-c\sqrt{\log N})\)，Adajar 等（2026）对一般交集多项式得到 \(\exp(-c_{h,\mu}(\log N)^\mu)\)——固定幂 \(N^{1-c}\) 始终缺一格，本文补上。

## 主要结果

定理（Theorem 1.1）：对每个整数 \(k\ge2\) 存在常数 \(c_k\in(0,1)\)，使得对每个次数为 \(k\)、首项系数为正的交集多项式 \(h\in\Z[x]\)，存在 \(C_h\ge1\) 与 \(N_h\)：只要 \(N\ge N_h\) 且 \(A\subseteq[N]\) 满足 \((A-A)\cap h(\N_+)\subseteq\{0\}\)，就有 \(|A|\le C_hN^{1-c_k}\)。隐含常数可以依赖 \(h\) 的全部系数，但指数对同次多项式统一。注意"交集性"允许不同模数的根来自 \(h\) 的不同因式，不要求有理根；\(h\) 的零值不施加限制。

## 证明思路

证明沿用同族平方差论文的"反射正 tuple 律 + 符号泛函"框架；多项式带来两个新障碍：换到等差数列时多项式本身会变，且构造出的局部分布未必是多项式取值的自然分布。

先做归一化：取 \(g(x)=h(r+D_0x)/M\)（\(r+D_0m\ge1\)），使每个选定 \(p\)-进根处首个非零 Taylor 系数是单位（unit）；只需对有限个素数除以 \(M\)。这一步的目的是让决定最终指数的全部结构参数只依赖 \(k\)。

再造对进度封闭的辅助族（Lucier 型）：多项式 \(h_l\)（\(h_1=h\)）与完全乘法函数 \(\lambda\) 满足 \(h_l(Dx-i)=\lambda(D)h_{lD}(x)\)、\(D\mid\lambda(D)\)、\(\lambda(D)\le D^k\)。子集在等差数列坐标下的回避性沿族传递，且系数界、完全指数和估计、局部提升性质对 \(l\) 一致。

然后对每个大素数 \(p\)，在固定偶基数标签集 \(V\) 的 \(\F_p^V\) 上构造加权概率律：指定圈的增量取 \(h_l\) 在导数非零（正则）自变量处的值，边权为给出该增量的自变量个数；此律反射正（reflection positive）、边际一致、条件混合，并在进度恒等式下精确协变。提升（Fourier lift）保留 \(1_A\) 在小分母有理频率处的归一系数，积分得非负量 \(Y_l(N,A)\ge(|A|/N)^d\)。

核（kernel）一步把律"落地"到整数：构造支在 \(h_l\) 真实正值上的符号核，其 Fourier 变换逼近圈边的对乘子——大弧（major arcs）靠提升式的局部系数精确计算，小弧（minor arcs）靠初等 Weyl 差分（Weyl differencing）。关键洞察是只需支集：回避集上的双线性型逐项为零，核权符号无关紧要。这把"造有用的 tuple 律"与"在真实多项式值上实现其对分布"两个问题解耦。

最后是传递与归纳：固定正比例 \(\rho_l\ge\rho_*=M_0^{1-L}\) 的"好"剩余类指派给出相消，其余指派连同可和的例外质量（\(\sum q_B\eta_{l,B}\le1/4\)）用更短区间、族中更远的多项式控制，得收缩递归。取 \(a_0=\frac12\min\{\sigma,\,\frac1{k+2/\zeta},\,\frac{-\log(1-3\rho_*/4)}{(k+2/\zeta)\log M_0}\}\)、\(b_0=2a_0/\zeta\)，收缩因子 \(\theta=M_0^{s_0}(1-3\rho_*/4)<1\)，对一切 \(l\) 同时强归纳证明 \(Y_l(N)\le C_0l^{b_0}N^{-a_0}\)（\(l>N^\zeta\) 时用次幂界兜底）。对归一化的 \(g\)，\(a_0/d\) 只依赖 \(k\)；按模 \(M\) 剩余类拆分 \(A\)，用 \(Mg(m)=h(r+D_0m)\) 把界传回 \(h\)，得 \(c_k=a_0/d\)。

## 可信度与备注

本篇暂无形式化证明。它在结果族 182 中承上启下：同族平方差论文是其直接方法论前身（本文复用其 tuple 律与符号泛函，并补上多项式与换尺度论证），而素数参数篇又以本文为直接前身。三篇构成互相支撑的方法链。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
