---
layout: default
title: "Threshold parallel repetition for finite-dimensional entangled games"
family: "277"
discipline: "Mathematical physics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Threshold parallel repetition for finite-dimensional entangled games

> 结果族 277：Threshold repetition for entangled games　·　学科：Mathematical physics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了任意有限二人一轮博弈的阈值并行重复 (threshold repetition) 定理：只要纠缠值 (entangled value) `@@M@@v<1@@`，在 `@@M@@k@@` 次独立重复中获胜占比超过 `@@M@@v+\delta@@` 的概率便对一切有限维联合策略一致地按 `@@M@@\exp(-\Omega(\delta^5 k/(1+\log d)))@@` 指数衰减，且允许任意相关问题分布——一般纠缠博弈的阈值错误放大由此实现。

## 问题背景

并行重复 (parallel repetition) 问的是：把一个验证者博弈 (game) 重复 `@@M@@k@@` 次，作弊者的成功概率能否随 `@@M@@k@@` 指数下降？Raz（1998）对经典博弈证明了"全胜"情形的指数衰减，Rao（2011）进一步证明了更强的"阈值"版本：胜利占比超过单局值任意固定增量的概率指数小，这是复杂性理论与密码学中错误放大的标准手段。纠缠博弈允许两个不通信的玩家共享量子态，重复时还可使用任意联合 POVM 测量，各局胜利高度相关，经典信息论论证随之失效。此前已知结果都带结构性限制：XOR 博弈（Cleve–Slofstra–Unger–Upadhyay 2008，完美重复）、唯一博弈 (unique games，Kempe–Regev–Toner 2010)、投影博弈 (projection games，Dinur–Steurer–Vidick 2015)、自由博弈 (free games) 等；对完全一般的博弈，Yuen（2016）只得到多项式衰减，Bavarian–Vidick–Yuen 的指数定理则需"锚定" (anchoring)——向博弈添加问题、从而改变问题分布。近著《Ten Advances》第 6 章与 Song（2026）相继对任意博弈的"全胜"事件给出指数与三次方衰减，但一般博弈的阈值版本始终缺位，本文补上这一环。

## 主要结果

**主定理（定理 1.1）**：存在普适常数 `@@M@@\kappa_0>0@@`，对任意有限二人一轮博弈 `@@M@@G@@`（布尔接受谓词），设其纠缠值 `@@M@@v=\omega^*(G)<1@@`，`@@M@@d=|\mathcal A||\mathcal B|@@` 为双方答案集大小之积。则对一切 `@@M@@0<\delta<1-v@@`、`@@M@@k\ge 1@@` 及任意有限维联合策略（问题分布 `@@M@@\mu@@` 可相关、允许零概率项与不连通支撑），

`@@M@@D\Pr\bigl[W_k\ge\lceil(v+\delta)k\rceil\bigr]\le\exp\!\left(-\frac{\kappa_0\delta^5}{1+\log d}\,k\right),@@`

其中 `@@M@@W_k@@` 是 `@@M@@k@@` 局中的获胜局数。不等式对策略取上确界仍成立；速率不依赖问题分布、问题表大小与策略维度。

**固定分布的三次方界（第 5 节推论）**：以 `@@M@@\mu@@` 的正概率问题对为顶点、共享一个问题的顶点相邻构成图，记其连通分量为 `@@M@@H_j@@`，令 `@@M@@\kappa_\mu=8\max_j(|H_j|-1)/\mu_{j,\min}@@`，则同一事件的概率不超过 `@@M@@\exp\bigl(-\delta^3 k/(16384(1+\kappa_\mu)(1+\log d))\bigr)@@`：对固定 `@@M@@\mu@@`，`@@M@@\delta@@` 的次数由五次升为三次，两个界可择优取用。当 `@@M@@v=0@@` 时文中还证得该概率恒为零。

**两侧错误放大（第 6 节推论）**：设 `@@M@@\omega^*(G)\ge c@@` 与 `@@M@@\omega^*(G)\le s@@`（`@@M@@0\le s<c\le1@@`，`@@M@@\Delta=c-s@@`），以阈值 `@@M@@t=(c+s)/2@@` 判定的重复博弈 `@@M@@H_k@@` 同时放大两侧：完备性至少 `@@M@@1-e^{-\Delta^2k/8}@@`，可靠性至多 `@@M@@e^{-\kappa_0(\Delta/2)^5k/(1+\log d)}@@`，且不增加玩家数、轮数或通信。

## 证明思路

全文脊柱是一条"条件化 ⇒ 阈值"的转移命题：若某条件化估计在预算 `@@M@@T\le\delta/4@@` 内有效——即当测试集 `@@M@@C@@` 的条件化成本 `@@M@@\tau=(\log(1/p_C)+|C|\log d)/(k-|C|)\le T@@` 时，条件于"`@@M@@C@@` 内全胜"后其余坐标的平均胜率不超过 `@@M@@v+\delta/4@@`——则阈值事件概率不超过 `@@M@@\exp(-\delta Tk/(16(1+\log d)))@@`。它把"用哪种条件化技术"与"如何导出集中不等式"彻底解耦。

转移命题用纯经典反证法。先假设上尾概率不低于 `@@M@@e^{-ck}@@`；再对 `@@M@@[k]@@` 均匀有放回地抽取约 `@@M@@ck@@` 个下标作为测试集。一个一阶矩论证（只涉及二元胜利指示变量的联合分布，不需要任何独立性）保证存在一个固定测试集 `@@M@@C@@`：其全胜概率 `@@M@@p_C@@` 不太小，且条件于此事件后总胜数仍大概率超过 `@@M@@(v+\delta/2)k@@`，折算得其余坐标的条件平均胜率至少 `@@M@@v+7\delta/16@@`；另一方面 `@@M@@C@@` 足够短、`@@M@@p_C@@` 足够大，使成本 `@@M@@\tau(C)<T@@`，条件化估计却给出至多 `@@M@@v+\delta/4@@`，矛盾。此论证只覆盖足够大的 `@@M@@k@@`；对短博弈，取 `@@M@@N@@` 份独立张量拷贝拼成长博弈，"每块都超阈值"蕴含全局超阈值，由 `@@M@@p_H^N\le e^{-cNk}@@` 解出 `@@M@@p_H\le e^{-ck}@@`，从而同一速率无遗漏地覆盖一切长度。

主定理只需把 Song（2026）的条件化估计（误差 `@@M@@B_4\tau^{1/4}@@`，常数普适）代入转移命题，取 `@@M@@T=(\delta/4B_4)^4@@`。三次方界则完全不借助 Song 的采样器：先用预解式纯化 (resolvent purification) 把条件化产生的一族正算子实现为公共有限维空间中的向量族（`@@M@@\mathcal F_T^*\mathcal F_T=T@@`），配套的算子 Jensen 不等式把向量间平均平方距离控制在算子熵差之内，传输后的 POVM 还精确保持答案概率；再按固定顺序逐坐标暴露问题——第 `@@M@@i@@` 个坐标之前暴露 Alice 的问题、之后暴露 Bob 的——移动分界点张出两条熵望远镜 (entropy telescope)，总代价至多 `@@M@@2p\tau@@`，于是依赖双方问题的条件向量被两个"单问题可描述"的向量近似；最后在每个支撑连通分量内选定根 (root) 问题，把该分量全部条件向量统一替换为根处的向量，沿支撑图路径用 Cauchy–Schwarz 累积误差（至多 `@@M@@\kappa_\mu p\tau@@`），并以共享旗标的直和态构造出分量博弈的合法策略，配合相对熵与 Pinsker 不等式控制条件化后分量权重的漂移。合并得条件化误差 `@@M@@O_\mu(\sqrt\tau+\tau)@@`，取 `@@M@@T\asymp\delta^2@@` 即得三次方速率。

## 可信度与备注

本文主结果已由 Lean 形式化证明（见结果族 277 文档 lean/docs/277.md），在这批 OpenAI 手稿中属验证等级最高的一类。它与姊妹篇构成递进链条：《Ten Advances》第 6 章提供预解式纯化与条件化机器，Song（2026）提供平滑采样器与条件化估计，本文新增的转移命题把前两者升级为阈值结论，各篇互为印证。依 OpenAI 官方声明，未经形式化的结果可能有问题，引用未进入 Lean 部分的具体常数时应以论文原文与社区核验为准。

{% endraw %}
