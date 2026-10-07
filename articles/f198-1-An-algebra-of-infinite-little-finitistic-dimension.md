---
layout: default
title: "An algebra of infinite little finitistic dimension"
family: "198"
discipline: "Algebra"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | An algebra of infinite little finitistic dimension

> 结果族 198：A counterexample to finitistic-dimension finiteness　·　学科：Algebra　·　验证状态：主结果已 Lean 形式化

## 一句话结论

构造出一个复数域上的有限维代数 `@@M@@A@@`：对任意 `@@M@@m\ge1@@` 都有有限维模 `@@M@@N_m@@` 满足 `@@M@@2m-2\le\pd_A N_m<\infty@@`。同一个代数上有限投射维数无上界，Bass 提出的有限维代数小有限维数猜想（little finitistic-dimension conjecture）被否定。

## 问题背景

对域 `@@M@@k@@` 上的有限维代数 `@@M@@A@@`，其小有限维数（little finitistic dimension）`@@M@@\findim A@@` 是诸有限生成左模中投射维数（projective dimension）有限者的上确界；把范围放宽到所有左模，就得到大有限维数（big finitistic dimension）`@@M@@\Findim A@@`。Bass 于 1960 年普及了这一问题，其猜想断言：每个有限维代数都有 `@@M@@\findim A<\infty@@`。它允许个别投射分解永不终止，只问"会终止的分解"长度是否一致有界。已知的正面情形包括单项代数（monomial algebra）、根基三次幂为零的 Artin 代数与表示维数（representation dimension）至多 `@@M@@3@@` 的代数；Huisgen-Zimmermann 1992 年的例子有 `@@M@@\findim=n@@`、`@@M@@\Findim=n+1@@`，否定了二者相等，但维数仍有限。卡点是：能否在同一个代数上让有限投射维数任意大？本文造出这样的代数，否定猜想。

## 主要结果

主定理：存在复数域上的有限维含幺代数 `@@M@@A@@`，使得对每个整数 `@@M@@m\ge1@@` 都有有限维左 `@@M@@A@@`-模 `@@M@@N_m@@` 满足 `@@M@@2m-2\le\pd_A N_m<\infty@@`。关键在量词顺序：`@@M@@A@@` 先于 `@@M@@m@@` 固定，故其有限生成模有长度无界的终止投射分解，`@@M@@\findim A=\infty@@`；又因小维数不超过大维数，`@@M@@\Findim A=\infty@@`，反驳了 Artin 代数的普遍有限性断言。由 Rickard 定理（内射生成（injective generation）蕴含大维数有限）知其内射左模不生成无界导出范畴。结合 Cummings 的三角矩阵构造还得到极端左右不对称的推论：存在 `@@M@@\Lambda@@`，其左小、大维数均为 `@@M@@\infty@@`，右侧均为 `@@M@@0@@`。

## 证明思路

证明分三步，把"逐次挑选"的群论过程翻译成同调代数，再压进一个固定代数。

第一阶段构造熄灭时间任意长的选择过程（selection process）。文中给出源于 Abels 型矩阵群的有限表现群 `@@M@@G@@`：生成元 `@@M@@T_1,T_2,T_3@@` 共轭时平移三族生成元 `@@M@@U_i(r),V_i(r),W_{ij}(r)@@` 的下标。核心产物是一族中心对合（central involution）`@@M@@z_N=[U_i(a),V_i(b)]@@`（`@@M@@a+b=N@@`），以及把 `@@M@@z_N@@` 平移到 `@@M@@z_{N+1}@@` 的自同构。取群代数（group algebra）`@@M@@R=\C G@@` 与中心幂等元（central idempotent）`@@M@@e=(1+z_0)/2@@`，令 `@@M@@H(Y)={}_\alpha(eY)@@`（取 `@@M@@eY@@` 并拉回作用），迭代满足 `@@M@@H^{\circ j}(Y)\cong{}_{\alpha^j}(e_0\cdots e_{j-1}Y)@@`。对每个 `@@M@@m@@`，用 `@@M@@\F_2[t]/(t^m-1)@@` 上的矩阵造有限商群，使 `@@M@@z_0,\ldots,z_{m-1}@@` 的像独立生成 `@@M@@(\Z/2)^m@@`；再以特征标（character）取模 `@@M@@Y_m@@`，使前 `@@M@@m-1@@` 个幂等元恒等、第 `@@M@@m@@` 个为零，则 `@@M@@H@@` 恰在第 `@@M@@m@@` 次迭代后熄灭。

第二阶段把选择实现为一次导出张量（derived tensor product）。先把 `@@M@@R@@` 的二次表现齐次化为三点有向代数 `@@M@@B@@`，无长度三的路径使 `@@M@@B@@` 有限维且 `@@M@@\gldim B\le2@@`；再在同伦范畴中反转两条特殊箭头，得 Verdier 商（Verdier quotient）范畴，`@@M@@R@@` 作用于其上。障碍有二：幂等元在商范畴中未必分裂，"奇双层"引理表明 `@@M@@U\oplus U[3]@@` 反而同构于真实对象，故改而实现 `@@M@@eY\oplus(eY)[3]@@`；商范畴的态射是分式，需一次性"通分"提升回同伦范畴，关系只余链同伦（chain homotopy）意义。三列微分矩阵把这些同伦编入真实的 `@@M@@B@@`-双模（bimodule）复形 `@@M@@P@@`；无更长路径，故无高阶相干障碍。最后 `@@M@@\gldim B\le2<4@@` 迫使截断三角形分裂，得到对一切 `@@M@@Y@@` 一致的 `@@M@@P\otL_B M(Y)\simeq M(H(Y))\oplus M(H(Y))[3]@@`。

第三阶段换成普通代数。用根基平方零的链代数记录 `@@M@@P@@` 的各项与微分得普通双模，在积代数 `@@M@@D@@` 上取 `@@M@@X@@`，使两步导出张量 `@@M@@F^2@@` 恰是一次实现；再取平方零扩张（square-zero extension）`@@M@@A=D\ltimes X@@`。bar 分解按单词中 `@@M@@X@@` 的个数拆分出 `@@M@@D\otL_A N\simeq\bigoplus_{r\ge0}(F^rN)[r]@@`（`@@M@@X^2=0@@` 保证不混合）。于是 `@@M@@F^{2m}N_m\simeq0@@` 经极小投射分解（minimal projective resolution）与 Nakayama 引理给出 `@@M@@\pd_A N_m<\infty@@`，而 `@@M@@F^{2m-2}N_m\not\simeq0@@` 给出下界 `@@M@@2m-2@@`。

## 可信度与备注

按任务文件标注，本文主结果已通过 Lean 形式化验证。结果族 198 的姊妹篇在特征 `@@M@@2@@` 情形用投射–内射分解的逐次余核独立构造出小、大有限维数均无穷的反例，与本复数域反例方法不同、结论互证。依 OpenAI 官方声明，未经形式化的结果可能存在问题，故文中其余构造细节仍应以社区核验为准。

{% endraw %}
