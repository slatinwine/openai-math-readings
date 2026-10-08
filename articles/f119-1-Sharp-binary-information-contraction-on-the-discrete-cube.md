---
layout: default
title: "Sharp binary-information contraction on the discrete cube"
family: "119"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Sharp binary-information contraction on the discrete cube

> 结果族 119：The Courtade–Kumar and Hellinger conjectures　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

你把 8 个开关的状态拍照发给朋友，传输通道会随机把某些位翻转。哪种"读数总结"在噪声后保真度最高？直觉说：干脆只转发第 1 个开关——看似偷懒，信息反而保得最全。这篇论文证明这个直觉在任意维度、任意噪声强度下都严格成立。

**关键词卡片**

- 离散立方体（discrete cube）：所有 `@@M@@n@@` 位 `@@M@@\pm1@@` 字符串构成的空间。
- 互信息（mutual information）：收到观测后，对原始信息还剩多少确定度。
- 二元对称信道（binary symmetric channel）：每个比特独立地以概率 `@@M@@\varepsilon@@` 翻转。
- 独裁函数（dictatorship）：只读一个坐标的函数 `@@M@@f(x)=x_i@@`。
- 噪声算子（noise operator `@@M@@T_\rho@@`）：把函数平均到含噪版本的工具。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="40" y="32" font-size="15">原始信号 X（8 位）</text>
  <rect x="40" y="42" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="100" y="42" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="160" y="42" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="220" y="42" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="280" y="42" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="340" y="42" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="400" y="42" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="460" y="42" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <text x="62" y="71" text-anchor="middle" font-size="15">1</text>
  <text x="122" y="71" text-anchor="middle" font-size="15">1</text>
  <text x="182" y="71" text-anchor="middle" font-size="15">0</text>
  <text x="242" y="71" text-anchor="middle" font-size="15">1</text>
  <text x="302" y="71" text-anchor="middle" font-size="15">0</text>
  <text x="362" y="71" text-anchor="middle" font-size="15">1</text>
  <text x="422" y="71" text-anchor="middle" font-size="15">1</text>
  <text x="482" y="71" text-anchor="middle" font-size="15">0</text>
  <line x1="533" y1="95" x2="533" y2="145" stroke="#333" stroke-width="2"/>
  <polygon points="533,150 527,138 539,138" fill="#333"/>
  <text x="40" y="122" font-size="14">噪声信道：每位独立地以概率 ε 翻转</text>
  <rect x="40" y="152" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="100" y="152" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="160" y="152" width="45" height="45" fill="#fdd" stroke="#333" stroke-width="2"/>
  <rect x="220" y="152" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="280" y="152" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="340" y="152" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="400" y="152" width="45" height="45" fill="#fdd" stroke="#333" stroke-width="2"/>
  <rect x="460" y="152" width="45" height="45" fill="none" stroke="#333" stroke-width="2"/>
  <text x="62" y="181" text-anchor="middle" font-size="15">1</text>
  <text x="122" y="181" text-anchor="middle" font-size="15">1</text>
  <text x="182" y="181" text-anchor="middle" font-size="15">1</text>
  <text x="242" y="181" text-anchor="middle" font-size="15">1</text>
  <text x="302" y="181" text-anchor="middle" font-size="15">0</text>
  <text x="362" y="181" text-anchor="middle" font-size="15">1</text>
  <text x="422" y="181" text-anchor="middle" font-size="15">0</text>
  <text x="482" y="181" text-anchor="middle" font-size="15">0</text>
  <text x="40" y="224" font-size="13">浅红格 = 被翻转的位（第 3、7 位）</text>
  <text x="40" y="252" font-size="14">独裁函数 f(x) = x₁：只读第 1 位，保住的信息仍最多</text>
</svg>

</div>

公式卡（数字版定理）：`@@M@@I(f(X);Y)\le 1-h_2(\varepsilon)@@`，`@@M@@f=\pm x_i@@` 取等。代入 `@@M@@\varepsilon=0.1@@`：`@@M@@h_2(0.1)\approx0.469@@`，任何布尔函数最多保住约 `@@M@@0.531@@` 比特——转发单个开关恰好做到。论文更强：对任意随机化的"软"摘要 `@@M@@u@@` 也有锐利收缩界 `@@M@@I(T_\rho u)\le\psi(|\rho|\,\psi^{-1}(I(u)))@@`，坐标仍取等。

**为什么值得关心**

Courtade–Kumar 猜想自 2013 年起横亘在信息论与布尔函数分析之间，此前只在平衡函数、高噪声区等部分范围成立。卡壳的根源是经典对数索博列夫不等式只给线性的熵产生率，缺一块非线性比较不等式；本文用两条熵容量轮廓加上"拼接代价"的显式三点优化补上缺口，再沿维数归纳与噪声半群积分收官，还附赠保留输出熵的加细版本。

> 已 Lean 形式化

## 一句话结论

本文证明了 Courtade–Kumar 猜想：在独立均匀比特的全体布尔函数中，单个坐标（独裁函数）在独立比特翻转噪声下保留的互信息最多；更强的"软信道"锐利收缩定理对任意随机化二进制摘要给出比较界，并附依赖均值的熵产生加细。

## 问题背景

设 `@@M@@X@@` 均匀分布在 `@@M@@n@@` 维离散立方体 `@@M@@\{-1,1\}^n@@` 上，每个比特经独立的二元对称信道（binary symmetric channel）以概率 `@@M@@\varepsilon@@` 翻转，得到 `@@M@@Y@@`。Courtade 与 Kumar 在 2013–2014 年提出猜想：哪个布尔函数 `@@M@@f@@` 的 `@@M@@f(X)@@` 与 `@@M@@Y@@` 的互信息（mutual information）最大？猜测的答案是看似最平凡的单个坐标 `@@M@@f(x)=x_i@@`，且在任意维度、任意噪声水平下都最优。该问题横跨信息论与布尔函数分析，此前只在平衡函数、高噪声区、`@@M@@\rho\le0.914@@` 等部分范围被证明（Samorodnitsky、Yu、Javanmard–Woodruff 等）。卡壳的根源在于：经典对数索博列夫不等式（logarithmic Sobolev inequality）只给线性熵产生率 `@@M@@2I@@`，其上的非线性剩余需要一个纯信息量轮廓无法满足的局部比较不等式。

## 主要结果

论文把对象扩到"软二进制信道"（soft binary channel）：辅助符号 `@@M@@U@@` 满足 `@@M@@\mathbb E[U\mid X]=u(X)@@`，`@@M@@u:\{-1,1\}^n\to[-1,1]@@`，即任意随机化二进制摘要。记均值 `@@M@@r@@` 的符号的二元熵为 `@@M@@H(r)@@`、熵亏损（entropy deficit）`@@M@@\psi(r)=\log 2-H(r)@@`，`@@M@@I(u)=I(U;X)@@`，`@@M@@T_\rho@@` 为噪声算子。

定理（锐利软信道收缩）：对一切 `@@M@@n\ge0@@`、一切 `@@M@@u@@` 与 `@@M@@-1\le\rho\le1@@`，
`@@M@@DI(T_\rho u)\le\psi\big(|\rho|\cdot\psi^{-1}(I(u))\big),@@`
且软坐标 `@@M@@u(x)=a x_i@@`（`@@M@@|a|\le1@@`）取等。直观地说：与 `@@M@@u@@` 信息量相同的"公平软坐标"，其有效振幅 `@@M@@\psi^{-1}(I)@@` 在噪声下至少以坐标的速度指数收缩；锐利性是就固定初始信息量的一切软信道而言。

推论（带输出偏置的布尔界）：布尔函数 `@@M@@f@@`、均值 `@@M@@m=\mathbb E f@@` 时，
`@@M@@DI(f(X);Y)\le\psi(|\rho|\,r_m)\le\psi(|\rho|),\qquad r_m=\psi^{-1}(H(m)),@@`
比特单位下即 `@@M@@I(f(X);Y)\le1-h_2(\varepsilon)@@`——这正是 Courtade–Kumar 猜想，且第一条不等式保留了输出熵 `@@M@@H(m)@@` 的加细。论文还证明了更强的均值依赖熵产生定理：`@@M@@D(g)\ge\max\{\mathcal B_m(I(g)),F(I(g))\}@@`。

## 证明思路

骨架是 Chen–Gohari–Nair 的"局部到全局"方案：先证局部熵产生不等式，再沿立方体维数归纳，最后沿噪声半群积分。熵流恒等式 `@@M@@\frac{d}{dt}I(P_tg)=-D(g)@@`（其中 `@@M@@D(g)=\mathbb E[V(g)Ng]@@`，`@@M@@V=\operatorname{atanh}@@`，`@@M@@N@@` 为噪声生成元）把目标化为证 `@@M@@D(g)\ge F(I(g))@@`，而 `@@M@@F(\psi(r))=rV(r)@@` 恰是软坐标的产生率。

难点在于：纯信息轮廓 `@@M@@F@@` 的局部比较对某些耦合律失效（Chen–Gohari–Nair 注记 5），必须把均值一并保留。于是引入第二条轮廓 `@@M@@\mathcal B_m@@`——把信息量在两个"容量"之间分配：容量 `@@M@@c_m=H(m)-(1-m^2)\log 2@@` 按线性率 2 支付，剩余容量 `@@M@@(1-m^2)\log 2@@` 按坐标的精确率支付。

先沿一条坐标把立方体切成两半，能量恰好分解为两面内部产生之和加上"拼接代价" `@@M@@\mathbb E\,c(g_+,g_-)@@`，其中 `@@M@@c(a,b)=\frac{a-b}{4}[V(a)-V(b)]@@`。归纳步骤要求拼接边支付轮廓的增量，于是归结为一个"局部拼接问题"：在固定两个子均值与平均条件熵的约束下最小化拼接代价。作者给熵定价（拉格朗日乘子 `@@M@@p\ge0@@`），利用归一化熵的正项级数证明严格凸性，解出显式三点优化子：一个有序内部点对 `@@M@@(x,y)@@`，加上可能的两个相同输出角点 `@@M@@(1,1)@@`、`@@M@@(-1,-1)@@`，并用仿射支撑不等式完成全局最优性认证。优化子只有两种几何：低熵时是反射核 `@@M@@(r,-r)@@`，高熵时是单角点形态，两者在阈值 `@@M@@e_0=(1-m)H(\delta/(1-m))@@` 处衔接。

付款分两笔。第一笔是确定性容量比较，即方差加细的一比特不等式 `@@M@@D\ge(1-m^2)F(J/(1-m^2))@@`，用尺寸偏置（size-biased）后验信息表示加 Jensen 不等式证明，用于支付内部核。第二笔是"公共输出稀释"：向拼接律中加入相同输出（如 `@@M@@(1,1)@@`）时，所需付款至少按保留质量成比例缩小；其证明是 Euler 型微分恒等式加曲率界 `@@M@@F''\le M/(L-I)^2@@`（`@@M@@M=4L^2/3@@`，`@@M@@2>3M@@`），其中一个关键多项式的非负性由显式分解认证。最后取两轮廓的最大值 `@@M@@\widehat{\mathcal B}_m=\max\{\mathcal B_m,F\}@@`：信息量超过一半时 `@@M@@\mathcal B_m\ge F@@` 自动成立；不足一半时需求 `@@M@@F(I)-F(j)@@` 随公共均值严格递增，于是把反射核沿保代价路径推到单角点"墙壁"，由同一条稀释定理支付。维数归纳给出锐利产生定理；在振幅坐标 `@@M@@r=\psi^{-1}(I)@@` 下不等式化为 `@@M@@r'\le-r@@`，积分即得收缩定理，布尔情形因 `@@M@@I(f)=H(m)@@` 直接给出推论。

## 可信度与备注

本篇主结果已由 Lean 形式化。同族姊妹篇《Hellinger contraction with arbitrary Boolean output bias》从平方根轮廓独立证明 Hellinger 猜想并推出同一 Courtade–Kumar 界，两篇互相印证；本篇还与 Chen 等人 2026 年计算机辅助路线的产生轮廓做了比较：近容量处 `@@M@@\mathcal B_m/C_m\to1+m>1@@`，本篇轮廓更强。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇已有形式化证明，置信度较高。

{% endraw %}
