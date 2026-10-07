---
layout: default
title: "Quantitative Superexponential Bounds for van der Waerden Numbers"
family: "160"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Quantitative Superexponential Bounds for van der Waerden Numbers

> 结果族 160：Superexponential van der Waerden numbers　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明对一切 \(k\ge K_0\)、\(r\ge2\) 有 \(W_r(k)>k^{ck\lfloor\log_2 r\rfloor}\)（\(c\) 绝对），故 \(W_r(k)^{1/k}\to\infty\)，定量解决Erdős超指数增长问题，含两色。

## 问题背景

van der Waerden 定理（1927）断言：把区间 \([N]=\{1,\dots,N\}\) 任意染成 \(r\) 种颜色，只要 \(N\) 足够大，就必然出现单项颜色（monochromatic）的 \(k\) 项等差数列；满足此性质的最小长度记作 van der Waerden 数 \(W_r(k)\)。下界问题反过来问：不出现单色 \(k\) 项等差数列的染色，最长能维持多大的区间？Erdős 在 1980 年明确提问：两色时 \(W_2(k)^{1/k}\) 是否趋于无穷，即增长是否超指数（superexponential）。此前的最好结果——Berlekamp 的代数构造 \(W_2(p+1)>p2^p\)、Szabó 的 \(W_2(k)\ge 2^k/k^\varepsilon\)、Kozik–Shabanov 的 \(W_r(k)\ge\beta r^{k-1}\)，以及 2026 年 Campos–Fox–Schildkraut 的 \(W_2(k)\ge(1-o(1))k2^{k-1}\)——都停留在指数量级；最后一项虽推出 \(W_2(k)/2^k\to\infty\)，却给不出完整的超指数极限。卡点在于：经典概率方法（如局部引理的常规用法）天然只产生指数级下界，突破必须依靠结构完全不同的构造加稀疏随机扰动。

## 主要结果

主定理（引言中 Theorem，标签 main:intro）：存在绝对整数 \(K_0\)，使得对每个整数 \(k\ge K_0\) 与每个整数 \(r\ge2\)，
\[W_r(k)>k^{ck\lfloor\log_2 r\rfloor},\qquad c=10^{-5}.\]
特别地，固定任一 \(r\ge2\) 都有 \(\lim_{k\to\infty}W_r(k)^{1/k}=\infty\)；且阈值 \(K_0\) 不依赖 \(r\)，界对一切颜色数一致成立，这严格强于"\(W_2(k)/2^k\to\infty\)"。另一极端（定理 transfer:large-r）：对一切 \(r\ge256\)、\(k\ge3\)，\(W_r(k)>\exp\bigl((\log r)^2/(64\log 2)\bigr)\)，即固定公项长度时 \(W_r(k)\) 随颜色数超多项式（superpolynomial）增长；与伴侣论文的拟多项式（quasipolynomial）上界配合，固定 \(k\ge3\)、\(r\to\infty\) 时增长被夹在超多项式与拟多项式之间。

## 证明思路

第一步在循环群上构造。取大于 \(k\) 的素数 \(P\)（由中心二项式系数的初等论证给出，\(k<P\le2k^2\)），令 \(q\) 为 \(P\) 的、至少 \(k^{ck/D}\) 的最小方幂，维数 \(D=\lceil k^{1/10}\rceil\)，则 \(N=q^D\ge k^{ck}\)，目标是造 \(\mathbb{Z}/N\mathbb{Z}\) 上无单色 \(k\) 项数列的二染色。第 7 节的"数字乘积"命题再把循环染色搬回整数区间：把 \(n\) 写成 \(N\) 进制，用各数位颜色组成的向量作新颜色；若出现单色等差数列，取整除公差的最大幂 \(N^i\)，第 \(i\) 位数字恰构成非零步长的循环单色数列，矛盾。于是 \(W_{2^m}(k)>N^m\)，取 \(m=\lfloor\log_2 r\rfloor\) 即覆盖一切 \(r\ge2\)。

第二步搭几何骨架（第 2 节）。用同态 \(x_i(n)=n/q^i\bmod 1\) 与 \(y_i(n)=\lambda x_i(n)\)（\(1\le i\le D\)）给出两套圆环坐标，其中伸缩 \(\lambda\) 吸收了每个周期 \(h\le 2M=2\lceil k^{1/2}\rceil\) 在小素数处的全部素幂分量；于是任何约化分母要么是 \(1\)、要么超过 \(h_0=D^2\)，短周期与长周期被干净分离。\(y\) 坐标圆被切成在切割点 \(1/2\) 附近指数式加密的自适应网格，群元素按坐标所在的区间盒获得标签（label）；对标签随机赋色，用论文自证的有限非对称局部引理（asymmetric local lemma）挑出平衡外层染色 \(c_*\)：轻位置足够多的数列与合格模式中，两色各占至少四分之一。

第三步证明二分法（第 5 节）：任一循环 \(k\) 项数列要么两色各出现至少 \(\gamma k\) 次，要么其全部居中 \(y\) 坐标可整体提升为实仿射（affine）序列 \(\tilde y(n_j)=A+jB\)。枢轴是出现超过 \(k/M\) 次的"重标签"：最近回访给出有理周期 \(h\le2M\) 与微小漂移，而宽度不足 \(1\) 的盒内三点强迫仿射；当 \(h\le h_0\) 时 \(h\mid\lambda\)，步长落在格 \(q^{-i}\mathbb{Z}\) 上，与网格宽度比较后要么各标签互异（与重标签矛盾）、要么整体仿射；当 \(h>h_0\) 时按周期 \(h\) 分块，每块都是外层平衡的合格模式，两色各占至少 \(h/8\)，累计仍得 \(\gamma k\) 次。

第四步用稀疏扰动（第 6 节）消灭残余情形。给每个"键"（\(y\) 坐标盒连同范数带 \(\lfloor\|q\tilde y(n)\|_2^2\rfloor\)）挂独立的 Bernoulli(\(p=k^{-1/20}\)) 翻转，最终颜色 \(C(n)=c_0(n)+E_{\kappa(n)}\bmod 2\)。沿任一数列，同一盒内的点共线且两两距离至少 \(1\)，而范数带与每条半直线至多交出长度 \(1\)（Behrend 式几何），故每键出现至多 \(4\) 次。于是平衡数列变单色需 \(\gamma k/4\) 个键同时翻转，概率 \(p^{\gamma k/4}\)，对至多 \(q^{2D}\) 条数列取并界，指数系数 \(2c-\gamma/80<0\)，故为 \(o(1)\)；仿射数列则按"签名"计数：平方范数是 \(j\) 的二次式，与不超过 \(Dq^2/4\) 的整数比较构成三维超平面安排（hyperplane arrangement），签名总数对数 \(O(k^{9/10}\log k)=o(pk)\)，相同签名规定同一事件，并界亦为 \(o(1)\)。两概率之和小于 \(1\)，故存在翻转选择使一切单色数列消失。第 3 节的全局与锚定模式计数（如 \((CDh)^{6D}\)）为平衡性提供定量输入，技术性较强，此处从略。

## 可信度与备注

本批任务元数据标注该主结果已有 Lean 形式化证明；论文自含全部所需工具，包括局部引理的完整证明与初等上界附录。组合计数细节集中于第 3 节，本解读未逐条复述。本批次中该结果族仅此一篇手稿；其引用的伴侣论文给出固定 \(k\) 时关于 \(r\) 的拟多项式上界，与本文下界共同夹出该方向的成长阶。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本篇主结果已形式化，可信度较高。

{% endraw %}
