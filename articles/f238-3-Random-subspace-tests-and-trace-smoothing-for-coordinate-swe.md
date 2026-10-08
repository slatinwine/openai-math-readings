---
layout: default
title: "Random-subspace tests and trace smoothing for coordinate sweeps"
family: "238"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Random-subspace tests and trace smoothing for coordinate sweeps

> 结果族 238：Optimal logarithmic mixing of the Thorp shuffle　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

检查一间大礼堂干不干净，与其逐个座位摸灰，不如称出"全部座位的总灰量"。这篇论文检查 Thorp 洗牌就用这个思路：不去逐个估计对称群数不清的"基本成分"，而是给全体成分的加权总收缩量记一笔"总账"，一步锁死整副牌的混合速度。

**关键词卡片**

- 正则表示（regular representation）：把所有置换一视同仁打包的大空间，每种基本成分按维数重复出现
- 迹平滑（trace smoothing）：不逐个数成分，而给"全体成分的加权总收缩"一个统一上界
- 随机子空间测试（random-subspace test）：在行、列两套坐标系里各随机撒一个低维复平面，用两平面几乎不相交来量化两套坐标有多"合不来"
- 三线插值（three-lines interpolation）：复分析的经典工具，把两个边界上的好估计缝成中间整段的好估计
- 全变差距离（total variation distance）：洗牌后的牌序分布与完全随机差多远的尺子

**看个具体例子**

主定理本身就是数字版的：存在绝对常数 `@@M@@P@@`，使一次扫掠的算子 `@@M@@Q_n@@` 满足 `@@M@@\operatorname{Tr}_{\rm reg}|Q_n|^P\le 1+n^{-10}@@`。于是扫 `@@M@@v@@` 次（`@@M@@2v\ge P@@`）后，无论从哪副牌开始，距离都被钉死：`@@M@@\|\mu_v-U\|_{\rm TV}\le\tfrac12n^{-5}@@`。代入 `@@M@@n=2^{10}=1024@@`，得数字版定理 `@@M@@\tfrac12\cdot2^{-50}\approx4.4\times10^{-16}@@`——比连掷 50 枚硬币全部同面还难。配上计数下界（1024 张牌至少约 `@@M@@2d=20@@` 次物理洗牌），得 `@@M@@t_{\rm mix}=\Theta(\log n)@@`，阶已最优。

**为什么值得关心**

"逐个控制表示"是谱方法的老瓶颈，这笔总账式估计绕开了它；显式的 `@@M@@n^{-5}@@` 误差也是同族结果里最干净的定量版。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明：对 `@@M@@n=2^d@@` 个位置的 Thorp 洗牌，**绝对常数次**坐标扫掠（即 `@@M@@O(d)@@` 次物理洗牌）就能把整副排列与均匀分布的全变差（total variation）距离压到 `@@M@@\tfrac12n^{-5}@@` 以内，且对任意初始牌序一致成立——混合时间达到最优阶 `@@M@@\Theta(\log n)@@`，匹配计数下界 `@@M@@2d-O(1)@@`。

## 问题背景

Thorp 洗牌（Thorp 1973 年研究 Faro 纸牌时提出）把 `@@M@@n=2^d@@` 张牌按二进制坐标逐位"配对交换或不动"。一次坐标扫掠（coordinate sweep）后每张牌各自均匀，但所有牌共用同一批随机开关，牌与牌之间留下强相关，因此难点在于**整副排列**的联合分布。历史上 Morris 用演化集（evolving sets）与变色龙过程得到 `@@M@@O(d^{44})@@`，Montenegro–Tetali 改进到 `@@M@@O(d^{29})@@`，Morris 的熵方法先后给出 `@@M@@O(\log^4 n)@@`（一般偶数牌数）与 `@@M@@O(d^3)@@`（二的幂次）；这些均为物理洗牌计数。谱方法的标准出路是控制对称群 `@@M@@S_n@@` 全部不可约表示上的 Fourier 矩阵，但逐个表示控制还不够——正则表示（regular representation）中每个不可约块带有 `@@M@@D_\lambda@@` 重副本，需要整体"迹平滑"式的聚合估计，这正是本文的切入点。

## 主要结果

主定理（正则迹平滑，regular-trace smoothing）：存在绝对常数 `@@M@@P\ge 2@@`，使得对每个二的幂次 `@@M@@n\ge 2@@`，
`@@M@@D\operatorname{Tr}_{\rm reg}|Q_n|^P=\sum_{\lambda\vdash n}D_\lambda\operatorname{Tr}_{V_\lambda}|Q_n(\lambda)|^P\ \le\ 1+n^{-10},@@`
其中 `@@M@@Q_n@@` 是一次扫掠的平均算子，`@@M@@|Q_n|=(Q_n^*Q_n)^{1/2}@@`，求和遍及 `@@M@@S_n@@` 的所有分割（partition）`@@M@@\lambda@@`。由此，任何满足 `@@M@@2v\ge P@@` 的整数 `@@M@@v@@` 次独立扫掠后，全变差距离至多 `@@M@@\tfrac12n^{-5}@@`，对每个确定性初始牌序一致成立。因一次扫掠恰为 `@@M@@d@@` 次物理洗牌，这给出 `@@M@@O(d)@@` 上界；而支集计数（`@@M@@t@@` 次物理洗牌至多产生 `@@M@@2^{tn/2}@@` 个排列）给出下界 `@@M@@2d-O(1)@@`，故阶最优。

## 证明思路

证明按表示维数 `@@M@@X=\log D_\lambda@@` 分三段处理。先处理极大维数段（`@@M@@X\ge A_1n@@`）：援引相伴论文《Routing densities and representation contraction for Thorp sweeps》的偏牌平滑（partial-deck smoothing）结论——正扫掠接反扫掠的某个固定幂在任意 `@@M@@l@@` 张牌的有序嵌入上的密度至多 `@@M@@e^{Cl}/(n)_l@@`，取 `@@M@@l=n@@` 即正则表示对角元估计，直接吸收该段。再处理第一行极长的"稀疏"段（`@@M@@1\le k=n-\lambda_1\le ne^{-M\sqrt{\log n}}@@`）：把扫掠按粗坐标线切成约 `@@M@@\sqrt{\log n}@@` 段，对每段的局部算子作极分解形变 `@@M@@Y(z)=W|Y|^{p_0z/2}@@`，在 `@@M@@\Re z=0@@` 用算子范数 `@@M@@\le 1@@`、在 `@@M@@\Re z=1@@` 用两种取向的密度界，经三线插值得到 `@@M@@q@@` 张牌放置空间上的 Schatten 矩估计；随后数"共线接触"——把牌的路径连成图，其最大度不超过 `@@M@@e^{C\sqrt{\log n}}@@`，用无放回抽样的一致包含概率把矩母函数压到 `@@M@@\exp((q^2/n)e^{C\sqrt{\log n}})@@`；最后由分枝法则（branching rule）算出重数 `@@M@@m_\lambda=\binom qkD_\beta\ge D_\lambda^{1/10}@@`，把放置空间的迹换回正则表示，该段总贡献 `@@M@@\le n^{-12}@@`。剩下的表示全落在窗口 `@@M@@ne^{-A_0\sqrt{\log n}}\le X\le A_1n@@` 内，用本文的核心几何步骤：把坐标对半 split 成 `@@M@@a\times b@@` 棋盘，行、列子群的 Fourier 投影交叠（记 `@@M@@E_R,E_F@@`）满足 `@@M@@D_\lambda\operatorname{Tr}(E_RE_F)\le D_RD_F\exp(X/(\log n)^{1/3})@@`。其证明用正交的行/列标签把交叠化为不变张量范数，再在偶/奇字母张量空间中各自独立地取酉不变随机 `@@M@@r@@` 维复子平面（`@@M@@r=\lfloor n^{1/100}\rfloor@@`）做测试：一面用 Weyl 维数公式证明随机平面测试保留了 `@@M@@\lambda@@` 同型分量的一份可控比例；另一面，通过双测试的向量几乎所有槽都落入一个维数仅 `@@M@@4r^2@@` 的偶子空间，压缩到两两正交的格点标签后，Perelomov 相干轨道分解加算术–几何均值给出指数级衰减 `@@M@@m^{-m}@@`，其 `@@M@@e^{-n}@@` 恰好抵消换序归一化的 `@@M@@e^{n}@@`。最后封闭归纳：`@@M@@Q_n=YZ@@` 按行、列分解，Araki–Lieb–Thirring 迹不等式把乘积的幂拆成两因子幂之积，谱分解后逐项套用交叠命题与归纳假设，指数只需乘 `@@M@@1+2(\log n)^{-1/4}@@`，沿逐次二分求积有界，得一致 `@@M@@P@@`。收尾用 Schatten–Hölder：`@@M@@\|Q_n^v-\Pi\|_{\rm HS}^2\le\operatorname{Tr}_{\rm reg,\perp}|Q_n|^{2v}\le n^{-10}@@`，再由 Cauchy–Schwarz 得 `@@M@@\|\mu_v-U_{S_n}\|_{\rm TV}\le\tfrac12n^{-5}@@`。

## 可信度与备注

本文暂无形式化证明；其极大维数段明确依赖相伴论文《Routing densities…》的偏牌密度定理，而同族另两篇（本文与《Row–column symmetry…》《Compatibility entropy…》）以不同技术路线证明同一 `@@M@@\Theta(d)@@` 混合结论，其中《Compatibility entropy…》主结果已有 Lean 形式化，可作独立交叉印证。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
