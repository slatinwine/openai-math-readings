---
layout: default
title: "A translational tile with no fully periodic tiling in dimension three"
family: "155"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A translational tile with no fully periodic tiling in dimension three

> 结果族 155：A counterexample to periodic tiling in dimension three　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

贴瓷砖时，如果花纹能周期性重复，活儿就轻松：找到一小段基本单元，平移复制即可铺满整面墙。周期铺砌猜想猜的就是"能铺满的瓷砖必有周期铺法"。这篇论文在三维造出一块叛逆瓷砖：它铺得满三维格点空间，却不存在任何周期铺法。

**关键词卡片**

- 平移铺砌（translational tiling）：只用平移（不旋转、不翻转）把瓷砖不重不漏地盖满空间。
- 周期铺法（periodic tiling）：存在平移向量，挪完后整幅图案与原来重合。
- 全周期（fully periodic）：平移集在某个有限指标子群下不变的严格说法。
- 格 ℤ³：三维整数坐标点组成的空间，即铺砌发生的"棋盘"。

**看个具体例子**

示意图：同样的方砖与长砖，上排按周期排列，平移一个周期图案重合；下排打乱后，任何平移都对不上：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="32" text-anchor="middle" font-size="16">同样的砖，两种铺法（示意）</text><text x="70" y="100" font-size="14">周期铺法：</text><rect x="160" y="80" width="40" height="40" fill="#e8e8e8" stroke="#333"/><rect x="210" y="80" width="80" height="40" fill="#c9c9c9" stroke="#333"/><rect x="300" y="80" width="40" height="40" fill="#e8e8e8" stroke="#333"/><rect x="350" y="80" width="80" height="40" fill="#c9c9c9" stroke="#333"/><rect x="440" y="80" width="40" height="40" fill="#e8e8e8" stroke="#333"/><line x1="160" y1="62" x2="280" y2="62" stroke="#2e7d32"/><polygon points="160,62 168,58 168,66" fill="#2e7d32"/><polygon points="280,62 272,58 272,66" fill="#2e7d32"/><text x="330" y="52" font-size="13" fill="#2e7d32">平移一个周期，图案重合</text><text x="70" y="180" font-size="14">无周期铺法：</text><rect x="160" y="160" width="80" height="40" fill="#c9c9c9" stroke="#333"/><rect x="250" y="160" width="40" height="40" fill="#e8e8e8" stroke="#333"/><rect x="300" y="160" width="40" height="40" fill="#e8e8e8" stroke="#333"/><rect x="350" y="160" width="80" height="40" fill="#c9c9c9" stroke="#333"/><rect x="440" y="160" width="80" height="40" fill="#c9c9c9" stroke="#333"/><text x="280" y="230" text-anchor="middle" font-size="14" fill="#c0392b">任何平移都无法让整幅图案重合</text><text x="280" y="260" text-anchor="middle" font-size="13" fill="#555">论文：三维格点中存在只能无周期铺砌的有限瓷砖</text></svg>

</div>

论文的瓷砖是 ℤ³ 里一组有限格点 T：存在平移集 A 使 A⊕T=ℤ³（每点恰被盖一次），但任何铺法的平移集都不是全周期的；把它加厚成实体 Ω=T+[0,1]³ 后，在 ℝ³ 中允许任意实数平移，结论不变。

**为什么值得关心**

一维（Newman）与二维（Bhattacharya）的答案都是"必有周期"，三维是第一个失败维度——猜想在最小可能的维度被否定。

> 已 Lean 形式化

## 一句话结论

本文在 `@@M@@\mathbb{Z}^3@@` 中构造出一块有限平移瓷砖（translational tile）`@@M@@T@@`：它能铺满 `@@M@@\mathbb{Z}^3@@`，却没有任何全周期铺法；其单位立方体加厚在 `@@M@@\mathbb{R}^3@@` 中同样如此，即便允许任意实数平移向量。周期铺砌猜想由此在最小可能的维度三被否定。

## 问题背景

铺砌理论的基本问题：一块"瓷砖"能否用自身的平移副本不重不漏地盖满空间？能铺满的瓷砖若还容许周期铺法，就有了可把握的结构。周期铺砌猜想（periodic tiling conjecture，Lagarias–Wang 给出显式欧氏表述）断言每个平移瓷砖都容许周期铺法。低维证据全是正面的：Newman 的有限状态论证表明 `@@M@@\mathbb{Z}@@` 中有限瓷砖的每条铺法都周期；Bhattacharya 证明 `@@M@@\mathbb{Z}^2@@` 的每个有限瓷砖都有周期铺法，Greenfeld–Tao 又给出定量强化。而 Greenfeld–Tao 已在足够高的维度造出反例。三维因此是悬而未决的最小维度，本文将其解决，答案是否定的。

## 主要结果

记 `@@M@@A\oplus F=G@@` 表示交换群 `@@M@@G@@` 中每个元素都有唯一分解 `@@M@@g=a+f@@`（`@@M@@a\in A@@`，`@@M@@f\in F@@`）；铺法称为全周期（fully periodic），指平移集 `@@M@@A@@` 在某个有限指标子群（subgroup of finite index）下不变。定理 1.1：存在有限非空集 `@@M@@T\subset\mathbb{Z}^3@@`，(i) `@@M@@T@@` 可平移铺满 `@@M@@\mathbb{Z}^3@@`，但任何满足 `@@M@@A\oplus T=\mathbb{Z}^3@@` 的平移集都不在有限指标子群下不变；(ii) 加厚体 `@@M@@\Omega=T+[0,1]^3@@` 在 `@@M@@\mathbb{R}^3@@` 中可铺满（至多差零测集），但没有铺法的平移集在满秩格（full-rank lattice）下不变。由 Newman 与 Bhattacharya 的一、二维正面结果，三维是该结论在格铺砌情形下可能成立的最小维度。

## 证明思路

证明遵循 Greenfeld–Tao 的"数独编码"策略，分四步。

第一步先造自带非周期性的组合障碍。取素数 `@@M@@p>200@@`、字母表 `@@M@@\Sigma=\F_p^\times@@`、列集 `@@M@@I=\{0,\dots,p^2-1\}@@`。线规则（line rule）要求数组 `@@M@@W@@` 在每条整数斜率直线 `@@M@@m=dn+e@@` 上的采样词都是允许词（allowed word）：存在不被 `@@M@@p@@` 同时整除的 `@@M@@a,b@@`，使词值恰为 `@@M@@an+b@@` 的最后一个非零 `@@M@@p@@` 进数字。核心命题：满足线规则且每列非常数的数组没有正的竖直周期（vertical period）。证明先做全局仿射逼近——数出一块无例外的 `@@M@@4\times4@@` 方块再沿行双向传播，得 `@@M@@W@@` 几乎处处等于非零仿射型 `@@M@@An+Bm+C@@`；再证每列非常数等价于 `@@M@@B\ne0@@`，且周期必被 `@@M@@p@@` 整除；最后对极小周期 `@@M@@M@@` 作伸缩 `@@M@@W_1(n,m)=W(n,pm)@@`，得到周期 `@@M@@M/p@@` 的更小解，无穷下降矛盾。模型 `@@M@@W(n,m)=f(m)@@`（`@@M@@f@@` 为最后非零数字函数）表明这种数组存在。

再把词约束编码成同一未知集 `@@M@@A@@` 的联立铺砌方程（simultaneous tiling equations）。环境群 `@@M@@G=\mathbb{Z}^2\times V@@`，其中有限群 `@@M@@V@@` 的各因子阶两两互素，故为循环群——这是与高维反例的关键差别。图方程 `@@M@@A\oplus H_0=G@@` 把 `@@M@@A@@` 逼成函数图；每列对应一个通道，其有用输出只许依赖 `@@M@@(L_n(x),k_n)@@`（`@@M@@L_n(x)=x_2+nx_1@@` 为线映射）；符号由活跃性编码：改动对应的输入数位能改变输出即称活跃。循环测试瓷砖凭排列判据禁止禁词同时活跃；两个种子通道在特定余数类强制常数词 `@@M@@1@@`、`@@M@@2@@`，保证每列非常数；激活测试再保证每个普通位置至少活跃一个符号。于是全周期公共解会导出带竖直周期的合规数组，与第一步矛盾；第 5 节又显式构造出公共解：普通通道 `@@M@@i@@` 恰好活跃 `@@M@@f(L_i(x))@@`，一个共享输出同时满足两个种子测试。

然后堆叠合并：取新素数 `@@M@@q@@`，随机染色给出 `@@M@@\Zmod{q}=E_1\sqcup\cdots\sqcup E_s@@` 且每色差集为全群，把方程堆叠成 `@@M@@\mathbb{Z}^2\times\Zmod{Q}@@`（`@@M@@Q=q|V|@@`，仍循环）中的单块瓷砖 `@@M@@F@@`：可铺砌、无全周期铺法。

最后升维并驯服实平移。经投影 `@@M@@\pi:\mathbb{Z}^3\to\mathbb{Z}^2\times\Zmod{Q}@@`（核为 `@@M@@\mathbb{Z} w@@`），用概率法选出剩余代表元横截 `@@M@@T_0@@`，其差集覆盖所有不超过 `@@M@@m@@` 的非格向量；移动一个标记点得 `@@M@@T_1@@`，拼出最终瓷砖 `@@M@@T@@`，铺砌存在性由 `@@M@@B=\pi^{-1}(A)@@` 直接验证。关键的刚性论证处理任意实平移：大公共部分把假设周期铺法的部件中心逼进同一 `@@M@@m\mathbb{Z}^3@@` 陪集（辅助立方体的测度计数加图连通性），标记点的覆盖又强制平移集沿核方向不变，铺砌遂可下降到商群，产生 `@@M@@F@@` 的全周期铺砌——矛盾。单位立方体加厚把结论同样带到 `@@M@@\mathbb{R}^3@@`。

## 可信度与备注

主结果（定理 1.1 两条）已由 Lean 形式化验证（族文档 lean/docs/155.md），论文完整给出每个构造与非周期性论证；有限瓷砖数据可经会终止的有限搜索选出，证明可铺砌性的无穷铺法则由最后非零数字函数显式给出。本结果族仅此一篇，离散与欧氏两条结论落在同一块瓷砖上，互相印证。按 OpenAI 官方声明"未经形式化的结果可能有问题"，本文主结果已形式化，属可信度最高一档；但定理只排除全周期铺法，未断言瓷砖连通，也不排除单个非零周期。

{% endraw %}
