---
layout: default
title: "Invariant anticanonical indices and conversion of twisted differentials"
family: "068"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Invariant anticanonical indices and conversion of twisted differentials

> 结果族 068：Anticanonical nonvanishing in every dimension　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明两条独立定理——紧环面作用下反典范幂的不变 Euler 特征（invariant Euler characteristic）在可除等差数列上为多项式且在零点取真值；光滑半正反典范簇上可从无界有效扭曲中消去固定伪有效误差——再经"先下降后转换"组合成丘成桐反典范非消没问题的完整证明。

## 问题背景

本文围绕两个动机问题展开。其一：紧环面 \(T\) 在紧复流形 \(F\) 上全纯作用时，指数 \(m=0\) 处的不变 Euler 特征 \(I_T(0)\) 能否 forcing 大指数处的上同调？其二：光滑射影簇上，固定的伪有效（pseudoeffective）误差能否从一列无界增长的有效扭曲中消去？两者汇合于丘成桐 Problem 75 的反典范非消没问题：\(-K_X\) 光滑半正时 \(H^0(X,-mK_X)\) 是否非零。此前障碍在于剩余单值作用（monodromy）以紧环面作用在万有覆盖的紧因子上，截面未必能下降；而已知方法（Müller 2025）需要半放大假设。本文的关键新意是"在零点取值"：单纯的多项式渐进无法区分多项式是否恒为零，端点信息才是排除零多项式的武器。

## 主要结果

定理 1.1（不变反典范指标）：紧实环面 \(T\) 全纯作用于紧复流形 \(F\)，\(-K_F\) 取微分诱导的自然线性化（natural linearization），则存在 \(a>0\) 与 \(P\in\mathbb Q[t]\) 使 \(I_T(m)=P(m)\) 对 \(a\) 的每个正倍数成立，且 \(P(0)=I_T(0)\)。无需射影性、Kähler 性或任何正性假设。定理 1.2（伪有效误差转换）：\(S\) 光滑连通射影，\(L=-K_S\) 有半正曲率光滑度量，\(D\) 为伪有效 Cartier 除子；若 \(H^0(S,\mathcal O_S(m_jL-D))\ne0\) 对严格递增的 \(m_j\) 成立，则存在 \(k>0\) 使 \(H^0(S,\mathcal O_S(kL))\ne0\)。推论 5.2：光滑连通射影复簇上 \(-K_X\) 光滑半正则 \(H^0(X,-mK_X)\ne0\) 对某 \(m>0\) 成立。

## 证明思路

指标定理走局部化路线：Atiyah–Bott–Segal–Singer 等变 Dolbeault 不动点公式把 \(I_T(m)\) 写成平凡特征系数，对固定分量极化分母后成为有理多面体上的多项式加权格点计数；先在闭多面体上用基本平行六面体分解与二项式恒等式（加权 Ehrhart 理论）得到可除指数上的多项式性；删去的坐标面贡献的常数项是 \((\chi(D)-\chi(A))W(0,0)\)，而反典范特征 \(w=\sum_i\nu_i\) 恰好使外点 \(u\)（在 \(I\) 上坐标为 \(-1\)、其余为 \(1\)）落在多面体的仿射方程空间中，从 \(u\) 出发的射线首次进入 \(D\) 必经被删面，给出形变收缩（deformation retraction）\(\chi(A)=\chi(D)=1\)，删面贡献的常数项相消；幸存常数恰为 \(m=0\) 处的真实计数。再配合半正系数的 Hard Lefschetz 定理（DPS 2001）：\(I_T(0)\ne0\) 时某固定 \(p\) 与无界大 \(m\) 给出不变扭曲形式 \(H^0(F,\Omega_F^p\otimes L_F^{m+1})^T\ne0\)。转换定理则分四步：先取被 \(L\) 支配的极大基，截面比值必落在 \(\mathbb C(Y)\) 中，插值恒等式使水平零点阶随指数仿射变化，得 \(N_2-N_1\) 水平部分有效；再沿基除子取垂直阶数最小值，规范化出基上线丛 \(B\) 与非零映射 \(\sigma:f^*B\to\ell\pi^*L\)，并由极大性证出伴随直像秩一；接着用 Berndtsson 直像半正性定理，以 \(L^{2k}\) 范数经 Hölder 不等式与 Dini 定理收敛到 \(\sigma\) 的逐纤维最大值权，配以规范化提供的边界估计，得 \(B\) 上局部有界的半正度量；最后混合度量使曲率 \(\ge\epsilon f^*\omega_H\) 且乘子理想子（multiplier ideal）平凡（Skoda/Demailly–Kollár 可积性），Fujino 的 Kollár–Nadel 消没定理对一切 \(k\ge0\) 生效，Euler 多项式 \(Q(k)=h^0\) 处处成立，例外典则截面使 \(Q(0)>0\)，多项式非零故某正指数有截面，乘 \(\sigma^k\) 后推到 \(S\)。应用环节次序关键：引用姊妹篇的有限覆叠结构定理与 étale 范数引理，把 \(F\) 上的不变形式先张上其他因子的不变典则框架、经牌不变性单射下降到有限覆叠 \(S\)，转换定理只在下降后使用，无需任何等变强化。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。其几何骨架（有限覆叠结构、范数引理）直接引用同族第一篇手稿，而第一篇的有限体积归纳路线又与本文的不变指标路线互补，两篇交叉印证同一主结论；第三篇则把结论推广到 klt 对。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
