---
layout: default
title: "Maximal Multipoint Seshadri Constants in Higher Dimensions"
family: "039"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Maximal Multipoint Seshadri Constants in Higher Dimensions

> 结果族 039：Nagata's conjecture and maximal Seshadri constants　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把"能量布料"换成 `@@M@@n@@` 维的能量块：总能量 `@@M@@L^n@@`，戳进 `@@M@@r@@` 个一般点后每点分到体积 `@@M@@L^n/r@@`，它的 `@@M@@n@@` 次方根就是 Seshadri 常数的天花板。本文证明：维数 `@@M@@\ge 3@@` 时，只要点数越过某个阈值，这个天花板就被精确达到——高维版的 Nagata–Biran–Szemberg 断言成立。

**关键词卡片**

- 多点 Seshadri 常数（multipoint Seshadri constant）：曲线经过点组时每单位重数至少要付的单价。
- 体积界（volume bound）：`@@M@@(L^n/r)^{1/n}@@`，由爆炸簇上自交数非负给出。
- jet 分离（jet separation）：截面像显微镜一样分辨指定阶消没信息的能力。
- 指数重塑（reshaping）：把截面指数集逐步改造成"针状标准形"的核心操作。
- 非常一般点（very general points）：位于可数个特殊闭集之外的点组。

**看个具体例子**

取 `@@M@@X=\mathbb P^3@@`、`@@M@@L=\mathcal O(2)@@`，则 `@@M@@L^3=8@@`；对 `@@M@@r=32@@` 个非常一般点：

`@@M@@D\varepsilon=\Big(\frac{L^3}{r}\Big)^{1/3}=\Big(\frac{8}{32}\Big)^{1/3}=\frac{1}{\sqrt[3]{4}}\approx 0.63 .@@`

这就是"每点分到体积 `@@M@@1/4@@`、取棱长"的均分图像在三维的落地：任何经过这 32 个点的曲线，交数与重数之比都不会更省。点数翻倍到 `@@M@@r=64@@`，份额缩成 `@@M@@8/64=1/8@@`，棱长 `@@M@@(1/8)^{1/3}=1/2@@`——均分规则随点数自动缩放。定理同时断言爆炸簇上对应的实除子类 nef 且最高自交为零。此前高维只有渐近最优的下界与有条件的结果，"每个足够大的点数都精确取等"一直悬而未决。

**为什么值得关心**

它把"点够多时正性取满"从平面、曲面推进到一切维数，为高维插值与正性理论立下精确标尺；至此这一谱系在复数域的所有维数上都已闭合。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
对 `@@M@@n\ge 3@@` 维光滑整复射影簇 `@@M@@X@@` 与丰富线丛 `@@M@@L@@`，本文证明存在阈值 `@@M@@r_0(X,L)@@`，使 `@@M@@r\ge r_0@@` 时 `@@M@@r@@` 个非常一般点处的普通多点 Seshadri 常数恰等于体积界 `@@M@@(L^n/r)^{1/n}@@`，确立高维的定性 Nagata–Biran–Szemberg 断言。

## 问题背景
普通多点 Seshadri 常数（ordinary multipoint Seshadri constant）`@@M@@\varepsilon(X,L;\mathbf p)=\inf_C L\cdot C/\sum_i \mathrm{mult}_{p_i}C@@` 度量丰富线丛在一组点处的局部正性，其万有上界是体积界 `@@M@@(L^n/r)^{1/n}@@`（在爆炸簇上考查 `@@M@@D_t^n=L^n-rt^n\ge 0@@` 即得）。定性 Nagata–Biran–Szemberg 问题——由 Roé–Ross 在任意维度明确表述——问 `@@M@@r@@` 充分大时等式是否总在非常一般点处成立。已有结果各有局限：Biran 的辛堆满稳定性是四维辛几何类比而非代数陈述；Küchle 给出渐近最优下界，但渐近最优并不蕴含最终等式；Biran–Roé–Ross 乘积不等式将簇上点数与射影空间点数相联系，仍是有条件的结果。曲面情形由本族姊妹篇解决，其最终测试是有限环面子群上的单射 jet 评估；本文把该平面几何机制改编为双变量多项式空间，改用满射的满维 jet 评估。

## 主要结果
主定理：设 `@@M@@X@@` 是 `@@M@@n\ge 3@@` 维光滑整复射影簇，`@@M@@L@@` 丰富，记 `@@M@@V=L^n@@`，则存在整数 `@@M@@r_0=r_0(X,L)@@`，使得对每个整数 `@@M@@r\ge r_0@@`，在非常一般点组处（可数个真 Zariski 闭子集之外）有 `@@M@@\varepsilon(X,L;\mathbf p)=(V/r)^{1/n}@@`；等价地，爆炸簇上的实除子类 `@@M@@\pi^*L-(V/r)^{1/n}\sum_i E_i@@` 是 nef 的且最高自交为零。注意这是对每个这样的点数的精确等式，而非归一化常数随 `@@M@@r@@` 增大时的极限收敛；阈值依赖固定的极化簇。

## 证明思路
出发点是 jet 与交数的联系：若 `@@M@@H^0(X,kL)@@` 在 `@@M@@r@@` 个点处分离直到 `@@M@@m@@` 阶的 jet，则 `@@M@@\varepsilon\ge m/k@@`。故目标变为：取 `@@M@@w=(V/r)^{1/n}@@`，对每个固定 `@@M@@0\lt\theta\lt w@@` 与所有充分大的 `@@M@@k@@`，分离直到 `@@M@@\lfloor k\theta\rfloor@@` 阶的 jet。

第一步用完全交旗（complete-intersection flag）构造指数集：取 `@@M@@D@@` 使 `@@M@@DL@@` 很丰富，一般截面给出旗 `@@M@@X\supset X_1\supset\cdots\supset C@@`，按字典序取截面芽的最小 Taylor 指数，得到集合 `@@M@@S_k\subset kP_0\cap\mathbb Z^n@@`，满足半群性质 `@@M@@S_k+S_l\subset S_{k+l}@@`，元素个数恰为 `@@M@@h^0(X,kL)@@`，且 `@@M@@P_0=\Delta(1/D,\ldots,1/D,D^{n-1}V)@@` 的体积为 `@@M@@V/n!@@`（与 Hilbert 多项式首项一致）。单项式空间的 jet 满射性可经加权退化 `@@M@@z_i=s^{\lambda_i}Z_i@@` 传回 `@@M@@X@@` 的截面。

第二步是重塑（reshaping）：把单纯形的任意两个截距 `@@M@@A,B@@` 替换为 `@@M@@w@@` 与 `@@M@@AB/w@@`（`@@M@@w@@` 充分小），该操作保持指数个数、半群性质以及"替换后 jet 满射蕴含替换前 jet 满射"的推理方向，其余坐标原样携带。迭代 `@@M@@n-1@@` 次后得到含于 `@@M@@P_*=\Delta(w,\ldots,w,rw)@@` 的集合 `@@M@@F_k@@`——一个前 `@@M@@n-1@@` 个截距均为 `@@M@@w@@` 的针形单纯形，体积仍为 `@@M@@V/n!@@`。这一步技术上要求替换参数满足 `@@M@@3w/\ell\lt 1/16@@`（`@@M@@\ell@@` 为原单纯形最小截距），故需 `@@M@@r@@` 足够大使 `@@M@@w@@` 足够小。

第三步是饱和与插值：体积不变意味着 `@@M@@kP_*@@` 中只有 `@@M@@o(k^n)@@` 个格点缺失；半群性质把它升级为内部紧集上的满密度——内部一点约有多达 `@@M@@k^n@@` 种分解，而空洞只能排除其中 `@@M@@o(k^n)@@` 个。这是 Kaveh–Khovanskii 半群内部逼近定理的满密度版本。随后取 `@@M@@r@@` 个仅最后一坐标不同的点，对其余坐标的单项式系数做一元 Hermite 插值，即得直到 `@@M@@\lfloor k\theta\rfloor@@` 阶的任意 jet。

最后组装：满射性是 Zariski 开条件，Baire 纲论证给出使全部测试同时成立的非常一般点组；令 `@@M@@\theta\uparrow w@@` 得下界 `@@M@@\varepsilon\ge w@@`，与体积上界合并即得定理。从 jet 到曲线交数的一步用 Hilbert–Samuel 重数的一维局部论证：满射 jet 直到 `@@M@@m@@` 阶蕴含 `@@M@@A\cdot C\ge m\sum_i\mathrm{mult}_{p_i}C@@`，对曲线奇点处同样有效。

## 可信度与备注
本文暂无形式化证明，请以社区核验为准。姊妹篇的平面与曲面结论均已 Lean 形式化；本文自包含地重证了所需的传递与计数断言，曲面极大性定理并非其输入，但共享同一套几何机制。按 OpenAI 官方声明，未经形式化的结果可能有问题，本文结论宜以同行核验为最终确认。

{% endraw %}
