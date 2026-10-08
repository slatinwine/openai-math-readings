---
layout: default
title: "Classical capacity and entropy inequalities for generalized amplitude damping"
family: "276"
discipline: "Mathematical physics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Classical capacity and entropy inequalities for generalized amplitude damping

> 结果族 276：Classical capacity of generalized amplitude damping　·　学科：Mathematical physics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

一个发光的量子比特泡在热环境里：激发会衰变掉，环境的热又会把它往回泵。沿这条"最熟悉的噪声管道"，经典信息最多能传多快？发送方可以把消息编成整块纠缠的量子态、接收方做联合测量，但本文证明这样做毫无增益——答案是算一个一元函数的最大值即可，量子信息论里少见的"一锤定音"。

**关键词卡片**

- 广义振幅阻尼（generalized amplitude damping）：量子比特与定温热环境相互作用的噪声信道，参数 γ 与 ν。
- 经典容量（classical capacity）：无误传信速率的上限。
- Holevo 容量（Holevo capacity）：单次使用信道时最优编码的平均信息量。
- 可加性（additivity）：多次使用不比单次更高效的性质，Hastings 已证一般不成立。
- 最小输出熵（minimum output entropy）：信道输出最"纯"时的熵。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="150" y1="80" x2="330" y2="80" stroke="#333" stroke-width="2.5"/><text x="344" y="85" font-size="15" fill="#333">|1⟩ 激发态</text><line x1="150" y1="200" x2="330" y2="200" stroke="#333" stroke-width="2.5"/><text x="344" y="205" font-size="15" fill="#333">|0⟩ 基态</text><line x1="200" y1="90" x2="200" y2="190" stroke="#c0392b" stroke-width="2.5"/><polygon points="200,190 194,178 206,178" fill="#c0392b"/><text x="60" y="145" font-size="14" fill="#c0392b">衰减 γ(1−ν)</text><line x1="280" y1="190" x2="280" y2="90" stroke="#2980b9" stroke-width="2.5"/><polygon points="280,90 274,102 286,102" fill="#2980b9"/><text x="392" y="145" font-size="14" fill="#2980b9">热泵回 γν</text><text x="60" y="252" font-size="14" fill="#333">γ：衰减强度　ν：环境热占据——两个参数定义整条信道</text></svg>

</div>

容量的数字版：`@@M@@C=\frac{1}{\ln 2}\max_{0\le p\le1}\{h(t)-g(v(p))\}@@`，其中 `@@M@@t=(1-\gamma)p+\gamma\nu@@`。代入边界看：γ=0（无噪声）时 C=1 比特；γ=1（全坏）时 C=0；ν=1/2、γ=1/2 时 `@@M@@C=1-g(\gamma/4)/\ln 2\approx0.13@@` 比特。最优信号就是等概率、反相位的两个纯态。环境越热（ν 越大），泵回越猛，容量越低；且容量在 ν 换成 1−ν 时保持不变。

**为什么值得关心**

普通阻尼（ν=0）的公式二十多年前就有人算出，而正阻尼加热占据的这一格此前无人能解。它关上了 Leditzky 等 2018 年公开问题清单上的最后一格：这条基础噪声信道的容量从此有闭式答案，且它与任意信道并联时容量与熵量全部可加。

> 已 Lean 形式化

## 一句话结论

本文彻底确定了量子比特广义振幅阻尼信道（generalized amplitude damping channel）的经典容量（classical capacity）：它恰等于单次使用的 Holevo 容量，由一个单变量最大化显式给出，纠缠块编码没有任何增益，且与任意有限维信道并联使用时容量与熵量全部可加。

## 问题背景

振幅阻尼（amplitude damping）描述量子比特把激发能量耗散给环境的退相干过程，是量子通信最基本的噪声模型之一。环境处于非零温时激发还会被反向泵回：衰减强度 `@@M@@\gamma@@` 与稳态激发占据 `@@M@@\nu@@` 一起定义广义振幅阻尼信道 `@@M@@\mathcal A_{\gamma,\nu}@@`，它把 `@@M@@\begin{pmatrix}1-q&z\\\bar z&q\end{pmatrix}@@` 映为 `@@M@@\begin{pmatrix}1-t&\sqrt{1-\gamma}\,z\\\sqrt{1-\gamma}\,\bar z&t\end{pmatrix}@@`，其中 `@@M@@t=(1-\gamma)q+\gamma\nu@@`。问题在于：发送方可把消息编码成整个输入块上任意可纠缠的态，接收端做联合测量（collective decoding），无误传信的速率上限是多少？

Holevo 与 Schumacher–Westmoreland 的编码定理把容量写成 Holevo 信息（Holevo information）的正则化 `@@M@@C=\sup_n\frac1n\chi(\mathcal N^{\otimes n})@@`，而 Hastings 在 2009 年证明可加性（additivity）一般不成立，"单次最优即容量"必须逐信道论证。普通阻尼（`@@M@@\nu=0@@`）的单次最优化由 Bennett–Shor–Smolin–Thapliyal 与 Giovannetti–Fazio 早年完成，完整容量则被 Leditzky 等人 2018 年列为公开问题；Tang–Zhu–Bai–Wang 在 2026 年用"存在纯输出"的判据解决了含 `@@M@@\nu=0@@` 的情形，但正阻尼且热占据取内点时输出恒为满秩混合态、没有纯输出，旧判据失效——本文补上的正是这最后一格。

## 主要结果

**主定理**：对一切 `@@M@@\gamma,\nu\in[0,1]@@`、一切整数 `@@M@@n\ge1@@`，
`@@M@@D\chi(\mathcal A_{\gamma,\nu}^{\otimes n})=n\,\chi(\mathcal A_{\gamma,\nu})=\frac{n}{\ln2}\max_{0\le p\le1}\bigl\{h((1-\gamma)p+\gamma\nu)-g(v_{\gamma,\nu}(p))\bigr\},@@`
其中 `@@M@@h@@` 为二元熵（binary entropy），`@@M@@g(u)=h\bigl(\tfrac{1+\sqrt{1-4u}}2\bigr)@@` 为行列式熵函数（二维态的熵只依赖行列式 `@@M@@u@@`），`@@M@@v_{\gamma,\nu}(p)=\gamma\nu(1-\nu)+\gamma(1-\gamma)(p-\nu)^2@@`。特别地 `@@M@@C(\mathcal A_{\gamma,\nu})=\chi(\mathcal A_{\gamma,\nu})@@`：容量就是单发 Holevo 容量（one-shot Holevo capacity），算一个一元最大化即可。最优值由等概率、反相位的两纯态信号 `@@M@@\phi_\pm=\sqrt{1-p}\,\ket0\pm\sqrt p\,\ket1@@` 达到，其独立乘积在每个块长都达到最优。

**推论（与任意伙伴并联的可加性）**：对任意有限维完全正保迹（CPTP）信道 `@@M@@\mathcal N@@`，单发 Holevo 容量、最小输出熵（minimum output entropy）与正则化容量三者皆可加，例如 `@@M@@C(\mathcal A\otimes\mathcal N)=C(\mathcal A)+C(\mathcal N)@@`，而伙伴自身的正则化原样保留。并得 `@@M@@S_{\min}(\mathcal A_{\gamma,\nu})=g(\gamma\nu(1-\nu))@@`，在 `@@M@@p=\nu@@` 处取得。特例：`@@M@@\nu=0@@` 回到普通阻尼的 Giovannetti–Fazio 与 Tang 等人公式；`@@M@@\nu=\tfrac12@@` 给出与 King 的 unital 信道定理一致的 `@@M@@C=1-g(\gamma/4)/\ln2@@`，最优信号为 `@@M@@(\ket0\pm\ket1)/\sqrt2@@`；`@@M@@\gamma=1@@` 容量为零、`@@M@@\gamma=0@@` 为一比特，且容量在 `@@M@@\nu\mapsto1-\nu@@` 下不变。

## 证明思路

全文围绕一个"保人口的熵下界"：对任意纯 `@@M@@n@@` 比特输入 `@@M@@\psi@@`，证明 `@@M@@\mathcal S(\mathcal A_{\gamma,\nu}^{\otimes n}(\proj\psi))\ge\sum_{j=1}^n e(p_j)@@`，其中 `@@M@@p_j@@` 是第 `@@M@@j@@` 位激发概率，`@@M@@e(p)=g(v_{\gamma,\nu}(p))@@` 恰为单比特输出熵。这个界必须逐位保留人口信息——只控最小输出熵会抹掉 `@@M@@p_j@@`，撑不起后续的 Holevo 优化，这正是与以往工作的分水岭。

先建立零块熵不等式（zero-block entropy inequality）：对分块矩阵 `@@M@@M=\begin{pmatrix}A&B\\mathbb{C}&0\end{pmatrix}@@`，若三个非零块的平方 Hilbert–Schmidt 质量 `@@M@@x,y,z@@` 之和为一，则 `@@M@@\mathcal S(MM^*)\ge x\,\mathcal S(AA^*/x)+y\,\mathcal S(BB^*/y)+z\,\mathcal S(CC^*/z)+g(yz)@@`。证明先把熵亏损写成对数行列式之差的积分，再利用 `@@M@@G_Z(D,E)=\ln\det(D+ZE^{-1}Z^*)-\ln\det D@@` 的联合凸性（二阶方向导数化为 `@@M@@\|L\|^2-\Tr((RL)^2)@@`，而 `@@M@@R=(I+K)^{-1}@@` 是压缩矩阵，故非负），对坐标符号做平均把矩阵参数压成对角，最后用一次齐次且超可加的标量亏损函数归并；矩形块由零填充化归方块。

再做热扩展：正阻尼加内点热占据时输出不再呈零块结构，论文把热态写成两个零块分解的凸组合——固定行和与交叉系数后，非负系数解集是一条线段，其两个端点各给出一个零块分解，且角块质量之积同为 `@@M@@u@@`，于是标量项 `@@M@@g(u)@@` 在混合中保持不变，熵凹性便保住下界。这一步正是越过"纯输出判据"的关键。

继而接入信道并迭代：按首比特把输入拆成两个条件分支，用伙伴信道的 Kraus 表示构造矩阵 `@@M@@X,Y@@`（第 `@@M@@\ell@@` 列取 `@@M@@V_\ell\psi_0@@`、`@@M@@V_\ell\psi_1@@`），其 Gram 积恰为两分支输出，一步递归给出 `@@M@@\mathcal S\ge e(p)+(1-p)\,\mathcal S(\sigma_0)+p\,\mathcal S(\sigma_1)@@`；又因 `@@M@@\sqrt{v(p)}@@` 是仿射向量的范数、`@@M@@s\mapsto g(s^2)@@` 单调凸（即 Wootters 熵–并发函数的经典性质），`@@M@@e@@` 是凸函数，据此把条件人口合并回原人口，归纳完成逐位下界。

最后做系综优化：平均输出熵由对角熵界与经典次可加性控在 `@@M@@\sum_j h((1-\gamma)\bar p_j+\gamma\nu)@@`，各信号输出熵的平均由上述下界控在 `@@M@@\sum_j e(\bar p_j)@@`，两者相减并逐点最大化得上界；反相位对的相干在平均输出中相消，使独立乘积系综达到等号。伙伴可加性由同一递归对 `@@M@@\mathcal N^{\otimes n}@@` 迭代、再正则化而得。

## 可信度与备注

按本项目记录，主结果已有 Lean 形式化证明，机器验证显著降低了冗长矩阵推导出错的风险。姊妹篇 Tang–Zhu–Bai–Wang 的三角块熵不等式是本文零块估计的前身，其纯输出情形被本文作为特例覆盖并推广到全部热参数；`@@M@@\nu=\tfrac12@@` 与 `@@M@@\nu=0@@` 特例又分别与 King、Giovannetti–Fazio 的既有公式交叉吻合。依 OpenAI 官方声明，未经形式化的结果可能存在问题，本文虽已形式化，读者仍宜以社区核验与形式化文档为最终参照。

{% endraw %}
