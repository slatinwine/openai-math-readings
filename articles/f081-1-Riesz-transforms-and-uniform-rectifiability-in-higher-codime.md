---
layout: default
title: "Riesz transforms and uniform rectifiability in higher codimension"
family: "081"
discipline: "Real and complex analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Riesz transforms and uniform rectifiability in higher codimension

> 结果族 081：Riesz transforms and rectifiability in higher codimension　·　学科：Real and complex analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

在最后未解的高余维范围 \(d\ge4\)、\(2\le n\le d-2\) 内，论文证明：只要 \(n\) 维 Ahlfors–David 正则测度的 Riesz 变换（Riesz transform）在所有正硬截断下共享一个 \(L^2\) 算子界，其支撑就必定一致 \(n\)-可矫正（uniformly \(n\)-rectifiable），这正面回答了 David–Semmes 问题的剩余部分。

## 问题背景

奇异积分能否"读出"其所作用测度的几何，是几何测度论与实分析交叉处的核心问题。David 与 Semmes 在 1990 年代建立一致可矫正性理论，作为与奇异积分相配的量化可矫正性，并明确提出：对整数维正则测度，Riesz 变换的 \(L^2\) 有界性本身是否足以强迫这种几何？平面情形由 Mattila–Melnikov–Verdera（1996）借助 Cauchy 积分与 Menger 曲率的关系解决；一维情形可由曲率方法处理；余维一情形由 Nazarov–Tolsa–Volberg（2014）证明，但他们的论证依赖最大原理（maximum principle），并明确指出高余维没有已知的类比，这成为多年的障碍。Mas–Tolsa（2014）用截断的 \(\rho\)-变差（\(\rho>2\)）在所有维数给出刻画，但那控制的是跨尺度变化，是比"每个截断单独有界"更强的假设。剩余范围 \(1<n<d-1\) 由 Tolsa 在 2026 年 ICM 报告中作为公开问题列出；本文在该范围给出肯定回答。

## 主要结果

论文的支柱概念都是量化的：测度 \(\mu\) 称为 \(n\)-Ahlfors–David 正则（\(n\)-Ahlfors–David regular），若 \(C_{\rm AD}^{-1}r^n\le\mu(B(x,r))\le C_{\rm AD}r^n\) 对一切支撑点 \(x\) 与 \(0<r\le D_E\) 成立。其 \(n\) 维 Riesz 变换的正硬截断（hard truncation）为
\[R_{\mu,\varepsilon}f(x)=\int_{|x-y|>\varepsilon}\frac{x-y}{|x-y|^{n+1}}f(y)\,d\mu(y),\qquad\varepsilon>0,\]
假设不涉及逐点主值，只要求存在与 \(\varepsilon\) 无关的界 \(\|R_{\mu,\varepsilon}f\|_{L^2(\mu;\mathbb R^d)}\le C_{\rm R}\|f\|_{L^2(\mu)}\)。

**主定理**：设 \(d\ge4\)、\(2\le n\le d-2\)，\(\mu\) 是 \(\mathbb R^d\) 上满足上述算子界的 \(n\)-AD 正则 Radon 测度，则 \(\mu\) 一致 \(n\)-可矫正：存在 \(\theta>0\) 与 \(M<\infty\)，使对每个 \(x\in E=\mathrm{supp}\,\mu\) 与 \(0<r\le D_E\)，都有 \(M\)-Lipschitz 映射 \(g:B_{\mathbb R^n}(0,r)\to\mathbb R^d\) 满足 \(\mu(B(x,r)\cap g(B_{\mathbb R^n}(0,r)))\ge\theta r^n\)。常数 \(\theta,M\) 只依赖 \(d,n,C_{\rm AD},C_{\rm R}\)。结论即"欧氏球的一致 Lipschitz 图像大块"（uniform big pieces of Lipschitz images）。第 8 节还据此导出 Riesz 截断的变差界与几乎处处主值存在性（对文中指定的奇 \(C^2\) 核同样成立）。

## 证明思路

整条证明是"分析振荡 → 几何平坦 → 打包计数"长链。先建立两个 Carleson 打包估计：其一，用平均零 Lipschitz 测试的 Bessel 不等式，把"Riesz 配对振荡大"的二进方体装入例外族；其二，由"或有平坦球、或有大环形变换"的二择一引理——没有平坦球时，取两次切极限（tangent）并利用法向核的固定符号逐次降维即得矛盾——可知另一个 Carleson 族之外，每个方体都在一致有界深度内含有双边平坦的后代（flat seed）。

传播的骨架是紧致性反证。假若平坦性不能传向小尺度，就得到一列测度，其 excess（到仿射 \(n\)-平面的尺度归一化 \(L^2\) 距离）沿一串二进半径都很小，且 Riesz 配对在越来越大的球上振荡趋零。第一步是平面极限：比较相邻尺度的拟合平面，提炼出单一参考平面与法向坐标；弱极限支撑在该平面上且无反射（reflectionless），再用刚性论证——极限密度满足以二阶差分算子 \(\mathcal L\) 为核的方程，其 Fourier 符号 \(c_n|\xi|\) 在原点外恒正——故极限必为常数倍平面测度。第二步是全文最关键的新意：普通弱收敛只能让 excess 趋零，给不出相对于初始误差的改进，论文转而把法向高度（normal height）除以初始尺度 \(\delta\) 再取第二次极限。用未归一化高度乘截断充当测试函数，配对的正部恰好给出分数次能量 \(\iint|w(x)-w(y)|^2/|x-y|^{n+1}\) 的上界，除以 \(\delta^2\) 后一致有界；配合变动测度上的有限分划紧致性论证，归一化高度收敛到平面上的函数 \(v\)，一二阶矩也同时收敛。第三步是高度方程与仿射刚性：把小配对过渡到极限，\(v\) 在平均零测试下满足 \(\int v\,\mathcal L g=0\)（按模常数解释）；同一符号的正性迫使 \(v\) 的分布 Fourier 变换支于原点，故 \(v\) 是多项式，而加权尾部可积性排除二次及以上，\(v\) 必为仿射。第四步回到几何：极化引理把矩收敛强化为对固定仿射代表的强收敛，仿射法向图像随即倾斜成平面，excess 除以 \(\delta\) 趋零；紧致性反证再将其升级为对一切测度、中心、尺度一致的"一致 excess 传播定理"。

最后是计数收尾：在支撑的二进胞腔上，从平坦种子出发沿链迭代传播定理；一旦某后代失去双边平坦（bilateral flatness），中间必夹有振荡大的祖先，落入先前的 Carleson 族。一个有限种子计数引理把这些失败也控制成 Carleson 集，即双边弱几何引理（bilateral weak geometric lemma）；套用 David–Semmes 的经典判据，便得到主定理所需的一致 Lipschitz 球面映射。

## 可信度与备注

论文主结果（含常数只依赖 \(d,n,C_{\rm AD},C_{\rm R}\)、覆盖无界支撑的定量版本）已有配套 Lean 形式化，可对照 `lean/docs/081.md` 与相应的 comparator 陈述；但第 8 节的变差与主值推论不在形式化范围之内，该部分仍应以社区核验为准。本结果族目前仅此一篇手稿，其内部各模块（打包估计、平面极限、高度紧致性、仿射刚性、传播与打包）环环相扣构成完整证明链，并与 Nazarov–Tolsa–Volberg 的余维一论证在机制上互相呼应。按 OpenAI 官方声明，未经形式化的结果可能有问题，读者引用推论部分时宜保持审慎。

{% endraw %}
