---
layout: default
title: "Polynomial Hitting Lists for Noncommutative Rational Formulas"
family: "116"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Polynomial Hitting Lists for Noncommutative Rational Formulas

> 结果族 116：Uniform black-box noncommutative identity testing across characteristics　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

这篇的电路多了"除法"键——矩阵世界的除法是求逆，一旦代进去的矩阵不可逆，整个求值就地卡死。于是单个万能钥匙不够用了，论文改配一整串钥匙：只要公式本身"有救"（存在合法求值），钥匙串里总有一把既不把锁芯卡死、还能拧出非零的转动。

**关键词卡片**

- 有理非交换公式（noncommutative rational formula）：在加减乘之外允许"求逆门"的计算电路。
- 求逆门（inverse gate）：对中间结果取逆的一元门；矩阵不可逆时该处求值无定义。
- 可采纳（admissible）：公式至少存在一处代入，使求值有定义。
- 打击列表（hitting list）：一列矩阵元组；非零可采纳公式必在某个元组处求值有定义且取值可逆。
- 黑盒（black-box）：只许代入求值、不许看内部描述的访问方式。

**看个具体例子**

先看一个带除法的迷你公式长什么样：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 300">
  <text x="25" y="40" font-size="15">Φ = x₁ + (x₂·x₃)⁻¹</text>
  <circle cx="280" cy="55" r="22" fill="none" stroke="#333" stroke-width="2"/>
  <text x="280" y="61" text-anchor="middle" font-size="18">⊕</text>
  <circle cx="130" cy="145" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="130" y="151" text-anchor="middle" font-size="15">x₁</text>
  <rect x="383" y="120" width="74" height="50" rx="12" fill="none" stroke="#333" stroke-width="2"/>
  <text x="420" y="151" text-anchor="middle" font-size="15">(·)⁻¹</text>
  <circle cx="420" cy="222" r="22" fill="none" stroke="#333" stroke-width="2"/>
  <text x="420" y="228" text-anchor="middle" font-size="18">⊗</text>
  <circle cx="330" cy="272" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="330" y="278" text-anchor="middle" font-size="15">x₂</text>
  <circle cx="510" cy="272" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="510" y="278" text-anchor="middle" font-size="15">x₃</text>
  <line x1="263" y1="70" x2="147" y2="130" stroke="#333" stroke-width="2"/>
  <line x1="297" y1="70" x2="402" y2="120" stroke="#333" stroke-width="2"/>
  <line x1="420" y1="170" x2="420" y2="200" stroke="#333" stroke-width="2"/>
  <line x1="403" y1="237" x2="347" y2="260" stroke="#333" stroke-width="2"/>
  <line x1="437" y1="237" x2="493" y2="260" stroke="#333" stroke-width="2"/>
  <text x="25" y="225" font-size="13">圆 = 加/乘门，圆角方框 = 求逆门：</text>
  <text x="25" y="248" font-size="13">代入的 x₂·x₃ 不可逆时，求值就地卡死</text>
</svg>

</div>

论文定理：只凭 `@@M@@n@@` 和 `@@M@@s@@`，确定性机器在多项式比特时间内输出一份多项式长的有理矩阵元组列表；任何规模 `@@M@@\le s@@` 的非零可采纳公式，必在列表中某处取到有定义且可逆的值——与公式里有理常数的位数、逆门嵌套多深都无关。

**为什么值得关心**

它把含除法门的黑盒非交换恒等测试从拟多项式打击集降到多项式大小的列表，解决了 Garg–Gurvits–Oliveira–Wigderson 提出的黑盒 SINGULAR 构造问题的有理系数版本。

> 已 Lean 形式化

## 一句话结论
对含求逆门的有理非交换公式，确定性生成器仅凭变量数 `@@M@@n@@` 与规模 `@@M@@s@@`，在多项式比特时间内输出多项式大小的有理矩阵列表，使每个非零且可采纳的公式在某个元组处求值有定义且取值可逆，把黑盒有理恒等测试的打击集从拟多项式降到多项式规模。

## 问题背景
有理非交换公式（noncommutative rational formula）在加法、有序乘法之外允许一元求逆门，求值时要求每个逆门遇到的矩阵都可逆，否则该求值无定义。Hrubeš–Wigderson（2015）建立了这一计算模型并把它化为线性矩阵奇异性测试；随后算子缩放与非交换秩计算（GGOW、IQS 等）给出读取输入的白盒确定性多项式时间算法，但它们都要用到公式的具体系数。黑盒方面，Arvind–Chatterjee–Mukhopadhyay 先后对逆高度 2 与任意逆嵌套给出拟多项式大小的有理矩阵打击集；Derksen–Makam 证明可采纳公式存在定义求值所需的维度多项式界并由此得到随机算法。悬而未决：能否只凭规模参数、不依赖输入系数，确定性生成通用打击列表并具多项式维度？这正对应 Garg–Gurvits–Oliveira–Wigderson 提出的黑盒 SINGULAR 构造问题的有理系数版本。本文在 `@@M@@\mathbb Q@@` 上解决。

## 主要结果
定理 1.1：存在确定性图灵机 `@@M@@G@@` 与常数 `@@M@@C,k@@`：输入 `@@M@@1^n,1^s@@`，输出有限列表 `@@M@@\mathcal H_{n,s}@@`，成员是 `@@M@@n@@` 个有理方阵构成的元组；生成时间与输出总比特长均不超过 `@@M@@C(n+s+1)^k@@`。对每个规模至多 `@@M@@s@@` 的非零可采纳（admissible，即存在某个正维数的有理矩阵求值有定义）有理公式 `@@M@@\Phi@@`，列表中某元组给出 `@@M@@\Phi@@` 的一个有定义求值，且取值可逆。可逆值结论强于非零值要求。同一列表适用于一切这样的公式，与其有理常数的比特长、逆门嵌套深度无关；生成器不接收公式、不用随机性或外部建议，所有元组共享仅依赖 `@@M@@n,s@@` 的同一维数。论文另有推论：同一构造打击每个阶至多 `@@M@@B@@` 的可行（feasible）有理仿射铅笔（affine linear pencil，形如 `@@M@@A_0+\sum_iA_ix_i@@` 的矩阵）；并构造非自适应列表，用归一化求值的秩恢复长方有理铅笔的非交换秩（noncommutative rank，即自由除环上的秩）。

## 证明思路
证明按"桥接—扩张—变形—有理化"四步展开。第一步把公式树编码为线性代数：对每个子树 `@@M@@h@@` 构造仿射铅笔 `@@M@@L_h@@` 与常值行、列 `@@M@@u_h,v_h@@`，使 `@@M@@h=u_hL_h^{-1}v_h@@`，其中逆门对应块矩阵 `@@M@@\begin{pmatrix}L_g&v_g\\u_g&0\end{pmatrix}@@`，铅笔阶数为 `@@M@@|h|+1@@`。规模 `@@M@@s@@` 的公式由此给出至多 `@@M@@s+1@@` 个阶 `@@M@@\le B=2s+1@@` 的铅笔，它们同时可逆恰保证原树每个逆门有定义且终值可逆。配合除环提升引理——把任一有定义非零求值中的矩阵提升进循环符号除环（cyclic/symbol division algebra），非零值即成可逆值——非零可采纳公式必拥有这样一族可行铅笔。这一步保留了原公式树：后来会消去的分支里的求逆条件同样要满足。

第二步解决"在与系数无关的矩阵上取得高秩"：构造 `@@M@@n+1@@` 个 `@@M@@\mathbb Q[t]@@` 上的长方矩阵 `@@M@@R_i(t)@@`，它们反转在互异点 `@@M@@0,\ldots,n@@` 处的 Taylor 展开并以 `@@M@@t@@` 的幂加权 Taylor 系数；Wronskian 界表明，任何维数 `@@M@@\le B@@` 的非零子空间（系数甚至可取 Laurent 级数）的诸像之和的维数严格超过其维数的 `@@M@@n@@` 倍，从而可行铅笔满足 `@@M@@\rank\bigl(\sum_iA_i\otimes R_i(t)\bigr)>(q-1)M@@`。第三步做除环变形：引入参数 `@@M@@p,r@@`，以 `@@M@@X=pD@@`、`@@M@@Y=rS@@`（`@@M@@XY=\omega YX@@`，`@@M@@\omega@@` 为单位根）生成嵌于 `@@M@@M\times M@@` 矩阵的除环，块元素落入其中时普通秩被 `@@M@@M@@` 整除，故上述严格不等式强制满秩 `@@M@@qM@@`；相应行列式是 `@@M@@t,p,r@@` 的次数 `@@M@@\le3BM^2@@` 的非零多项式，左除 `@@M@@R_0^*@@` 则恢复铅笔的常数项。第四步消除单位根并落到有理数：用代数 `@@M@@\mathcal R=\mathbb Q[\xi]/(\xi^\ell+1)@@`（`@@M@@M@@` 取 2 的幂，`@@M@@\ell=M/2@@`）的正则表示把单位根系数替换为有理矩阵，可逆条件须在全部 `@@M@@\ell@@` 个根处同时成立。对固定公式，至多 `@@M@@s+2@@` 个铅笔与 `@@M@@\ell@@` 个根的行列式条件之积是次数有界的非零多项式，因此固定的三维整数网格 `@@M@@\{1,\ldots,H\}^3@@` 中必有一点使其非零；生成器对每个格点计算 `@@M@@Z_i=\rho_M(\widetilde R_i(t_0,p_0,r_0))@@`，凡 `@@M@@Z_0@@` 可逆即输出元组 `@@M@@(Z_0^{-1}Z_1,\ldots,Z_0^{-1}Z_n)@@`。精确有理算术给出时间与输出的比特界。

## 可信度与备注
据结果族元信息，本文主结果已附 Lean 形式化证明；本族另两篇姊妹篇（无除法公式的单个打击点、正特征素域打击点）暂无形式化，按 OpenAI 官方声明"未经形式化的结果可能有问题"，宜以社区核验为准。三篇共享"编码 + 秩或阶数界 + 有限化下降"的框架并互相支撑，本文处理其中最一般的带除法情形，且其打击列表只需规模参数即可生成。

{% endraw %}
