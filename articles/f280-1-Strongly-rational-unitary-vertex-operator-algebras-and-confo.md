---
layout: default
title: "Strongly rational unitary vertex operator algebras and conformal nets"
family: "280"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Strongly rational unitary vertex operator algebras and conformal nets

> 结果族 280：Unitary vertex operator algebras and conformal nets　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明任一单酉强有理顶点算子代数都自动满足能量界与强局部性，从而生成完全有理共形网；全部单模可酉化，且模范畴与网的有限指标扇区构成辫子酉张量等价——两种手征场论语言在最核心一类对象上被证等同。

## 问题背景

顶点算子代数（vertex operator algebra, VOA）与共形网（conformal net）是二维手征共形场论的两大数学框架：前者记录场量的模式与代数恒等式，后者把可观测量的冯·诺依曼代数指派到圆周的区间上。二者理应等价，但严格对应分解析与表示论两半。Carpi–Kawahigashi–Longo–Weiner（CKLW）证明强局部性（strong locality）是从酉 VOA 构造共形网的充分条件，并猜测它对一切单酉 VOA 成立。难点在于：无界场形式对易并不保证生成的冯·诺依曼代数对易；真空上的正定形式也不会自动传递到模或融合积上。此前完整结果仅限于酉仿射、Virasoro、格、仿费米子与 `@@M@@W@@`-代数等特例。

## 主要结果

主定理设 `@@M@@V@@` 为单、酉、强有理（strongly rational：CFT 型、有理、`@@M@@C_2@@`-余有限且自逆步）的复 VOA，则：

1. `@@M@@V@@` 满足多项式能量界（polynomial energy bounds）且 CKLW-强局部，其涂抹场（smeared field）生成不可约共形网 `@@M@@A_V@@`；
2. `@@M@@V@@` 完全酉（completely unitary）：每个单分次限制模皆可酉化，且典范不变厄米融合形式（fusion form）正定；
3. 每个酉的有限长度模强可积（strongly integrable），闭涂抹场等式成立；
4. `@@M@@A_V@@` 完全有理（completely rational：不可约、分裂、强可加且 `@@M@@\mu@@`-指标有限）；
5. Carpi–Weiner–Xu 函子给出辫子酉张量范畴等价 `@@M@@\Rep(V)\simeq\Rep^u(V)\to\Rep^f(A_V)@@`，网侧张量积与辫子分别为 Connes 融合与 DHR 辫子。

推论还给出 `@@M@@\mu(A_V)=\sum_i d(M_i)^2@@`（网的二区间指标等于 VOA 融合范畴的整体维数），并经 Gui 的延拓定理把 `@@M@@V@@` 的 CFT 型共形延拓与 `@@M@@A_V@@` 的不可约有限指标局部延拓一一对应。

## 证明思路

关键次序在于：正定型先只在已知酉的对象上可用。先从 `@@M@@C_2@@`-余有限性造网：有限生成滤过把齐次向量展开为厄米拟初级（quasi-primary）生成元的单项式，Zhu 单点收敛定理给出指数初始界，首次压缩（`@@M@@\rho=1-\tfrac1{2D}<1@@`）将其压为多项式增长；再用精细的正规积计数（零模式约束经 Cauchy–Schwarz 省下一个 `@@M@@N@@` 的幂）与 `@@M@@(L_1-L_{-1})/2@@` 生成的 Möbius 流，把非零模估计无损转移到零模式并完成第二次压缩，对权 `@@M@@d\geq2@@` 的场得到最优能量阶 `@@M@@d-1@@`，恰为修正版 CTW 判据所需，故得不可约网 `@@M@@A_V@@`。

再积分已酉的模：以固定倍增圆环（doubled annulus）控制局部插入，Möbius 因子化使估计在插入点趋近圆周时一致，于是在每个已酉模上得到与实际闭涂抹场相等的正规局部作用。融合正定性随之而来：产生场在真空局部代数给出正定 Gram 矩阵 `@@M@@K_{ij}=T_i(r)^*T_j(r)@@`，经正规表示传到任意酉源模；刚性给出融合积上的非退化不变形式，多项式矩的正性分离各能量层。

然后酉化全部单模：令 `@@M@@D=V\otimes V@@`、`@@M@@U@@` 为翻转不动点子代数、`@@M@@R=P\otimes P^\vee@@`。Barron–Dong–Mason 转置扭模 `@@M@@T=T_\sigma(V)@@` 在 `@@M@@U@@` 上酉；置换融合公式的荷映射单射，把 `@@M@@R|_U@@` 的每个单成分检测进正定的 `@@M@@T\boxtimes_U T^\vee@@`，得正 `@@M@@U@@`-不变形式 `@@M@@h_1@@`；符号部分 `@@M@@J@@` 的作用经输运给出第二形式 `@@M@@h_2@@`，取伴恰使二者互换，故 `@@M@@h_1+h_2@@` 为 `@@M@@D@@`-不变正形式，限制后即酉化 `@@M@@P@@`。

最后穷竭扇区：任取不可约局部正规表示（不设有限指标假设），其旋转谱为纯点谱；Henriques–Tener 重构在特征子空间直和上给出弱酉模，正则性析出普通单模 `@@M@@S@@`；约化投影的闭域论证表明投影与整个网对易，不可约性迫使它为恒等，故该扇区即 `@@M@@S@@`。扇区有限多，结合分裂性与 Longo–Xu 二分法得完全有理性，分解后得本质满射与最终等价。

## 可信度与备注

论文署名 OpenAI，主结果暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。作为结果族 280 的支柱论文，五步论证层层相依（造网、积分、融合正定、全模酉化、扇区穷竭），并复用 CKLW、CTW、Gui、Henriques–Tener、ABD、Carnahan–Miyamoto 等经同行评议的定理；文中还指出 DLXY 证明一处指数笔误，便于分块复核。

{% endraw %}
