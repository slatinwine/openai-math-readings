---
layout: default
title: "The Reconstruction Threshold for the Ferromagnetic Four-State Potts Model"
family: "229"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Reconstruction Threshold for the Ferromagnetic Four-State Potts Model

> 结果族 229：Exact three- and four-state reconstruction thresholds and four-state tree capacity　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了铁磁四态 Potts 广播模型在一切 `@@M@@d\ge2@@` 正则树与均值 `@@M@@d>0@@` 的泊松树上，重构当且仅当 `@@M@@d\lambda^2>1@@`，且临界等号处不重构；把此前仅大度数成立的结论推广到全部度数，而四态恰是谱阈值仍然精确的边界情形。

## 问题背景
在树上的广播过程（broadcast process on a tree）中，根的自旋沿每条边独立地通过噪声通道传给子代；重构问题（reconstruction problem）问：无穷远处的叶子自旋还保留多少关于根自旋的信息？Kesten–Stigum 二阶矩判据 `@@M@@d\lambda^2>1@@` 自 1966 年起给出重构的充分方向，但其必要性依赖通道本身：Mossel（2001）证明谱判据并非普遍必要；Sly（2011）证明三态模型在大度数正则树上阈值精确，而 `@@M@@q\ge5@@` 态时谱判据失效。四态正处在"精确"与"失效"的分界线上，Mézard–Montanari（2006）与 Ricci-Tersenghi 等人的空腔方法数值都支持其精确性，但严格结论（Mossel–Sly–Sohn 2025）此前只覆盖足够大的平均度。本文对铁磁四态去掉大度数限制；反铁磁（antiferromagnetic）情形被排除是必要的——那里确实可在阈值以下重构。

## 主要结果
通道为四态 Potts 型 `@@M@@P_\lambda(j\mid i)=\lambda\mathbf 1_{\{i=j\}}+(1-\lambda)/4@@`，`@@M@@\lambda\in[0,1]@@` 是通道的非平凡特征值，`@@M@@\lambda\ge0@@` 即铁磁区域。主定理：若 `@@M@@d\lambda^2\le1@@`，则重构优势
`@@M@@Da_n(d,\lambda)=\E\Big[\tfrac12\sum_{i=1}^4\big|\Pr(\sigma_\rho=i\mid T,\sigma_{L_n})-\tfrac14\big|\Big]@@`
趋于零，对每个整数 `@@M@@d\ge2@@` 的正则树与每个实数 `@@M@@d>0@@` 的泊松 Galton–Watson 树均成立，特别包含等号 `@@M@@d\lambda^2=1@@`；泊松情形观测整棵树，期望不依存活条件化。结合已知的 `@@M@@d\lambda^2>1@@` 重构方向，这给出精确的 Kesten–Stigum 阈值。

## 证明思路
核心对象是后验概率向量 `@@M@@p@@` 的分布（后验律），而非单个向量。定义二次信息 `@@M@@A(p)=4\sum_i p_i^2-1@@`；一次通道步使 `@@M@@\E A@@` 乘以 `@@M@@\lambda^2@@`，真正的困难在于不同子树观测合并时的非线性效应。作者构造一个六次多项式 `@@M@@H@@`（连同辅助多项式 `@@M@@F,G@@`，系数以千分位有理数显式给出），使约束 `@@M@@\E H(p)\ge0@@` 所定义的对称后验律类 `@@M@@\mathcal C@@` 在通道步、条件独立乘积与按可观测标签混合三种操作下封闭；初始的完全揭示实验与无信息实验都属于该类。随后两条显式多项式不等式给出：合并两个实验时 `@@M@@\E A@@` 次可加，且当两支都有信息量时严格节省一个三次项 `@@M@@A(p)A(q)(A(p)+A(q))/1000@@`。于是在树上先合并前两个分支、再逐个加入其余分支，得到矩递推 `@@M@@m_{n+1}\le d\lambda^2m_n-\frac{2}{1000}\Pr(D\ge2)(\lambda^2m_n)^3@@`。三次负项在等号处至关重要：线性系数恰为 1 时它仍迫使 `@@M@@m_n\downarrow0@@`；正则树 `@@M@@\Pr(D\ge2)=1@@`，泊松树 `@@M@@\Pr(D\ge2)=1-(1+d)e^{-d}>0@@` 对一切 `@@M@@d>0@@` 成立，连 `@@M@@d\le1@@` 的噪声临界情形也直接覆盖。约束对后验律是线性的，故对可观测后代数的混合封闭——这使同一组两两不等式同时处理泊松与正则两类模型。最后由 `@@M@@a_n\le\frac12\sqrt{m_n}@@` 把矩衰减转化为优势衰减。剩余的多项式不等式（`@@M@@F,G\ge0@@`、`@@M@@H\ge-1/2@@` 及两条乘积不等式）由精确有理算术验证：将单形按排序坐标参数化后，利用齐次单项式系数非负性（Bernstein 型判据），对有理函数则用 `@@M@@z^{-k}@@` 的五阶泰勒下界（T 型证书）或带精确认证余项的插值（P 型证书）在有限细分上逐格验证；插值精度本身从不需要被假设，余项被精确认证，因此整个验证是可复现的严格证明。

## 可信度与备注
本文是结果族 229 的四态支柱：同族三态论文给出对称三态通道的精确阈值，容量判据论文则把本文的封闭后验律类与矩节省命题（其命题 3.2）作为显式输入，把结论推广到任意有界度确定性树。主结果暂无 Lean 形式化证明；本文是计算机辅助证明——概率论证在文中完整给出，多项式不等式由附录中的精确算术程序验证——请以社区核验为准。OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
