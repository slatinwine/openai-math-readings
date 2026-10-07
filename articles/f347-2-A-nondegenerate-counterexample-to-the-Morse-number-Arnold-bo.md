---
layout: default
title: "A nondegenerate counterexample to the Morse-number Arnold bound"
family: "347"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A nondegenerate counterexample to the Morse-number Arnold bound

> 结果族 347：Counterexamples to stable-Morse and strong Arnold fixed-point bounds　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在实维数为 12 的闭辛流形上，本文构造出所有不动点均非退化、轨道均可缩的光滑哈密顿流，其不动点总数却严格低于流形的常义 Morse 数（Morse number），且缺口可任意大——直接推翻了 Arnold 猜想的 Morse 数形式。

## 问题背景

Arnold 不动点猜想把哈密顿动力系统与有限维临界点理论联系起来：对足够 `@@M@@C^2@@`-小的自治哈密顿量，时间 1 映射的不动点恰是其临界点。问题在于对任意哈密顿路径，这个下界还能保留多少。Floer 理论及其后的虚拟模空间方法确立了非退化情形的同调下界（如总 Betti 数），但同调量并不等于常义 Morse 数 `@@M@@\Morse(M)@@`——基本群的生成元个数可以强迫额外的指标 1 与 `@@M@@n-1@@` 临界点。Damian 已知闭流形的常义与稳定 Morse 数（stable Morse number）可以不同；Ma 的预印本则断言非退化哈密顿不动点的最小个数总等于 `@@M@@\Morse(M)@@`。本文的反例说明该断言不成立，且亏损无界。

## 主要结果

主定理：存在闭连通辛流形 `@@M@@(M,\omega)@@`（实维数 12）与光滑 1-周期哈密顿量 `@@M@@H@@`，使 `@@M@@\phi_H^1@@` 的每个不动点都非退化（nondegenerate，即 `@@M@@1\notin\Spec(d_x\phi_H^1)@@`）、每条不动点轨迹可缩（contractible），且

`@@M@@D\#\Fix_0(\phi_H^1;H)=\#\Fix(\phi_H^1)=\chi(M)+128<\Morse(M).@@`

推论：对任意 `@@M@@D>0@@`，可在同样的 12 维构造中实现 `@@M@@\Morse(M)-\#\Fix(\phi_H^1)>D@@`（流形随 `@@M@@D@@` 改变，维数不变）。例子的整同调无挠且集中于偶数维，故不动点数超过一切已知同调下界——缺口完全来自基本群的"生成代价"。

## 证明思路

全部机关藏在基本群 `@@M@@G=A_5^k@@` 的两个代数不变量的悬殊差距里：群生成元个数 `@@M@@d(G)@@` 随 `@@M@@k@@` 无界增长（鸽笼论证：若 `@@M@@k>|S|^m@@` 则 `@@M@@d(S^k)>m@@`）；而增广理想（augmentation ideal）`@@M@@I=\ker(\Z[G]\to\Z)@@` 作为右模却恒可由 `@@M@@b=2@@` 个元素生成，与 `@@M@@k@@` 无关（Cossey–Gruenberg–Kovács 直积定理；文中给出初等证明：先证模每个素数可由两元生成，再经中国剩余定理与行列式扰动提升回整数）。

第一步把短生成列表变成 Morse 函数。Gompf 定理给出 `@@M@@\pi_1(X)\cong G@@` 的闭辛四维流形 `@@M@@X@@`；在固定的 12 维余边界（cobordism）`@@M@@W=X\times E@@` 上做手柄分解，其中 `@@M@@E\subset\R^8@@` 由二次型 `@@M@@Q(u,v)=(|v|^2-|u|^2)/2@@` 的两个水平面与半径 3 的侧面围成。万有覆叠上的手柄复形是 `@@M@@\Z[G]@@` 上的链复形，且 `@@M@@\operatorname{im}\partial_1=I@@`。先引入 `@@M@@b@@` 对五/六指标相互抵消的新手柄，使其边界列恰为增广理想的 `@@M@@b@@` 个生成元，并把旧指标 5 手柄的边界列全部化为零；再用初等行变换引理（仅靠 `@@M@@x_j\leftarrow x_j+x_iq@@` 型基变换即可把某个系数变成恰好 1）选出可抵消的一对，配合 11 维水平中的 Whitney 移动（Whitney move）消除成对交点——Whitney 圈零伦恰需系数等于 1 而非任意环单元，这是绕过难点的关键。逐个几何抵消旧手柄，再反转余边界同样处理指标 7，最终手柄计数为 `@@M@@(1,b,\chi(X)-2+2b,b,1)@@`，临界点共 `@@M@@\chi(X)+4b@@` 个，函数在紧集外恒等于 `@@M@@Q@@`。

第二步把局部模型封进闭流形 `@@M@@M=X\times(S^2)^4@@`。四个球面的南北选择给出十六个帽子，各嵌入一份小时间回射映射 `@@M@@\Phi_F^\epsilon@@`。极点处的辛极坐标与一张精心设计的旋转角表（如 `@@M@@s_j=-1@@` 时北极为 `@@M@@\epsilon@@`、南极为 `@@M@@2\pi-\epsilon@@`）保证旋转端点与二次模型吻合，尽管路径可差整整一圈；支撑在帽子内部的修正项 `@@M@@K_t=\epsilon(F-Q\circ\Phi_F^{-\epsilon t})@@` 完成插入。短周期引理（Yorke 型 Lipschitz 估计）与特征值模界保证 `@@M@@\epsilon@@` 足够小时不动点恰为 `@@M@@F@@` 的临界点且全部非退化；凸组合收缩说明不动点轨道可缩。最后，零/一手柄图的自由基本群满射到 `@@M@@\pi_1@@`，对偶地指标 11 同样受控，Euler 恒等式给出 `@@M@@\Morse(M)\ge\chi(M)+4d(G)@@`；取 `@@M@@k>60^{32}@@` 即 `@@M@@d(G)>32@@`，严格不等式成立，`@@M@@k@@` 增大给出任意亏损。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准；其中代数部分完全初等自足，高维手柄滑动与相对消去是经典但繁琐的几何技术。同族姊妹篇——复三维二次超曲面上恰有三个不动点的退化反例——主结果已 Lean 形式化，两文分别从非退化与退化方向否定 Arnold 猜想的无限制形式。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
