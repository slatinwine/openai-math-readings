---
layout: default
title: "The Subcritical Hénon–Lane–Emden Conjecture"
family: "370"
discipline: "Partial differential equations"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Subcritical Hénon–Lane–Emden Conjecture

> 结果族 370：The Lane–Emden and Hénon–Lane–Emden conjectures　·　学科：Partial differential equations　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了次临界 Hénon–Lane–Emden 猜想：当 `@@M@@\frac{n+A}{p+1}+\frac{n+B}{q+1}\gt n-2@@` 时，方程组 `@@M@@-\Delta u=|x|^A v^p@@`、`@@M@@-\Delta v=|x|^B u^q@@` 在全空间没有正整体解，且不需要任何对称性或无穷远条件；结合经典径向存在性定理，进一步给出了解存在的精确判据。

## 问题背景

Lane–Emden 型方程组的 Liouville 定理（Liouville theorem，即"无非平凡正整体解"类结论）是非线性椭圆方程的基石：它是导出先验估计与奇性分析的爆破（blow-up）论证的标准输入。标量情形由 Gidas 与 Spruck 在 1981 年解决；方程组情形困难得多，Mitidieri 的 Rellich 恒等式、Serrin–Zou、Poláčik–Quittner–Souplet 与 Souplet 的工作逐步解决了低维无权情形，Li–Li–Wei 又把无权非存在区域推广到 `@@M@@n\ge5@@`。带权 `@@M@@|x|^A@@`、`@@M@@|x|^B@@` 的 Hénon 推广更加棘手：权函数以原点为中心，破坏了方程的平移不变性，而传统 Liouville 证明恰恰依赖平移与平移不变的伸缩分析。此前 Bidaut-Véron–Giacomini 在径向理论中确定了临界双曲线，Phan 把无限制的问题表述为猜想 C，Li–Zhang 解决了三维，Li 覆盖了四、五维的部分指数范围，Huang–Zou 的猜想 B 则只在附加稳定性、衰减或能量假设时成立——高维全区域一直是空白。

## 主要结果

**主定理**：设 `@@M@@n\ge2@@`、`@@M@@p,q\gt0@@`、`@@M@@A,B\in\R@@` 且 `@@M@@\frac{n+A}{p+1}+\frac{n+B}{q+1}\gt n-2@@`，则不存在 `@@M@@u,v\in C^2(\R^n\setminus\{0\})\cap C(\R^n)@@` 的严格正函数在 `@@M@@x\ne0@@` 处满足上述方程组。假设之弱值得强调：只要求解在原点连续（不必可微），在无穷远处不加任何有界性、可积性或增长衰减条件。取 `@@M@@A=B=0@@` 立即得到经典无权 Lane–Emden 猜想：`@@M@@n\ge3@@` 且 `@@M@@\frac1{p+1}+\frac1{q+1}\gt\frac{n-2}{n}@@` 时无非平凡正解。注意加权结论无法由无权结论推出——例如 `@@M@@n=5@@`、`@@M@@p=q=4@@`、`@@M@@A=B=3@@` 满足加权次临界条件，但对应的无权分数 `@@M@@2/5\lt3/5@@`。**分类推论（Phan 猜想 C）**：当 `@@M@@n\ge3@@`、`@@M@@A,B\gt-2@@` 时，"无正整体解"当且仅当上述严格不等式成立；反向弱不等式（含临界双曲线上）时存在径向正整体解，此部分由 Bidaut-Véron–Giacomini 的径向定理给出，二者合成完整的存在—不存在二分法。

## 证明思路

先做归约：仅凭正性即可排除 `@@M@@n=2@@`、`@@M@@A@@` 或 `@@M@@B\le-2@@` 以及 `@@M@@pq\le1@@`，工具是球面平均通量 `@@M@@(r^{n-1}\bar u')'@@` 的严格单调性与积分。随后是全文的关键观察：权以原点为中心，故平移不保持方程，但**以原点为中心的伸缩** `@@M@@u_R(x)=R^\alpha u(Rx)@@` 保持方程；据此在 `@@M@@B_1@@` 上对源质量作自举估计（`@@M@@M_f\ge cM_g^q@@`、`@@M@@M_g\ge cM_f^p@@` 结合 `@@M@@pq\gt1@@`）得到通用中心估计 `@@M@@\int_{B_R}f\le CR^{n-2-\beta}@@`，并证明 `@@M@@u,v@@` 恰为 Newton 位势 `@@M@@u=K*g@@`、`@@M@@v=K*f@@`。定义次临界间隙 `@@M@@\gamma=a(n+B)+b(n+A)-(n-2)@@`，恒等式 `@@M@@\gamma=(1-a-b)(\alpha+\beta+2-n)@@` 表明 `@@M@@\gamma\gt0@@` 蕴含能量伸缩指数 `@@M@@\alpha+\beta+2-n\gt0@@`。于是整个证明归约为一个目标：给局部能量 `@@M@@E=\int\eta(fu+gv)@@` 一个不依赖于解的一致上界——对 `@@M@@u_R,v_R@@` 用该界并令 `@@M@@R\to\infty@@`，`@@M@@B_1@@` 内能量以 `@@M@@R^{\alpha+\beta+2-n}@@` 增长，必与一致界矛盾。

再建立局部化 virial 恒等式：引入相互作用测度 `@@M@@\dd\pi(x,y)=f(x)g(y)K(x-y)\dd x\dd y@@`，其两个边缘恰为 `@@M@@fu@@` 与 `@@M@@gv@@`；对紧支撑向量场 `@@M@@X=x\eta@@` 分部积分得 `@@M@@a(n+B)E_f+b(n+A)E_g-aW_f-bW_g=(n-2)\int\Phi\,\dd\pi@@`。Taylor 展开与位势尾部估计显示 `@@M@@\Phi@@` 可近似为 `@@M@@\eta(x)-w(x)D(x,y)@@`，误差被 `@@M@@\eps E+C_\eps@@` 吸收；整理后左端系数之和恰为 `@@M@@\gamma@@`，于是只欠"压强"估计 `@@M@@aW_f+bW_g-(n-2)\int wD\,\dd\pi\le\eps E+C_\eps@@`。

最后是最技术性的一步：把源 `@@M@@f@@` 沿方向 `@@M@@e@@` 按水平集 `@@M@@\{f\gt t\}@@` 切成区间分量，只保留足够短的区间，其权重取帽权 `@@M@@h_e@@` 的区间内下确界，方向 `@@M@@e@@` 被限制在径向 `@@M@@\omega_x@@` 附近的小帽内。两条平行线上的纯几何区间比较引理——由分部积分的中点恒等式加上差 `@@M@@h=s-s'@@` 的分布关于中点分离的对称性证明——给出核积分的端点控制；层端点值 `@@M@@(t/|x|^B)^{1/q}@@` 不是常数 `@@M@@t^{1/q}@@`，这一障碍用区间长度不超过 `@@M@@2\delta d@@` 来压小；被丢弃的长区间由极坐标积分源质量并作高/低水平分解控制。合并全部误差即得压强估计，进而 `@@M@@\frac\gamma2E\le\eps E+C@@`，取 `@@M@@\eps@@` 充分小便有 `@@M@@E\le C@@`，再由伸缩导出最终矛盾。

## 可信度与备注

据任务元数据，本文主结果已通过 Lean 形式化证明，可信度属最高一档，结果族条目亦附有 Lean 文档链接。本批解读即结果族 370 的核心论文：非存在性定理是本文新贡献，分类推论的存在性一半则直接引用 Bidaut-Véron–Giacomini 的经典径向定理，属可靠引用而非新构造。仍需记住 OpenAI 官方声明"未经形式化的结果可能有问题"——好在本文核心定理已形式化，但文中引用的历史结论仍应以原始文献为准。

{% endraw %}
