---
layout: default
title: "Abundance after nonvanishing for compact Kähler fourfolds"
family: "034"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Abundance after nonvanishing for compact Kähler fourfolds

> 结果族 034：Log abundance for compact Kähler spaces under logarithmic Iitaka subadditivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一个蓄水系统，只要"水位对每条水渠都不欠账"（nef），而且历史上真的存进过一滴水（某个倍数有非零截面），就能开闸灌溉整片田——截面处处生成，给出真正的映射（半丰富）。论文在四维的解析世界（紧 Kähler，可以不是射影的）里证明这台水泵一定开得动；水位档位为零时结论更强：整条水渠干脆是平的，线丛本身平凡。

**关键词卡片**

- 紧 Kähler 空间（compact Kähler）：比射影簇更广的解析形状，可能没有足够的整体多项式函数
- nef（analytically nef）：与每条曲线相交都不负的温和正性，这里是解析版本
- 半丰富（semiample）：某个正倍数的截面处处生成，从而定义到射影空间的映射
- Iitaka 维数（Iitaka dimension）：截面数随次数增长的速度档位
- klt（Kawamata log terminal）：奇点温和度等级

**看个具体例子**

难点和新点都在 `@@M@@\kappa=0@@`：手里只有一个非零截面 `@@M@@s_0@@`，直觉上它可能在某些点"归零"。定理证明这不可能——`@@M@@s_0@@` 必处处非零，于是它直接把线丛平凡化。数字版结论：`@@M@@\kappa(X,K_X+\Delta)=0@@` 时 `@@M@@\mathcal O_X(m(K_X+\Delta))\simeq\mathcal O_X@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><ellipse cx="150" cy="110" rx="90" ry="52" fill="none" stroke="#4a6fa5" stroke-width="2.5"/><g stroke="#c0504d" stroke-width="2.5"><line x1="118" y1="98" x2="130" y2="110"/><line x1="130" y1="98" x2="118" y2="110"/><line x1="178" y1="140" x2="190" y2="152"/><line x1="190" y1="140" x2="178" y2="152"/></g><ellipse cx="410" cy="110" rx="90" ry="52" fill="none" stroke="#4a6fa5" stroke-width="2.5"/><text x="70" y="210" font-size="15" fill="#c0504d">截面有零点（×）：κ=0 时被定理排除</text><text x="340" y="210" font-size="15" fill="#4a6fa5">截面处处非零 → 线丛平凡</text><text x="160" y="252" font-size="15" fill="#333">同一个非零截面 s₀ 的两种命运</text></svg>

</div>

**为什么值得关心**

丰度猜想是极小模型纲领的后半程；Kähler 世界没有丰富除子可当扶手，这一步把"非消失后丰度"从射影推广到了解析四维，是族内姊妹篇的解析支柱。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
在紧 Kähler 四维组上证明了"非消失后的丰度"（abundance after nonvanishing）：klt 组 `@@M@@(X,\Delta)@@` 的实际 `@@M@@\mathbb{Q}@@`-Cartier 伴随 `@@M@@K_X+\Delta@@` 只要解析 nef，且某个正 Cartier 倍数有非零截面，就必半丰富；Iitaka 维数为零时该线丛实为平凡全纯线丛。证明不需要射影性与 `@@M@@\mathbb{Q}@@`-因子性假设。

## 问题背景
丰度猜想断言：极小模型上的典范伴随除子应当半丰富（semiample），即某个正倍数由整体截面生成、从而定义到射影空间的映射。射影三维情形由 Miyaoka、Kawamata 等奠基；在紧 Kähler 范畴，由于没有全局丰富除子可用，收缩与正性论证必须重造——Höring–Peternell 建立了紧 Kähler 三维组的 MMP，Campana–Höring–Peternell 与 Das–Ou 先后解决了三维典范与 lc 情形的丰度。对正 Iitaka 维数，Höring–Lazić–Lehn 已处理到四维；真正的缺口是 Iitaka 维数为零的情形。难点有两个：四维组边界上的三维分支各自有丰度，但截面须在交口处残差相容；且相容截面还须从边界提升回四维组。本文正是攻克这两个"边界问题"。

## 主要结果
**主定理**：设 `@@M@@X@@` 是正规连通紧 Kähler 复空间，`@@M@@\dim X=4@@`，`@@M@@\Delta@@` 为有效有理 Weil 除子，`@@M@@(X,\Delta)@@` 为 klt（Kawamata log terminal），且实际伴随（actual adjoint）`@@M@@D=K_X+\Delta@@` 为 `@@M@@\mathbb{Q}@@`-Cartier——即某个自反伴随幂是可逆全纯层，允许 `@@M@@K_X@@` 与 `@@M@@\Delta@@` 各自不 `@@M@@\mathbb{Q}@@`-Cartier。若 `@@M@@D@@` 解析 nef（analytically nef：固定 Kähler 形式 `@@M@@\omega@@` 后，任给 `@@M@@\varepsilon>0@@`，某固定 Cartier 倍数带光滑 Hermitian 度量，其规范化曲率 `@@M@@\geq-\varepsilon\omega@@`）且 `@@M@@\kappa(X,D)\geq0@@`，则存在 `@@M@@m>0@@` 使 `@@M@@mD@@` Cartier 且赋值映射 `@@M@@H^0(X,\OO_X(mD))\otimes_\mathbb{C}\OO_X\to\OO_X(mD)@@` 处处满。若 `@@M@@\kappa(X,D)=0@@`，还可取 `@@M@@m@@` 使 `@@M@@\OO_X(mD)\simeq\OO_X@@`。文中还证明一条独立的、任意维数的**支撑提升定理**（supported lifting）：dlt 组 `@@M@@(V,B)@@` 上若有效非零有理 `@@M@@\mathbb{Q}@@`-Cartier 除子 `@@M@@P\sim_\mathbb{Q} A=K_V+B@@` 且 `@@M@@\operatorname{Supp}P=\operatorname{Supp}\lfloor B\rfloor@@`、限制 `@@M@@A|_S@@` 在整个约化底空间 `@@M@@S=\lfloor B\rfloor@@` 上半丰富，则 `@@M@@\kappa(V,A)\geq1@@`。

## 证明思路
证明按 Iitaka 维数分叉。先设 `@@M@@\kappa\geq1@@`：取 crepant 的普通 `@@M@@\mathbb{Q}@@`-因子紧 Kähler 模型（Das–Hacon–Păun 的构造），套用 Höring–Lazić–Lehn 的定理得半丰富，拉回 Cartier 线丛的截面恰是 `@@M@@X@@` 上的截面，生成性遂下降回原空间。剩下 `@@M@@\kappa=0@@`：取非零截面 `@@M@@s_0\in H^0(X,\OO_X(m_0D))@@`，令 `@@M@@M=\frac1{m_0}\operatorname{div}(s_0)@@`。若 `@@M@@M=0@@` 即得平凡化；设 `@@M@@M\neq0@@` 并寻求矛盾。第一步构造支撑模型：在 Log 解析上把 `@@M@@\operatorname{Supp}M@@` 的严格变换与例外素除子系数提到 1，经"支撑程序"（配合本文新证的两个收缩准备命题：nef 且 big 三维类在零轨迹为有限条曲线时的收缩，以及借助上法同态直接像消没与解析加厚把素底收缩扩张到全空间）得到正规普通 `@@M@@\mathbb{Q}@@`-因子紧 Kähler dlt 四维组 `@@M@@(V,B)@@`：其伴随 `@@M@@A=K_V+B@@` 解析 nef，且 `@@M@@P\sim_\mathbb{Q} A@@` 非零有效、`@@M@@\operatorname{Supp}P=\operatorname{Supp}\lfloor B\rfloor@@`、`@@M@@\kappa(V,A)=0@@`；`@@M@@P\neq0@@` 由例外负性保证。第二步证底生成：`@@M@@S=\lfloor B\rfloor@@` 的正规分支与低维 strata 带实际伴随线丛，用 Das–Ou 三维 lc 丰度使其半丰富，但须选取经层层交口残差相容的截面——相容条件经低维 strata 上的扰动程序化为 Mori 收缩 `@@M@@\PP^1@@` 纤维上两个系数 1 标记点给出的"链环"（link，承 Fujino 的 admissible 截面归纳与 Kollár 的 sources and links）；非射影曲面 strata 上还要加上 Kähler 类限制给出的正平方类约束，使"返回链"在固定次数的多截面上的像有限（McMullen 的非射影 K3 自同构例子说明此约束不可省），有限范数乘积与超平面避让最终选出相容截面组，证明 `@@M@@A|_S@@` 半丰富。第三步用支撑提升定理：取在 `@@M@@S@@` 上生成的 `@@M@@G=qP@@` 得形态 `@@M@@f:S\to T=\PP^b@@`，在紧纤维邻域取根配对与规范化循环覆盖把支撑除子化为约化 Cartier 除子 `@@M@@E@@`，目标是各阶截断层间的满射；其障碍是带链式法则的分次导子 `@@M@@\delta_k@@`，第二次取根与分裂残差映射把障碍嵌入解析 SNC 除子的残差上同调，一个局部微分恒等式把导子的非零值转化为光滑射影参数覆盖上被 Hodge 消没排除的映射，从而逐阶消灭障碍；循环不变量再给出带 `@@M@@\OO_T(1)@@` 正扭转的递归除子层，截面增长而高阶上同调与 `@@M@@H^1(V,\OO_V)@@` 损耗有界，逼出 `@@M@@\kappa(V,A)\geq1@@`。这与 `@@M@@P\neq0@@`、`@@M@@\kappa(V,A)=0@@` 矛盾，故 `@@M@@M=0@@`，`@@M@@s_0@@` 处处非零，平凡化 `@@M@@\OO_X(m_0D)@@`。

## 可信度与备注
主结果暂无 Lean 形式化证明。本文是结果族 034 的解析支柱：族中姊妹篇《Uniform effective log Iitaka fibrations for fourfolds》的半丰富模型比较正引用本定理的射影类比作输入；作者声明本文所需的两条解析边界论证均自证，不依赖射影补充篇。文中对 McMullen K3 自同构、Das 最新预印本等近邻工作有明确区分。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
