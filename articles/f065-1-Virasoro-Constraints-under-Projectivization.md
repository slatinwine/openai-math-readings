---
layout: default
title: "Virasoro Constraints under Projectivization"
family: "065"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Virasoro Constraints under Projectivization

> 结果族 065：Virasoro constraints for complete intersections and projective-bundle towers　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文证明传递定理：若光滑射影复簇 `@@M@@B@@` 满足全套普通含后代 Virasoro 约束，则任意秩 `@@M@@r\geq2@@` 代数向量丛 `@@M@@E@@` 的射影化 `@@M@@X=\mathbb P_B(E)@@` 也满足——不要求 `@@M@@E@@` 分裂或具正性，覆盖每个亏格、每条整曲线类与含本原、奇类的全部插入，并可迭代到投影丛塔。

## 问题背景

Virasoro 约束把光滑射影簇的含后代（descendant）Gromov–Witten 不变量组织成母函数 `@@M@@Z_Y@@` 的一族微分方程 `@@M@@L_k^YZ_Y=0@@`，源自 Witten 猜想与 Kontsevich 定理的点目标情形，经 Eguchi–Hori–Xiong 提出、Eguchi–Jinzenji–Xiong（含 Katz 修正的 Hodge 分次）推广到一般目标。全亏格的已知结果集中在半单量子上同调（Givental 量子化加 Teleman 重建）、亏格零（Liu–Tian）与目标曲线（Okounkov–Pandharipande）。至于"约束能否沿纤维化从底传到全空间"，最接近的是 Coates–Givental–Tseng（CGT）对线丛之和构造的环面丛给出的充要条件；Fan 对任意投影丛建立了全亏格重建与陈类依赖，但重建本身不保证与 Virasoro 微分算子相容。不分裂、无正性向量丛的传递此前悬而未决。

## 主要结果

主定理：设 `@@M@@B@@` 为光滑连通射影复簇，`@@M@@E@@` 为其上秩 `@@M@@r\geq2@@` 的代数向量丛，`@@M@@X=\mathbb P_B(E)@@` 参数化纤维的一维子空间，则 `@@M@@\mathcal V(B)\Longrightarrow\mathcal V(X)@@`。其中 `@@M@@\mathcal V(Y)@@` 指所有模式 `@@M@@k\geq-1@@` 的普通、未约化含后代 Virasoro 方程，逐亏格、逐条整曲线类成立，插入取遍 `@@M@@H^*(Y;\C)@@`，含本原（primitive）类与奇（odd）类；Virasoro 算子由第一 Hodge 分次 `@@M@@\mu_Y|_{H^{p,q}}=(p-\tfrac12\dim_\C Y)\id@@` 与 `@@M@@R_Y=c_1(TY)\cup@@` 构成。`@@M@@E@@` 可以不分裂、无正性，`@@M@@B@@` 的量子上同调可以非半单。定理可逐层迭代到投影丛塔；配合 Okounkov–Pandharipande 的曲线结果，立即给出光滑射影曲线上任意投影丛及其塔的完整约束。

## 证明思路

证明分五步走。先把 `@@M@@E@@` 张量以充分负的线丛（这不改变 `@@M@@X@@`，且使 `@@M@@E^*@@` 全局生成），引入辅助"主空间"`@@M@@W=\mathbb P_B(E\oplus\mathcal O)@@`：让 `@@M@@\C^*@@` 缩放平凡和项，`@@M@@\lambda@@` 为等变参数，其不动分量恰是 `@@M@@B@@` 与 `@@M@@X@@`。用虚拟定位化（virtual localization）把 `@@M@@W@@` 的祖先势（ancestor potential）分解为 `@@M@@B@@` 与 `@@M@@X@@` 的逆 Euler 扭转祖先势之乘积，迁移因子是上三角辛级数 `@@M@@R(z)@@` 的量子化，同一 `@@M@@R@@` 也分解亏格零基本解。与 CGT 的环面丛情形不同，这里的轨道线本身构成正维族 `@@M@@X@@`：动腿的模空间是 `@@M@@\mathcal O_X(-1)@@` 的 `@@M@@m@@` 次根 gerbe，其贡献是上同调对应（correspondence）而非有限和，论文为此补上了 CGT 备注 3.7 留空的张量粘合论证。

但定位化只给出同时含两个不动理论的关系，还须把它们拆开。再作谱分析：亏格零平移算子把 `@@M@@\lambda@@` 平移圈变量 `@@M@@z@@`，其系数在固定底度下是 `@@M@@y@@` 的多项式，模去 `@@M@@z@@` 与正底度后谱值为 `@@M@@\lambda+h@@`，其中 `@@M@@h^r(h+\lambda)=y@@`；在 `@@M@@y=0@@` 附近一条分支趋于零、对应 `@@M@@B@@`，其余 `@@M@@r@@` 条趋于 `@@M@@\lambda@@`、合成 `@@M@@X@@` 簇。关键在于这一谱分解无需对角化 `@@M@@B@@` 的量子上同调。接着在每块上构造可量子化的 Virasoro 型模式：等变分次中含有 `@@M@@\lambda\partial_\lambda@@`，块上平移算子的对数含有 `@@M@@z\partial_\lambda@@`，减去 `@@M@@\lambda/z@@` 乘此对数即消去对系数的微分，剩下系数环上的圈算子；在 `@@M@@y=0@@` 处与不动分量算子比较，并用量子 Riemann–Roch 把后者（差一个三角模式变换）识别为 `@@M@@B@@` 或 `@@M@@X@@` 上的普通 Virasoro 模式。

最后做延拓与定标：连通祖先不变量对 `@@M@@y@@` 是多项式，且祖先 `@@M@@\bar\psi@@` 幂次被 `@@M@@3g-3+n@@` 界住（与纤维度无关），故量子化方程的每个系数只涉及有限多个模式系数，是真正的全纯芽恒等式；覆盖 `@@M@@h\mapsto h^r(h+\lambda)@@` 去掉分歧值后连通，其单值群传递地置换 `@@M@@r+1@@` 条分支，把 `@@M@@B@@` 分支上的方程搬运到所有分支；对 `@@M@@X@@` 簇的 `@@M@@r@@` 条分支求和并回到 `@@M@@y=0@@`，反向运用不动分量比较，即得 `@@M@@X@@` 的普通方程（至多差一个与插入无关的标量）。量子化只投射地确定方程，故末步用交换子 `@@M@@[L_{-1},L_1]=-2L_0@@` 与 `@@M@@[L_0,L_k]=-kL_k@@` 消去标量，并给出 `@@M@@L_0@@` 中规定的常数 `@@M@@C_Y=\chi(Y)/16-\str(\mu_Y^2)/4@@`。

## 可信度与备注

本结果暂无形式化证明。论文自含定位化、粘合与延拓的完整论证，并与已知结果相容：底半单时结论此前已由 Iritani–Koto 加 Givental–Teleman 覆盖，本文新意正在非半单底。它也是结果族 065 的传递支柱：姊妹篇攻克射影空间完全交后，本文把约束进一步送到任意向量丛的射影化与投影丛塔。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
