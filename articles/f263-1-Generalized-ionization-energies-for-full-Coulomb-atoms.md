---
layout: default
title: "Generalized ionization energies for full Coulomb atoms"
family: "263"
discipline: "Mathematical physics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Generalized ionization energies for full Coulomb atoms

> 结果族 263：The ionization and generalized ionization conjectures　·　学科：Mathematical physics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文在完整库仑模型（双自旋、含任意关联态）中证明广义电离猜想的能量部分：移走 `@@M@@m@@` 个电子的费用 `@@M@@I_m(Z)\sim a_{\rm TF}m^{7/3}@@`，只要 `@@M@@m\to\infty@@` 且 `@@M@@Z/m\to\infty@@`；常数正是托马斯–费米理论预言的 `@@M@@a_{\rm TF}@@`，且得到猜想的两个迭代极限。

## 问题背景

电离能衡量固定原子核下移走电子的代价。托马斯–费米（Thomas–Fermi）理论描述大电荷主阶能量，Lieb–Simon 1977 年证明它与多体薛定谔理论在 `@@M@@Z^{7/3}@@` 阶一致；但两次总能量渐近相减控制不了小得多的电离能——余项足以淹没所求之差。Solovej 2016 年提出广义电离猜想（generalized ionization conjecture）：只要移走的电子数 `@@M@@m@@` 远小于核电荷 `@@M@@Z@@`，移走 `@@M@@m@@` 个电子的领头费用仍由 TF 决定，表述为先 `@@M@@Z\to\infty@@` 再 `@@M@@m\to\infty@@` 的迭代极限。此前 Seco–Sigal–Solovej 对 `@@M@@m=1@@` 只得 `@@M@@CZ^{20/21}@@` 型上界，Ivrii 的估计覆盖逐电子电离能与 TF 化学势（chemical potential）同阶的近中性区域（`@@M@@Z^{5/7}\ll Z-N\ll Z@@`）；均匀电离界只在 TFvW 与 Hartree–Fock 等近似变分模型中已知（Benguria–Lieb、Solovej）。完整模型需要新的屏蔽估计来对付任意关联态。

## 主要结果

记 `@@M@@I_m(Z)=E_Z(Z-m)-E_Z(Z)@@`。定理（广义电离能）：对完整双自旋库仑哈密顿量，只要 `@@M@@m\to\infty@@`、`@@M@@Z/m\to\infty@@`，就有 `@@M@@I_m(Z)/m^{7/3}\to a_{\rm TF}>0@@`；特别地 `@@M@@\lim_{m\to\infty}m^{-7/3}\limsup_{Z\to\infty}I_m(Z)=a_{\rm TF}@@`，`@@M@@\liminf@@` 版本同样成立——两个迭代极限正是 Solovej 公式化的能量部分，而联合极限是更强的陈述；固定 `@@M@@m@@` 时对 `@@M@@Z@@` 的收敛既不假设也不断言。关键中间结果（定价亏量定理）：引入带价最小值 `@@M@@P(\lambda)=\min_n(E_n+\lambda n)@@`，在 `@@M@@\lambda=s^{-4}@@`、`@@M@@s\to0@@`、`@@M@@Zs^3\to\infty@@` 时，每个极小化区间 `@@M@@n@@` 都满足 `@@M@@s^3(Z-n)\to q@@`；`@@M@@q@@` 是方程 `@@M@@\Delta F=4\pi k((F-1)_+)^{3/2}@@` 唯一经典解（原点附近被 `@@M@@|x|^{-4}@@` 的倍数上下夹住、无穷远处一致趋零）的外部电荷，且 `@@M@@a_{\rm TF}=\frac37q^{-4/3}@@`。

## 证明思路

定价是全文枢纽：固定 `@@M@@Z@@` 时若允许电子数浮动、给每个电子记价 `@@M@@\lambda@@`，试验态便不必保持粒子数，价格精确记账，局部比较才可行；在尺度 `@@M@@s=\lambda^{-1/4}@@` 上被移走的电荷量级为 `@@M@@s^{-3}@@`。证明先沿地基篇的含噪观测与空间切割做局部条件比较：把 TF 试验态与带价多体态在小球内比较，新切一刀在球外留下条件核，其条件屏蔽场在球内调和；两种后验定律严格区分、分别使用，联立得到局部密度与局部位势之间的双向蕴含。再构造障碍（barrier）传播：在最内尺度造正的次解（subsolution），逐层穿过观测尺度向外推，例外数据用期望质量趋零的误差密度支付；弱微分不等式先在保留分支的邻域上证明、后取最大值，避免在活动界面上求导。随后取极限：把条件场重标度为 `@@M@@F_s(x)=s^4(V-K*\mu)(sx)@@`，球面平均恒等式给出下界、帽子型上界控制正部，合成局部 `@@M@@L^1@@` 控制，调和内部估计加 Arzelà–Ascoli 得紧性；极限场满足带价 TF 方程且一致衰减，障碍传递又保住正奇性 `@@M@@B|x|^{-4}\le F_\infty@@`。伸缩（dilation）接触论证识别出 Sommerfeld 系数 `@@M@@|x|^4F\to(12/4\pi k)^2@@` 并证明唯一性（无需径向假设），从而一切极小化区间有同一亏量 `@@M@@q@@`。最后把价格积分回固定区间：`@@M@@P@@` 关于 `@@M@@\lambda@@` 是凹的，极小化区间夹住割线斜率，黎曼和加细得增量极限；零价格端的积分常数用地基篇的中性偏移界 `@@M@@E_Z(Z)-E\le C@@`；能量单调性把目标区间 `@@M@@Z-m@@` 夹在两个极小化区间之间，得 `@@M@@(E_Z(Z-m)-E_Z(Z))/m^{7/3}\to\frac37q^{-4/3}@@`。TF 侧的平行计算（含精确质量伸缩 `@@M@@\rho(x)=m^2\sigma(m^{1/3}x)@@`，即 `@@M@@I_m^{\rm TF}(Z)=m^{7/3}I_1^{\rm TF}(Z/m)@@`）验证 `@@M@@a_{\rm TF}=\frac37q^{-4/3}@@`，与 Bénilan–Brezis 的经典弱电离律一致。

## 可信度与备注

按任务标注，本文主结果已有 Lean 形式化证明，是族 263 中验证状态最强的一篇。其证明显式依赖地基篇（均匀超额电荷与外半径）的局域化、屏蔽估计与中性偏移界——带价极小化态的能量偏移可随 `@@M@@s^{-7}@@` 增长，故"任意偏移下仍成立"的局部场估计不可或缺。常数与 TF 理论经典预测吻合是内在一致性检查；依 OpenAI 官方声明，未经形式化的结果可能有问题，族内尚未形式化的部分仍以社区核验为准。

{% endraw %}
