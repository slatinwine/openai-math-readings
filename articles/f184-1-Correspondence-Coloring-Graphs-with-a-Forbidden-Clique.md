---
layout: default
title: "Correspondence coloring graphs with a forbidden clique"
family: "184"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Correspondence coloring graphs with a forbidden clique

> 结果族 184：Correspondence coloring with a fixed forbidden subgraph　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对每个固定整数 `@@M@@r\ge 4@@`，论文证明最大度 (maximum degree) `@@M@@\Delta@@` 充分大的 `@@M@@K_r@@`-free 图的对应色数 (correspondence chromatic number) 满足 `@@M@@\chi_{\mathrm{DP}}(G)\le O_r(\Delta/\log\Delta)@@`，以最强的对应染色形式解决了 Alon–Krivelevich–Sudakov 1999 年染色猜想；排除任意固定子图 `@@M@@F@@` 的推广同样成立。

## 问题背景

图染色要求给相邻顶点分配不同颜色；贪心算法保证 `@@M@@\Delta+1@@` 色总够用，而高围长 (girth) 随机图表明这一界一般无法改进。1999 年 Alon、Krivelevich 与 Sudakov 猜想：若图不含某个固定图 `@@M@@F@@` 作为（不必诱导的）子图，则 `@@M@@\Delta@@` 充分大时 `@@M@@O_F(\Delta/\log\Delta)@@` 色即可，比贪心好一个对数因子；此前该猜想即使在普通染色下也悬而未决。论文处理的是更强的对应染色 (correspondence coloring / DP-coloring)：每个顶点 `@@M@@v@@` 有自己的列表 `@@M@@L(v)@@`，每条边 `@@M@@uv@@` 附带 `@@M@@L(u)\times L(v)@@` 中的一个匹配 (matching) `@@M@@M_{uv}@@`，须从各列表选色使相邻顶点的选择对避开匹配；对应色数同时控制普通色数与列表色数，`@@M@@\chi\le\chi_{\mathrm{list}}\le\chi_{\mathrm{DP}}\le\Delta+1@@`，故证明的是最强版本。

## 主要结果

主定理：对每个整数 `@@M@@r\ge 4@@` 存在常数 `@@M@@C_r>0@@` 与 `@@M@@\Delta_r@@`，使每个最大度 `@@M@@\Delta\ge\Delta_r@@` 的 `@@M@@K_r@@`-free 图 `@@M@@G@@` 满足
`@@M@@D\chi_{\mathrm{DP}}(G)\ \le\ \left\lceil C_r\frac{\Delta}{\log\Delta}\right\rceil,@@`
且界对顶点数、列表大小与匹配方式一致。推论：把 `@@M@@K_r@@` 换成任意固定有限图 `@@M@@F@@`，常数改为依赖 `@@M@@F@@` 的 `@@M@@C_F@@` 后结论仍成立——这正是 AKS 猜想的对应染色加强版；普通染色与列表染色 (list coloring) 自动同界。当 `@@M@@F@@` 含圈时，由 Bollobás 的高围长图知 `@@M@@\Delta/\log\Delta@@` 这一阶已不可改进。

## 证明思路

证明采用 Johansson 式多轮半随机染色。第一步把对应关系化为图结构：令 `@@M@@H@@` 为全部正权重列表条目构成的图，匹配禁对为边。由匹配性，每个条目在任一列表中至多一个邻居；`@@M@@H@@` 的团 (clique) 投影为 `@@M@@G@@` 的团，故 `@@M@@H@@` 亦 `@@M@@K_r@@`-free，于是可直接在 `@@M@@H@@` 上操作而无需跨列表辨识颜色。

每轮给条目 `@@M@@i@@` 维护权重 `@@M@@w_i@@`：顶点 `@@M@@v@@` 的总权重 `@@M@@W_v@@` 保持在窗口 `@@M@@[K/2,2K]@@` 内，单个权重至多 `@@M@@\Delta^{-0.99}@@`，两者合起来保证可用条目约 `@@M@@\Delta^{0.99}@@` 个。势函数 `@@M@@F_v@@` 含三项：相对初始权重的熵 (entropy)、防止总权重塌缩的线性惩罚项、以及冲突边质量 `@@M@@D_v@@`。轮内每个条目以正比于权重的概率激活 (activation)，无邻居同时激活者"成功"并被选为宿主顶点的颜色，冲突条目随之清零；给邻居染色同时削减 `@@M@@D_v@@` 与度数。

真正的难点在于：相邻条目的公共邻居激活会同时删去两者的权重，一阶补偿后仍残留正的边相关，其在条目 `@@M@@i@@` 处的代价正比于 `@@M@@t_i@@`，即经过 `@@M@@i@@` 的加权三角形质量的两倍。论文的核心新工具——局部权重调整引理——给出一族支撑在 `@@M@@O(\log\log\Delta)@@` 半径球内、每个列表至多触及 `@@M@@P_0@@` 个条目的乘子与删除操作，其线性组合恰好抵消 `@@M@@t_i@@`（至多差常数倍边质量），且每条目的操作速率有界。该引理的证明先用对偶价格 (dual prices) 与闭锥分离把逐顶点不等式化约为一个标量三角形估计，再按价格二进层分组并重标权重，借助均值一随机乘子与顶点分裂 (vertex splitting) 反复压低邻域权重，各级损失可求和。

集中性方面，同一列表内的条目演化并不独立，故改用"读取-k"型集中引理（Finner 广义 Hölder 不等式加 Hoeffding 界）：当每个随机标志只进入少数几个被求和函数时即得指数集中，每列表参与度界正是为此设计。激活碰撞则先界碰撞图的度数，再从中取大匹配、利用匹配端点激活的独立性给出尾估计；最后以 Lovász 局部引理 (Lovász local lemma) 保证所有顶点同时进展，并裁剪极端权重恢复假设。如此迭代约 `@@M@@2\tau^{-1}\log\Delta@@` 轮（每轮剩余度数乘以 `@@M@@1-\tau@@`）后，剩余度降至 `@@M@@\Delta^{0.96}@@` 量级，远小于可用条目数，贪心染色即可收尾。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。它在结果族 184 中与姊妹篇《A logarithmic independence bound for clique-free graphs》配套：后者的乘子构造与熵-分裂方法是本文调整引理的源头，本文在其上补齐参与度界、集中不等式与局部引理等染色专属环节。按 OpenAI 官方声明，未经形式化的结果可能存在问题。论文不优化常数与度数门槛。

{% endraw %}
