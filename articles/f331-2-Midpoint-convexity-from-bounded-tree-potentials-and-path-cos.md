---
layout: default
title: "Midpoint convexity from bounded tree potentials and path costs"
family: "331"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Midpoint convexity from bounded tree potentials and path costs

> 结果族 331：Reflexive midpoint convexity and diamond distortion　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

给向量"量长度"的规则（范数）本身就是一件可以设计的东西。这篇论文在一棵能无穷分叉的树上立规矩：任何一条从根出发的路径，沿途系数的累加和都必须夹在 `@@M@@[-1,1]@@` 里。用这条规矩当尺子，造出一批新的无穷维空间。反直觉的结论是：这些尺子在"中点"意义下是凸的，可无论换成哪把功能等价的新尺子，都得不到更强的"渐近一致凸"——两种凸性被证明可以彻底分家，而且分家发生在最温和的自反空间里。

**关键词卡片**

- 范数（norm）：给向量量长度的规则；同一个空间可以配许多把不同的尺子
- 渐近一致凸（AUC, asymptotically uniformly convex）：一种很强的凸性——单位球在任何高维"远方"方向都严格鼓着，常能靠换尺子获得
- 渐近中点一致凸（AMUC）：只在线段中点处检验的凸性，条件看起来弱一截
- 再赋范（renorming）：给空间换一把等价的新尺子，不改变收敛与连续
- 自反空间（reflexive space）：泛函分析中最"规矩"的一类空间，本文的反例连它也没放过

**看个具体例子**

在有限高的树上，这套尺子有一本干净的账：向量 `@@M@@x@@` 的长度 `@@M@@L_n(x)=\inf\big(\|h\|_2+\|\mu\|_1\big)@@`，即把 `@@M@@x@@` 拆成"一个欧氏向量加若干条根路径"的最小总成本。中点凸性则有显式曲线：取 `@@M@@t=0.8@@`，中点模 `@@M@@\widehat\delta(0.8)\ge\sqrt{1+0.8^2/4}-1\approx 0.077@@`，也就是说中点至少往球内压这么多。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="20" y="30" font-size="16" fill="#333">无穷分叉的树：红色路径的系数一路累加</text>
<circle cx="80" cy="150" r="7" fill="#333"/>
<text x="62" y="180" font-size="14" fill="#333">根</text>
<line x1="87" y1="144" x2="210" y2="70" stroke="#c33" stroke-width="3"/>
<line x1="87" y1="150" x2="210" y2="150" stroke="#aaa"/>
<line x1="87" y1="156" x2="210" y2="230" stroke="#aaa"/>
<circle cx="210" cy="70" r="7" fill="#c33"/>
<circle cx="210" cy="150" r="5" fill="#aaa"/>
<circle cx="210" cy="230" r="5" fill="#aaa"/>
<line x1="217" y1="64" x2="340" y2="30" stroke="#c33" stroke-width="3"/>
<line x1="217" y1="76" x2="340" y2="110" stroke="#aaa"/>
<circle cx="340" cy="30" r="7" fill="#c33"/>
<text x="96" y="92" font-size="14" fill="#c33">系数 f₁</text>
<text x="248" y="26" font-size="14" fill="#c33">系数 f₂</text>
<text x="298" y="62" font-size="14" fill="#c33">位势 P=f₁+f₂</text>
<text x="30" y="250" font-size="14" fill="#333">约束：任何一条路径上，位势 P 都被夹住：</text>
<line x1="400" y1="180" x2="540" y2="180" stroke="#333" stroke-width="2"/>
<line x1="400" y1="170" x2="400" y2="190" stroke="#333" stroke-width="2"/>
<line x1="540" y1="170" x2="540" y2="190" stroke="#333" stroke-width="2"/>
<text x="392" y="212" font-size="13" fill="#333">-1</text>
<text x="536" y="212" font-size="13" fill="#333">1</text>
<line x1="470" y1="160" x2="470" y2="180" stroke="#c33" stroke-width="4"/>
<text x="442" y="152" font-size="13" fill="#c33">P 在这里</text>
</svg>

</div>

**为什么值得关心**

"弱凸性能否靠换尺子升级成强凸性"是 2016 年提出的公开问题，本文给出了包含自反反例在内的一族最干净答案，把两种凸性的分离推进到自反世界。

> 已 Lean 形式化

## 一句话结论
本文用可数分支树上的有界位势（bounded tree potential）显式构造出多个 Banach 空间：它们的平均渐近中点模满足 `@@M@@\widehat\delta(t)\ge\sqrt{1+t^2/4}-1@@`，却都不容许任何等价的渐近一致凸范数；其中二次路径空间与线段起点空间还是自反的，把 Baudier 的 AMUC/AUC 分离现象推进到自反空间。

## 问题背景
渐近中点一致凸（AMUC）是否在再赋范意义下等价于渐近一致凸（AUC），是 Dilworth–Kutzarova–Randrianarivony–Revalski–Zhivkov（2016）提出的公开问题。Baudier 等人 2017 年证明：对具无条件渐近结构的可分自反空间二者等价，于是"无结构假设的自反反例"长期悬置（Perreau 2021 年仍记录为开放）。Baudier 2026 年借 Kadets–Werner 的 Daugavet 例子给出一般否定回答，但那个例子具 Schur 性质、非自反。卡在何处：如何在自反空间里同时实现"中点有增益"与"一切等价范数都非 AUC"这两件方向相反的事。本文的切入点是把两种效应都归结为树上路径的标量约束：路径和有界既挡住单侧凸性，系数的二次预算又允许中点两侧配对增益。

## 主要结果
设 `@@M@@T=\mathbb N^{<\omega}@@` 为可数分支树，系数族 `@@M@@f@@` 的位势为 `@@M@@P_f(s)=\sum_{u\preceq s}f_u@@`。取测试集 `@@M@@K@@`：要求 `@@M@@|P_f(s)|\le1@@`，再附加四种二次约束之一——兄弟组约束（`@@M@@K_{\rm s},K_{\rm p}@@`，后者含根坐标）、有限反链约束（`@@M@@K_{\rm a}@@`，antichain）或全局 `@@M@@\ell_2@@` 约束（`@@M@@K_{\rm g}@@`）。范数取 `@@M@@\|x\|_K=\sup_{f\in K}\sum f_sx_s@@`，完备化得 `@@M@@X_K@@`。定理证明：四个空间都是可分无限维实 Banach 空间，且对 `@@M@@0<t<1@@` 一致满足 `@@M@@\widehat\delta(t)\ge\sqrt{1+t^2/4}-1\ (\ge t^2/16)@@`，同时任何一个都不容许等价 AUC 范数。在有限高树 `@@M@@T_n=\mathbb N^{\le n}@@` 上，全局约束模型满足精确恒等式 `@@M@@L_n(x)=\inf_{x=h+B_n\mu}(\|h\|_2+\|\mu\|_1)@@`——即"Hilbert 向量与根路径的最小可加成本"；高度一时恰为 Dilworth 等人的 `@@M@@\ell_2@@` 反例。把成本换成欧氏组合得到二次路径空间 `@@M@@X_{\rm q}@@`，把根路径换成任意起点的线段并按起点计费得到线段起点空间 `@@M@@X_S@@`：二者都自反、每点半径处最大渐近中点模为正、且无等价 AUC 范数。

## 证明思路
中点下界的核心是"成对向内测试"。难点在于：支撑在有限初始集 `@@M@@D@@` 内的中心 `@@M@@x@@` 的赋范测试 `@@M@@f@@`，其位势可能已经顶在区间 `@@M@@[-1,1]@@` 的边界上，任意的尾部扰动 `@@M@@g@@` 会把位势推出区间。解决办法是把尾部测试在每个 `@@M@@T\setminus D@@` 分量上的相对位势 `@@M@@R(s)@@` 按头部继承值 `@@M@@c=P_f(r)@@` 的内侧拆成两个正部 `@@M@@U,V@@`：`@@M@@U-V=R@@` 且都指向区间内部。取符号正部是 1-Lipschitz 的，故新系数逐点被 `@@M@@|g_s|@@` 控制，二次约束自动保留；位势界为 2，除以 2 后仍是合法测试。关键一步是验证 `@@M@@af+\theta u@@` 与 `@@M@@af+\theta v@@`（`@@M@@a=\sqrt{1-\theta^2}@@`）都属于 `@@M@@K@@`：头部与尾部支撑不相交，任一二次组的预算按勾股式合成 `@@M@@a^2+\theta^2=1@@`，而位势因"向内"而被夹在 `@@M@@[-1,1]@@` 中。把这两个测试分别作用于 `@@M@@x+ty@@` 与 `@@M@@x-ty@@` 再相加，即得平均 `@@M@@\ge a\|x\|_K+\frac{t\theta}{2}g(y)@@`，对 `@@M@@g@@` 取上确界后选 `@@M@@\theta=t/\sqrt{4+t^2}@@` 便得 `@@M@@\sqrt{1+t^2/4}@@`。配对的好处是无需预先挑端点：对一侧不利的尾部位势恰好为另一侧提供向内测试。排除 AUC 再赋范用的是"有界弱零树"引理：若空间含有一致有界的树 `@@M@@(p_s)@@`（`@@M@@m\le\|p_s\|\le M@@`）且子增量 `@@M@@d_{s,n}=p_{s^\frown n}-p_s@@` 弱零、范数 `@@M@@\ge c@@`，则任何等价范数的单侧模在 `@@M@@t_0=\alpha c/(2\beta M)@@` 处为零——否则沿树逐层选子节点，凸性迫使范数每步乘 `@@M@@(1+\gamma/2)@@`，有限层后突破一致上界。四个模型里路径向量 `@@M@@p_s=\sum_{u\preceq s}e_u@@` 由位势条件归一，兄弟 `@@M@@\ell_2@@` 约束使子增量弱零且范数为 1，引理以 `@@M@@m=M=c=1@@` 生效。自反模型 `@@M@@X_{\rm q},X_S@@` 的范数等价于 Hilbert 范数故自反；其AMUC靠对偶空间的截断、停止与匹配论证（如尾部估计 `@@M@@\|Q_Ay\|\le 8\sqrt{R^2-\|x\|^2}@@`、线段空间中 `@@M@@\|Q_Ey\|_{\rm I}\le(\sqrt2+\sqrt6)\sqrt{1-\|x\|_{\rm I}}@@`），AUC 排除则复用同一弱零树机制。

## 可信度与备注
论文声明主结果已有 Lean 形式化证明。作为结果族 331 的构造主干，它与本族另两篇互补：Daugavet 子空间一篇算出精确模曲线，独立乘积一篇给出 `@@M@@L^1@@` 内的随机实现，本文则贡献显式树模型与自反反例，三者共同支撑"中点一致凸不迫使 AUC 可再赋范，即使在自反世界"。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇虽已形式化，文中诸多数值常数（如 `@@M@@1/64@@`、`@@M@@495@@`、`@@M@@252@@`）仍以原文与社区核验为准。

{% endraw %}
