---
layout: default
title: "QMA-hardness of continuum Coulomb energy with unit nuclear charges"
family: "275"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | QMA-hardness of continuum Coulomb energy with unit nuclear charges

> 结果族 275：QMA-hardness of continuum Coulomb energy　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

上一篇证明"分子能量难算"借用了指数大的核电荷当道具；这篇更狠：全用氢核（电荷恰为 1），分子能量依然 QMA 难。诀窍像"先摊煎饼再撒芝麻"——先设计一块均匀带电的板，把想要的性质全都配好，再用数学搬运把连续电荷换成一颗颗单位点电荷，误差全程可控。

**关键词卡片**

- clamped 核（clamped nuclei）：原子核固定不动，只算电子的账（玻恩–奥本海默式设定）。
- 超交换（superexchange）：电子绕道邻位产生的二阶有效耦合，Anderson 1959 年提出。
- 单态介导子（singlet mediator）：一对强束缚的辅助自旋，负责传递指定符号的耦合。
- IMS 局部化（IMS localization）：把能量按空间分块估计的数学工具。
- 输运（transport）：把一块电荷分布连续搬到目标分布的几何手法。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><rect x="40" y="80" width="170" height="110" fill="none" stroke="#333" stroke-width="2"/><circle cx="70" cy="105" r="2.5" fill="#999"/><circle cx="108" cy="105" r="2.5" fill="#999"/><circle cx="146" cy="105" r="2.5" fill="#999"/><circle cx="184" cy="105" r="2.5" fill="#999"/><circle cx="70" cy="135" r="2.5" fill="#999"/><circle cx="108" cy="135" r="2.5" fill="#999"/><circle cx="146" cy="135" r="2.5" fill="#999"/><circle cx="184" cy="135" r="2.5" fill="#999"/><circle cx="70" cy="165" r="2.5" fill="#999"/><circle cx="108" cy="165" r="2.5" fill="#999"/><circle cx="146" cy="165" r="2.5" fill="#999"/><circle cx="184" cy="165" r="2.5" fill="#999"/><text x="46" y="68" font-size="14" fill="#333">均匀电荷板（密度 ρ）</text><line x1="228" y1="135" x2="310" y2="135" stroke="#333" stroke-width="2.5"/><polygon points="310,135 298,129 298,141" fill="#333"/><text x="242" y="122" font-size="13" fill="#333">数学搬运</text><circle cx="380" cy="100" r="4" fill="#c0392b"/><circle cx="420" cy="100" r="4" fill="#c0392b"/><circle cx="460" cy="100" r="4" fill="#c0392b"/><circle cx="500" cy="100" r="4" fill="#c0392b"/><circle cx="380" cy="140" r="4" fill="#c0392b"/><circle cx="420" cy="140" r="4" fill="#c0392b"/><circle cx="460" cy="140" r="4" fill="#c0392b"/><circle cx="500" cy="140" r="4" fill="#c0392b"/><circle cx="380" cy="180" r="4" fill="#c0392b"/><circle cx="420" cy="180" r="4" fill="#c0392b"/><circle cx="460" cy="180" r="4" fill="#c0392b"/><circle cx="500" cy="180" r="4" fill="#c0392b"/><text x="352" y="68" font-size="14" fill="#333">单位点核阵列（每颗电荷 = 1）</text><text x="40" y="235" font-size="14" fill="#333">每节点质量恰 1/λ，取 λ = 8k³/ρ 后电荷回到 1</text><text x="40" y="260" font-size="14" fill="#333">误差两级：λ^(−2/3) 与 λ^(−4/3)；阈隙 b−a ≥ (7/16)λτ²γ &gt; 1</text></svg>

</div>

搬运用的是两点高斯求积：把宽板切成边长 h=1/k 的小立方体，每块放 8 个等质量节点，取 λ=8k³/ρ 让每颗恰好带单位电荷。最终阈隙 `@@M@@b-a\ge\tfrac{7}{16}\lambda\tau^2\gamma>1@@`，YES 与 NO 之间隔着清晰的鸿沟。

**为什么值得关心**

在最刚性的物理设定（只有氢核、无附加势场、无束缚假设）下难度依然成立，说明"难"不是道具造出来的假象；有限构造与姊妹篇同构，连续实现则完全独立，两条路线互为印证。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明：当所有原子核电荷均为 `@@M@@1@@`（氢核）、位置为互异有理数时，在全自旋费米连续空间上逼近电子基态能下确界 `@@M@@E_0@@` 仍是 QMA 难的。确定性多项式归约只输出多项式多个单位核、电子与有理阈值，阈隙至少 1，全程不借助轨道基、磁场或束缚假设——这是最刚性外场约定下的连续硬度结果。

## 问题背景

电子结构复杂性的既有结果各留缺口：有限模 `@@M@@N@@`-可表示性的 QMA 完全性（Liu–Christandl–Verstraete 2007）允许任意二体费米系数；Schuch–Verstraete（2009）的 Hubbard 硬度依赖局部磁场，其连续实现靠自由设计的标量与自旋相关势场；O'Gorman 等（2022）证明了给定有限轨道基下电子结构的 QMA 完全性，其附录 D 虽含单位正电荷构造，但轨道基仍是输入的一部分，限制了参与极小化的电子态。更本质的障碍是：投影能量只给连续下确界的变分上界，要把 NO 实例传递下去必须对所有被省略的连续态给出下界——作者们在文中强调这正是有限基工作遗留的无限维问题。正点核生成的外场比自由设计的势场受限得多，本文在此设定下解决该问题。

## 主要结果

定理 1（单位电荷库仑硬度）：对固定的 clamped 核（全部 `@@M@@Z_\alpha=1@@`、位置 `@@M@@R_\alpha\in\Q^3@@` 互异），电子哈密顿量

`@@M@@DH=-\frac12\sum_{i=1}^N\Delta_{x_i}-\sum_{i=1}^N\sum_{\alpha=1}^M\frac1{|x_i-R_\alpha|}+\sum_{i<j}\frac1{|x_i-x_j|}@@`

作用于 `@@M@@\mathcal H_N=\bigwedge^N(L^2(\R^3)\otimes\C^2)@@`，取 `@@M@@E_0=\inf\operatorname{spec}H@@`（由闭二次型定义的自伴算子，不假设下确界可达）。输入为核位置、一元电子数 `@@M@@N@@` 与有理阈值 `@@M@@a<b@@`（`@@M@@b-a\ge L^{-1}@@`），YES 为 `@@M@@E_0\le a@@`、NO 为 `@@M@@E_0\ge b@@`。该承诺问题在确定性经典多项式时间多一归约下 QMA 难，且归约输出多项式多个核与电子、多项式位长的有理坐标与阈值，阈隙至少 1。定理不主张属于 QMA，也不设电中性、严格束缚、基态存在性或谱隙假设。

## 证明思路

有限阶段与二进制电荷姊妹篇同构：从 Cubitt–Montanaro–Piddock 方晶格海森堡 QMA 完全源问题出发，经 Piddock–Montanaro 单态介导子（singlet mediator）把带符号交换全正化，并给出键长可独立调节的平面接触布局；每个格点配一个带双自旋的局域空间模，`@@M@@m@@` 电子时正占有惩罚偏爱每格点恰一个电子，虚双占据的超交换（superexchange，Anderson 1959）在二阶还原出规定的正交换。

连续实现走多项式尺度路线：取伸缩坐标 `@@M@@y=\lambda x@@`（`@@M@@\lambda@@` 为 `@@M@@n@@` 的固定幂），能量除以 `@@M@@\lambda^2@@` 后单位核耦合为 `@@M@@1/\lambda@@`。平面模由 `@@M@@f=(1-|r|^2)_+^{16}@@`、`@@M@@\phi=(-\Delta_r+1)^{-1}f@@`、`@@M@@W=-f/(2\phi)@@` 构造：`@@M@@-\Delta_r/2+W@@` 以 `@@M@@\varphi=\phi/\|\phi\|_2@@` 为基态、能量 `@@M@@-1/2@@` 且有固定隙；横向取频率 `@@M@@\omega=\sqrt{4\pi\rho}@@` 的高斯模 `@@M@@g@@`，得 `@@M@@\psi_i=\varphi(r-u_i)g(z)@@`、单粒子能量 `@@M@@e_*=-1/2+\omega/2@@`。与姊妹篇不同，此处直接库仑系数 `@@M@@v_{ij}=v(|u_i-u_j|)@@` 与同位 `@@M@@U=v(0)@@` 保留在主导阶：占有惩罚写成 `@@M@@\frac12\sum_{i,j}v_{ij}(n_i-1)(n_j-1)@@`，其核恰为单占自旋空间，而库仑强制性 `@@M@@(v_{ij})\ge cI@@`（经 Poisson 方程与 disjoint 试探丘证明）给出固定隙；井深微调 `@@M@@1+b_i/\lambda@@` 实现抵消单体项 `@@M@@-\sum_i s_in_i@@`。超交换的虚激发能恰为 `@@M@@U-v_{ij}@@`，故目标跳跃取 `@@M@@t_e^{\rm tar}=\tau\sqrt{K_e(U-v_{ij})}@@`；因跳跃轮廓 `@@M@@T(d)\asymp e^{-d}@@`，逐链二分求解标量方程 `@@M@@\lambda T(d)=\tau\sqrt{K_e(U-v(d))}@@` 即可标定全部距离，无需单调性假设。

合成分两步。先用非负连续电荷密度：在宽板 `@@M@@\Omega=[-H,H]^2\times[-S,S]@@`（`@@M@@H=\lceil\lambda^5\rceil@@`，`@@M@@S@@` 约 `@@M@@D=\log\lambda@@` 量级）上，常密度 `@@M@@\rho@@` 的库仑场既提供横向简谐约束 `@@M@@2\pi\rho z^2@@` 又充当正背景，叠加井势后总密度 `@@M@@\rho+\Delta V_\ell/(4\pi)@@` 保持在 `@@M@@[\rho/2,3\rho/2]@@` 内非负；IMS 局部化（Simon）在平面与竖向分别做张量分解，在整个单粒子补空间上建立固定隙。再把密度换成点核：Moser–Dacorogna 输运流把均匀密度送到目标密度，在边长 `@@M@@h=1/k@@` 的立方体上取三阶精确的两点 Gauss 张量积（每立方体 8 节点），由 `@@M@@\lambda=8k^3/\rho@@` 使每节点质量恰为 `@@M@@1/\lambda@@`，回到物理坐标即得单位电荷。误差分两级：任意 `@@M@@H^1@@` 态上的形式误差 `@@M@@\lambda^{-2/3}@@`（近节点用 Hardy 不等式），光滑模上的压缩误差 `@@M@@\lambda^{-4/3}@@`。最后多体比较：补空间固定隙加配方（square completion）使模外泄漏以混合块误差的平方进入，得 `@@M@@E_\Pi-p(n,D)\lambda^{-4/3}\le\inf\operatorname{Spec}\mathcal H\le E_\Pi@@`；压缩哈密顿量与有限模型 `@@M@@H_d@@` 之差仅 `@@M@@\lambda^{-0.1}@@`。输出阈值经仿射映射 `@@M@@\mathcal F@@` 给出，分离 `@@M@@b-a\ge\frac7{16}\lambda\tau^2\gamma>1@@`。实现章固定尺度选取次序（先 `@@M@@\rho@@`、再源尺度与 `@@M@@\tau@@`、最后 `@@M@@k=\lceil Cn^A\rceil@@`），热核积分、截断库仑核求积、流 ODE 的 Euler 步进（误差 `@@M@@O(a_0+\nu+\epsilon_v+a_1/\nu)@@`）与有理舍入均在多项式位复杂度内完成，输出 `@@M@@8|\Omega|h^{-3}@@` 个单位核。

## 可信度与备注

本篇与二进制电荷姊妹篇共享源问题与有限构造框架，但连续实现彼此独立（多项式尺度＋等质量求积 vs 指数大电荷＋指数精度认证），两文均声明不依赖对方定理；单位电荷结论直接蕴含更大输入类（二进制电荷）的硬度，两条路线互为印证。据任务元信息，本篇 formalized 标记为 false，主结果尚无 Lean 形式化证明；OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。

{% endraw %}
