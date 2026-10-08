---
layout: default
title: "Self-dual random-cluster interfaces below one"
family: "223"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Self-dual random-cluster interfaces below one

> 结果族 223：Random-cluster interfaces: critical, disordered, thermal, and natural-time scaling　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

还是那个方格"连边"游戏，但把团块偏好的旋钮拧到 q<1：现在团块之间互相嫌弃，越大越不受欢迎。此前关于这类游戏的全部证明都偷偷借用了"好事扎堆"的直觉（正相关），q<1 时它彻底失效。这篇论文在没有这块地基的废墟上重建整套工具，证明分界线照样收敛到那条著名的随机曲线。

**关键词卡片**

- 随机簇模型（random-cluster model）：方格连边模型；q<1 是团块互相排斥的"反社交"区域。
- 自对偶点（self-dual point）：模型与自己的镜像重合的边概率 `@@M@@p=\sqrt q/(1+\sqrt q)@@`，恰为临界位置。
- FKG 正相联（positive association）："好事扎堆出现"的性质，q≥1 才有，q<1 时失效。
- 探索界面（Dobrushin interface）：两种边界待遇之间的分界曲线。
- SLE（Schramm–Loewner evolution）：布朗运动驱动的随机曲线；κ∈(6,8) 时比渗流的 SLE₆ 更"暴躁"，还会自我触碰。

**看个具体例子**

定理的数字版：`@@M@@\kappa(q)=\dfrac{4\pi}{\arccos(-\sqrt q/2)}@@`，代入 `@@M@@q=\tfrac14@@` 得 `@@M@@\kappa\approx6.89@@`；令 `@@M@@q\to0@@` 得 `@@M@@\kappa\to8@@`，正接上生成树界面的 SLE₈（已知老结果）；令 `@@M@@q\to1^-@@` 得 `@@M@@\kappa\to6@@`，与渗流的 SLE₆ 无缝相接。加上姊妹篇的 1≤q<4，全区间 0<q<4 拼成一条完整的 κ 曲线。

**为什么值得关心**

它补齐了 Rohde–Schramm 猜想缺失的 q<1 半段，而且是在"正相关失效"这一无地基条件下完成的，工具箱本身即是一大突破。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
对每个 `@@M@@0<q<1@@`，论文证明方格随机簇模型在自对偶点的 Dobrushin 界面收敛到 `@@M@@\kappa\in(6,8)@@` 的 chordal `@@M@@\SLE_\kappa@@`；在 FKG 正相联失效的条件下从零重建交叉比较工具，补齐了 Rohde–Schramm 预言的 `@@M@@q<1@@` 半段。

## 问题背景
随机簇模型的簇权重 `@@M@@q\ge1@@` 时满足 FKG 不等式（正相联，positive association），RSW 型交叉估计与随机比较随之可用，这是 `@@M@@1\le q\le4@@` 已有成果的共同地基。当 `@@M@@0<q<1@@`，正相联失效：Beffara–Duminil-Copin 的临界点识别、Duminil-Copin–Sidoravicius–Tassion 的连续性与交叉估计都不再适用；无穷体积层面只有 Glazman–Lammers 的自对偶 Gibbs 测度与 Klausen–Kravitz 的非共存等零星结果，自对偶点是否为无穷体积临界点本身都无定论。Rohde–Schramm 的界面猜想（Conjecture 9.7）与 Schramm 的公开问题都覆盖全部 `@@M@@0<q<4@@`，而 `@@M@@q<1@@` 半段此前没有任何严格收敛结果。本文的策略是绕开无穷体积理论，直接对有限域的自对偶律证明界面标度极限；另一端点 `@@M@@q=0@@` 的 spanning tree 界面（LSW 定理，`@@M@@\SLE_8@@`）则早已闭合。

## 主要结果
主定理（Theorem thm:main）：固定 `@@M@@q\in(0,1)@@`，记 `@@M@@d=\sqrt q=2\cos\lambda@@`、`@@M@@\rho=\lambda/\pi\in(1/3,1/2)@@`、`@@M@@\kappa=4\pi/\arccos(-\sqrt q/2)\in(6,8)@@`。设 `@@M@@D@@` 为边界光滑的有界 Jordan 域，`@@M@@a,b@@` 为其边界上不同点；格点逼近是带标记顶点的简单闭多边形，边界参数化一致收敛到 `@@M@@D@@` 的参数化。取一段边界弧 wired（含端点）、其余顶点单点，此时该有限律的 medial 探索线 `@@M@@\eta_\delta@@` 在模递增重参数化的有向曲线度量中依分布收敛到 chordal `@@M@@\SLE_\kappa(D;a,b)@@`，且沿整个网格序列成立。推论（Corollary cor:full-fk-range）把它与姊妹篇的 `@@M@@1\le q<4@@` 定理合并：对全部 `@@M@@0<q<4@@`，在 `@@M@@p(q)=\sqrt q/(1+\sqrt q)@@` 处同一收敛陈述成立，参数同为 `@@M@@\kappa(q)=4\pi/\arccos(-\sqrt q/2)@@`。

## 证明思路
证明分四层，层层递进。第一层造出没有 FKG 的替代品：引入顶点变量的配分多项式，证明其负对数的非常系数全部非负（谱系上承 Sokal 的外场随机簇多项式、Jackson–Sokal 转述 Dong 的负参数 Tutte 定理与 Scott–Sokal 排斥气体原理）；对顶点求导得到连通多重集上的概率律，配合平面偶对偶给出邻接边的受限制比较与粘合不等式，从而建立矩形交叉估计。第二层做不规则圆盘局部化（localization）：对探索产生的裂缝域，沿直径递减的横截线下探，要么找到有界物理桥、要么找到对两墙都有清晰入口的路线，相邻分离横截线留出的未检查空间让被暴露的实际交叉得以延伸，得到纯网络与实际路径两类衰减定理。第三层是可观测值与边界问题：沿用四变换 open-cap 可观测值 `@@M@@h_\delta(z)@@`（闭合回路带权重 `@@M@@d=\sqrt q<1@@`），先在边界弧树上算出标记极限与侧线条件，再用有限六顶点传递矩阵与融合计算控制其有限差分，规范化靠周期六顶点压强定理（Duminil-Copin 等五人）；`@@M@@d<1@@` 使部分边界因子为负，作者把辅助插入放得充分近，令负贡献必须付出额外的反色交叉，从而被相对交叉损失压住。之后把多边形套进第二重匹配墙构造：闭合墙上小缺口后（正规范化下），两变量可观测值渐近分解为 `@@M@@h_\delta(z)J(u)@@`，两次带号估计分别消去边界值的多余项并控制混合差商；极限中外因子 `@@M@@J@@` 非常数，逼出 `@@M@@h@@` 全纯，辐角原理加 Schwarz–Christoffel 公式把连接概率定为超几何型积分 `@@M@@f(\chi)=I_C/(I_B+I_C)@@`。第四层移到移动边界：把固定多边形公式推进到部分探索后的裂缝域，在自由边界插入短 wired 区间，open-cap 律下条件配对概率是精确鞅；先取网格极限、换成有界表达式、再与原律比较、最后缩小区间，两个鞅测试定出 Loewner 驱动的漂移与二次变差（策略承自 LSW 的 spanning tree 工作），配合 Kemppainen–Smirnov 可避交叉判据得到曲线与驱动的联合紧性，最终识别整条有向曲线。

## 可信度与备注
本篇暂无形式化证明，请以社区核验为准。它与覆盖 `@@M@@1\le q<4@@` 的姊妹篇方法同源（同样的四变换观测值、配墙反射与鞅识别骨架），但概率输入全部重建以绕开 FKG；其推论把两篇合并成 `@@M@@0<q<4@@` 的完整定理。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
