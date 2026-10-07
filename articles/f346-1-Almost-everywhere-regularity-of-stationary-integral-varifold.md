---
layout: default
title: "Almost-everywhere regularity of stationary integral varifolds"
family: "346"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Almost-everywhere regularity of stationary integral varifolds

> 结果族 346：Sharp singular-set bounds for stationary integral varifolds　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明：任意正维数与余维数的平稳积分 \(m\)-varifold，其奇异集 (singular set) 的 \(m\) 维 Hausdorff 测度为零——几乎所有支撑点附近，varifold 恰是某个光滑嵌入极小子流形的固定正整数倍；单位球面上同样成立。

## 问题背景

平稳积分 varifold (stationary integral varifold) 是带整数重数 (multiplicity) 的测度论极小曲面：一阶变分 (first variation) 为零，却允许自交、高重数与奇点。Allard 正则性理论能处理密度为一的点，但高整数密度的点无从下手——把 varifold 除以密度并不保持 Allard 定理所需要的几乎处处下密度界。Simon 2018 年讲义已把"广义平均曲率为零时奇异集是否 \(\mathcal H^m\)-零测"列为公开问题，Brena、Decio、De Lellis 于 2025 年将其记录为 Conjecture 1.2，并提出"以极小图高阶逼近加唯一延拓"的路线图。此前最强的相关结论——Brena–De Lellis–Franceschini 的光滑可求长性 (smooth rectifiability)——只给出零测集之外的可数光滑覆盖，不断言几乎每点的整个邻域等于一张极小图；Hirsch–Spolaor 只在余维一、密度至多二的电流情形得到几乎处处正则。

## 主要结果

**定理。** 对开集 \(U\subset\R^{m+n}\) 中任意平稳积分 \(m\)-varifold（\(m,n\ge1\)），

\[\mathcal H^m(\operatorname{Sing}V)=0 .\]

不需要稳定性、极小性、可定向性、密度上界或余维数假设。**推论（球面）。** 在完整单位球面 \(S^{m+n}\) 上对切向变分平稳的积分 varifold，其球面奇异集满足 \(\mathcal H^m_{g_{\mathrm{round}}}(\operatorname{Sing}_S V)=0\)，同样不需要质量、密度或重数上界，也不需要可定向性或 mod-2 循性。

## 证明思路

全文的引擎是带符号超余估计 (signed excess)。设 \(\pi\) 为到基平面的投影，\(M=\pi_\#\mu-Q\,\mathrm dy\) 是带符号质量差（而非绝对值超余），\(D\) 是倾斜投影测度。当总超余质量不超过 \(d=e^{-T}\) 时，定理给出 \(\int w\,(2M-D)\le d\exp[-F_Q(T)]\)，其中 \(F_Q(T)=\exp_{2Q}\!\big(\sqrt{\log_{2Q}T}\,\big)\) 增长快于对数的任何幂：保留符号使误差被压到任何多项式改进都达不到的水平。其证明按参考整数 \(Q\) 归纳：先用热位势 (heat potential) 构造把"违反点"指派到中心与尺度的接触测度 (contact measure)；若 \(Q\) 个法向高度分成互相分离的组，则在小组球内得到整数计数更小的真实平稳限制，可调用归纳假设并在远离组处赢得少量倾斜；沿选定路径把阻尼带符号质量平均的上确界与"到至多 \(Q\) 个代表高度的截断平方距离矩"比较，代表点至多合并 \(Q-1\) 次，故某个高度区间内无合并，从而在许多尺度上产生定量法向通量；法向平稳性又阻止这些通量集中在超额密度过高的集合上；最后用二进打包 (packing) 论证证明承载这些尺度的集合小得无法支撑原始接触质量，闭合归纳。

正则性部分取 \(\mu\)-几乎处处满足典型点假设（伸缩后收敛到 \(Q\) 重平面，且其它重数的质量相对密度趋于零）的点，先逐尺度用极小图拟合支撑：对平均高度作 Jacobi 型椭圆正则化并解非线性修正（承接 BDLF 的构造），相邻拟合在高度误差的二阶意义下相容；把每个点的首次失败尺度做成 Lipschitz"帐篷"函数 \(t\)，粘合成单张 \(C^J\) 中心图 \(S\)。关键结构事实是：一次失败会在每个固定内球中强制出现两个法向分离、且各自重数严格小于 \(Q\) 的投影 entry——这一步本身要用带符号估计加上一段有限半径的唯一延拓型频率论证。同时，多重数缺陷测度控制影响区域 \(\{t>0\}\) 的体积密度为 \(o(r^m)\)，在影响区域之外支撑高度为零。

最后是向内引导：在中心上定义加权高度 \(H\)、带符号质量 \(A\)、频率 \(P=A/H\) 与倾斜量 \(E,R\)；对薄外圈求解径向散度方程，以保持带符号比较中倾斜项的系数 \(1\)，推出频率近单调与高度倍增；再沿一列频率受控的半径，用分离配置与高阶高度矩把失败区域的消失体积转化为消失投影质量，与高度下界矛盾。于是支撑局部落在 \(S\) 上，常返性 (constancy) 与椭圆正则性把它升级为常重数光滑极小图。球面推论用极坐标锥构造：球面 varifold 的锥是 \(\R^{m+n+1}\) 中的平稳 \((m+1)\)-varifold，其奇异集（除顶点）恰是球面奇异集的射线积，对锥套用主定理并作 Hausdorff 切片即得结论。

## 可信度与备注

本文主结果暂无形式化证明。姊妹篇《A Codimension-One Bound for the Singular Set of a Stationary Integral Varifold》直接以本文的带符号超余定理与拟合、频率局部估计为输入，把"奇异集零测"强化为"维数至多 \(m-1\)"，两篇合起来构成结果族 346 的完整图景。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
