---
layout: default
title: "Finite ordinary minimal model programs on compact Kähler fourfolds"
family: "056"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Finite ordinary minimal model programs on compact Kähler fourfolds

> 结果族 056：Termination of projective and Kähler fourfold minimal model programs　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

还是那台"化简机器"（极小模型纲领），但这次工作场地从铺好坐标网的射影空间，搬进了更幽暗的紧 Kähler 世界：那里没有全局代数坐标，射影情形惯用的计数工具集体失灵。论文证明：在四维 Kähler 场地上，每步任选一条负射线的化简程序必定停机，而且终点只有两种好结局。

**关键词卡片**

- 紧 Kähler 流形（compact Kähler manifold）：比射影簇更大的一类复空间，局部像复平面、整体能测"面积"
- 极小模型纲领（minimal model program）：反复收缩最负方向来化简空间的流水线
- 极端射线（extremal ray）：藏在空间里最"负"的方向，化简沿它进行
- nef（numerically effective）：伴随除子不再与任何曲线负相交的安稳状态
- Mori 纤维空间（Mori fibre space）：另一种终点——整个空间化成一束低维纤维

**看个具体例子**

停机的理由一半可以数出来：空间里三维"循环类"撑出的维数 c₃，每次除子收缩都严格下降（翻转则不变），所以除子型手术只能做有限次；剩下的无穷翻转尾巴再由同族姊妹篇的定理排除。终点是谁，由伴随除子 K+Δ 是否伪有效决定。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <defs>
    <marker id="ar" markerWidth="8" markerHeight="8" refX="6" refY="3" orient="auto">
      <path d="M0,0 L7,3 L0,6 z" fill="#34506e"/>
    </marker>
  </defs>
  <rect x="30" y="28" width="82" height="40" rx="8" fill="#eef3fb" stroke="#34506e" stroke-width="2"/>
  <text x="71" y="53" text-anchor="middle" font-size="14" fill="#1a2433">(X0,Δ0)</text>
  <rect x="152" y="28" width="82" height="40" rx="8" fill="#eef3fb" stroke="#34506e" stroke-width="2"/>
  <text x="193" y="53" text-anchor="middle" font-size="14" fill="#1a2433">(X1,Δ1)</text>
  <text x="266" y="54" text-anchor="middle" font-size="16" fill="#1a2433">⋯</text>
  <rect x="300" y="28" width="82" height="40" rx="8" fill="#eef3fb" stroke="#34506e" stroke-width="2"/>
  <text x="341" y="53" text-anchor="middle" font-size="14" fill="#1a2433">(Xn,Δn)</text>
  <path d="M 112,48 L 150,48" stroke="#34506e" stroke-width="2" marker-end="url(#ar)"/>
  <path d="M 234,48 L 298,48" stroke="#34506e" stroke-width="2" marker-end="url(#ar)"/>
  <path d="M 341,68 C 341,110 240,115 165,138" stroke="#34506e" stroke-width="2" fill="none" marker-end="url(#ar)"/>
  <path d="M 341,68 C 341,110 440,115 470,138" stroke="#34506e" stroke-width="2" fill="none" marker-end="url(#ar)"/>
  <rect x="40" y="142" width="205" height="62" rx="8" fill="#eefbef" stroke="#3a7d44" stroke-width="2"/>
  <text x="142" y="166" text-anchor="middle" font-size="13" fill="#1f4a26">K+Δ 伪有效</text>
  <text x="142" y="188" text-anchor="middle" font-size="13" fill="#1f4a26">终于 nef 模型</text>
  <rect x="320" y="142" width="205" height="62" rx="8" fill="#fdf6e8" stroke="#b07a2a" stroke-width="2"/>
  <text x="422" y="160" text-anchor="middle" font-size="13" fill="#5a4212">非伪有效：Mori 纤维空间</text>
  <line x1="345" y1="172" x2="500" y2="172" stroke="#b07a2a" stroke-width="2"/>
  <line x1="360" y1="170" x2="360" y2="196" stroke="#b07a2a" stroke-width="2"/>
  <line x1="395" y1="170" x2="395" y2="196" stroke="#b07a2a" stroke-width="2"/>
  <line x1="430" y1="170" x2="430" y2="196" stroke="#b07a2a" stroke-width="2"/>
  <line x1="465" y1="170" x2="465" y2="196" stroke="#b07a2a" stroke-width="2"/>
  <text x="280" y="234" text-anchor="middle" font-size="13" fill="#1a2433">除子收缩次数受计数控制：c3 逐次严格下降（示意 12 → 9 → 6）</text>
  <text x="280" y="258" text-anchor="middle" font-size="13" fill="#445368">每个中间模型都保持：正规 + 紧 Kähler + klt + 整体 Weil ℚ-因子化</text>
</svg>

</div>

**为什么值得关心**

四维终止性由此从"射影且伴随除子有效"的特殊情形，推进到一般紧 Kähler 有理 klt 配对，是复几何版极小模型纲领的关键落子。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了紧 Kähler 四维 klt 配对上任何极大普通负射线极小模型程序都终止：伴随除子 `@@M@@K_X+\Delta@@` 伪有效时终于 nef 模型，否则终于射影 Mori 纤维空间。四维 MMP 的终止性由此从"射影且伴随除子有效"的特殊情形推进到一般紧 Kähler 有理 klt 配对。

## 问题背景

极小模型程序（minimal model program, MMP）逐条收缩伴随除子 `@@M@@D=K_X+\Delta@@` 为负的极射线（extremal ray），必要时做翻转（flip），把簇换成 `@@M@@D@@` 越来越正的双有理模型。单步的存在与整条程序的终止性（termination）是两个难题，高维终止性至今没有一般解答。复几何情形更难：空间只是紧 Kähler（compact Kähler）而非射影，没有整体丰富线丛作极化，射影情形依赖的计数式论证大量失效。此前最好结果：Höring–Peternell 对非 uniruled（不被有理曲线覆盖）的紧 Kähler 三维簇造出极小模型；Das–Hacon–Păun 处理了 `@@M@@D@@` `@@M@@\mathbb{Q}@@`-线性等价于有效除子的四维紧 klt 情形。卡点在于：无整体极化时负射线可以是超越的、flip 所需的整体代数有限生成没有着落、终止性缺乏可用的有限计数。另有一个范畴陷阱：整体 Weil `@@M@@\mathbb{Q}@@`-因子化（每个整体素 Weil 除子均 `@@M@@\mathbb{Q}@@`-Cartier）不同于逐点解析局部 `@@M@@\mathbb{Q}@@`-因子化，即便对射影簇也不同（文末附录给出光滑射影反例），本文全程维护这一区分。

## 主要结果

主定理（普通程序的终止性）：设 `@@M@@X@@` 为正规、整体 Weil `@@M@@\mathbb{Q}@@`-因子化的紧 Kähler 四重簇（fourfold），给定典范 Weil 除子 `@@M@@K_X@@`，`@@M@@\Delta\geq0@@` 为有理除子且 `@@M@@(X,\Delta)@@` 是 klt 配对。则从 `@@M@@(X,\Delta)@@` 出发、每步取 `@@M@@D@@`-负极射线的任意极大普通程序终止，得到有限链 `@@M@@(X,\Delta)=(X_0,\Delta_0)\dashrightarrow\cdots\dashrightarrow(X_n,\Delta_n)@@`；每个 `@@M@@X_i@@` 保持正规、紧 Kähler、整体 Weil `@@M@@\mathbb{Q}@@`-因子化，每个 `@@M@@(X_i,\Delta_i)@@` 保持 klt 且 `@@M@@D_i=K_{X_i}+\Delta_i@@` 为 `@@M@@\mathbb{Q}@@`-Cartier。终点二选一：（i）`@@M@@D@@` 伪有效（pseudo-effective）时 `@@M@@D_n@@` nef，复合映射不提取素除子，且对数差异（log discrepancy）满足 `@@M@@a(E;X,\Delta)\leq a(E;X_n,\Delta_n)@@`，对被收缩的素除子严格；（ii）`@@M@@D@@` 非伪有效时存在射影满态射 `@@M@@g:X_n\to S@@`，其中 `@@M@@S@@` 正规紧 Kähler、`@@M@@\dim S<4@@`、`@@M@@\rho(X_n/S)=1@@`、`@@M@@-D_n@@` 为 `@@M@@g@@`-ample，即 Mori 纤维空间（Mori fibre space）。每个负收缩（含 `@@M@@g@@`）的相对 Bott–Chern 维数为一；强整体 `@@M@@\mathbb{Q}@@`-因子化若初始成立则全程保持；只指定典范有理线丛的内蕴表述同样成立，且第一个模型就是 `@@M@@X@@` 本身。文中明确：伪有效情形只断言 nef，不做丰度（abundance）断言。

## 证明思路

证明分三步：先保证每一步能走，再证明每类步骤只有有限个，最后识别终点。

第一步解决单步存在。对每个 `@@M@@D@@`-负极射线 `@@M@@R@@`，由广义锥定理（Hacon–Xie）与紧切片上的极值论证，在 `@@M@@R^\perp@@` 中造出带 Kähler 余量的支撑类 `@@M@@\alpha@@`：`@@M@@\alpha@@` nef、`@@M@@\NA(T)\cap\alpha^\perp=R@@`、`@@M@@\alpha-c_1(D)@@` Kähler。再证"支撑收缩"命题（对维数归纳的断言 `@@M@@\mathsf B_d@@`，一直做到 `@@M@@d=4@@`）：这样的 `@@M@@\alpha@@` 必是某收缩 `@@M@@f:T\to Z@@` 的拉回 `@@M@@f^*\gamma@@`。关键新工具是整数下降引理：双有理收缩下数值平凡的线丛无需额外张量幂即整体下降为线丛，从而保住 Cartier 指标。于是有理伴随除子本身给出全局相对极化（证明 `@@M@@f@@` 射影、`@@M@@-D@@` 相对丰富），小收缩时给出整体 flip 代数 `@@M@@\bigoplus_{m\ge0}f_*\cO_T(mrD)@@`，其相对 Proj 就是翻转，新空间继承全部范畴性质。广义配对只在锥定理与自由点定理处进入，程序每一步都是普通的。

第二步排除无穷。Borel–Moore 局部化给出"循环类损失"引理：紧 Kähler 空间上 `@@M@@k@@` 维紧解析循环张成空间的维数 `@@M@@c_k@@` 有限；不提取除子的双有理变换保持 `@@M@@c_3@@`，而除子收缩使其严格下降（例外除子的类被 Kähler 形式的三次方积分为正检测）。因此除子型步骤只有有限个，无穷尾必全为 flip；这样的尾巴被同族姊妹篇的广义 log canonical flip 序列终止定理（取零 nef 部分）排除。姊妹篇所用的低差异位点、相对程序、提取与特殊终止等结果恰由本文后续章节独立证明，且支撑收缩的归纳不反过来使用主定理，逻辑无环。

第三步识别终点。在公共分解上每步满足 `@@M@@p^*D=q^*D'+F@@`（`@@M@@F\geq0@@`），正电流的拉回与下降说明伪有效性沿程序不变；Mori 纤维空间上相对反丰富的伴随除子不伪有效（把正电流限制到位势有限点处的纤维曲线即得矛盾）；而 nef 蕴含伪有效。两个终点枝由此严格互斥。辅助构件还包括：固定一个 Kähler 类作缩放方向的程序（阈值处的步骤 crepant，差异随参数线性插值，保持广义 klt），以及把 Kawamata–Matsuda–Matsuki 与 Fujino 的四维 terminal 翻转差异计数论证（含 Fujino 勘误的低差异位点处理）移植到紧 Kähler、实边界情形。

## 可信度与备注

两版手稿均无形式化证明，按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。本批实为同一论文的两个修订，共享同一输出路径：2026-09-24 版证"存在一条有限普通程序"（Birkar 极限扰动策略），2026-10-05 版加强为"每个极大程序终止"，本文以更强的新版为准。族内互撑：本文为姊妹篇提供低差异位点、相对程序、提取、特殊终止等输入，姊妹篇反过来排除本文的无穷 flip 尾巴，依赖关系无环。

{% endraw %}
