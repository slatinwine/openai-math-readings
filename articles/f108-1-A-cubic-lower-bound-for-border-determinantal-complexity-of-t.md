---
layout: default
title: "A cubic lower bound for border determinantal complexity of the permanent"
family: "108"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A cubic lower bound for border determinantal complexity of the permanent

> 结果族 108：A cubic permanent–determinant lower bound　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 \(m\times m\) 积和式（permanent）的 border 行列式复杂度为 \(\Omega(m^3)\)：即便允许任意仿射线性矩阵的行列式做逐系数极限逼近，矩阵阶数仍须至少 \(c\,m^3\)。长期停留在平方级的这一下界首次被推进到立方，精确表示与代数分支程序规模获得同阶界。

## 问题背景

积和式 \(\per_m(X)=\sum_{\sigma\in S_m}\prod_i x_{i,\sigma(i)}\) 与行列式只差排列符号，却横亘在代数复杂度理论的核心：Valiant（1979）证明算术公式可写成行列式投影且积和式代数完备，"用行列式表示 \(\per_m\) 至少要多大"由此成为分离代数复杂度类的定量入口。精确模型 \(\dc(f)\) 要求 \(f=\det(A_0+\sum_j x_jA_j)\)；border 模型 \(\bdc(f)\) 只要求 \(f\) 落在这类行列式的逐系数闭包中，也是 Mulmuley–Sohoni 几何复杂度理论（geometric complexity theory）轨道闭包表述的对象。Mignon–Ressayre（2004）用 Hessian 秩比较证得 \(\dc(\per_m)\ge m^2/2\)，Landsberg–Manivel–Ressayre（2010）在无限制复 border 模型得到同阶下界；上界一侧至今只有 Grenet 的 \(2^m-1\)。指数这道"2"坎一卡二十余年，本文将其翻到"3"。

## 主要结果

主定理：存在绝对常数，对一切 \(m\ge1408\) 有 \(\bdc(\per_m)\ge m^3/(5\,529\,600e)\)；论文还证明逐系数闭包与射影轨道闭包两种 border 表述等价，故下界同时覆盖几何复杂度理论所用的模型。由于精确表示是恒定逼近序列，\(\dc(\per_m)\) 有同样立方下界。对仿射线性代数分支程序（algebraic branching program），计算 \(\per_m\) 需 \(\Omega(m^3)\) 个顶点和 \(\Omega(m^3)\) 条边，即使允许顶点或边预算固定而图可变的极限逼近亦然；非齐次多项式最低非零齐次项光滑者也有同型下界。全部推论共享一个通用障碍定理：若 \(r\ge2\) 次、\(d\ge2\) 变量的非零齐次多项式 \(G\) 的射影零集光滑，则 \(\bdc(G)\ge(r-1)(d-1)/(4e)\)。于是只需在 \(\per_m\) 的固定仿射限制里造出"次数线性、变量数二次"的光滑形式，立方界即水到渠成。

## 证明思路

证明像三级火箭：先造多项式，再证某个线性限制光滑，最后极式计数收网。

第一级是选择子（selector）构造。取 \(D=\diag(\theta_1,\ldots,\theta_k)\) 与 \(q=\lfloor(k-1)/3\rfloor\)，定义 \(G_D(X)=[s^qt^q]\per_k(X+sI+tD)\)，其关于 \(X\) 的次数 \(r=k-2q\) 线性于 \(k\)。作者以两个"计数门"（各自强制完美匹配恰用 \(q\) 条指定颜色的特殊边）配合 \(2k\) 个以权重 \(-2\) 制造内部相消的"相等 gadget"，把 \(G_D\) 在非零标量 \((-2)^{2k}((k-q)!)^4\) 意义下实现为阶数 \(11k-2q\) 积和式的仿射限制；由 \(\bdc(a\,f\circ A)\le\bdc(f)\)，对 \(\per_m\) 的任何逼近都自动成为对 \(G_D\) 各仿射限制的逼近。

第二级在特征 2 中证明光滑性。\(K=\overline{\mathbb F}_2\) 上积和式即行列式，于是每个矩阵 \(X\) 对应平面曲线 \(C_X=V(\det(sI+t\bar D+uX))\)。关键代数引理：伴随矩阵（adjugate）各元素恰好生成所有在伴随零方案 \(Z\) 上消失的 \(k-1\) 次形式；若梯度 \(\nabla G_{\bar D}(X)=0\)，以互补单项式逐项提取系数可证 \(q\) 次形式到 \(Z\) 的限制是单射，故 \(\length Z\ge T=\binom{q+2}{2}\)（二次于 \(k\)）。经传导理想（conductor）与正规化亏值 \(\delta(C_X)\) 比较，再援引 Christ–He–Tyomkin 任意特征的 Severi 维数定理并辅以 Hilbert 方案（Hilbert scheme）估计，得临界矩阵集余维数 \(\ge T-k\)。这样 \(d=\lfloor k^2/100\rfloor\) 维一般线性子空间可整体绕开奇异轨迹；最后经特殊化把维数结论传回复参数域，得到光滑形式 \(G\) 与固定仿射映射 \(\Phi_m\) 使 \(G=\per_m\circ\Phi_m\)。

第三级是极式（polar）计数。光滑性供出 \(d-2\) 个一阶极式，其与 \(G=0\) 恰交于 \(\mu=r(r-1)^{d-2}\) 个单点。若 \(G\) 被 \(n\) 阶仿射行列式逐系数逼近，就取一个足够近的真实行列式 \(\det A(x)\)：单点在扰动下持久，且每点处 \(A\) 秩为 \(n-1\)，具唯一左、右核线，从而把交点提升为 \(\PP^{d-1}\times\PP^{n-1}\times\PP^{n-1}\) 上双线性核方程组的光滑解。Schur 补消元确认提升后仍单点，多元齐次 Bézout 计数给出 \(\mu\le2^{d-2}\binom{2n-1}{d-1}\)，开 \(d-1\) 次方得 \(n\ge(r-1)(d-1)/(4e)\ge k^3/(3200e)\)；代入 \(k=\lfloor m/11\rfloor\ge m/12\) 即主定理。

## 可信度与备注

本结果暂无形式化证明，任务标注的 Lean 链接属家族级说明，请以社区核验为准；论文自陈常数远未优化。本批次中该结果族仅此一篇手稿，无姊妹篇互证；但其核方程计数骨架与 2026 年 Sheshadri 及 Kumar–Volk 预印本独立呼应，后者以类似工具证得对角幂和精确模型的平方界，可作方法学旁证。按 OpenAI 官方声明，未经形式化的结果可能有问题，最终认定有待同行评议。

{% endraw %}
