---
layout: default
title: "Full support of the zero-temperature Sherrington–Kirkpatrick order parameter"
family: "281"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Full support of the zero-temperature Sherrington–Kirkpatrick order parameter

> 结果族 281：QAOA attains the SK optimum in the thermodynamic-first limit　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

自旋玻璃的最优解由一个"序参量"函数 `@@M@@\gamma@@` 编码，它像一份楼梯设计图：在哪些尺度上加台阶、加多高。此前已知最优楼梯的台阶有无穷多级，却不清楚中间会不会留空档。本文证明：最优楼梯在整段 `@@M@@[0,1)@@` 上处处缓缓升高——没有任何被跳过的空档。

**关键词卡片**

- 序参量（order parameter）：`@@M@@[0,1)@@` 上的非降函数 `@@M@@\gamma@@`，编码自旋间的重叠层级
- Parisi 泛函（Parisi functional）：对 `@@M@@\gamma@@` 取极小便得到基态能量
- 支撑（support）：`@@M@@\gamma@@` 真正增长的那些尺度，像楼梯真正被踩到的台阶
- 满支撑（full support）：支撑充满 `@@M@@[0,1)@@`，任何一段都不空
- 零温（zero temperature）：对应求基态的纯优化问题

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="35" y="34" font-size="14" fill="#000">被排除的形状：留有间隙</text>
  <line x1="40" y1="228" x2="350" y2="228" stroke="#000" stroke-width="1.2"/>
  <line x1="40" y1="228" x2="40" y2="105" stroke="#000" stroke-width="1.2"/>
  <path d="M45 218 H135 L155 160 H255 L275 118 H340" fill="none" stroke="#333" stroke-width="1.8"/>
  <line x1="155" y1="160" x2="255" y2="160" stroke="#c00" stroke-width="3" stroke-dasharray="6,4"/>
  <text x="163" y="148" font-size="12" fill="#c00">间隙：γ 不增长</text>
  <line x1="135" y1="224" x2="135" y2="232" stroke="#000" stroke-width="1.2"/>
  <line x1="255" y1="224" x2="255" y2="232" stroke="#000" stroke-width="1.2"/>
  <text x="131" y="248" font-size="12" fill="#000">a</text>
  <text x="251" y="248" font-size="12" fill="#000">b</text>
  <text x="18" y="100" font-size="12" fill="#000">γ(t)</text>
  <text x="340" y="248" font-size="12" fill="#000">t</text>
  <text x="383" y="34" font-size="14" fill="#000">定理：满支撑（无间隙）</text>
  <line x1="390" y1="228" x2="535" y2="228" stroke="#000" stroke-width="1.2"/>
  <line x1="390" y1="228" x2="390" y2="105" stroke="#000" stroke-width="1.2"/>
  <path d="M395 218 C 430 214 470 185 530 120" fill="none" stroke="#06c" stroke-width="1.8"/>
  <text x="370" y="100" font-size="12" fill="#000">γ(t)</text>
  <text x="506" y="248" font-size="12" fill="#000">t</text>
  <text x="408" y="160" font-size="12" fill="#06c">处处严格递增</text>
  <text x="78" y="266" font-size="13" fill="#000">最优 γ 的支撑充满 [0,1)：任何一段都不空，且 γ′(t) 恒正</text>
</svg>

</div>

公式卡（数字版定理）：最优 `@@M@@\gamma@@` 光滑（`@@M@@C^\infty@@`）、`@@M@@\gamma(0)=0@@`，且 `@@M@@\gamma'(t)>0@@` 对一切 `@@M@@0<t<1@@` 成立——是一条处处有正坡度的坡道，而非带平台的楼梯。

**为什么值得关心**

"没有间隙"正是同族 QAOA 论文构造古典出发点时依赖的关键性质，也是理解自旋玻璃层级结构的基石。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了零场纯 SK 模型零温 Parisi 泛函的每个可积极小化子 `@@M@@\gamma@@`，其 Stieltjes 测度的支撑在 `@@M@@[0,1)@@` 上是满的：低于 1 的任何重叠尺度处都没有间隙，且 `@@M@@\gamma@@` 光滑、导数严格为正——这正是族内 QAOA 论文所依赖的关键古典输入。

## 问题背景

自旋玻璃的 SK 模型中，基态能量极限由 Parisi 变分公式给出，其变元是编码"重叠（overlap）层级"的泛函序参量（order parameter）。Auffinger 与 Chen 建立了零温 Parisi 公式并证明极小值可达；Auffinger–Chen–Zeng 进一步证明零温极小化子的支撑点有无穷多个，但无穷多个支撑点并不排除支撑内部留有"间隙"（gap）。正温度方面，Zhou 与 Lopatto 近年相继证明了低温 SK 相的区间支撑。零温下的同一"满支撑"结论由 Chen（2026）得到；本文给出一条独立、无条件的证明，核心是一个显式的有理强制性恒等式，而非依赖正温度区间支撑经弱极限传递。

## 主要结果

设 `@@M@@\mathcal U@@` 为非负、非降、右连续且可积的函数 `@@M@@\gamma:[0,1)\to[0,\infty)@@`，其 Stieltjes 测度满足 `@@M@@\mu_\gamma([0,t])=\gamma(t)@@`。值函数 `@@M@@\Phi_\gamma@@` 是带终端条件 `@@M@@\Phi(1,x)=|x|@@` 的 Parisi 方程 `@@M@@\Phi_t=-\tfrac12(\Phi_{xx}+\gamma(t)\Phi_x^2)@@` 的解，也可写成布朗控制（Brownian control）的变分表示；要极小化的泛函是 `@@M@@\mathcal P(\gamma)=\Phi_\gamma(0,0)-\frac12\int_0^1t\gamma(t)\,\dd t@@`，零温 Parisi 公式给出 `@@M@@P_*=\lim_n\frac1n\E\max_\sigma H_n(\sigma)=\min_{\gamma\in\mathcal U}\mathcal P(\gamma)@@`（Auffinger–Chen）。主定理（Theorem 1.1，零温满支撑）：若 `@@M@@\gamma@@` 极小化 `@@M@@\mathcal P@@`，则 `@@M@@\supp\mu_\gamma=[0,1)@@`（相对拓扑），特别地对任意 `@@M@@0\le a<b<1@@` 有 `@@M@@\gamma(b)>\gamma(a)@@`；同时最优扩散 `@@M@@\dd X_t=\gamma(t)u_\gamma(t,X_t)\,\dd t+\dd B_t@@` 满足一致性恒等式 `@@M@@\E[u_\gamma(t,X_t)^2]=t@@`、`@@M@@\E[\Phi_{\gamma,xx}(t,X_t)^2]=1@@`。推论恢复 `@@M@@\gamma\in C^\infty([0,1))@@`、`@@M@@\gamma(0)=0@@`、`@@M@@\gamma'(t)>0@@`（`@@M@@0<t<1@@`），即 `@@M@@\mu_\gamma=\gamma'(t)\,\dd t@@` 具有处处严格正的光滑密度。后部推论进一步给出值的鞅表示 `@@M@@P_*=\E[U_1B_1]=\int_0^1\E a(t,X_t)\,\dd t@@` 与有限高斯系数逼近，并验证 El Alaoui–Montanari–Sellke 优化定理所需的严格递增假设，得到 `@@M@@C(\varepsilon)n^2@@` 次实数运算的近优算法。

## 证明思路

记 `@@M@@q(t)=\E u_\gamma(t,X_t)^2@@`。梯度鞅恒等式给出 `@@M@@q'(t)=\E\Phi_{\gamma,xx}(t,X_t)^2@@`；对极小化子做第一变分可知 `@@M@@G(s)=\int_s^1(q(t)-t)\,\dd t@@` 非负、且在 `@@M@@\mu_\gamma@@` 的支撑上为零，故在支撑点处 `@@M@@q(t)=t@@`、`@@M@@q'(t)\le1@@`。反设内部有间隙 `@@M@@(a,b)@@`，其上 `@@M@@\gamma\equiv c>0@@` 为常数，则端点接触条件给出 `@@M@@q(a)=a@@`、`@@M@@q(b)=b@@`、`@@M@@q'(a),q'(b)\le1@@`。若能证明 `@@M@@q'@@` 在 `@@M@@(a,b)@@` 上严格凸，则它位于端点连线之下、内部小于 1，积分便得 `@@M@@q(b)-q(a)<b-a@@`，与端点接触矛盾——排除间隙的全部希望就押在"`@@M@@q'''@@` 严格为正"上。直接求导得 `@@M@@q'''(t)=c^{-2}\E[z^2-12vw^2+6v^4]@@`（`@@M@@r=c\Phi_x@@`，`@@M@@v,w,z@@` 为 `@@M@@r@@` 的各阶空间导数），其中含负项、无法逐点控制，这是全文的主要障碍。论文的绕法分三步：先对光滑有限步系数，把 `@@M@@X_t@@` 的密度分解为 `@@M@@f=e^{c\Phi}g@@`，`@@M@@g@@` 在跳跃之间满足前向热方程；向后传播 `@@M@@r@@` 的形状不等式、向前传播得分 `@@M@@s=-\partial_x\log g@@` 的不等式并比较 `@@M@@s/r@@`。这些符号信息随后保证一个精确的有理多项式恒等式经一次空间分部积分后非负：构造一个散度型、期望为零的多项式修正 `@@M@@F_2@@`（系数为 `@@M@@\frac1{13}@@`、`@@M@@\frac{53}{24}@@` 等显式有理数），使曲率表达式减去它后分解为五个带正系数的显式平方多项式 `@@M@@P_0,\dots,P_4@@` 与非负余项，最终得到 `@@M@@\E[z^2-12vw^2+6v^4]\ge10^{-3}\,\E v^4@@`。接着只把这条积分不等式传递到一般可积系数（不要求辅助密度得分收敛），初始与端点间隙再分别用边界层论证排除。当 `@@M@@q(t)=t@@` 处处成立时，Hessian 的 Itô 恒等式把 `@@M@@\gamma@@` 表成连续导数矩的商，对多项式矩反复求导自举出光滑性；再用"在固定时刻附近把系数换成常数"的逼近，把强制性不等式传到极限，得 `@@M@@\gamma'(t)>0@@`。最后由值公式与 Euler 离散的有限高斯系数恒等式导出算法推论。

## 可信度与备注

本文暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。论文明确说明 Chen（2026, Theorem 1.3）已证明同一满支撑结论及光滑密度，本文的贡献在于独立、直接的路线：显式有理恒等式给出的是无条件的严格曲率下界，而非条件性的穿越论证，从而避开正温度区间支撑经测度弱极限传递的障碍。作为族 281 的古典支柱，它输出的满支撑、扩散一致性与系数公式正是 QAOA 论文构造的出发点，两篇互相扣合、缺一不可。

{% endraw %}
