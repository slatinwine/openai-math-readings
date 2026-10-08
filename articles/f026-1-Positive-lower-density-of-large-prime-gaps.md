---
layout: default
title: "Positive lower density of large prime gaps"
family: "026"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Positive lower density of large prime gaps

> 结果族 026：Positive lower density of large prime gaps　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把素数想成数轴上的公交站：越往远处，平均站距约等于 ln p。早就知道偶有"超级长"的站距，但没人能证明"特别长的站距不只是深夜偶发，而是常态化占一定比例"。这篇论文证明：无论标准定多苛刻——站距超过平均值的 C 倍——够格的站距永远占一个不消失的比例。

**关键词卡片**

- 素数间隔（prime gap）：相邻两个素数的差 d_n = p_{n+1} − p_n。
- 平均间距 ln p：素数定理保证 p 附近平均隔 ln p 就有一站，是衡量长短的标尺。
- 正下密度（positive lower density）：在每一个足够长的初始段里都至少占固定比例 c(C)，不靠挑特殊片段充数。
- 一致性（uniformity）：估计对所有大的 N 同时成立——比以往"沿某条子列成立"的结果更强。

**看个具体例子**

p ≈ 10^6 处 ln p ≈ 13.8，即平均站距约 14。取 C = 2，站距需超过 2 ln p ≈ 27.6 才算"长"。定理说存在常数 c(2) > 0，使前 N 个间隔中至少 c(2)·N 个超过 2 ln p_n。论文还顺手回答了 1962 年埃尔德什–普拉哈之问：使 p_n/n 变大的那些指标也占正比例——由素数定理，p_n/n 与 ln p_n 相当，取 C = 2 应用主定理、丢掉有限个例外即得。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="35" y1="150" x2="522" y2="150" stroke="#333" stroke-width="2"/><polygon points="535,150 521,144 521,156" fill="#333"/><line x1="60" y1="142" x2="60" y2="158" stroke="#333" stroke-width="2"/><line x1="72" y1="142" x2="72" y2="158" stroke="#333" stroke-width="2"/><line x1="85" y1="142" x2="85" y2="158" stroke="#333" stroke-width="2"/><line x1="97" y1="142" x2="97" y2="158" stroke="#333" stroke-width="2"/><line x1="112" y1="142" x2="112" y2="158" stroke="#333" stroke-width="2"/><line x1="124" y1="142" x2="124" y2="158" stroke="#333" stroke-width="2"/><line x1="135" y1="142" x2="135" y2="158" stroke="#333" stroke-width="2"/><line x1="150" y1="142" x2="150" y2="158" stroke="#333" stroke-width="2"/><line x1="162" y1="142" x2="162" y2="158" stroke="#333" stroke-width="2"/><line x1="174" y1="142" x2="174" y2="158" stroke="#333" stroke-width="2"/><line x1="186" y1="142" x2="186" y2="158" stroke="#333" stroke-width="2"/><line x1="200" y1="142" x2="200" y2="158" stroke="#333" stroke-width="2"/><line x1="212" y1="142" x2="212" y2="158" stroke="#333" stroke-width="2"/><line x1="226" y1="142" x2="226" y2="158" stroke="#333" stroke-width="2"/><line x1="238" y1="142" x2="238" y2="158" stroke="#333" stroke-width="2"/><line x1="252" y1="142" x2="252" y2="158" stroke="#333" stroke-width="2"/><line x1="368" y1="142" x2="368" y2="158" stroke="#333" stroke-width="2"/><line x1="382" y1="142" x2="382" y2="158" stroke="#333" stroke-width="2"/><line x1="396" y1="142" x2="396" y2="158" stroke="#333" stroke-width="2"/><line x1="409" y1="142" x2="409" y2="158" stroke="#333" stroke-width="2"/><line x1="424" y1="142" x2="424" y2="158" stroke="#333" stroke-width="2"/><line x1="438" y1="142" x2="438" y2="158" stroke="#333" stroke-width="2"/><line x1="452" y1="142" x2="452" y2="158" stroke="#333" stroke-width="2"/><line x1="466" y1="142" x2="466" y2="158" stroke="#333" stroke-width="2"/><line x1="480" y1="142" x2="480" y2="158" stroke="#333" stroke-width="2"/><line x1="494" y1="142" x2="494" y2="158" stroke="#333" stroke-width="2"/><line x1="508" y1="142" x2="508" y2="158" stroke="#333" stroke-width="2"/><rect x="262" y="118" width="100" height="64" fill="none" stroke="#c0392b" stroke-width="2" stroke-dasharray="7 5"/><text x="312" y="105" font-size="15" text-anchor="middle" fill="#c0392b">长间隔：超过 C·ln p</text><text x="150" y="180" font-size="13" text-anchor="middle" fill="#555">常规间距</text><text x="300" y="235" font-size="14" text-anchor="middle" fill="#333">素数"车站"示意：长间隔不是稀有事件，至少占固定比例</text></svg>

</div>

**为什么值得关心**

"最大间隔有多长"名结果众多，"长间隔有多普遍"却一直缺无条件的正比例结论；本文用一套新的筛法权重首次把它钉死。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文证明：对任意固定 `@@M@@C>0@@`，都存在 `@@M@@c(C)>0@@`，使得每个足够大的前 `@@M@@N@@` 个素数里，相邻间隔 `@@M@@p_{n+1}-p_n>C\log p_n@@` 者至少占比例 `@@M@@c(C)@@`；由此 `@@M@@p_n/n@@` 递增的指标具有正下密度，肯定回答了 Erdős–Prachar 1962 年的问题。

## 问题背景

记 `@@M@@p_n@@` 为第 `@@M@@n@@` 个素数，`@@M@@d_n=p_{n+1}-p_n@@`。素数定理说明 `@@M@@p@@` 附近的平均间隔约为 `@@M@@\log p@@`；Westzynthius 早已证明 `@@M@@d_n/\log p_n@@` 无界，Erdős–Rankin 以及 Ford–Green–Konyagin–Tao、Maynard 又不断推高"最大间隔"的下界。但这些结果只描述极端大的间隔，并不能推出"正比例"的间隔超过平均值的固定倍数。频率问题真正的难点在于：数"无素数区间"与数"素数间隔"是两种计数——一条很长的间隔内部含有大量无素数短区间的起点，空区间占正比例完全可能只由稀疏的超长间隔撑起来。Bazzanella–Languasco–Zaccagnini 2010 年的定理 5 只在阈值低于 `@@M@@2/3.454\approx0.579@@` 时给出正比例；Tao 2019 年的空区间论证同样指出，从"区间测度"过渡到"间隔计数"需要额外控制；Gallagher 式的 Poisson 统计则依赖更强的均匀素数组假设，属于条件结果。1962 年 Erdős 与 Prachar 进一步问：使 `@@M@@p_n/n@@` 递增的指标集是否有正的下渐近密度（lower asymptotic density）？

## 主要结果

**主定理（Theorem 1.1）**：对每个固定实数 `@@M@@C>0@@`，存在常数 `@@M@@c(C)>0@@` 与 `@@M@@N_0(C)@@`，使得对每个整数 `@@M@@N\ge N_0(C)@@` 都有
`@@M@@D\#\{1\le n\le N:\ p_{n+1}-p_n>C\log p_n\}\ge c(C)N.@@`
注意这里是"寻常"下密度（ordinary lower density）：估计对**每个**足够大的初始段一致成立，而非只沿某个子列成立；比例常数可以依赖 `@@M@@C@@`。

**推论（Corollary 1.2）**：集合 `@@M@@\{n\ge1:\ p_n/n<p_{n+1}/(n+1)\}@@` 具有正下渐近密度。证明只有几行：该不等式等价于 `@@M@@d_n>p_n/n@@`，而素数定理给出 `@@M@@p_n/n\sim\log p_n@@`，故取 `@@M@@C=2@@` 应用主定理、丢弃有限多个例外指标即可。这肯定地回答了 Erdős–Prachar 问题。

## 证明思路

整个证明分两幕：先造权重，再把权重换算成间隔计数。固定 `@@M@@\lambda>\max\{C,1\}@@`，令 `@@M@@h=\lfloor\lambda\log X\rfloor@@`，在 `@@M@@X<m\le2X@@` 上取平均，给每个起点配两个相邻区间：前块 `@@M@@J=\{1,\dots,h\}@@`、后块 `@@M@@I=\{h+1,\dots,2h\}@@`，理想事件是"`@@M@@J@@` 中有素数、`@@M@@I@@` 中没有"。此时 `@@M@@J@@` 中最后一个素数 `@@M@@p(m)@@` 的后继素数超出 `@@M@@m+2h@@`，故它开启一条长于 `@@M@@h@@` 的间隔；而每个素数至多被 `@@M@@h@@` 个起点选中（必须 `@@M@@p-h\le m<p@@`），这一有界重数（multiplicity）正是把区间构造折算为间隔计数的关键：`@@M@@\delta X@@` 个好起点至少给出 `@@M@@\delta X/h@@` 条长间隔（Lemma 2.2）。

支撑换算的是权重命题（Proposition 2.1）：构造 `@@M@@W_X(m)\ge0@@`，使其平均质量趋于 1；在 `@@M@@J@@` 检测到的加权素数质量 `@@M@@\mathbb E(W_XV_J)\to\lambda@@`（其中 `@@M@@V_J=\frac1L\sum_{b\in J}\vartheta(m+b)@@`，`@@M@@\vartheta@@` 为带 `@@M@@\log@@` 权的素数指示函数）；在 `@@M@@I@@` 的素数质量却可压至任意小的 `@@M@@\varepsilon@@`；另有两条二阶矩界，防止加权质量挤在过少的素数或过少的起点上。随后两次 Cauchy–Schwarz 先给出至少 `@@M@@\delta X@@` 个普通好起点，再经重数引理换成间隔，最后取 `@@M@@X=\lfloor p_N/3\rfloor@@` 保证全部指标不超过 `@@M@@N@@`，得 `@@M@@c(C)=\delta/(4\lambda)@@`。

权重的构造是全文核心（谱系上承 Goldston–Yıldırım 的除数和相关法与 Maynard 的多维筛）：取光滑除数和的带符号和 `@@M@@Z@@`——对位移整数 `@@M@@m+b@@` 的因子求和，带 Möbius 函数 `@@M@@\mu@@` 与紧支集光滑测试函数——权重即 `@@M@@Z^2/w@@`。关键机制有二。其一，当素数标记落在 `@@M@@I@@` 的位移 `@@M@@a@@` 上时，支撑截断 `@@M@@\tau=1/8@@` 迫使该坐标的因子只能取 1，删去 `@@M@@a@@` 得到精确恒等式，效果是把第 `@@M@@j@@` 维测试函数替换为 `@@M@@f_j+Tf_{j+1}@@`：相邻维数由此耦合，"压低 `@@M@@I@@` 的素数质量"等价于让相邻层的函数几乎对消。其二，检测界常数 `@@M@@C_*=\lambda+\lambda^2c_G^2@@` 与维数 `@@M@@k@@` 及函数族无关，故可先把 `@@M@@\varepsilon@@` 压得足够小再进入计数。对消的具体实现（Proposition 4.2）：用近似 `@@M@@1/u@@` 的伸缩轮廓 `@@M@@g@@` 把一阶矩做得任意小，令 `@@M@@Q_j=k^{j/2}\prod_i g(kt_i)@@`，在最高 `@@M@@r=\lfloor\sqrt k\rfloor@@` 层取交错符号 `@@M@@(−1)^jQ_j/\sqrt{\alpha_j}@@`，相邻层相消至因子 `@@M@@1-\sqrt{(j+1)/k}@@`，最终 `@@M@@w\to1@@`、`@@M@@v\to0@@`。参数顺序至关重要：先让辅助参数 `@@M@@k\to\infty@@` 选定一个有限族，再让 `@@M@@X\to\infty@@`，从而完全避开对 `@@M@@k@@` 一致的除数和渐近公式。

解析基础是允许任意重合模式与一个素数标记的混合矩公式：经 Bombieri–Vinogradov 定理与 Euler 积的 Fourier 求值，主项分离为奇异级数（singular series）`@@M@@\mathfrak S(\mathcal H)@@` 乘以由重合模式决定的常数；完全混合偏导在坐标面上消失，正因如此 `@@M@@Z^2@@` 展开中不相配的子集自动消去，只剩平方范数。再配合 Gallagher 型的奇异级数方框平均，全部估计得以闭合。

## 可信度与备注

本篇暂无形式化证明，请以社区核验为准；论文署名 OpenAI，标注日期 2026 年 9 月 25 日，而 OpenAI 官方声明"未经形式化的结果可能有问题"。结果族 026 宣称的核心结论即本篇的主定理与推论；本批任务仅含这一篇手稿，其内部呈"权重命题—矩恒等式—维数对消—混合矩公式"的分层结构逐环咬合（Proposition 2.1 依赖 3.1 与 4.2，3.1 依赖 5.1）。核验时第 5 节的混合矩公式与奇异级数平均是技术负担最重、最值得先行复查的环节。

{% endraw %}
