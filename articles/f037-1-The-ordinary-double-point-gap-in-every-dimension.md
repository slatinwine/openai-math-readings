---
layout: default
title: "The ordinary-double-point gap in every dimension"
family: "037"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The ordinary-double-point gap in every dimension

> 结果族 037：The ordinary-double-point volume gap　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对任意 `@@M@@n\ge2@@`，证明了普通双重点（ordinary double point）体积间隙猜想：每个奇异的、边界为零的 klt 复代数 `@@M@@n@@` 维芽的正规化体积至多 `@@M@@2(n-1)^n@@`，等号恰在解析普通双重点取到，从而完整刻画了"仅次于光滑点"的第二大体积值。

## 问题背景

正规化体积（normalized volume）由 Chi Li 提出：对 klt 芽 `@@M@@(x,X)@@`，在所有中心在 `@@M@@x@@` 的实赋值（valuation）`@@M@@v@@` 上取 `@@M@@\widehat{\mathrm{vol}}(x,X)=\inf_v A_X(v)^n\operatorname{vol}(v)@@`，其中 `@@M@@A_X(v)@@` 是对数差异（log discrepancy），`@@M@@\operatorname{vol}(v)@@` 是赋值理想的渐近余长。Liu–Xu 证明光滑点恰取最大值 `@@M@@n^n@@`。受奇异 Kähler–Einstein 度量极限中体积密度的启发，Spotti–Sun 猜想：奇异芽体积不超过 `@@M@@2(n-1)^n@@`，等号刻画的正是最简单的奇点——非退化二次型定义的解析超曲面芽。该猜想也列入 Xu–Zhuang 的 K-稳定性公开问题清单。此前已知曲面（Li–Liu 的商奇点计算）、三维（Liu–Xu）、完备交（complete intersection，Liu）与环面（toric，Moraga–Süß）等带结构假设的情形；完全无结构假设的高维情形一直没有突破，难点在于一般 klt 芽既没有局部环表示，也没有现成的例外除子可用。

## 主要结果

**定理（每维数的 ODP 间隙）**：设 `@@M@@n\ge2@@`，`@@M@@x@@` 是正规复代数 `@@M@@n@@` 折迭 `@@M@@X@@` 的奇异闭点，`@@M@@K_X@@` 为 `@@M@@\mathbb{Q}@@`-Cartier 且 `@@M@@X@@` 在 `@@M@@x@@` 附近 klt、边界为零，则 `@@M@@\widehat{\mathrm{vol}}(x,X)\le2(n-1)^n@@`；等号成立当且仅当解析芽 `@@M@@(X,x)_{\mathrm{an}}@@` 同构于 `@@M@@\{z_0^2+\cdots+z_n^2=0\}\subset\mathbb{C}^{n+1}@@`。

**推论（全局体积界）**：奇异 K-半稳定 `@@M@@\mathbb{Q}@@`-Fano `@@M@@n@@` 折迭 `@@M@@V@@` 满足 `@@M@@(-K_V)^n\le2\bigl(\frac{n^2-1}{n}\bigr)^n<2n^n@@`；若 `@@M@@V\not\cong\mathbb{P}^n@@`，则 `@@M@@(-K_V)^n\le2n^n@@`，等号恰为光滑二次超曲面或 `@@M@@\mathbb{P}^1\times\mathbb{P}^{n-1}@@`。

## 证明思路

证明对 `@@M@@n@@` 归纳，基例是已知的二维、三维以及姊妹篇的四维定理。记密度 `@@M@@d=\widehat{\mathrm{vol}}/n^n@@`、阈值 `@@M@@p_n=2(\frac{n-1}{n})^n@@`，归纳步设 `@@M@@n=N+1\ge5@@`。

先做锥化约：对 `@@M@@d\ge p_n@@` 的奇异芽使用稳定退化（stable degeneration，Blum–Xu–Xu–Zhuang–LWX 系列），得到密度相同的 K-polystable Fano 锥 `@@M@@C@@`，且原芽的嵌入维数不超过锥的。再借助赋值密度的下半连续性与归纳假设（乘积引理加有限次公式）逐层压出结构：锥的顶点之外必须光滑，典范指标必为 `@@M@@1@@`，从而 `@@M@@C@@` 正规 Gorenstein——这些都是化约的结论，而非对原芽的假设。

随后用整值分次（integral grading）逼近极小化 Reeb 向量（Reeb vector）：分次的商是光滑 orbifold `@@M@@B@@`，带忠实丰富线丛 `@@M@@L@@` 且 `@@M@@-K_B=rL@@`。按最大稳定子阶 `@@M@@m_{\max}@@` 与 `@@M@@r/N@@` 的大小分两路推进。

小稳定子路（`@@M@@m_{\max}\le r/N@@`）：沿 Mori 弯折法脉络取一条极小 orbifold 有理曲线（Li–Zhou 构造、AOV 紧性）；若分次不自由，其形变给出映满 `@@M@@C@@` 的有限求值映射，把各叶的无穷小平移乘起来得到非零对称张量，再用 Collins–Székelyhidi 的 Ricci-flat 锥度量给出权上界，逼出自由分次且典范权恰为 `@@M@@N@@` 或 `@@M@@N+1@@`；最后由 Kobayashi–Ochiai 型高指标分类，`@@M@@(B,L)@@` 只能是二次曲面或射影空间，故 `@@M@@C@@` 是 ODP 锥或光滑。

大稳定子路（`@@M@@m_{\max}\ge r/N@@`）：在最大稳定点记录每个截面的次数与横截 Taylor 首项指数，构成格点半群 `@@M@@\Gamma@@`，其典范点 `@@M@@c_0=(r,1,\dots,1)@@`；近极小性给出的矩不等式与一个指数期望估计共同把 `@@M@@c_0@@` 压入锥内部，配合 Howald 乘子理想公式与 Kawamata–Viehweg 消没提升 Taylor 单项式，迫使 `@@M@@\Gamma@@` 有理多面体化且恰好饱和。两次滤过（filtration）由此构造出同维数的奇异 klt 切片 `@@M@@Y@@`，其上第二个稳定子 `@@M@@h\ge2@@` 使单一特征标只承担 `@@M@@1/h@@` 的首项余长，经 Hölder 优化得 `@@M@@d(o,C)\le\frac{p_n+M_n}{2}@@`，其中 `@@M@@M_n@@` 是奇异 `@@M@@n@@` 维密度的上确界。对逼近 `@@M@@M_n@@` 的序列套用此式即得 `@@M@@M_n\le p_n@@`——这一步只用了 `@@M@@M_n@@` 的定义，规避了同维数循环论证。

等号分析：逐环追等号得 `@@M@@h=2@@`、限制赋值 `@@M@@w=\frac{2N}{n}\mathrm{wt}_\xi@@`；一个严格余长计数给出 `@@M@@w(v)\le2@@`，整数取整进而迫使 `@@M@@Nm_{\max}\le r@@`，回到小稳定子情形，故 `@@M@@C@@` 是 ODP 锥，原芽嵌入维数 `@@M@@\le n+1@@` 而为超曲面芽。最后用加权超曲面测试（在二次部分缺失的方向赋权 `@@M@@1-\epsilon@@`）证明等号迫使次数为 `@@M@@2@@` 且二次部分非退化，全纯 Morse 引理收尾。

## 可信度与备注

本文暂无形式化证明，按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。文章把稳定退化、有限次公式、差异几何与经典分类定理等成熟文献作为公开输入并逐一标明引用。姊妹篇《The normalized-volume gap in dimension four》证明四维基例，本文以它为唯一伴随输入向上归纳，两篇合起来给出猜想的完整证明。论文还自足完成 ODP 处的体积计算：利用调和多项式表示的不可约性与极小赋值的唯一性，把极小赋值钉在次数赋值上，得 `@@M@@2(n-1)^n@@`。

{% endraw %}
