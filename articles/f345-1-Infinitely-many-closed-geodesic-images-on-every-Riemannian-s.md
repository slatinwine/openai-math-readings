---
layout: default
title: "Infinitely many closed geodesic images on every Riemannian sphere"
family: "345"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Infinitely many closed geodesic images on every Riemannian sphere

> 结果族 345：Infinitely many closed geodesics on Riemannian spheres and closed three-manifolds　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了闭测地线无穷性问题（closed-geodesic infinitude problem）的球面情形：任何 `@@M@@S^n@@`（`@@M@@n\ge2@@`）上的光滑黎曼度量都有无穷多条两两像不同的素闭测地线；结合 Perelman 几何化与 Rademacher–Taimanov 定理，任意闭三维流形上亦然。

## 问题背景

闭测地线（closed geodesic）是测地方程的周期解；"素"（prime）指轨迹只走一圈，"几何不同"指像（image）不同——迭代、反向、换起点都不算新像。Lyusternik–Fet（1951）保证任何闭黎曼流形至少有一条，但"无穷多条"难得多：Gromoll–Meyer 判据说，自由环路空间（free loop space）的 Betti 数无界即可推出无穷性，Vigué-Poirrier–Sullivan（1976）补足其拓扑条件，而球面的上同调只需一个生成元，判据恰好失效。二维球面由 Bangert、Franks、Hingston 解决；高维此前只有强 bumpy 度量（Rademacher）与 `@@M@@S^3@@` 上至少两条（Long–Duan）等部分结论。Klingenberg 专著中的证明被 Asselle–Mazzucchelli 指认有误，本文又指出 Charles（2019）证明的两处未证步骤，含退化度量的任意度量情形由此悬置至今。

## 主要结果

**主定理**：对每个 `@@M@@n\ge2@@` 与 `@@M@@S^n@@` 上任意光滑黎曼度量，存在无穷多条素闭测地线，其像两两不同。`@@M@@n=2@@` 为经典结论；`@@M@@n\ge3@@` 是新结果，不要求非退化（nondegenerate）或 bumpy，零平均指标（zero mean index）测地线亦在覆盖之列。

**推论一**：凡有到某 `@@M@@S^n@@`（`@@M@@n\ge2@@`）的有限光滑覆盖的闭流形（如实投影空间、球面空间形式 spherical space form），其上任意度量同样成立。

**推论二**：任何非空闭三维流形（可不定向）上任意度量亦然：基本群无穷时直接用 Rademacher–Taimanov 定理；有限时由 Perelman 椭圆化定理（elliptization）知 `@@M@@M\cong S^3/\Gamma@@`，得有限覆盖化为推论一。

## 证明思路

反证：设 `@@M@@n\ge3@@` 且素像只有有限条，则一切正能量临界环路都是有限条定向素轨迹的迭代。论证先建立与度数无关的一致填充，再排除中途消失的瞬态类，最后用倍增对称性在"首次激活"处导出矛盾，共四层。

第一层，局部控制（第 3 节）。在 Hilbert 环路空间 `@@M@@\Lambda=H^1(S^1,S^n)@@` 上建立能量的等变梯度流与多边形逼近；根类型归约把任意迭代的零化场归结为有限多个根类型，配合平均指标估计 `@@M@@|I_{i,m}-m\Delta_i|\le n@@`，得每个临界穿越的局部同调秩一致有界。所有同调映射由同一个等变流定义；有限条素像又填不满球面，赋值落入刺破的球面，故上积类 `@@M@@e=\ev_0^*[S^n]^*@@` 在每个反射穿越上为零。

第二层，一致填充（第 4–6 节），不用有限素假设：存在与度数无关的常数 `@@M@@D@@`，凡在平方根能量水平 `@@M@@a@@` 以下且在全环路空间零调的循环，已在 `@@M@@a+D@@` 以下零调。切割算子 `@@M@@D_T@@`（切下前缀、短弧闭合、帽积 Thom 类与 Goresky–Hingston 幂）把高度数压入固定带并省下长度，拼接算子 `@@M@@\mu@@`（环积 loop product 的链模型）恢复度数，过滤交换定理 `@@M@@\mu(D_Tx,y)\simeq\mu(D_Ty,x)@@` 使长度代价为绝对常数；Hingston–Rademacher 共振定理（resonance）联系度数与临界水平，并保证球幂经切割恰得环积单位 `@@M@@[M]@@` 作修正项。

第三层，瞬态类有界（第 8–9 节）。令 `@@M@@B_a@@` 为反射等变上同调（equivariant cohomology，相对常环路），`@@M@@T(a)@@` 统计水平 `@@M@@a@@` 处不来自全空间的类数。度数间隙中乘 `@@M@@w@@` 是同构，非零瞬态类会沿 `@@M@@w@@` 的幂传播成长串，与有限切割预算定理的线性 `@@M@@O(a)@@` 上界冲突，故 `@@M@@T(a)@@` 一致有界。

第四层，倍增与激活（第 10 节）。`@@M@@\mathbb F_2[U]@@` 模的自由–挠分解给出 `@@M@@T(2L)\ge T(L)@@`，等号迫使每个可见的奇阶"底部"类 `@@M@@\xi_{m,0}@@` 配独立"顶部"伙伴 `@@M@@\eta_{m,0}=e\xi_{m,0}@@`。`@@M@@T@@` 有界，取最大值的区间经倍增传到任意远；在那里选一个低切口不可见、高切口可见的奇数底部度数，取其首次激活：穿越正合列把 `@@M@@\xi_{m,0}@@` 的限制放入穿越群之像，而 `@@M@@e@@` 的上积在穿越上为零，故 `@@M@@\eta_{m,0}@@` 仍为零——可见而无伙伴，矛盾。素像必无穷。

## 可信度与备注

本文是结果族 345 的球面情形核心证明（本批仅含此一篇），两条推论在文中自足地由主定理导出。作者明确指认了 Klingenberg 与 Charles 旧证的疏漏，并把过滤切割–拼接、有限切割预算两个可复用组件单独成节，便于社区核验；但主结果尚无 Lean 形式化证明。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以同行评审与社区核验为准。

{% endraw %}
