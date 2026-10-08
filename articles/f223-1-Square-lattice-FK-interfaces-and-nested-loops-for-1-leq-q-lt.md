---
layout: default
title: "Square-lattice FK interfaces and nested loops for 1 <= q < 4"
family: "223"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Square-lattice FK interfaces and nested loops for 1 <= q < 4

> 结果族 223：Random-cluster interfaces: critical, disordered, thermal, and natural-time scaling　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

在一张巨大的方格纸上玩"连边"游戏：每条边按规则随机决定接通与否，接通的边把格子连成一个个团块。用一个旋钮 q 控制团块爱不爱扎堆，再在边界的两段设下不同待遇，中间自然出现一条蜿蜒的分界线。这篇论文证明：格子无限变细时，这条分界线收敛到一条著名的随机曲线 SLE，还顺带算出了游戏的各种临界指数。

**关键词卡片**

- 随机簇模型（random-cluster model）：统一的"连边"框架，q=1 是渗流，q=2 是 Ising 模型。
- 簇权重 q（cluster weight）：调节团块扎堆偏好的旋钮，1≤q<4 时临界行为最丰富。
- 探索界面（Dobrushin interface）：两种边界待遇相遇处自然生成的分界曲线。
- SLE（Schramm–Loewner evolution）：由布朗运动驱动的随机曲线族，κ 是它的"性格参数"。
- Cardy 公式（Cardy's formula）：矩形左右两边被连通的概率公式，共形不变性的标志性检验。

**看个具体例子**

代入数字：q=1（渗流）时 κ=6，q=2（Ising）时 κ=16/3，通式为 `@@M@@\kappa(q)=4\pi/\arccos(-\sqrt q/2)@@`。q=1 还给出方格版 Cardy 公式：交叉概率收敛到 `@@M@@\int_0^x[t(1-t)]^{-2/3}dt\big/\int_0^1[t(1-t)]^{-2/3}dt@@`，代入 `@@M@@x=1/2@@` 恰得 `@@M@@1/2@@`——左右交叉对半开，符合直觉的"体检"。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="26" font-size="15" fill="#333">方格探索界面：格子无限变细 → 收敛到 SLE</text>
  <rect x="150" y="50" width="260" height="200" fill="#f7f7f7" stroke="#333" stroke-width="2"/>
  <path d="M150,250 L410,250 L410,50" fill="none" stroke="#36c" stroke-width="7" opacity="0.3"/>
  <path d="M150,250 C180,228 205,192 235,180 C272,165 262,128 292,118 C322,108 345,88 410,50" fill="none" stroke="#c33" stroke-width="3"/>
  <circle cx="150" cy="250" r="7" fill="#333"/>
  <circle cx="410" cy="50" r="7" fill="#333"/>
  <text x="130" y="272" font-size="14" fill="#333">a</text>
  <text x="416" y="46" font-size="14" fill="#333">b</text>
  <text x="418" y="150" font-size="13" fill="#888">free 边界</text>
  <text x="30" y="230" font-size="13" fill="#36c">wired 边界</text>
  <text x="30" y="248" font-size="13" fill="#36c">（连成一片）</text>
  <text x="30" y="140" font-size="14" fill="#c33">界面 η</text>
  <line x1="70" y1="136" x2="142" y2="136" stroke="#c33" stroke-width="2" stroke-dasharray="4 3"/>
  <text x="428" y="220" font-size="13" fill="#555">κ(q)=4π/arccos(−√q/2)</text>
  <text x="428" y="240" font-size="13" fill="#555">q=1→SLE₆，q=2→SLE₁₆/₃</text>
</svg>

</div>

**为什么值得关心**

它证实了 Rohde–Schramm 2005 年的猜想在 1≤q<4 成立，把二十年来只有渗流、Ising 两个孤立端点的知识连成完整一段。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
对每个固定 `@@M@@1\le q<4@@`，论文证明方格上临界随机簇模型的 Dobrushin 界面收敛到 chordal `@@M@@\SLE_{\kappa(q)}@@`，全体嵌套回路收敛到 whole-plane `@@M@@\CLE_{\kappa(q)}@@`，并在 `@@M@@q=1@@` 时顺带得到方格键渗流的 Cardy 公式与临界指数，证实了 Rohde–Schramm 预言在该参数范围成立。

## 问题背景
随机簇模型（random-cluster model，Fortuin–Kasteleyn 表示）以簇权重 `@@M@@q@@` 把渗流（`@@M@@q=1@@`）、Ising（`@@M@@q=2@@`）与 Potts 模型纳入同一框架。传递矩阵与 Coulomb-gas 方法（Temperley–Lieb、Baxter 等）早已预言：方格自对偶点 `@@M@@p_q=\sqrt q/(1+\sqrt q)@@` 是临界的，界面的标度极限应为 Schramm–Loewner evolution（SLE），参数 `@@M@@\kappa(q)=4\pi/\arccos(-\sqrt q/2)\in(4,6]@@`。Rohde–Schramm（2005，Conjecture 9.7）与 Schramm 的公开问题集（Problem 2.6）将其列为猜想。严格已知的只有两个端点：Smirnov 证明的三角格点渗流收敛到 `@@M@@\SLE_6@@`，以及 Chelkak–Duminil-Copin–Hongler–Kemppainen–Smirnov 证明的 FK-Ising 收敛到 `@@M@@\SLE_{16/3}@@`；对一般 `@@M@@1\le q\le 4@@`，此前只有 Duminil-Copin 等五人的旋转不变性定理，极限曲线并未被识别。难点在于既要算出共形不变的连接概率，又要在随机探索挖出的移动区域里保持公式有效。

## 主要结果
主定理断言两件事。其一（界面）：任取有界 Jordan 域（Jordan domain）`@@M@@D@@` 与边界上不同两点 `@@M@@a,b@@`，在标记边界一致逼近的格点多边形下，wired/free Dobrushin 边界条件产生的探索界面 `@@M@@\eta_n@@` 在模递增重参数化的有向曲线度量中依分布收敛到从 `@@M@@a@@` 到 `@@M@@b@@` 的 chordal `@@M@@\SLE_{\kappa(q)}@@`，且沿整个网格序列收敛。其二（回路）：自由无穷体积律下所有嵌套 medial 回路（保留重复计数与遍历顺序）缩放后，在球面匹配拓扑中收敛到嵌套 whole-plane `@@M@@\CLE_{\kappa(q)}@@`，极限 Möbius 不变。其三（Cardy 公式）：`@@M@@q=1@@` 时包括边界键在内的所有键独立以概率 `@@M@@1/2@@` 采样，交叉概率收敛到 `@@M@@\int_0^x[t(1-t)]^{-2/3}\,\dd t\big/\int_0^1[t(1-t)]^{-2/3}\,\dd t@@`。推论还给出方格键渗流的临界指数：单臂 `@@M@@\pi_1(R)=R^{-5/48+o(1)}@@`、`@@M@@2k@@` 条交替臂 `@@M@@\pi_{2k}(r,R)=R^{-(4k^2-1)/12+o(1)}@@`，以及关联长度 `@@M@@\xi(p)=|p-\tfrac12|^{-4/3+o(1)}@@` 等热力学指数。

## 证明思路
全文的引擎是"四变换可观测值"（four-change observable）：在四段交替着色边界、四个端口开放的 open-cap 律下，给每条边界弧赋显式复权，其有限乘积和的期望定义 `@@M@@h_n(z)@@`。先在"边界弧树"上精确算出边界值：多数分支权重为零或两步相消，标记点取值由两个连接事件决定，对角残项用正倾侧测度与相对去耦估计消去。再证全纯性（holomorphicity）：把两份观测值贴在同一面墙的两侧，反复反射并叠加角衰减估计，得混合差商除以网格平方后趋零，分布意义下 `@@M@@\bar\partial h\cdot\partial_jJ=0@@`；外场 `@@M@@J@@` 非常数，逼出 `@@M@@\bar\partial h=0@@`。Schwarz–Christoffel 公式把极限识别为特定四边形上的共形双射，连接概率化为积分 `@@M@@f(\chi)=I_C/(I_B+I_C)@@`，`@@M@@q=1@@`（`@@M@@\rho=1/3@@`）时正是 Cardy 被积函数。然后从固定正交多边形转移到任意 Jordan 域：在同一格上同时画"更容易"与"更难"两个测试四边形，用 FK 单调性与实际路径夹逼目标概率。接着让公式在随机探索后依然成立：以原始开关律对历史平均六臂估计（six-arm estimate），构造避开候选连接点的有向障碍物，对齐两张图的比较坐标，得到停止时刻的条件公式。再由此导出 `@@M@@M_t(x)=(xg_t'(x)/(g_t(x)-W_t))^h@@` 是一致有界的近似鞅；两个测试点的凸性组合给出 `@@M@@\E[(W_\tau-W_\sigma)^2]\le C\,\E[\tau-\sigma]@@`，Itô 公式与 Lévy 刻把驱动过程识别为 `@@M@@\sqrt\kappa B_t@@`（`@@M@@\kappa=8/(1+h)@@`）。最后用 Aizenman–Burchard 型物理紧性排除沿边界滑动，用"小门"与 Miller–Wu 维数论证排除零容量区间上的额外游动，完成整条有序曲线的收敛；回路部分改用均匀墙剥离（peeling）构造分支探索树，匹配分支 SLE 的构造，绕圈信息定出回路标签，再用逃逸估计把收敛升级为保留重数的球面匹配收敛。

## 可信度与备注
本篇与另外两篇姊妹篇同属结果族 223："Self-dual random-cluster interfaces below one"覆盖 `@@M@@0<q<1@@`，其推论直接引用本篇定理，合并出 `@@M@@0<q<4@@` 的完整区间；"Quenched SLE Universality"则在 `@@M@@q=2@@` 上加入固定强度无序仍得 `@@M@@\SLE_{16/3}@@`。三篇共用"四变换可观测值+鞅识别驱动"的骨架，互相印证方法的稳健性。三篇均暂无形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
