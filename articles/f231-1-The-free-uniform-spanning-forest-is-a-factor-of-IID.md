---
layout: default
title: "The free uniform spanning forest is a factor of IID"
family: "231"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The free uniform spanning forest is a factor of IID

> 结果族 231：The free uniform spanning forest is a factor of IID　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了在任意无穷连通局部有限图上，自由均匀生成森林都是独立同分布标签的因子：一条对所有图统一、不选根、同构等变的 Borel 规则即可从顶点标签译码出整片森林；可数群上平移不变的强 Rayleigh 过程亦然。

## 问题背景

均匀生成森林（uniform spanning forest）是无穷图边集上的典范概率律：Pemantle（1991）在整数格上构造了生成树的无穷体积极限，Benjamini–Lyons–Peres–Schramm（2001）建立一般理论。"自由"版本（free uniform spanning forest, FUSF）取有限连通穷竭上均匀生成树的弱极限、不粘合边界顶点，极限存在且与穷竭无关。因子 of IID（factor of IID, FIID）问的是：这个全局随机对象能否从顶点上的独立标签出发，等变、可测地"译码"出来？Lyons 在 2013 年 Oberwolfach 报告中明确提出了 Cayley 图上的 FUSF 因子问题。此前已知的结果都带限制：暂态图上的 wired 森林可经 Wilson 算法（以无穷远为根）得到 IID 构造；Lyons–Thom（2016）在可均群上证明等变行列式测度的 Bernoulli 同构；Timár（2025）在常返及"不变可均"的 unimodular（单模）随机图上证明了自由森林的 FIID 可表示性。而无任何可均性假设、逐图成立、且只用一条规则的完整版本，在他 2025 年 12 月版本的前言里仍列为公开问题——本文正面解决它。

## 主要结果

**定理 1（主定理）**：存在单一的 Borel、不用根顶点（root-independent）、等变规则 `@@M@@\Phi(G,U,e)\in\{0,1\}@@`，使得对每个无穷连通局部有限简单无权无向图 `@@M@@G@@` 与独立 `@@M@@\mathrm{Uniform}[0,1]@@` 顶点标签 `@@M@@U@@`，边集 `@@M@@\{e:\Phi(G,U,e)=1\}@@` 的联合分布恰为 `@@M@@\FUSF_G@@`；等变性指在保持标签与所标边的图同构下不变。不假设可均性（amenability）、暂态性、度的一致界或度矩；结论是普通 Borel 因子，不承诺有限编码半径或有限字母表。推论：在所述图类上支撑的每个 unimodular 律之下，FUSF 都是图的 FIID，且同一条规则对所有律通用——肯定回答了 unimodular 随机图的一般因子问题。

**定理 2（群上的强 Rayleigh 过程）**：可数群 `@@M@@\Gamma@@` 上每个在左正则平移 `@@M@@\tau_g@@` 下不变的强 Rayleigh 律（strongly Rayleigh：生成多项式在各变量取上半平面值时无零点，无穷情形要求一切有限边际满足）都是该作用的 IID 因子，无需可均性。推论覆盖具有自伴正压缩核 `@@M@@K@@`（`@@M@@0\le K\le I@@`）且平移不变的行列式过程（determinantal process），特别包括 `@@M@@K@@` 与左正则表示交换的情形。

## 证明思路

整个构造是一场"布朗观察—滤波—反解码"的三幕剧。先把隐藏配置 `@@M@@X\sim\FUSF_G@@` 浸入噪声：观察过程 `@@M@@Y_e(t)=tX_e+B_e(t)@@`，`@@M@@B_e@@` 为独立布朗运动。对有限条边，后验恰是森林律的指数倾斜。定量心脏是加权生成树的响应恒等式：若 `@@M@@p_e@@` 为边 `@@M@@e@@` 的入树概率、`@@M@@h_f@@` 为边 `@@M@@f@@` 的对数权重，则 `@@M@@\sum_f|\partial p_e/\partial h_f|=2p_e(1-p_e)\le 1/2@@`。先由矩阵树公式得 `@@M@@\partial p_e/\partial h_f=\operatorname{Cov}(\xi_e,\xi_f)@@`，非对角项等于 `@@M@@-c_ec_f(a_e^{\mathsf T}L^{-1}a_f)^2\le 0@@`（负关联），而生成树边数固定使整行协方差之和为零，恒等式由此而来；常数 `@@M@@1/2@@` 与边数、权重全然无关。经自由极限传递，得到处处有定义的漂移 `@@M@@b(t,y)@@`：对场的任意有界扰动一致 `@@M@@1/2@@`-Lipschitz，哪怕场本身在图上无界。滤波一幕证明 `@@M@@b(t,Y(t))=\E[X\mid\mathcal H_t]@@`（逐固定时刻成立），且创新过程 `@@M@@\widehat W_e(t)=Y_e(t)-\int_0^t b_e(s,Y(s))\,ds@@` 是独立布朗运动——这是 Fujisaki–Kallianpur–Kunita 型创新恒等式的可数坐标版本，用条件特征函数加时间细分，每小区间误差 `@@M@@O(h^{3/2})@@`，求和后消失。最后反解码：Lipschitz 界使积分方程 `@@M@@Z_e(t)=w_e(t)+\int_0^t b_e(s,Z(s))\,ds@@` 对每个连续输入经 Borel Picard 迭代唯一可解，相邻迭代之差以 `@@M@@(t/2)^{k+1}/(k+1)!@@` 速率对所有坐标一致收敛——只需差有界，从不假设场属于 `@@M@@\ell^\infty@@`。于是 `@@M@@Y=Z(\widehat W)@@`：把独立布朗路径喂给确定性译码器 `@@M@@Z@@` 即重现观测律，再由 Borel–Cantelli 得 `@@M@@Y_e(n)/n\to X_e@@`，读出 `@@M@@\mathbf 1\{\limsup_n Z_e(n)/n>1/2\}@@` 便恢复整片森林。落到图上还剩两件事：顶点标签拆出"钥匙"`@@M@@K_v@@` 与私有序列，边 `@@M@@\{u,v\}@@`（`@@M@@K_u<K_v@@`）取排名变量 `@@M@@V_{u,r}@@`，使各边获得独立均匀变量并 Borel 地织成布朗路径（钥匙碰撞时置零路径：零概率、Borel、等变）；漂移用边为中心的内在球 `@@M@@H_n(e)@@` 与"先 `@@M@@m\to\infty@@`、后 `@@M@@\limsup_n@@`"的固定顺序极限定义，保证同构等变且在变动的图空间上 Borel。强 Rayleigh 情形把恒等式换成不等式：对称齐次化（symmetric homogenization）添加哑坐标以固定总占用数，Rayleigh 不等式给出非正非对角协方差，行界 `@@M@@\le 1/2@@` 照旧；群平移穷竭 `@@M@@S_n(h)=hF_n@@` 使漂移等变，而行列式过程的有限边际本就强 Rayleigh，故一并落入采样准则。作者特别提醒一致性假设是实质的：各以 `@@M@@1/2@@` 概率取全 0、全 1 配置的律，其行和为 `@@M@@|S|/4@@` 无界，创新引理虽仍适用，却无确定性反解码可用。

## 可信度与备注

本手稿任务标注 formalized 为 false，即主结果尚无 Lean 形式化证明，请以社区核验为准。论文内部结构自洽互证：定理 1 与定理 2 共用"一致响应界 + 布朗采样准则"同一骨架，命题化的采样准则把概率论证与目标测度的定量性质分离；方法谱系上承 Eldan 的随机定位（stochastic localization）与 Nam–Sly–Zhang 关于正则树上自由 Ising 律的 FIID 工作，文内引用的姊妹篇则给出该 Ising 问题的尖锐阈值（含临界情形），与本文的均匀响应反演互补。按 OpenAI 官方声明，未经形式化的结果可能存在问题，最终定性有待同行评审与独立核验。

{% endraw %}
