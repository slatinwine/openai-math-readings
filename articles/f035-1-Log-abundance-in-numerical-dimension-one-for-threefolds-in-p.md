---
layout: default
title: "Log abundance in numerical dimension one for threefolds in positive characteristic"
family: "035"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Log abundance in numerical dimension one for threefolds in positive characteristic

> 结果族 035：Log-canonical threefold abundance in numerical dimension one　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在特征 \(p>3\) 的代数闭域上，射影对数典范（log canonical）三维对 \((X,B)\) 的伴随除子 \(K_X+B\) 若为 \(\mathbb{Q}\)-Cartier、nef 且数值维数（numerical dimension）等于一，则必半丰富（semiample）。这补全了正特征三维丰富性猜想在数值维数一情形的最后缺口，且不要求 \(X\) 终端或 \(\mathbb{Q}\)-因子化。

## 问题背景

丰富性猜想（abundance conjecture）是极小模型纲领的后半程：当 \(K_X+B\) 在极小模型上成为 nef 除子后，猜想它的某个正 Cartier 倍数由整体截面生成，即半丰富，从而把纯粹数值的有效性转化为 Iitaka 纤维化这样一个几何态射。复数域上，Miyaoka 与 Kawamata 证明了三维数值维数一的情形，Keel–Matsuki–McKernan 又推广到对数典范三维对。正特征的门槛更高：在 Hacon–Xu、Birkar、Hacon–Witaszek 等人逐步建立起三维 MMP 之后，Xu 在特征 \(p>3\) 下证明了对数典范三维对的非消失（nonvanishing）、nef 维数至多二时的丰富性，以及数值维数二的情形。遗留下来的恰是最微妙的组合：数值维数一而 nef 维数为三——此时所有现成定理都不适用。

## 主要结果

主定理（原文 Theorem 1.1）：设 \(k\) 为特征 \(p>3\) 的代数闭域，\((X,B)\) 为 \(k\) 上的射影对数典范三维对，\(X\) 正规，\(B\) 为有效 \(\mathbb{Q}\)-除子，\(K_X+B\) 为 \(\mathbb{Q}\)-Cartier。若 \(K_X+B\) nef 且数值维数为一——等价地，对某丰富 Cartier 除子 \(H\) 有 \((K_X+B)H^2>0\) 而 \((K_X+B)^2H=0\)——则 \(K_X+B\) 半丰富。边界系数允许对数典范性下的一切有理数；\(X\) 既不必终端（terminal），也不必 \(\mathbb{Q}\)-因子化（\(\mathbb{Q}\)-factorial）。

## 证明思路

全文是反证法，最终目标是构造出一个被姊妹篇禁止的"循环障碍"（cycle obstruction）。

先做归约：经不可数域扩张，再取 crepant \(\mathbb{Q}\)-因子化 dlt 修改并跑相对典范 MMP，可假设底层簇本身终端且 \(\mathbb{Q}\)-因子化，而新对仍为对数典范、新 log 典范类仍 nef、数值维数一、nef 维数三——终端性靠"MMP 中离散量不下降"保住。Xu 的非消失定理随即给出非零有效 Cartier 除子 \(N_0\sim m(K_X+B)\)。

真正的困难在于：障碍定理需要"典范丛的幂"在某除子邻域上的关系，而手里只有混入边界 \(B\) 的伴随除子。论文分三步拆解。第一步是边界分离：证明 \(B\cdot N_0\cdot H=0\)，从而 \(B\) 的每个素分量要么整个含于 \(\operatorname{Supp} N_0\)、要么与之完全不相交。若不然，由 \((K_X+B)N_0H=0\) 可推出 \(K_XN_0H<0\)；取 \(u_lH\) 与 \(v_l(H+lN_0)\) 的一般完全交曲线 \(C_l\)，可使比值 \(N_0C_l/(-K_XC_l)\) 任意小，于是 Jovinelly–Lehmann–Riedl 的定量 bend-and-break 定理给出过 \(C_l\) 每一点、\(N_0\)-度数为零的有理曲线，而这类曲线穿过 very general 点，与 nef 维数为三矛盾。

第二步是孤立化与挠性：把边界沿 \(N_0\) 抬到对数典范阈值，在 dlt 模型上造出一个系数为一的分量；再跑一段对整个 log 典范类平凡的 partial MMP（沿用 Keel–Matsuki–McKernan 的光线论证、Xu 的表述），把这个分量与除子的其余部分分离。对该约化分量用伴随（adjunction）和曲面丰富性（Tanaka、Posva），得其 Cartier 倍元的法线是挠群（torsion）；再借助姊妹篇的延拓论证，把挠性从约化概型提升到整个非约化 Cartier 概型——后续的 jet 计算必须用非约化版本。

第三步组装被禁的循环：终端性使奇点集有限，于是公共分解的例外除子服从与边界相同的支撑分离；对多重典范指数 \(m\) 的 prime-to-\(p\) 部分作有限可分根覆盖并取分解，最后取拉回除子的一个连通分支并除以重数的最大公因数，得到光滑三维簇 \(V\) 上的 Cartier 除子 \(D\)：它 nef、支撑连通且为简单正规交叉、重数本原（gcd 为一）、法线 \(\mathcal{O}_D(D)\) 挠，且 \(\omega_V^{\otimes p^b}\) 在其邻域上同构于支撑在 \(D\) 中的除子对应的线丛。这正是姊妹篇障碍定理（原文 Theorem 2.1）断言不存在的对象，矛盾。故 nef 维数至多二，最后用 Xu 的丰富性定理收尾。

## 可信度与备注

本文主结果暂无形式化证明。它是家族中的"推广篇"：核心的循环障碍定理来自九月的姊妹篇（终端三维体一文），本文将其当作黑箱使用，自己负责从任意有理边界的对数典范数据构造出全部所需输入；两篇合起来覆盖从终端到一般对数典范的完整谱系。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
