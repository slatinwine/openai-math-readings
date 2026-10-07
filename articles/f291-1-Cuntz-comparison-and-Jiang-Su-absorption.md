---
layout: default
title: "Cuntz comparison and Jiang–Su absorption"
family: "291"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Cuntz comparison and Jiang–Su absorption

> 结果族 291：Cuntz comparison, nuclear dimension, and equivariant Jiang–Su stability　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明 Toms–Winter 正则性问题"严格比较推出 Jiang–Su 吸收"方向：可分单核非初等 C*-代数只要在扩展泛函意义下严格比较就 `@@M@@\mathcal Z@@`-稳定；更一般地，Cuntz 半群几乎无穿孔且完全几乎可除的可分核代数吸收 `@@M@@\mathcal Z@@`，非单、非酉、无界迹一并解决。

## 问题背景

Cuntz 比较（Cuntz comparison）问：正元素之间的次序 `@@M@@a\precsim b@@` 是否由数值尺寸决定？可除性（divisibility）问：正元素能否拆成近似等份？对核 C*-代数，这两个纯序论问题与张量吸收 Jiang–Su 代数 `@@M@@\mathcal Z@@`（即 `@@M@@A\cong A\otimes_{\min}\mathcal Z@@`）深刻相连，构成 Toms–Winter 正则性问题（Toms–Winter regularity problem）的三条等价线之一。比较推出吸收这一方向的历史结果均带迹边界限制：Matui–Sato 处理有限个极值迹，Sato、Kirchberg–Rørdam、Toms–White–Winter 推广到紧有限维极值边界，CETW（2022）把剩余条件归结为一致 Γ 性质。本文取消迹边界与一致 Γ 假设，并覆盖非酉代数、含理想代数与无界迹。非单情形另有两大障碍：正元素可以在每个相关表示中都大，却没有统一整数控制全部理想比较；迹可能只在遗传局部化之后才有限。

## 主要结果

论文给出四条定理。其一（单代数定理）：可分、单、核、非初等（non-elementary）的 C*-代数若满足扩展泛函严格比较（strict comparison）——对 Cuntz 半群 `@@M@@\Cu(A)@@` 的全体泛函 `@@M@@\varphi@@`，由 `@@M@@\varphi(x)\le\varphi(y)@@` 且在正有限值处严格不等可推出 `@@M@@x\le y@@`——则 `@@M@@A\cong A\otimes_{\min}\mathcal Z@@`；这解决 Toms–Winter 问题的该方向蕴含，含稳定无投影代数与无界迹。其二（条件 (C) 吸收定理）：可分核代数若满足条件 (C)，即 Cuntz 半群几乎无穿孔（almost unperforation）加完全几乎可除（full almost divisibility，对每个 `@@M@@x@@` 与 `@@M@@N@@` 存在同一 `@@M@@u@@` 使 `@@M@@Nu\le x\le(N+1)u@@`），则存在单酉 *-同态 `@@M@@\mathcal Z\to F_\omega(A)@@`，从而 `@@M@@A\cong A\otimes\mathcal Z@@`。其三：典范映射 `@@M@@\Cu(A)\to\Cu(A\otimes\mathcal Z)@@` 是同构即保证吸收。其四：`@@M@@A\cong A\otimes\mathcal Z@@` 当且仅当 `@@M@@\Cu(A)\cong\Cu(A\otimes\mathcal Z)@@` 在 Cu 范畴中抽象同构（不必由任何 *-同态诱导）。后两条分别肯定回答非单 Toms–Winter 问题的 (iii)`@@M@@\Rightarrow@@`(ii) 与 Problems 2025 的问题 XXVI。

## 证明思路

布局是两条进路汇入同一构造。单代数进路只需精确性（exactness），不需可分与核：先把迹值逐级转移到越来越小的遗传支撑（hereditary support）中、在整数水平取整（rounding），再把各级碎片装进一个范数收敛的稳定块直和；所有误差相对一个固定的非零谱切割度量并做成可和，故原类的泛函值为无穷亦无妨；零泛函与在每个非零类上恒取无穷的泛函由一条三分类引理单独处理，使整个扩迹锥都可用而无需公共归一化——这正是非酉代数没有统一迹空间时的替代方案；比较假设最后提供三明治 `@@M@@Nu\le x\le(N+1)u@@` 的两侧，得到完全几乎可除，汇入条件 (C)。

公共吸收进路用可分性与核性，目标是中心矩阵锥（matrix cone，即 `@@M@@M_p@@` 的 c.p.c. 零阶序映射）`@@M@@\alpha:M_p\to F_\omega(A)@@` 加缺陷填充元 `@@M@@s@@`，满足 `@@M@@s^*s=1-\alpha(1)@@`、`@@M@@\alpha(e_{11})s=s@@`——这恰是素维数坠落代数（prime dimension-drop algebra）`@@M@@I(p,p+1)@@` 的酉表示。先由支撑收缩（support shrinking）与纯态词模型构造范数可见的中心矩阵锥，用以固定坐标理想重数；再由 Hirshberg–Kirchberg–White 与 Brown–Carrión–White 的凸零阶序（order-zero）核逼近构造迹锥，其精度在重数固定之后才选取。随后谱余量先产生精确的坐标 Cuntz 不等式、再控制比较见证使之与矩阵大小无关，从而允许一列缓慢增长的正交等价"中心槽位"；对角化时用 Choi–Effros 提升与 Arveson 扩张保住映射的完全正性；Gabe 的近似支配定理把有限次同时压缩打包进槽位，把维数坠落关系升格为单一的中心拷贝 `@@M@@\mathcal Z\to F_\omega(A)@@`；最后按 Nawata 的非幺判据做提升与缠绕，完成 `@@M@@A\cong A\otimes\mathcal Z@@`。

## 可信度与备注

本文主结果尚无 Lean 形式化证明，请以社区核验为准。它是结果族 291 的序论支柱：姊妹篇核维数论文把本文推论引为其 Cuntz 半群判据，等变稳定性论文在其铺就的 `@@M@@\mathcal Z@@`-稳定地基上处理群作用。文中大量使用经典工具（Winter–Zacharias 零阶序结构定理、Choi–Effros 提升、Arveson 扩张、Jiang–Su 及 Rørdam–Winter 关于 `@@M@@\mathcal Z@@` 的结构性定理），新构造集中于中心锥与打包步骤。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
