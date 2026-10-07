---
layout: default
title: "An FPRAS for Common Integer Polymatroid Bases with Binary Capacities"
family: "114"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An FPRAS for Common Integer Polymatroid Bases with Binary Capacities

> 结果族 114：Approximate counting of common integer polymatroid bases　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明：对两个由精确秩值预言机给出的同总秩整多拟阵，其公共整数基的计数存在完全多项式随机近似格式（FPRAS）——预言机调用与比特运算在每次执行中都只以地面集大小和容量二进制编码长度的多项式为界，且每个整数向量恰计一次。

## 问题背景

整多拟阵（integral polymatroid）刻画带子模（submodular）容量约束的非负整数分配。设 `@@M@@E=\{1,\dots,n\}@@`，秩函数 `@@M@@r_i@@` 归一、单调、子模且总秩相同 `@@M@@r_1(E)=r_2(E)=R@@`，要数的是同时满足两套约束的整数基——这是拟阵交（matroid intersection）与带容量运输问题的共同推广。多拟阵论源自 Edmonds 1970 年的工作：在秩值预言机下，可行性与优化都能多项式求解，计数却长期没有算法。障碍有二：其一，总秩与容量按二进制编码，单个坐标可取随 `@@M@@R@@` 指数增多的值；其二，若把每单位容量展开成带标签元素（Helgason 的 hypermatroid 表示），实例规模与每个向量的带标签实现数（二项系数之积）同时爆炸，计数权被彻底改变。此前结果或固定维数（列联表方向：Dyer–Kannan–Mount、Cryan–Dyer、Bezáková–Bhatnagar–Vigoda 等），或含 `@@M@@2^{O(r)}@@` 因子（Anari–Oveis Gharan–Vinzant 对公共基）。本文补上了"容量二进制编码、两个多拟阵任意"这一格。

## 主要结果

定理 1.1（thm:main）：存在单一的一致随机算法，输入二进制给出的 `@@M@@R@@`、两个精确秩值预言机 `@@M@@r_1,r_2@@`（查询为 `@@M@@n@@` 位子集指示，回答为二进制整数）及有理数 `@@M@@\varepsilon,\delta\in(0,1)@@`，输出非负有理数 `@@M@@\widehat Z@@`，满足
`@@M@@D\mathbb P\bigl((1-\varepsilon)Z\le\widehat Z\le(1+\varepsilon)Z\bigr)\ge1-\delta,@@`
其中 `@@M@@Z@@` 是公共整数基集 `@@M@@\Omega(r_1,r_2)=\{x\in\mathbb Z_{\ge0}^E:\ x(E)=R,\ x(A)\le r_i(A)\ \forall A\subseteq E,\ i\in\{1,2\}\}@@` 的基数，每个向量权重为一。若 `@@M@@Z=0@@`，算法每次执行都输出零。核心保证是：在每次执行（而非仅仅期望）中，预言机调用次数与其余比特运算都被 `@@M@@n,\ell,\varepsilon^{-1},\log(\delta^{-1})@@` 的一个固定多项式界定（`@@M@@\ell@@` 为 `@@M@@n,R,\varepsilon,\delta@@` 的二进制编码长）。算法直接处理二进制容量，不展开为带标签副本。作者明言多项式的固定指数很大——重点是依赖关系，不是运行时间。

## 证明思路

先做确定性准备：用子模极小化与有理分离—优化理论（Grötschel–Lovász–Schrijver）精确判定可行性，并用行列式替换构造公共基多面体的有理中心（rational center）。中心附近近似紧的秩不等式诱导 `@@M@@E@@` 的两个划分，各部分总量被限制在中心周围多项式长的整数区间内——这些"端口"（port）就是算法保留的离散变量。

再消去其余自由度。在两个划分的关联二部图上取生成树，非树边坐标充当自由变量；其范围随 `@@M@@R@@` 的数值增大，于是对秩违反施加凸的软惩罚，然后对自由坐标积分（Prékopa 边际定理保持对数凹性），得到关于端口总量的正的对数凹块权。几何端的比较论证（方向对数凹性加小同伦缩放）证明这个加权和以相对误差 `@@M@@O(N^{-7})@@` 逼近 `@@M@@JZ@@`，其中 `@@M@@J@@` 是一个可高精度计算的平移求和归一化因子。

但对数凹性不足以给出计数链所需的离散二次签名（signature）不等式。论文把积分权与紧支撑光滑核卷积，再乘以小的严格凹二次因子；导数估计控制离散二阶差分与连续 Hessian 的偏差，严格曲率在所有退火幂 `@@M@@h^s@@`（`@@M@@0\le s\le1@@`）下压住误差，使加性（addition）与省略（omission）两种签名检验在每一相位都通过。

最后组装计数。每个长 `@@M@@d_v@@` 的端口用 `@@M@@d_v@@` 对带标签元素表示，并定义两个阶乘修正权 `@@M@@f,\widetilde f@@`：在横截集（每对恰选一元）上二者的多重性因子严格抵消，平衡质量恰为未标记端口轮廓的质量。验证 `@@M@@f@@` 具省略性质、`@@M@@\widetilde f@@` 具加性性质且两者在缺陷类上相互可比之后，调用姊妹篇证明的运输不等式与迹链（trace chain）框架：沿 `@@M@@k_j=(2^{-U}h)^{j/H_o}@@` 的乘方表退火，封顶重启提供热起始，链上观测估计相邻相位质量比与缺陷类频率以学习乘子 `@@M@@w_{il}@@`，连乘除以 `@@M@@J@@` 的估计得到 `@@M@@\widehat Z@@`；每次权重评估由 Dyer–Frieze–Kannan 凸体积随机算法多项式完成。所有大型展开（展开拟阵、几何细分、运输流）只是证明装置，实际被采样的显式实例只含 `@@M@@2p@@` 个元素。

## 可信度与备注

本文暂无形式化证明。它站在两篇同族姊妹篇之上：母篇《Approximate counting of common bases of two matroids》（主结果已 Lean 形式化）提供正秩亏权、运输不等式与迹链混合的通用框架；cell-bounded 列联表篇提供双阶乘提升与封顶退火实现。本文的独立贡献是把二进制容量实例归约到显式规模为多项式的实例，并在积分之后重建所需的离散二次不等式。按 OpenAI 官方声明，未经形式化的结果可能有问题，本文结论请以社区核验为准。

{% endraw %}
