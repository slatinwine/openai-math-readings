---
layout: default
title: "A strict four-row permanent inequality and permutation moments"
family: "238"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A strict four-row permanent inequality and permutation moments

> 结果族 238：Optimal logarithmic mixing of the Thorp shuffle　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明 \(S_4\) 上近均匀且坐标边际恰均匀的置换律满足指数严格小于 2 的 permanent（积和式）不等式，并用它驱动四行矩递归，证明固定次数坐标扫掠使 \(N=2^d\) 张牌的 Thorp 洗牌整置换趋于均匀，混合时间达最优阶 \(O(\log N)\)。

## 问题背景

permanent 不等式研究 \(\mathbb E\prod_i f_i(\pi(i))\) 型泛函的范数控制：Carlen–Lieb–Loss 在 2006 年证明了均匀律下指数 2 的界并刻画等号情形（全部函数为常数）；Bristiel–Caputo 在 2024 年对均匀律得到对所有 \(p\ge p_c=4\log4/\log24\) 的尖锐界。但 Thorp 洗牌递归中出现的置换律只是接近均匀，恰恰需要"对保持坐标边际的小扰动稳定"的严格低于 2 的指数形式，这在此前文献中并不存在。洗牌方面，\(N=2^d\) 张牌的 Thorp 洗牌的混合时间此前最好上界是 Morris 的 \(O(d^3)\) 物理洗牌（更早有 \(O(d^{44})\)、\(O(d^{29})\)、\(O((\log N)^4)\)），支撑计数给下界 \(2d-O(1)\)。本文把两条线索接通：用四行分解把洗牌矩递归化为 permanent 不等式的反复使用。

## 主要结果

定理一（鲁棒四行不等式）：存在绝对常数 \(p_0\in(4/3,2)\) 与 \(\varepsilon>0\)，使得凡 \(S_4\) 上概率测度 \(\nu\) 满足 \(\|\nu-u\|_{\TV}<\varepsilon\) 且每个坐标边际恰为 \(1/4\)，则对四个非负函数恒有 \(\mathbb E_\nu\prod_{i=1}^4 f_i(\pi(i))\le\prod_{i=1}^4\|f_i\|_{p_0}\)。边际假设不可去：令三个函数恒为一、第四个在常数附近变动，即可由不等式反推其边际必须均匀。定理二（带度数节省的固定矩）：存在与 \(N\) 无关的偶数 \(r\ge2\) 与 \(\eta>0\)，对每个二进 \(N\) 与 \(\lambda\vdash N\)，\(D_\lambda\Tr B_N(\lambda)^r\le D_\lambda^{1-\eta}\)，其中 \(B_N(\lambda)=T_N(\lambda)T_N(\lambda)^*\) 是扫掠平均算子与其伴的乘积；从而存在绝对整数 \(q\)，使 \(q\) 次前向扫掠与均匀律的全变差（total variation）距离对初始牌序一致趋于零。配合支撑估计 \(t\ge\lceil(2/N)\log_2(3N!/4)\rceil=2d-O(1)\)，混合时间为最优阶 \(\Theta(\log N)\)。

## 证明思路

permanent 部分是"局部加紧性"论证。先按齐次性归一化 \(\|f_i\|_2=1\)，函数组空间紧。近常值区写 \(f_i=1+g_i\)，\(g_i\) 零均值；均匀无放回采样给出交叉矩 \(\mathbb E_u g_i(\pi(i))g_j(\pi(j))=-\frac13\langle g_i,g_j\rangle\)，故全部二次项之和不超过 \(V/6\)，其中 \(V=\sum_i\|g_i\|_2^2\)；测度扰动至多改变 \(O(\varepsilon V)\)，线性项因坐标边际恰均匀而为零，三、四次项由 \(O(bV)\) 控制（\(b=\max_i\|g_i\|_\infty\)）。右端做 Taylor 展开：\(\prod_i\|1+g_i\|_p=1+\frac{p-1}2V+O(bV)\)。严格间隙 \((p-1)/2>1/6\) 正解释了端点 \(4/3\) 的出现；取 \(b\) 与 \(\varepsilon\) 充分小即在此区得证。远离常值的区域上，指数 2 的 Carlen–Lieb–Loss 不等式有正的最小间隙，再用紧性与对 \(p\)、\(\nu\) 的连续性覆盖全空间。随后对 \(b\) 个独立置换做张量化（tensorization，逐坐标归纳）。洗牌应用走四行递归：去掉两个坐标方向后剩一个 \(4\times(N/4)\) 阵列，四个行内是独立的小扫掠，最后两个方向在列内作用；用 Araki–Lieb–Thirring 正迹比较把扫掠矩化为四个较小矩乘以限制重数（multiplicity）的平方幂，幂指数 \(\theta=1-1/p_0\) 严格小于 \(1/2\)——这一严格改进正是维数比较得以成功的全部余量。重数通过去掉杨图（Young diagram）前几行与前几列来控制，水平与垂直 Pieri 规则控制被移除的条带；并由 Berele–Regev 的正 hook-Schur 特殊化证明：对每个固定宽度 \(h\)，四个子图在前 \(h\) 行列之外的格子总数不超过父图。接近一行或一列的稀疏图停止递归；树求和把所有尺度上的成本（含停止的子结点）与钩长公式（hook-length formula）比较，\(\theta<1/2\) 恰好吸收这些成本。最后按 Diaconis–Shahshahani 的有限群 Fourier 方法把矩放大为混合，因扫掠算子非正规而保留矩阵范数。

## 可信度与备注

本篇主结果暂无形式化证明，请以社区核验为准。它是结果族 238 的第三条独立路线：姊妹篇《Conditional coordinate sweeps and analytic transfer》的主结果已 Lean 形式化，《Signed tensor densities and diagram budgets for the Thorp shuffle》给出带号张量熵预算路线，三者结论一致、互相支撑。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文的 permanent 不等式与递归求和技术性较强，尤宜对照原文逐节核对。

{% endraw %}
