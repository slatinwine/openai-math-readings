---
layout: default
title: "Equidistribution of Prime-Degree Torus Packets with Arbitrary Local Type"
family: "015"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Equidistribution of Prime-Degree Torus Packets with Arbitrary Local Type

> 结果族 015：Torus-packet equidistribution in prime, quartic, and sextic degrees　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对固定素数次数 \(n\ge5\) 的全实域，本文无条件证明：任意局部同位类型的环面束（torus packet）按轨道体积加权后，随乘子序判别式趋于无穷而弱收敛到 Haar 概率测度，且无质量逃逸。这正面解决了 ELMV 遗留的高维 Duke 均分布问题的束形式，全程不用子凸性界。

## 问题背景

幺模格空间 \(X_n=\SL_n(\Z)\backslash\SL_n(\R)\) 带对角群 \(A_n\) 的右作用，是齐性动力学的经典舞台。全实数域 \(K\) 经其 \(n\) 个实嵌入映入 \(\R^n\) 后，其分数理想与单位群给出 \(X_n\) 中紧的 \(A_n\)-轨道，编码了理想类与单位的信息。Linnik 的遍历方法与 Duke 1988 年关于模曲面上实二次域闭测地线均分布的定理开创了这一方向；Einsiedler–Lindenstrauss–Michel–Venkatesh（ELMV）2011 年证明了三次域的环面束均分布，但其向更高素数次数的推广（其文 1.6.3 节）依赖尚未解决的子凸性（subconvexity）猜想。此后 Khayutin 需要极大序与二重传递假设，Lemke Oliver–Thorner–Zaman 则须排除一小族例外域。卡点有二：高次数下子凸性缺失；非极大序带来任意的局部模类型。

## 主要结果

固定素数 \(n\ge5\)。设 \(K\) 为 \(n\) 次全实域，\(M\subset K\) 为张成 \(K\) 的秩 \(n\) 自由 \(\Z\)-子模（full lattice，全格）。其乘子序（multiplier order）定义为 \(\cO(M)=\{\alpha\in K:\alpha M\subset M\}\)，判别式为 \(D(M)=|\Disc(K)|[\cO_K:\cO(M)]^2\)。两个全格称为局部同位（locally homothetic），若对每个有理素数 \(\ell\) 有 \(M'_\ell=c_\ell M_\ell\)。在 \(M\) 的局部同位类中取 \(K^\times\)-同位代表、嵌入后归一化协体积为 1，再连同全部坐标符号平移 \(w\)，得到有限多条紧对角轨道，构成束 \(\cP_{K,M,\sigma}\)。按轨道体积加权平均各轨道的不变概率，即得束概率测度 \(\mu_{K,M,\sigma}\)。

主定理：凡 \(D(M_i)\to\infty\)，必有 \(\mu_{K_i,M_i,\sigma_i}\) 弱收敛到 \(X_n\) 的 Haar 概率测度 \(m_n\)，且没有质量逃入尖端（cusp）。定理对每个局部类型单独成立，允许非极大序指数无界增长，也允许在固定域中让序指数增长（此时域判别式保持有界）。取 \(M=\cO_K\) 即得极大序理想类束的经典特款。

## 证明思路

全文遵循 ELMV 的"计数到刚性"（counting-to-rigidity）策略：先展开束测度，再做局部与解析两层估计，继而由计数导出几何界，最后经熵进入测度分类。

第一步把束测度精确写成带权理想和。记 \(R=\cO_K\)、饱和指数 \(q=[RM:M]\)、计数尺度 \(Q=q\sqrt D\)。束概率等于对极大序各理想类一致平均、对每个理想 \(I\) 上的有限局部标号集 \(\cN(I)\) 一致平均、再沿单位群基本域积分；类数公式给出总体积 \(h_K\vol(F)=\sqrt D\,\kappa_K\)，其中 \(\kappa_K\) 是 \(\zeta_K\) 在 \(s=1\) 处的留数。于是格向量计数的束平均经 Hecke 式展开（unfolding）化为 \(\int E_f\,d\mu_*=\frac{1}{\sqrt D\,\kappa_K}\sum_{\mathfrak a}P(\mathfrak a)\,\cV_f(\N\mathfrak a/Q)\)，权重 \(P(\mathfrak a)\) 是"随机局部标号包含给定元素"的局部概率之积。

第二步一致控制局部权重，这是覆盖任意局部类型的核心。先证精确恒等式 \(\sum_{\mathbf k}P(\mathbf k)/d(\mathbf k)=Z_S/q\)：单位随机平移下落入指定模的概率总和恰为 \(1/q\)；再配一个方幂衰减的矩估计与尾估计。其证明只用到全生成条件 \(R_\ell L_\ell=R_\ell\) 迫使每个分量投影含单位，从而赋值呈指数尾——既不需要各分量独立，也不需要模可逆。

第三步解析计数：不求子凸性，而是保留留数。Stark 例外零点下降断言过近于 \(1\) 的实零点迫使 \(K\) 含二次子域，奇数次数排除之，故一切零点满足 \(|1-\rho|\gg_n1/\log D\)，得 \(h\zeta_K(1+h)\asymp_n\kappa_K\)。结合 Pollack 一致化形式的 Shiu 短区间定理，得 \(\sum_{x-y<\N\mathfrak a\le x}P(\mathfrak a)\ll_n\kappa_K y/q\)；剔除 \(q\) 的素因子处的 Euler 因子，恰好补出抵消归一化 \(1/q\) 的因子。

第四步几何转译：取原点立方体的示性函数控制尖端质量于 \(C_n\theta^n\)（Mahler 紧性判据给出紧性，无质量逃逸由此而来）；取坐标全非零向量附近的小方体，配合逐点选取无零坐标的格向量，给出极限测度的普通球界 \(\mu(xB(r))\le C_\Omega r^n\)。

最后熵与分类收尾。\(A_n\) 维数为 \(n-1\) 而球指数为 \(n\)，多出的一维压迫出正熵：双侧管道邻域可被 \(O(r^{-(n-1)})\) 个 \(r\)-球覆盖，故管道质量为 \(O(e^{-\lambda t})\)，由 ELMV 熵判据得 \(h_\xi(a(1))\ge\lambda/3\)。关键强化在于对被极限有限倍控制的每个不变概率都给出正熵，经遍历分解即可排除正权重的零熵分量族；再用 Einsiedler–Katok–Lindenstrauss 的素数维测度分类——正熵的 \(A_n\)-遍历概率必为 Haar。于是所有子序列极限同为 \(m_n\)，紧性保证整列收敛且无质量逃逸。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准；OpenAI 官方声明，未经形式化的结果可能有问题。技术亮点在于各估计对固定 \(n\) 与任意序指数一致，并用 Stark 零点下降替代子凸性。同族两篇姊妹篇分别处理本原四次域的任意序环面束与本原六次域的极大序理想类束；偶数次数须另避二次子域，方法上与本文互补。

{% endraw %}
