---
layout: default
title: "Determination of a metric and a unitary connection from one boundary patch"
family: "365"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Determination of a metric and a unitary connection from one boundary patch

> 结果族 365：Joint metric and connection recovery from one boundary patch　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象一位医生只在手腕一小块皮肤上"打信号、收信号"，就要推断出全身骨骼的形状和神经传导的规则。这篇论文证明这在数学上可行：在高维空间体上，只用边界任意一小块补丁上的测量，就能同时恢复内部的"距离结构"（度量）与向量的"平行输运规则"（酉联络）——看不见的内部，被一小块边界彻底照亮。

**关键词卡片**

- Calderón 逆问题（Calderón inverse problem）：从边界上的输入—响应数据反推内部系数的一大类问题的总称。
- 黎曼度量（Riemannian metric）：规定内部每一点各方向"长度与夹角"的几何量。
- 酉联络（unitary connection）：向量值解在空间中移动时如何旋转、如何配对的规则。
- 边界补丁（boundary patch）：边界上任意一小块开区域；输入与观测都被限制在这里。
- 微分同胚歧义（diffeomorphism ambiguity）：光滑坐标重排造成的原理性不可分辨，是唯一无法消除的歧义。

**看个具体例子**

定理代入：若两组 `@@M@@(g_1,A_1)@@` 与 `@@M@@(g_2,A_2)@@` 在同一补丁 `@@M@@\Gamma@@` 上的能量型测量相等，则存在 `@@M@@\Phi@@` 与 `@@M@@U@@` 使 `@@M@@g_2=\Phi^*g_1@@`、`@@M@@A_2=U^{-1}(\Phi^*A_1)U+U^{-1}dU@@`，且 `@@M@@\Phi|_\Gamma=\mathrm{Id}@@`、`@@M@@U|_\Gamma=I@@`。这两个变换恰好保持测量不变，所以结论描述的就是全部歧义；联络无需满足任何场方程，补丁也不必连通。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><ellipse cx="290" cy="135" rx="140" ry="75" fill="none" stroke="#333" stroke-width="2"/><path d="M172,95 Q150,135 172,175" fill="none" stroke="#333" stroke-width="7"/><text x="60" y="62" font-size="15" fill="#333">边界补丁 Γ</text><ellipse cx="310" cy="135" rx="80" ry="45" fill="none" stroke="#999" stroke-width="1.5" stroke-dasharray="6 5"/><ellipse cx="310" cy="135" rx="40" ry="22" fill="none" stroke="#999" stroke-width="1.5" stroke-dasharray="6 5"/><text x="352" y="176" font-size="15" fill="#555">度量 g</text><text x="240" y="100" font-size="15" fill="#555">联络 A</text><line x1="110" y1="115" x2="158" y2="127" stroke="#888" stroke-width="2"/><polygon points="158,127 147,128 149,121" fill="#888"/><line x1="158" y1="150" x2="110" y2="162" stroke="#888" stroke-width="2"/><polygon points="110,162 121,163 119,156" fill="#888"/><text x="55" y="205" font-size="15" fill="#555">输入与输出都在 Γ 上</text></svg>

</div>

**为什么值得关心**

此前光滑范畴的"度量＋联络"联合恢复只在实解析或全边界测量下已知；本文同时去掉这两个限制，把测量压缩到任意小的一块补丁。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
在 `@@M@@n\ge 3@@` 维紧流形上，仅用一个任意小的边界开补丁做零频率测量（输入与观测都限制在该补丁上），就能同时确定光滑黎曼度量和秩二埃尔米特丛上的光滑酉联络，且只差一个在该补丁上恒为恒等的微分同胚与酉规范变换。

## 问题背景
Calderón 逆问题问：边界测量能否确定内部系数？其几何（各向异性）版本把未知量换成黎曼度量（Riemannian metric），而保持边界不动的微分同胚（diffeomorphism）是原理上无法消除的歧义。若向量丛上的联络（connection）也未知——它支配向量值解的平行输运——问题便同时含"度量"与"联络"两个未知量。此前的里程碑多带附加条件：Lee–Uhlmann 与 Lassas–Uhlmann 的实解析恢复，Albin–Guillarmou–Tzou–Uhlmann 用完整柯西数据在固定曲面上恢复联络，Cekić 在固定度量上恢复 Yang–Mills 联络，Gabdurakhmanov–Kokarev 在实解析范畴实现度量与联络的联合恢复。光滑范畴、度量与任意酉联络同时未知、且测量仅限单一补丁的情形，此前没有结果，本文将其解决。

## 主要结果
设 `@@M@@M@@` 为 `@@M@@n\ge 3@@` 维紧连通光滑流形（带光滑边界），`@@M@@\Gamma\subset\partial M@@` 为任意非空相对开真子集（边界补丁，boundary patch）。未知对象是光滑度量 `@@M@@g@@` 与平凡埃尔米特丛 `@@M@@M\times\mathbb C^2@@` 上的光滑酉联络 `@@M@@d_A=d+A@@`（`@@M@@A@@` 取值于反埃尔米特矩阵代数 `@@M@@\mathfrak u(2)@@`）。对 `@@M@@f,h\in C_c^\infty(\Gamma;\mathbb C^2)@@`，设 `@@M@@u_f@@` 解 `@@M@@L_{g,A}u_f=0@@`、边值为 `@@M@@f@@`，其中 `@@M@@L_{g,A}=d_A^{*g}d_A@@` 是联络拉普拉斯算子（connection Laplacian）；测量是能量型（energy form）
`@@M@@\langle\Lambda_{g,A,\Gamma}f,h\rangle=\int_M\langle d_Au_f,d_Au_h\rangle_g\,dV_g@@`。
**定理**：若两组 `@@M@@(g_1,A_1)@@`、`@@M@@(g_2,A_2)@@` 的该型在 `@@M@@\Gamma@@` 上相等，则存在光滑微分同胚 `@@M@@\Phi:M\to M@@` 与光滑映射 `@@M@@U:M\to U(2)@@`，使
`@@M@@D\Phi|_\Gamma=\Id,\quad U|_\Gamma=I,\quad g_2=\Phi^*g_1,\quad A_2=U^{-1}(\Phi^*A_1)U+U^{-1}dU .@@`
这两种变换恰好保持测量不变，故结论描述的正是全部歧义；对联络不施加任何 Yang–Mills 方程，补丁也不必连通。

## 证明思路
先在补丁上恢复边界射流（jet）：把测量解释为密度取值的 Dirichlet–to–Neumann 算子，其主符号 `@@M@@(\det k)^{1/2}\rho\,I@@` 先定出边界度量；再对算子做符号因式分解递归，度量的新法向射流项是频率变量 `@@M@@\xi@@` 的偶函数、联络项是奇函数，奇偶分离逐一归纳出 `@@M@@g@@` 与 `@@M@@A@@` 在 `@@M@@\Gamma@@` 上的全部泰勒射流。再借射流相等，把边界向外推成图 `@@M@@s=-b(z)@@`（`@@M@@b@@` 支在补丁内），粘出一个两侧系数光滑拼接的公共"外帽"区域 `@@M@@E@@`；一个 Dirichlet 能量极小化的变分比较证明两组格林矩阵（Green matrix）在 `@@M@@E@@` 上逐点相等。以 `@@M@@E@@` 内源产生的解在每点的取值为坐标：点分布对偶加上具标量主部方程组的唯一延拓（unique continuation）表明这些取值映满纤维、分离内点，从而定义一个极大"匹配"——局部等距 `@@M@@\Phi@@` 附加酉丛映射 `@@M@@J@@`。

若匹配存在内部边界点，则取调和标架（harmonic frame，标架列全为解，方程无零阶项）与接触坐标，进入三步延拓。第一步在乘积空间中延拓"混合格林矩阵"（第一变量满足第一方程、第二变量满足第二方程），靠两个定量延拓估计穿过乘积中的超曲面。第二步用该核在缩小的测地球面上构造转移泛函，其表示密度是总质量为 `@@M@@I@@` 的矩阵值密度；角向强制性估计（angular coercivity）保证密度在球面缩小时仍一致有界。第三步处理矩阵特有的困难：转移的一阶矩是矩阵 `@@M@@D^1,\dots,D^n@@`，不能像标量情形那样用调和坐标规范化消去。作者把 `@@M@@D@@` 的实标量部分分离后，其余部分 `@@M@@W@@` 满足以共形 Killing 符号（conformal Killing symbol）为主部的一阶方程组；而 `@@M@@n\ge 3@@` 时该主部是有限型的（两次延拓即可由低阶射流定出全部三阶导数），据此把逆度量差的比较从 `@@M@@O(r)@@` 严格改进到 `@@M@@O(r^{3/2})@@`，再用连通性论证让球半径塌缩到零，得到度量共形、规范化后的调和标架方程相等。最后，因算子不含位势项，共形因子满足 `@@M@@\Delta_{g_1}(e^\phi)=0@@` 且在已知一侧恒为 1，唯一延拓迫使 `@@M@@\phi=0@@`（这里用到 `@@M@@n\ge3@@`），且 `@@M@@J_{\rm loc}=F_1F_2^{-1}@@` 沿平行输运保持酉性。匹配于是越过每个边界点填满整个内部，光滑延拓到边界，再用支在补丁内的检验函数逼出 `@@M@@\Phi|_\Gamma=\Id@@`、`@@M@@U|_\Gamma=I@@`，最后换回原始规范即得定理。

## 可信度与备注
本文主结果暂无形式化证明。同族的标量姊妹篇（光滑各向异性唯一性）发展了乘积延拓、球面几何与角向估计的标量机制，本文将其推广到具标量主部的方程组并补足矩阵步骤，两文互相支撑；但文中明确说明标量唯一性定理本身并未直接施用于矩阵值数据。据 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
