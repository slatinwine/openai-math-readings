---
layout: default
title: "Nearly minimal maxima and positive minima of Littlewood polynomials"
family: "076"
discipline: "Real and complex analysis"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Nearly minimal maxima and positive minima of Littlewood polynomials

> 结果族 076：Real ultraflat Littlewood polynomials and unbounded binary merit factors　·　学科：Real and complex analysis　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了存在系数全为 \(\pm1\) 的 Littlewood 多项式，在单位圆上每一点的模同时满足下界 \(\frac{1}{16}\sqrt N\) 与几乎最优的上界 \((1+\eta)\sqrt N\)——"最大模几乎取到 Parseval 下界"与"最小模有正的下界"这两个性质首次由同一组符号实现，且对一切足够大的长度 \(N\) 成立。

## 问题背景
Littlewood 多项式 \(P(z)=\sum_{k=0}^{N-1}\varepsilon_kz^k\)（\(\varepsilon_k\in\{-1,1\}\)）的平坦性问题是调和分析的经典课题，可追溯至 Erdős 1957 年的问题集与 Littlewood 1966 年的著作。Parseval 恒等式给出 \(\|P\|_\infty\ge\sqrt N\)，因此人们追问：能否让最大模任意接近 \(\sqrt N\)，同时最小模不塌缩到零？此前已知：Rudin–Shapiro 构造给出 \(\sqrt{2N}\) 的上界；Balister–Bollobás–Morris–Sahasrabudhe–Tiba（2020）证明模总在 \(\sqrt N\) 的两个固定正常数倍之间；Kahane（1980）用复单位模系数造出超平坦多项式，但实符号情形难得多。姊妹篇已证最大模可达 \((1+o(1))\sqrt N\)，但其构造的领头项在部分圆弧上取值很小，最小模可能为零——如何在不破坏几乎最优上界的前提下"垫高"这些塌缩区域，正是本文要解决的难关。

## 主要结果
**定理**：对每个 \(\eta>0\) 存在 \(N_0=N_0(\eta)\)，使得对每个整数 \(N\ge N_0\) 都有符号 \(\varepsilon_0,\ldots,\varepsilon_{N-1}\in\{-1,1\}\)，使
\[\frac1{16}\sqrt N\le\Bigl|\sum_{k=0}^{N-1}\varepsilon_kz^k\Bigr|\le(1+\eta)\sqrt N\qquad(|z|=1).\]
下界常数 \(\frac1{16}\) 与上界精度 \(\eta\) 无关；结论对同一个多项式在整圆上成立，包括 \(z=\pm1\) 两个实端点。

## 证明思路
证明分五个阶段。先在高维环面 \(\mathbb T^m\) 上构造实三角多项式 \(F\)：用递推 \(p_j=p_{j-1}+\frac{1-p_{j-1}^2}{2}\cos(2\pi y_j)\) 得到 \(|p|\le1\) 且平方平均趋近 1 的多项式，再用二次相位把每个 Fourier 系数摊到频率盒上，最终 \(\|F\|_\infty\le1\)、\(\|F\|_2\ge1-3\delta\)，且每个频率 \(a\) 的系数与其"宽度"\(w_a=|a\cdot v|\) 满足 \(|\widehat F(a)|/\sqrt{w_a}\le K_\delta\)，总宽度严格小于 1。接着用带符号区间装填引理（基于 Pippenger–Spencer 超图染色）在圆周上铺出互不相交的短弧。然后按公式 \(Y_{N,k}=\sum_h\chi_h(k/N)F\bigl(k\theta_h+\frac N2v(k/N-x_h^*)^2\bigr)\) 采样出松弛系数 \(Y_N\in[-1,1]^N\)；Poisson 求和与一致驻相公式表明 \(U_{Y_N}\) 一致逼近一组不相交的二次波 \(B_N\)，其模 \(B=|B_N|\) 与 \(N\) 无关，平方平均 \(\ge1-7\delta\)，而 \(B<\frac18\) 的"间隙"弧段总长度 \(\le10\delta\)。关键新增步骤是在这些间隙上构造修正项 \(R_N\)：振幅固定为 \(\frac12\)，相位为 \(N\) 倍固定的分段二次"领头相位"加上仿射微调；在过渡点处让修正波与原有波共享领头相位导数，仿射部分使完整相位值模 1 相等，再用宽度 \(w=N^{-3/4}\) 的缓升带开启振幅以避免相消，从而 \(|B_N+R_N|\) 全圆介于 \(\frac18-o(1)\) 与 \(K_\delta\) 之间。每个间隙的领头相位导数在中段线性扫过仅分配给它及其镜像的"导数槽" \(D_j\subset(1/4,3/4)\)，槽两两分离保证任一频率的驻相贡献至多来自一个间隙，于是 \(\sqrt N|\widehat R_N(k)|\le D\sqrt\delta\)；导数严格落在 \((0,1)\) 内部加上两次分部积分后边界项相消，使允许频率之外的 Fourier 系数总和为 \(O(N^{-1/4})\)。最后把修正后的系数除以 \(S_\delta=1+D\sqrt\delta\) 拉回 \([-1,1]^N\)，其相对缺陷 \(q_\delta\to0\)，用基于 Lovett–Meka 部分染色的取整引理舍入为符号，圆周一致误差 \(C\sqrt{q_\delta\log(80/q_\delta)}\) 随 \(\delta\to0\) 消失，两界分别收敛到 \(\frac18\) 与 \(1\)，取 \(\frac1{16}\) 与 \(1+\eta\) 即得定理。

## 可信度与备注
本文暂无形式化证明。它是结果族 076 的中间一环：上界部分复用并重写了姊妹篇"渐近极小最大值"的铺开、装填、采样与取整框架（该姊妹篇已有 Lean 形式化），下界修正是全新贡献；更晚的"超平坦"姊妹篇又反过来引用本文的装填与偏差两条引理，把下界从 \(\frac1{16}\) 推进到 \((1-\varepsilon)\)。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
