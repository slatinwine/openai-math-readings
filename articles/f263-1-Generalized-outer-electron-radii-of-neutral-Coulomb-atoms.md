---
layout: default
title: "Generalized outer-electron radii of neutral Coulomb atoms"
family: "263"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Generalized outer-electron radii of neutral Coulomb atoms

> 结果族 263：The ionization and generalized ionization conjectures　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

中性原子的电子云像一杯啤酒：泡沫总浮在最上层。定义"外半径 R_m"为外部恰好只剩 m 个电子的最小球半径——相当于问：要从杯口往下量多深，才只裹住 m 滴泡沫？定理给出精确答案：先让核电荷 Z 趋于无穷、再让 m 趋于无穷，这个半径渐近于一个常数乘 m 的负三分之一次方——尾部越薄，需要的半径越大，且比例系数与 Z 完全无关。

**关键词卡片**

- 外半径 `@@M@@R_m@@`（outer radius）：外部电子质量恰为 m 的半径，衡量电子云尾巴拖多长。
- 托马斯–费米极限（Thomas–Fermi limit）：大原子密度的主阶近似理论，常数的出处。
- 屏蔽场（screened field）：核吸引减去电子云排斥后的有效电场。
- 迭代极限（iterated limit）：先 `@@M@@Z\to\infty@@` 再 `@@M@@m\to\infty@@` 的取极限顺序。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="75" y="32" font-size="14">中性原子的电子密度尾部 ρ(r)：外面剩 m 个电子的半径</text>
  <line x1="70" y1="230" x2="530" y2="230" stroke="#333" stroke-width="2"/>
  <polygon points="538,230 526,224 526,236" fill="#333"/>
  <line x1="70" y1="230" x2="70" y2="50" stroke="#333" stroke-width="2"/>
  <path d="M75 55 C 130 70, 190 150, 300 185 C 390 210, 470 216, 525 220" fill="none" stroke="#369" stroke-width="2.5"/>
  <line x1="215" y1="196" x2="215" y2="230" stroke="#c33" stroke-width="1.5" stroke-dasharray="5 4"/>
  <line x1="415" y1="218" x2="415" y2="230" stroke="#c33" stroke-width="1.5" stroke-dasharray="5 4"/>
  <text x="180" y="250" font-size="13">R(m=64) ≈ 1.8</text>
  <text x="388" y="250" font-size="13">R(m=8) ≈ 3.7</text>
  <text x="85" y="62" font-size="13">ρ(r)</text>
  <text x="505" y="248" font-size="13">r</text>
  <text x="55" y="272" font-size="14">尾部规律：外部质量 ≈ b³·r^(−3) ⇒ R_m ≈ 7.37·m^(−1/3)（与 Z 无关）</text>
</svg>

</div>

数字版：`@@M@@b_{\rm TF}=(81\pi^2/2)^{1/3}\approx 7.37@@`，故 `@@M@@R_m\approx 7.37\,m^{-1/3}@@`——m=8 时约 3.7，m=64 时约 1.8；尾部外部质量满足 `@@M@@\int_{|x|>r}\rho\approx b_{\rm TF}^3\,r^{-3}@@`。

**为什么值得关心**

广义电离猜想的半径部分在完整薛定谔模型（任意关联基态）中获证；常数与 Solovej 的 Hartree–Fock 定理完全一致，构成交叉验证。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明广义电离猜想的半径部分：中性库仑原子任意基态选择下，期望外部电子质量为 `@@M@@m@@` 的半径先对 `@@M@@Z@@` 取上、下极限再让 `@@M@@m\to\infty@@`，均渐近于 `@@M@@(81\pi^2/2)^{1/3}m^{-1/3}@@`，与 Solovej 在 Hartree–Fock 理论中所得常数一致。

## 问题背景

电离问题问：核电荷增大时原子外层电子如何分布？中性原子的体密度在长度 `@@M@@Z^{-1/3}@@` 上收敛到托马斯–费米（Thomas–Fermi）极限（Lieb–Simon），但固定外部质量 `@@M@@m@@` 的半径只涉及占比 `@@M@@m/Z@@` 的质量，体收敛对它无能为力。对完整模型，Seco–Sigal–Solovej 只得到随 `@@M@@Z@@` 衰减的半径下界。Solovej 2003 年在无限制 Hartree–Fock 中证得同一常数的普适外半径律，并于 2016 年把完整薛定谔模型版写成广义电离猜想（generalized ionization conjecture，保留上、下两个大 `@@M@@Z@@` 极限）。此外，TF–Dirac–von Weizsäcker 与幂密度矩阵泛函等近似模型的尖锐半径估计亦已有结果，但都不针对任意关联的薛定谔基态。本文在含任意关联态的完整模型中证明其半径部分：地基篇姊妹文已证"留下半个期望电子"的半径有普适双侧界，本文则在该外部质量趋于无穷时识别出精确系数。

## 主要结果

对中性原子哈密顿量 `@@M@@H_Z=\sum_{i\le Z}(-\frac12\Delta_i-\frac{Z}{|x_i|})+\sum_{i<j}|x_i-x_j|^{-1}@@`，任取归一化基态 `@@M@@\Psi_Z@@`，其自旋求和密度 `@@M@@\rho_{\Psi_Z}@@` 总质量为 `@@M@@Z@@`。对 `@@M@@1\le m<Z@@` 定义 `@@M@@R_m(\Psi_Z)=\inf\{r:\int_{|x|>r}\rho_{\Psi_Z}\le m\}@@`。定理：记 `@@M@@b_{\rm TF}=(81\pi^2/2)^{1/3}@@`，对基态的任意选择，`@@M@@\lim_{m\to\infty}m^{1/3}\limsup_{Z\to\infty}R_m(\Psi_Z)=b_{\rm TF}@@`，`@@M@@\liminf@@` 版本同样成立。陈述对整个基态本征空间一致，不假设球对称，固定 `@@M@@m@@` 时对 `@@M@@Z@@` 的收敛也不需要。系数的来历：极限 TF 模型 `@@M@@\varrho=k(F_+)^{3/2}@@`、`@@M@@\Delta F=4\pi\varrho@@` 的正齐次解为 `@@M@@F_*(x)=A_*|x|^{-4}@@`（`@@M@@A_*=(12/4\pi k)^2=81\pi^2/8@@`），其外部质量 `@@M@@\int_{|x|>r}\rho_*=4A_*r^{-3}=b_{\rm TF}^3r^{-3}@@`，令其等于 `@@M@@m@@` 便得半径 `@@M@@b_{\rm TF}m^{-1/3}@@`。

## 证明思路

从量子态到极限场分四步。先条件化：给电子位置加独立小误差并条件化，光滑单位质量包的条件平均给出条件密度 `@@M@@\sigma@@`，核位势减其库仑势得屏蔽场（screened field）；在中间半径 `@@M@@s@@` 处按 `@@M@@s^4@@`（场）、`@@M@@s^6@@`（密度）重标度，比较估计在越来越大的环带上给出逐点 TF 关系。难点有二：场只有上界控制、重标度电子总质量可能发散；妙处是精确中性——牛顿球面平均恒等式使 `@@M@@\overline F(d)=\int_{|z|>d}(\frac1d-\frac1{|z|})\sigma\ge0@@`，与上界合成场的局部 `@@M@@L^1@@` 控制，调和内部估计对这种带号场也给出紧性。再传递正障碍（barrier）：在固定球上比较地基篇的中间次解（subsolution）与屏蔽场，减去一个逐点趋零的库仑修正位势，以 `@@M@@(W)_+@@` 为试验函数得 `@@M@@U\le F+L+c_S@@`，令球半径 `@@M@@S\to\infty@@` 得双侧界 `@@M@@B|x|^{-4}\le F\le C|x|^{-4}@@`。然后证刚性（rigidity）：设 `@@M@@b,h@@` 为 `@@M@@|x|^4F@@` 的上、下确界，在趋近上确界的点列上伸缩取极限，极限场在单位球面某点接触 `@@M@@b|x|^{-4}@@`，由 `@@M@@\Delta|x|^{-4}=12|x|^{-6}@@` 得 `@@M@@4\pi kb^{3/2}\le12b@@`；下确界一侧反向，两式夹出 `@@M@@F\equiv A_*|x|^{-4}@@`——全程不需径向假设。最后回到期望外部质量：包支撑的夹逼不等式（收缩、放大环带上的电子计数夹住包质量）消去光滑化，一致可积性排除例外观测，二进壳层求和给出尾部紧性，合起来得 `@@M@@s^3\int_{|y|>as}\rho_{\Psi}\to b_{\rm TF}^3/a^3@@`。取 `@@M@@a_-<b_{\rm TF}<a_+@@`：当 `@@M@@m@@` 充分大时，对一切 `@@M@@Z\ge Z_{\min}(m)@@` 与一切基态，半径被夹在 `@@M@@a_-m^{-1/3}@@` 与 `@@M@@a_+m^{-1/3}@@` 之间；去掉 `@@M@@Z@@` 的有限前缀不影响内层上、下极限，挤压即得两个迭代极限。

## 可信度与备注

本文是族 263 的"半径篇"：条件密度比较与正的中间次解直接取自地基篇（均匀超额电荷与外半径），中间尺度紧性与伸缩刚性论证则与能量篇共享方法，三篇互为支撑。常数 `@@M@@(81\pi^2/2)^{1/3}@@` 与 Solovej 的 Hartree–Fock 定理及 TF 理论完全一致，构成交叉验证。按任务标注本文暂无形式化证明；依 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
