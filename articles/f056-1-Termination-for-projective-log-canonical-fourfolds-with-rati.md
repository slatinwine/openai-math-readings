---
layout: default
title: "Termination for projective log canonical fourfolds with rational boundary"
family: "056"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Termination for projective log canonical fourfolds with rational boundary

> 结果族 056：Termination of projective and Kähler fourfold minimal model programs　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了特征零代数闭域上带有效有理边界的射影 log canonical 四重折叠的任意"许可"极小模型纲领必终止：允许任意负极端射线选择与混合双有理步骤，不假设 \(\Q\)-因子化或伪有效性，且每条负射线都有所需的收缩与正模型。

## 问题背景
极小模型纲领（minimal model program, MMP）通过除子收缩与翻转（flip）化简射影簇，期望终点是伴随除子 \(K_X+B\) 为 nef 的极小模型或 Mori 纤维化。存在性保证"能走"，终止性（termination）保证"走得完"；后者强于单个极小模型的存在，也强于某个带缩放程序的终止。四维已有结果各带限制：Shokurov 的有序终止法与 Birkar 的 klt 简证只覆盖被选定的程序；Kawamata–Matsuda–Matsuki 的终端、Fujino 的典范情形奠定差异（discrepancy）计数加曲面类下降的路线；Alexeev–Hacon–Kawamata 的加权难度需要 \(-(K_X+B)\) 数值有效；Chen–Tsakanikas 与 Moraga 的 lc 定理要求伪有效；Han–Liu–Zhuang 处理大边界 klt。普通 lc 四重折叠在无任何有效性假设下的任意终止一直是缺口，本文补上它，并允许模型非 \(\Q\)-因子化、允许"除子收缩后再接小修正"的混合步骤。

## 主要结果
主定理：设 \(k\) 为特征零代数闭域，\((X,B)\) 是带有效有理边界的四维射影 log canonical（lc）配对，不假设 \(\Q\)-因子化或伪有效性，则：(i) 每个阶段每条 \(D_i=K_{X_i}+B_i\)-负极端射线都有具正规射影靶、连通纤维、相对 Picard 数为一的收缩，且当其为双有理时存在许可的正模型；(ii) 从 \((X,B)\) 出发的每个许可程序——逐步任意选择负射线，步骤可为除子收缩、翻转或混合步骤——只有有限个双有理步；(iii) 每个极大程序终止于 nef 伴随的 lc 配对或 Mori 纤维化。证明先在 \(\mathbb C\) 上完成（分支估计用到拓扑），再把完整结论转移到任意特征零代数闭域。

## 证明思路
证明把终止化归为辅助终端模型上的数值问题，分五层推进。先用除子循环类的秩消去一切损失除子的步骤（含混合步），剩下的 klt 小尾巴提升为一串 crepant 终端连接点（terminal junctions），相邻连接点由提取系数的下降加一段有限小步骤连接；同一有限边界标签集贯穿全链，而曲面极小对数差异的 ACC 定理把系数仍在变化的标签限制在映到曲线或点的除子上。其次构造加权难度 \(\mathcal D\)：以天花板权重 \(w(u)=\lceil N\max\{u,0\}\rceil\) 统计对数差异低于二的赋值（\(N\) 只需清除初始与固定系数），在每个曲面处先局部扣除单标签上反复爆破形成的"默认"贡献再求和，并补上边界正规化上的除子循环秩；初等天花板不等式 \(\lceil x_1+\cdots+x_r\rceil\geq\sum\lceil x_j\rceil-(r-1)\) 表明 \(r\) 个变化分支带来的可能亏损恰为 \(r-1\)。第三，关键的分支估计定理为这笔亏损付账：它用 Deligne 混合 Hodge 理论、Beilinson–Bernstein–Deligne–Gabber 分解定理及 Saito 的 Hodge 模加细给出权与支撑估计，分离出奇曲线上的刺破度二局部系统；有限单径（monodromy）与范数把不变类实现为曲线原函数域上的线丛，Grothendieck 存在性定理与 Artin 逼近再将其延拓到剩余域不变的尖点 étale 邻域；小模型上的次数便给出原函数域中互异、零边界对数差异为二的除子赋值。这些项已是 \(\mathcal D\) 中的正项，故 \(\mathcal D\) 在连接点非负；正规化秩与分支默认之间的精确抵消使 \(\mathcal D\) 单调不增；正侧坏曲面经由整值缩放亏损跨过天花板阈值迫使 \(\mathcal D\) 单位下降，只能有限次，随后第二轮循环秩比较与图维数界完成 klt 终止。第四，把结论从 klt 传到 lc：先用 Fujino 的 dlt 特殊终止（依赖至多三维的经典 log MMP），对每个指定的楼下小尾巴取 crepant \(\Q\)-因子化 dlt 修改，在收缩基上运行初等 dlt 步骤直至相对 nef——垂直射线引理保证每步收缩绝对极端射线且保持双有理，负曲线的负多重截面保证"桥"非空，两端引理把终点等同于指定正模型的 crepant 提升——拼接所有桥即与 dlt 终止矛盾。连续性（构造混合步的正模型）由 Fujino 的 lc 锥与收缩定理加 Birkar 的有理补充对（complemented pair）定理给出好 log 极小模型，图支撑论证证明其半丰富模型的靶对基是小映射且边界恰为严格变换。最后是域转移：整个可数假想程序连同全部射线选择下降到一个可数子域并嵌入 \(\mathbb C\)，数值延拓引理（展铺加特化）保持数值空间与曲线锥；存在性则逐个有限图转移，固定极化类保证特化后收缩的仍是同一射线。

## 可信度与备注
本文主结果暂无 Lean 形式化证明，请以社区核验为准。它是本族另两篇 Kähler 姊妹篇的代数母体：广义 log canonical Kähler 一文的连接点构造、难度定义与分支界的正规化、参数化方法均显式改编自本文对应章节；广义典范 Kähler 一文则对应本文的 Fujino 式见证计数路线。文中端点处的丰度与补结论另引同系列文章，且终止证明本身独立于这些相伴结果。按 OpenAI 官方声明，未经形式化的结果可能有问题，读者宜以同行评议为最终标准。

{% endraw %}
