---
layout: default
title: "Compatibility entropy and the spectrum of a Thorp sweep"
family: "238"
discipline: "Probability and statistical mechanics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Compatibility entropy and the spectrum of a Thorp sweep

> 结果族 238：Optimal logarithmic mixing of the Thorp shuffle　·　学科：Probability and statistical mechanics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文证明：\(n=2^d\) 张牌的 Thorp 洗牌（Thorp shuffle）在 \(\Theta(d)\)（即 \(\Theta(\log n)\)）次物理洗牌内完成整副排列的全变差（total variation）混合，匹配支集计数下界 \(2d-O(1)\)；更强地，它完全刻画了一次扫掠的奇异值谱：正则表示中第 \(j\) 个奇异值不超过 \(j^{-1/(2p_*)}\)。

## 问题背景

Thorp 1973 年研究 Faro 纸牌的非完美洗牌时提出该模型：位置编号为 \(\{0,1\}^d\)，一次坐标扫掠（coordinate sweep）依次访问各坐标方向，独立地以概率 \(1/2\) 交换该方向每条边上的两张牌，恰等于 \(d\) 次物理洗牌。一次扫掠用 \(nd/2\) 个随机比特，已足以让每张牌的边缘分布均匀，但与均匀排列的熵 \(\log_2(n!)\) 相比远远不够，\(t\) 次物理洗牌支集至多 \(2^{tn/2}\)，给出下界 \(2d-O(1)\)——单牌均匀与整副混合之间横亘着"共用开关"带来的强相关。全牌混合的前沿记录依次是 Morris 的 \(O(d^{44})\)、Montenegro–Tetali 的 \(O(d^{29})\)、Morris 熵收缩的 \(O(\log^4 n)\) 与 \(O(d^3)\)；Czumaj–Vöcking 的 \(O(\log^2 n)\) 只针对固定比例的牌。本文以"一次扫掠的整个奇异值谱"为对象给出 \(\Theta(d)\) 的最优答案。

## 主要结果

把坐标对半 split 成 \(A\times D\) 棋盘（\(AD=n\)，两边均近 \(\sqrt n\)），行、列子群 \(R,C\) 的元素对 \((r,c)\) 称为**相容**（compatible），如果"先行后列"复合也能写成"先列后行"——等价于每个原始列中的输出两两不同。第一主定理（加权相容性）：对任意非负权 \(w_i,v_k\)，在 \(\theta=1-L/\log m\) 下
\[\frac{n!}{|R||C|}\,\mathbb E_U\Big[\mathbf 1_{\mathcal I}\prod_iw_i(r_i)\prod_kv_k(c_k)\Big]\le e^{C_0n^{.54}}\prod_i(\mathbb E w_i^{1/\theta})^\theta\prod_k(\mathbb E v_k^{1/\theta})^\theta .\]
第二主定理（有界正则矩）：存在绝对 \(p_*\) 使每个二的幂次 \(n\) 均有 \(Z_n(p_*)=\operatorname{Tr}_{\rm reg}(T_n^*T_n)^{p_*}\le 1+\tfrac1{16}\)；从而任取整数 \(M\ge p_*\)，\(M\) 次独立扫掠后最坏起点全变差 \(\le 1/8\)。推论给出奇值秩界 \(s_r(T_{n,\lambda})\le(16D_\lambda r)^{-1/(2p_*)}\)、正则奇值列表 \(s_j(T_n)\le j^{-1/(2p_*)}\)，以及混合时间 \(\Theta(d)\)、下界 \(2d-O(1)\)；且对每个固定 \(M>p_*\)，\(Md\) 次物理洗牌后的误差随 \(d\to\infty\) 趋于零。

## 证明思路

首个完整证明分四步。先用"稀疏路径二阶矩"处理第一行极长的表示（\(1\le h=n-\lambda_1\le n^{.60}\)，此时 \(\|T_{n,\lambda}\|\le n^{-bh}\)）：在有序 \(h\) 元组表示上做容斥 \(F=\sum_I(-1)^{h-|I|}D_I\)，孤立牌的路径组消后归零，存活构形必含一棵相互作用森林；每条森林边的碰撞概率为 \(2l/n\)，而蝴蝶接触引理（\(s\) 条路径共享开关数 \(\le\tfrac s2\log_2s\)，文中亦给熵证明）钉死剩余密度因子，得 \(n^{-h/50}\) 级二阶矩。第二步是核心的相容熵不等式：在支集含于相容事件 \(\mathcal I\) 的任意联合律 \(Q\) 下，\(\mathcal D(Q\|U_{R\times C})\ge n-O(n^{.54})+(1-\tfrac L{\log m})\sum(\text{行、列边缘熵亏})\)。证明用随机顺序暴露：先亮出行数组，再按随机优先级逐列、逐位暴露列置换；轻的、未结块的表项因先前暴露的列已禁止取值而各付近一奈特（对 \(-\log(1-x+x\alpha)\) 积分加 Jensen），重原子与结块表项的损失计入相应边缘相对熵。第三步，经 Carlen–Cordero-Erausquin 的有限熵–Brascamp–Lieb 对偶把熵不等式变成上述加权乘积不等式，其 \(-n\) 主项恰与换序归一化 \(n!/|R||C|\approx e^n\) 对消。最后是谱转换：\(T_n=K_CK_R\)，Araki–Lieb–Thirring 型正幂比较把 \(\operatorname{Tr}(T_n^*T_n)^t\) 化为四个行、列因子的交替迹，代数引理（四因子迹恒等式加对合的 Cauchy–Schwarz）把它精确写成带权的相容概率，再由逆 Hausdorff–Young 不等式用子扫掠的矩 \(Z_A,Z_D\) 控制行、线权，得到递归 \(Z_n(t)\le\exp(O(n^{.54}))\)（\(t=p(1+L'/\log m)\)）。收尾时把表示分两类：小层由森林估计吸收（\(D_\lambda\le n^{2h}\)）；大维块 \(D_\lambda\ge e^{n^{.58}}\) 在正则表示中带 \(D_\lambda\) 重复副本，指数再升 \(\delta=1/\log m\) 即被乘性放大消灭；有限小尺寸用严格谱隙（立方体边对换生成整个 \(S_n\)）作基，指数增量沿二分递归求积有界，得一致 \(p_*\)。混合结论由矩–秩转换与 Schatten–Hölder 给出，全程不需算子正规性。第 4 节之后给出多种替代证明与细化（条件秩、反色可用性、倾斜数组、分数可积、非对称棋盘、水平递归、奇异带、逐点平滑等）。

## 可信度与备注

本篇主结果已有 Lean 形式化证明（见结果族 238 的 Lean 文档），是该数学事实目前最强的机器验证背书；同族另两篇（加权路线与随机子平面路线）以独立技术得到同一 \(\Theta(d)\) 结论，与本文的熵–对偶路线交叉印证，且本文的稀疏估计与姊妹篇《Routing densities》的确定性接触引理互相衔接。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇形式化部分除外，其余细化估计仍请以社区核验为准。

{% endraw %}
