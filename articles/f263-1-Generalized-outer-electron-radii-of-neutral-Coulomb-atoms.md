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

## 一句话结论

本文证明广义电离猜想的半径部分：中性库仑原子任意基态选择下，期望外部电子质量为 \(m\) 的半径先对 \(Z\) 取上、下极限再让 \(m\to\infty\)，均渐近于 \((81\pi^2/2)^{1/3}m^{-1/3}\)，与 Solovej 在 Hartree–Fock 理论中所得常数一致。

## 问题背景

电离问题问：核电荷增大时原子外层电子如何分布？中性原子的体密度在长度 \(Z^{-1/3}\) 上收敛到托马斯–费米（Thomas–Fermi）极限（Lieb–Simon），但固定外部质量 \(m\) 的半径只涉及占比 \(m/Z\) 的质量，体收敛对它无能为力。对完整模型，Seco–Sigal–Solovej 只得到随 \(Z\) 衰减的半径下界。Solovej 2003 年在无限制 Hartree–Fock 中证得同一常数的普适外半径律，并于 2016 年把完整薛定谔模型版写成广义电离猜想（generalized ionization conjecture，保留上、下两个大 \(Z\) 极限）。此外，TF–Dirac–von Weizsäcker 与幂密度矩阵泛函等近似模型的尖锐半径估计亦已有结果，但都不针对任意关联的薛定谔基态。本文在含任意关联态的完整模型中证明其半径部分：地基篇姊妹文已证"留下半个期望电子"的半径有普适双侧界，本文则在该外部质量趋于无穷时识别出精确系数。

## 主要结果

对中性原子哈密顿量 \(H_Z=\sum_{i\le Z}(-\frac12\Delta_i-\frac{Z}{|x_i|})+\sum_{i<j}|x_i-x_j|^{-1}\)，任取归一化基态 \(\Psi_Z\)，其自旋求和密度 \(\rho_{\Psi_Z}\) 总质量为 \(Z\)。对 \(1\le m<Z\) 定义 \(R_m(\Psi_Z)=\inf\{r:\int_{|x|>r}\rho_{\Psi_Z}\le m\}\)。定理：记 \(b_{\rm TF}=(81\pi^2/2)^{1/3}\)，对基态的任意选择，\(\lim_{m\to\infty}m^{1/3}\limsup_{Z\to\infty}R_m(\Psi_Z)=b_{\rm TF}\)，\(\liminf\) 版本同样成立。陈述对整个基态本征空间一致，不假设球对称，固定 \(m\) 时对 \(Z\) 的收敛也不需要。系数的来历：极限 TF 模型 \(\varrho=k(F_+)^{3/2}\)、\(\Delta F=4\pi\varrho\) 的正齐次解为 \(F_*(x)=A_*|x|^{-4}\)（\(A_*=(12/4\pi k)^2=81\pi^2/8\)），其外部质量 \(\int_{|x|>r}\rho_*=4A_*r^{-3}=b_{\rm TF}^3r^{-3}\)，令其等于 \(m\) 便得半径 \(b_{\rm TF}m^{-1/3}\)。

## 证明思路

从量子态到极限场分四步。先条件化：给电子位置加独立小误差并条件化，光滑单位质量包的条件平均给出条件密度 \(\sigma\)，核位势减其库仑势得屏蔽场（screened field）；在中间半径 \(s\) 处按 \(s^4\)（场）、\(s^6\)（密度）重标度，比较估计在越来越大的环带上给出逐点 TF 关系。难点有二：场只有上界控制、重标度电子总质量可能发散；妙处是精确中性——牛顿球面平均恒等式使 \(\overline F(d)=\int_{|z|>d}(\frac1d-\frac1{|z|})\sigma\ge0\)，与上界合成场的局部 \(L^1\) 控制，调和内部估计对这种带号场也给出紧性。再传递正障碍（barrier）：在固定球上比较地基篇的中间次解（subsolution）与屏蔽场，减去一个逐点趋零的库仑修正位势，以 \((W)_+\) 为试验函数得 \(U\le F+L+c_S\)，令球半径 \(S\to\infty\) 得双侧界 \(B|x|^{-4}\le F\le C|x|^{-4}\)。然后证刚性（rigidity）：设 \(b,h\) 为 \(|x|^4F\) 的上、下确界，在趋近上确界的点列上伸缩取极限，极限场在单位球面某点接触 \(b|x|^{-4}\)，由 \(\Delta|x|^{-4}=12|x|^{-6}\) 得 \(4\pi kb^{3/2}\le12b\)；下确界一侧反向，两式夹出 \(F\equiv A_*|x|^{-4}\)——全程不需径向假设。最后回到期望外部质量：包支撑的夹逼不等式（收缩、放大环带上的电子计数夹住包质量）消去光滑化，一致可积性排除例外观测，二进壳层求和给出尾部紧性，合起来得 \(s^3\int_{|y|>as}\rho_{\Psi}\to b_{\rm TF}^3/a^3\)。取 \(a_-<b_{\rm TF}<a_+\)：当 \(m\) 充分大时，对一切 \(Z\ge Z_{\min}(m)\) 与一切基态，半径被夹在 \(a_-m^{-1/3}\) 与 \(a_+m^{-1/3}\) 之间；去掉 \(Z\) 的有限前缀不影响内层上、下极限，挤压即得两个迭代极限。

## 可信度与备注

本文是族 263 的"半径篇"：条件密度比较与正的中间次解直接取自地基篇（均匀超额电荷与外半径），中间尺度紧性与伸缩刚性论证则与能量篇共享方法，三篇互为支撑。常数 \((81\pi^2/2)^{1/3}\) 与 Solovej 的 Hartree–Fock 定理及 TF 理论完全一致，构成交叉验证。按任务标注本文暂无形式化证明；依 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
