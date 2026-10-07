---
layout: default
title: "A Gepner stability condition on every smooth quintic threefold"
family: "055"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Gepner stability condition on every smooth quintic threefold

> 结果族 055：Gepner symmetry and large-volume stability on threefolds　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
在每个光滑复五次三维超曲面（quintic threefold）上，作者构造出数值 Bridgeland 稳定性条件，使"张以超平面丛、再作结构层的球面扭转"这一自等价恰好把中心荷旋转 `@@M@@2\pi/5@@`、把半稳定相位平移 `@@M@@2/5@@`，从而证明了 Toda 的归一化五次 Gepner 猜想。

## 问题背景
Bridgeland 稳定性条件（Bridgeland stability condition）源自物理学家 Douglas 的 `@@M@@\Pi@@`-稳定性：用复值中心荷（central charge）配上相位切片（slicing），把导出范畴的对象排成有穷的半稳定 filtration。弦论里的 Gepner 点是模空间中对称性最高的特殊点，人们期望在那里存在与某个特殊自等价相容的稳定性条件：该函子应把中心荷旋转固定角度、把每个半稳定对象的相位平移固定量。对五次超曲面 `@@M@@X\subset\mathbb P^4_{\C}@@`，这个自等价是 `@@M@@\Phi=T_{\mathcal O_X}\circ(-\otimes\mathcal O_X(1))@@`，即先张以超平面线丛、再作结构层的球面扭转（spherical twist）。Toda 于 2013 年给出归一化五次表述，并指出真正的绊脚石：候选中心荷系数非有理，数值格在其下的像不离散，Harder–Narasimhan 滤波的存在性不能按老路得到。Li（2019）已证明五次超曲面上存在数值稳定性条件，但不含 Gepner 对称。

## 主要结果
主定理断言：每个光滑复五次三维超曲面都容许数值 Bridgeland 稳定性条件 `@@M@@\sigma=(Z,\mathcal P)@@`，它在整个数值 Grothendieck 群（numerical Grothendieck group）的实化 `@@M@@\Knum(X)_\R@@` 上满足支撑性质（support property），且对所有对象 `@@M@@E@@` 与相位 `@@M@@\varphi@@` 有
`@@M@@DZ(\Phi E)=e^{2\pi i/5}Z(E),\qquad \Phi(\mathcal P(\varphi))=\mathcal P(\varphi+2/5),\qquad Z(\mathcal O_x)=-1,@@`
其中 `@@M@@x@@` 为任意闭点。中心荷是唯一的：作者证明在 `@@M@@Z(\mathcal O_x)=-1@@` 的归一化下，满足特征方程 `@@M@@Z\circ\Phi=\lambda Z@@`（`@@M@@\lambda=e^{2\pi i/5}@@`）的数值同态唯一，并给出显式公式；其虚部恰为 `@@M@@\Im Z/(5t_0)=d+\tfrac12 c+ur@@`，其中 `@@M@@t_0=\tfrac12\cot(\pi/5)@@`，`@@M@@u=(5-\sqrt5)/10@@`，`@@M@@(r,c,d,e)@@` 是归一化陈特征坐标。自等价的周期关系 `@@M@@\Phi^5\simeq[2]@@` 是已知事实（Orlov 等价、Ballard–Favero–Katzarkov 的移位相容性），文中附录另给了一个直接证明。

## 证明思路
证明分四步，核心策略是：给 Toda 的第二刀保留两个独立的扰动参数，从而在定义半稳定对象之前就拿到支撑估计。

先做数值准备：用积分形式的弱 Lefschetz 定理与 Hirzebruch–Riemann–Roch（`@@M@@\mathrm{td}(X)=1+\tfrac56H^2@@`），把 `@@M@@\Knum(X)@@` 等同于秩四格 `@@M@@\Z\times\Z\times\tfrac1{10}\Z\times\tfrac1{30}\Z@@`；`@@M@@\Phi@@` 的诱导矩阵 `@@M@@M@@` 的特征多项式为 `@@M@@z^4+z^3+z^2+z+1@@`，特征值恰是四个非平凡五次单位根，据此解出唯一的归一化特征荷，并得到坐标估计 `@@M@@\|v\|\le C_0(|r|+|c|+|Z(v)|)@@`——控制住秩、`@@M@@c_1@@` 与荷即可控制整个数值类。

再构造通道（aisle，有界 t-结构的非正部分）：从 `@@M@@\Coh(X)@@` 出发两次倾斜（tilt）——先在斜率 `@@M@@-1/2@@` 处切一刀（张以 `@@M@@\mathcal O_X(1)@@` 后割线移到 `@@M@@+1/2@@`），再按 `@@M@@N_b^\eta=d-bc+ur+\eta_1c+\eta_0r@@` 切第二刀，`@@M@@\eta=0@@` 时正是 Toda 候选荷的虚部。斜率输入取自 Xu 的更强 Bogomolov–Gieseker 不等式，它给出包络函数 `@@M@@f@@`，提供严格余量，使比较在扰动下存活；由此得到两个参数在同一方格内独立变动的包含关系 `@@M@@\Phi U_\eta\subset U_\theta@@`：张丛一步实现参数错切，球面扭转则把 `@@M@@U_+@@` 送回 `@@M@@U_-@@`。

再把粗网格加密：由 `@@M@@\Phi^5\simeq[2]@@` 得到间距为 `@@M@@1@@` 的粗网格，而 `@@M@@\Phi^3[-1]@@` 把 `@@M@@Z@@` 乘以 `@@M@@e^{i\pi/5}@@`，提示在中间插入一刀。关键包含 `@@M@@D_3^\alpha\subset D_0^\beta[1]@@` 用反证法：若不成立，取参数趋于零的对象序列，其数值类的极限向量 `@@M@@v@@` 同时满足四个半平面不等式，先被逼出 `@@M@@Z(v)=0@@`；再让 `@@M@@v@@` 落在一切扰动心中，正性又逼出 `@@M@@r=c=d=e=0@@`，矛盾。于是得到间距 `@@M@@1/5@@` 的嵌套网格 `@@M@@V_k@@`，块 `@@M@@\mathcal S_k=V_k\cap V_{k+1}^\perp@@` 的电荷全部落在张角 `@@M@@\pi/5@@` 的闭扇形里。决定性的一步：同一个块对象属于前一网格位置的所有扰动心，让 `@@M@@\eta_0,\eta_1@@` 独立变号即得 `@@M@@\varepsilon(|r|+|c|)\le\Im Z/(5t_0)\le|Z|/(5t_0)@@`——支撑估计就此到手。

最后细化成切片：支撑估计加上电荷的正投影，同时限制了子对象的数值类与任何细化的长度；格本身的离散性保证极大相位存在、过程必然终止——全程不需要荷像离散，正面绕开了 Toda 指出的困难。合并共享端点的相位得到完整切片，直接构造相位切割以证明各相位范畴对直和项封闭，再用正投影界住严格 filtration 的长度，验证局部有限性。

## 可信度与备注
本文主结果尚无 Lean 形式化证明，属同行评审前的预印本，请以社区核验为准。它与本族姊妹篇《Prescribed large-volume charges on threefolds with trivial canonical bundle》共享同一套双倾斜框架与 Bogomolov–Gieseker 型不等式输入：姊妹篇把该框架推向一般平凡典则丛三维流的大体积区域，本文则聚焦五次超曲面上 `@@M@@2/5@@` 相位对称这一精细目标。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
