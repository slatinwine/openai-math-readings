---
layout: default
title: "A Smooth Metric with No Local Isometric Immersion into Three-Space"
family: "334"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Smooth Metric with No Local Isometric Immersion into Three-Space

> 结果族 334：A smooth surface metric with no local isometric immersion in ℝ<sup>3</sup>　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

想象一块神奇的布：在某个点处，无论放大多少倍，它看起来都和普通平面一模一样（各阶导数全部相同）；可整块布却怎么也无法不拉伸、不压缩地贴进三维空间。这篇论文就造出了这样一块布，从而否定了一个长期悬而未决的预期：光滑的"量长规则"总能局部实现成三维空间里的真实曲面。

**关键词卡片**

- 等距浸入（isometric immersion）：把曲面放进 `@@M@@\mathbb R^3@@` 且保持一切长度，不许拉伸压缩
- 全阶 Taylor jet（Taylor jet）：函数在某点的全部导数信息；本文度量在原点与欧氏度量 jet 完全相同
- 高斯曲率（Gaussian curvature）：由量长规则本身算出的内在弯曲度；本构造中央为负、外围为正
- Darboux 方程（Darboux equation）：任何浸入的高度函数都必须满足的方程，证明只用到这条必要条件
- Baire 纲论证（Baire category）：证明"绝大多数度量都不可实现"的存在性方法

**看个具体例子**

构造的曲率取 `@@M@@K=\kappa\,(x^2-h(y))@@`：曲线 `@@M@@x^2=h(y)@@` 围出的中央区域曲率为负（鞍形），外围为正（碗形），交界处曲率恰为零；再叠加越来越薄、越来越快的振荡脉冲，使原点的任何邻域内都导出矛盾。jet 条件的数字版：`@@M@@\partial^\alpha(g_{ij}-\delta_{ij})(0)=0@@` 对一切多重指标 `@@M@@\alpha@@` 成立。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="20" y="35" font-size="16" fill="#333">曲率布局：中央为负，外围为正</text>
<rect x="60" y="60" width="240" height="180" fill="none" stroke="#333"/>
<ellipse cx="180" cy="150" rx="45" ry="70" fill="#f2d5d5" stroke="#c33" stroke-dasharray="6 4"/>
<circle cx="180" cy="150" r="4" fill="#333"/>
<text x="196" y="146" font-size="13" fill="#333">原点</text>
<text x="128" y="105" font-size="14" fill="#c33">K&lt;0（鞍形）</text>
<text x="228" y="228" font-size="14" fill="#343">K&gt;0（碗形）</text>
<text x="122" y="222" font-size="13" fill="#c33">边界：K=0</text>
<text x="330" y="85" font-size="14" fill="#333">这块"布"在原点与平面</text>
<text x="330" y="108" font-size="14" fill="#333">全阶相同（jet 一致），</text>
<text x="330" y="131" font-size="14" fill="#333">但任何邻域都放不进 R³</text>
<text x="330" y="175" font-size="22" fill="#c33">R³：无解</text>
</svg>

</div>

**为什么值得关心**

它说明局部可实现性不由基点处的全部导数信息决定，与解析情形的 Janet–Cartan 定理形成鲜明对照，给"光滑局部等距实现"问题画上否定句号。

> 已 Lean 形式化

## 一句话结论

本文构造了 `@@M@@(-1,1)^2@@` 上一个光滑正定黎曼度量：它在原点与欧氏度量有相同的全阶 Taylor jet，但原点的任何邻域都不容许到 `@@M@@\mathbb{R}^3@@` 的光滑等距浸入，对无限制的光滑局部等距实现问题给出否定回答。

## 问题背景

局部等距实现问题（local isometric realization）问：黎曼曲面 `@@M@@(\Sigma,g)@@` 能否在每点附近实现为 `@@M@@\mathbb{R}^3@@` 中的光滑曲面，即在局部坐标下求光滑映射 `@@M@@F@@` 使 `@@M@@\langle\partial_iF,\partial_jF\rangle=g_{ij}@@`。解析范畴由经典的 Janet–Cartan 定理肯定解决；光滑范畴下，高斯曲率（Gaussian curvature）非零时问题化为椭圆或双曲型的 Darboux 方程，局部存在性已知，症结在曲率零点带来的退化与方程变型。Lin 处理了非负曲率与"干净变号"（`@@M@@K(p)=0@@`、`@@M@@dK(p)\ne0@@`）情形的有限正则性估计，Nakamura–Maeda 证明了干净变号下的光滑局部存在，更复杂的零集只在附加限制下有结果。低正则一端，Nash–Kuiper 定理给出 `@@M@@C^1@@` 柔性；Pogorelov 与 Nadirashvili–Yuan 则造出无局部 `@@M@@C^2@@` 实现的 `@@M@@C^{2,1}@@` 度量。而"任意光滑度量是否总有光滑局部实现"这一无限制问题——Yau 讨论过、Ghomi 综述列为 Problem 1.9——此前悬而未决，本文给出否定回答。

## 主要结果

**定理 A**：存在 `@@M@@(-1,1)^2@@` 上的 `@@M@@C^\infty@@` 正定度量 `@@M@@g@@`，使得原点的任何开邻域 `@@M@@U@@` 都不容许 `@@M@@C^\infty@@` 等距浸入（isometric immersion）`@@M@@F:(U,g)\to\mathbb{R}^3@@`；特别地也不容许等距嵌入——因为光滑浸入限制到任一点足够小的邻域后自动是嵌入，两种局部表述的存在性内容相同。定理不含任何完备性或拓扑假设。注意"正定"指度量本身而非曲率：构造同时使用正、负两种曲率，也未解决 `@@M@@K\ge0@@` 或 `@@M@@K\le0@@` 限制下的问题。

**推论**：该度量还可取得与欧氏度量在原点有完全相同的 Taylor jet，即对一切多重指标 `@@M@@\alpha@@` 有 `@@M@@\partial^\alpha(g_{ij}-\delta_{ij})(0)=0@@`。欧氏度量显然能放进 `@@M@@\mathbb{R}^3@@`，此度量却在原点的任何邻域都不行——光滑局部可实现性不由基点处的全 Taylor jet 决定。

## 证明思路

证明有两大任务：先在整个固定方块 `@@M@@S=[-3,3]^2@@` 上"阻碍"一个标量高度函数，再构造一个度量，使任何局部浸入都会在某个方块上产生这种高度。标量方程来自 Gauss 方程：浸入 `@@M@@F@@` 沿固定环境单位向量 `@@M@@e@@` 的高度 `@@M@@z=\langle F,e\rangle@@` 必满足 Darboux 方程 `@@M@@\det(\nabla_g^2z)=K\det(g)(1-|dz|_g^2)@@`；当 `@@M@@e@@` 在某点为法向时，该点 `@@M@@dz=0@@` 且协变 Hessian 恰为第二基本形式（second fundamental form）。全文只用这一必要条件。

模型曲率取 `@@M@@K=\kappa(x^2-h(y))@@`：中央为负、外围为正。在整个 `@@M@@S@@` 上满足该方程且 `@@M@@E>0@@`、`@@M@@H_{yy}\ne0@@`、`@@M@@|H_{xy}/H_{yy}|\le1/100@@` 的光滑 `@@M@@z@@` 称为容许高度。`@@M@@S@@` 内的曲率零点其实都是干净变号，故这与逐点存在性结果并不矛盾：后者给不出在整个 `@@M@@S@@` 上一致成立的高度。

先证帽正则性估计（cap regularity）：帽是三边处于正曲率、第四条"人工边"切入负曲率的区域。把 Darboux 方程解出 `@@M@@z_{xx}=P@@` 并对 `@@M@@\partial_y^lz@@` 求导，得到主部系数含 `@@M@@K@@` 的变型方程；换入流坐标使 `@@M@@D=\partial_x-q\partial_y=\partial_t@@`，其横向漂移系数正比于曲率导数 `@@M@@K_y@@`。有向乘子（directed multiplier）借这一漂移在曲率零集附近取正——零集上 `@@M@@-K_y+\epsilon x^2@@` 有正下界——再补一个小切向项处理 `@@M@@K_y=0@@` 处，并用在人工边上消失的加权椭圆估计控制强正曲率区；于是人工边上无需任何高阶边值数据，归纳即得帽内全阶导数界。

再做脉冲与纲论证（Baire category）：假设某个有界高度类稠密，就对固定度量 `@@M@@g_*@@` 叠加薄振荡脉冲 `@@M@@\tau^{-N}\chi_0(\xi)\phi_0(\tau\theta/\delta)\cos(\tau\xi)\,d\theta^2@@`。两个帽供应脉冲两侧一致光滑的数据，双曲能量估计把它们传播到脉冲两缘；与按 `@@M@@g_*@@` 递归构造的 Taylor 比较解之差满足零初值双曲方程，强迫项来自脉冲经曲率公式的 `@@M@@-\tfrac12\partial_\xi^2@@` 主贡献，量级 `@@M@@\tau^{2-N}@@` 且带定号。用 `@@M@@\chi_0\cos(\tau\xi)@@` 取矩：强迫矩 `@@M@@\gtrsim\delta\tau^{1-N}@@` 对条宽参数 `@@M@@\delta@@` 是线性的，竞争空间项 `@@M@@\lesssim\delta^2\tau^{1-N}@@` 是二次的——先固定 `@@M@@\delta@@` 足够小再令频率 `@@M@@\tau\to\infty@@`，即得矛盾。每个类无处稠密，Baire 定理给出剩余集。

最后拼装：由规定曲率引理（解 ODE `@@M@@f_{XX}=-K_0f@@` 造 `@@M@@\bar g=dX^2+f^2dY^2@@`）铺出背景度量，在趋于原点的负曲率圆盘链（边界曲率为零）外，按有限旋转网放置缩小且逼近每个边界点的阻碍方块，各级振幅可和衰减以保证整体光滑。若原点某邻域有浸入，局部成图后由边界鞍点引理（负曲率盘的第二基本形式不能沿整个边界退化）在某边界点得到秩一的 `@@M@@\mathrm{II}@@`；取该点法向高度，在核方向对齐的旋转网坐标下恰为容许高度，却落在被选为不容许高度的方块上——矛盾。

## 可信度与备注

按任务元信息，本文主结果已通过 Lean 形式化验证。本结果族（334）目前仅此一篇手稿，无姊妹篇互相印证，核验主要依赖形式化证明与社区评审；依照 OpenAI 官方声明"未经形式化的结果可能有问题"，文中主定理已形式化，其余细节仍建议以论文原文为准。另值得注意：作者明确指出 Nadirashvili–Yuan 早期预印本声称的更强反例（`@@M@@K\le0@@` 且无 `@@M@@C^3@@` 嵌入）与其正式发表版口径不一，对此分歧保持存疑，且本文的构造不依赖该断言、自备解析障碍。

{% endraw %}
