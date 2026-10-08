---
layout: default
title: "Brownian continuum random tree limits of finite Fortuin–Kasteleyn maps above four"
family: "211"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Brownian continuum random tree limits of finite Fortuin–Kasteleyn maps above four

> 结果族 211：The geometric phase diagram, diffusion, and spectra of random planar maps　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象一位制图师不停掷骰子，在球面上画出越来越大的随机"地图"。这篇论文证明了一件反直觉的事：只要"簇权"参数 q>4 并调到临界状态，这些地图虽然边数 n 越来越多，形状却越来越不像曲面，而越来越像一棵随机分叉的树——就像把纸团越揉越大，最后发现它的骨架其实是一根树枝。

**关键词卡片**

- 随机平面图（planar map）：嵌入球面的随机连通图，相当于一张随机"地图"，允许环与重边。
- Fortuin–Kasteleyn 模型（random-cluster model）：在地图上随机开关边、按连通块个数计权的模型，q 就是这个权重。
- 布朗连续随机树（Brownian continuum random tree）：由布朗运动轨道编码的经典随机树，是许多随机结构共同的极限。
- Gromov–Hausdorff–Prokhorov 拓扑：比较两个"带测度的抽象度量空间"像不像的严格方式。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <circle cx="140" cy="145" r="75" fill="none" stroke="#333" stroke-width="2"/>
  <circle cx="140" cy="145" r="38" fill="none" stroke="#333" stroke-width="1.5"/>
  <line x1="178" y1="145" x2="215" y2="145" stroke="#777" stroke-width="1.5"/>
  <line x1="159" y1="178" x2="177.5" y2="210" stroke="#777" stroke-width="1.5"/>
  <line x1="121" y1="178" x2="102.5" y2="210" stroke="#777" stroke-width="1.5"/>
  <line x1="102" y1="145" x2="65" y2="145" stroke="#777" stroke-width="1.5"/>
  <line x1="121" y1="112" x2="102.5" y2="80" stroke="#777" stroke-width="1.5"/>
  <line x1="159" y1="112" x2="177.5" y2="80" stroke="#777" stroke-width="1.5"/>
  <line x1="140" y1="107" x2="140" y2="70" stroke="#777" stroke-width="1.5"/>
  <line x1="140" y1="183" x2="140" y2="220" stroke="#777" stroke-width="1.5"/>
  <circle cx="140" cy="145" r="4" fill="#333"/>
  <text x="140" y="252" font-size="14" text-anchor="middle" fill="#222">n 条边的随机平面图</text>
  <path d="M 245 145 L 320 145" stroke="#c0392b" stroke-width="3" fill="none"/>
  <path d="M 320 145 L 308 138 M 320 145 L 308 152" stroke="#c0392b" stroke-width="3" fill="none"/>
  <text x="282" y="105" font-size="13" text-anchor="middle" fill="#c0392b">图距离 × c(q)/√n</text>
  <line x1="445" y1="215" x2="445" y2="160" stroke="#333" stroke-width="2.5"/>
  <line x1="445" y1="160" x2="410" y2="115" stroke="#333" stroke-width="2.5"/>
  <line x1="445" y1="160" x2="480" y2="115" stroke="#333" stroke-width="2.5"/>
  <line x1="410" y1="115" x2="385" y2="80" stroke="#333" stroke-width="2"/>
  <line x1="410" y1="115" x2="428" y2="75" stroke="#333" stroke-width="2"/>
  <line x1="480" y1="115" x2="462" y2="75" stroke="#333" stroke-width="2"/>
  <line x1="480" y1="115" x2="505" y2="80" stroke="#333" stroke-width="2"/>
  <line x1="385" y1="80" x2="368" y2="52" stroke="#333" stroke-width="2"/>
  <line x1="505" y1="80" x2="520" y2="52" stroke="#333" stroke-width="2"/>
  <circle cx="445" cy="215" r="4" fill="#333"/>
  <text x="445" y="252" font-size="14" text-anchor="middle" fill="#222">布朗连续随机树</text>
</svg>

</div>

具体代入：一张 n=10000 条边的临界 FK 地图，随机取两个顶点，典型图距离约为 c(q)×100 的量级，因为定理的缩小因子正是 `@@M@@c(q)n^{-1/2}=c(q)/100@@`。"距离与 `@@M@@\sqrt n@@` 同阶"是树的指纹：大小为 n 的随机树，从根到叶的距离恰好也是 `@@M@@\sqrt n@@` 量级；曲面该有的"面积感"完全消失了。

**为什么值得关心**

它补上随机曲面相图缺失的"树侧"：q<4 的临界地图像二维曲面、q>4 像树，至此不同 q 的几何行为凑齐，是二维量子引力数学的基础拼图。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

对每个簇权 `@@M@@q>4@@`，临界 Fortuin–Kasteleyn 平面图的图距离乘以 `@@M@@c(q)n^{-1/2}@@` 后，连同度测度一起收敛到布朗连续随机树：有限体积下"随机曲面退化成树"的猜想被证明，且对所有正整数规模一致成立。

## 问题背景

Fortuin–Kasteleyn 随机簇模型（random-cluster model）通过给边子集赋权把渗流与 Potts 自旋系统联系起来。当承载它的图本身也是随机的平面图（planar map，即嵌入球面的连通图，允许环与重边）时，簇权会反过来重塑底层几何——这是二维量子引力中的基本问题：不同 `@@M@@q@@` 的临界随机曲面究竟长什么样？Sheffield 的清单模型（inventory model）用两类汉堡、两类固定订单与弹性订单编码这种联合随机性，其参数 `@@M@@p=\sqrt q/(\sqrt q+2)@@` 恰使 `@@M@@q=4@@` 对应 `@@M@@p=1/2@@`；他证明库存涨落在 `@@M@@q=4@@` 处发生从二维到一维的相变，并在附录中预言 `@@M@@q>4@@` 时有限体积图的度量极限是布朗连续随机树。Feng 把它重述为猜想并证明了无限体积的局部版本；有限体积、紧拓扑、带度测度的完整陈述此前仍是公开问题，本文将其证明。

## 主要结果

对固定实数 `@@M@@q>4@@` 与 `@@M@@n\ge1@@`，按
`@@M@@D\P\big((M_n,A_n)=(M,A)\big)=\frac{1}{Z_{n,q}}\,q^{\,k_M(A)+(|A|-|V(M)|)/2}@@`
采样 `@@M@@n@@` 条边的根平面图 `@@M@@M_n@@` 与边子集 `@@M@@A_n@@`（等价地权为 `@@M@@q^{\ell/2}@@`，`@@M@@\ell@@` 为 FK 界面环数）。令 `@@M@@d_n@@` 为使用 `@@M@@M_n@@` 全部边的图距离，`@@M@@\mu_n(\{v\})=\deg_{M_n}(v)/(2n)@@` 为归一化度测度（环贡献度数 2）。记 `@@M@@e@@` 为标准布朗游程（Brownian excursion），`@@M@@\mathcal T_e@@` 为由 `@@M@@d_e(s,t)=e(s)+e(t)-2\min_{r\in[s\wedge t,s\vee t]}e(r)@@` 编码的布朗连续随机树（Brownian continuum random tree），`@@M@@\mu_e@@` 为 Lebesgue 概率测度的推前。主定理断言：存在确定性常数 `@@M@@c(q)\in(0,\infty)@@`，使得沿全部正整数 `@@M@@n@@`，
`@@M@@D\big(V(M_n),\,c(q)n^{-1/2}d_n,\,\mu_n\big)\ \Longrightarrow\ (\mathcal T_e,d_e,\mu_e)@@`
在紧度量概率空间（模保测等距）的 Gromov–Hausdorff–Prokhorov 拓扑中成立。收敛中忘掉根与 FK 装饰；常数可依赖固定的 `@@M@@q@@`，论文不主张 `@@M@@q\to4@@` 时的一致性。

## 证明思路

证明分四步。先把 FK 权重精确改写为词事件：取 `@@M@@t=\sqrt q@@`、`@@M@@p=t/(t+2)@@`、`@@M@@u=(1-p)/16@@`，长度 `@@M@@2n@@` 的独立清单词完全匹配（空归约）的概率恰为 `@@M@@a_nu^n@@`，其中 `@@M@@a_n@@` 是 `@@M@@n@@` 条边根平面图对装饰求和后的权重；恒等式经由"识别词 = 两个 Dyck 词的洗牌，对应带生成树的根平面图"的双射加删除–收缩递归的活动性展开证明。忽略汉堡类型后词变成简单对称随机游走，反射原理给出 Catalan 上界 `@@M@@a_nu^n=O(n^{-3/2})@@`，故母函数 `@@M@@T@@` 在 `@@M@@u@@` 处有限。再证平方根下界：在双侧独立词中固定一条缝，向左回溯至库存首次达 `@@M@@+h@@`、向右前伸至首次达 `@@M@@-h@@`，缝区间分解为独立的梯段片（ladder piece）；先用后向首个幸存汉堡的平稳协方差论证证出严格漂移 `@@M@@\E K\le 1/(2p)<1@@`，再借两类"截口"的正概率与供需频率比较，证明整段区间以不依赖 `@@M@@h@@` 的概率归约为空词，配合击中时尾估计得 `@@M@@\sum_{n\ge1}na_nu^nx^n\ge c(1-x)^{-1/2}@@`。然后进入块分解（block decomposition）：非平凡根平面图唯一分解为不可分的根块（nonseparable block）在各角（corner）处插入子图，得恒等式 `@@M@@T(z)=\Phi(zT(z)^2)@@`；一个"二次逆判据"纯靠上述上、下界（无需解析延拓过收敛端点）迫使 `@@M@@\Phi(v)=\tau@@`、`@@M@@2v\Phi'(v)=\Phi(v)@@`、`@@M@@\Phi''(v)<\infty@@`，即后代律 `@@M@@p_{2m}=b_mv^m/\Phi(v)@@` 临界且方差有限；条件在 `@@M@@2n+1@@` 个节点的带块标记 Galton–Watson 树精确再现 `@@M@@M_n@@` 的分布。最后取极限：Broutin–Marckert 的联合编码定理给出探索游走与深度共同收敛到同一布朗游程；难点是块形状任意、其距离标记可能很大，作者把每个节点的子女次序反转得到第二条深度优先游走，两条游走夹住祖先路径上的后代总数，配合按后代数截断，仅用二阶矩便证得标记路径和的一致大数律；进而地图距离与 `@@M@@(\beta/\nu)\big(W_j+W_{j'}-2\min W_r\big)@@` 一致接近，非根节点上的均匀测度经角对应恰为度测度 `@@M@@\mu_n@@`，最终由对应（correspondence）畸变估计拼装出 GHP 收敛，常数 `@@M@@c(q)=\sigma/(2\sqrt2\,\beta)@@`。

## 可信度与备注

本篇主结果暂无形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。家族 211 的姊妹篇分别处理 `@@M@@0<q<4@@` 的 LQG 球面极限与 `@@M@@q=4@@` 的临界情形，本文补上 `@@M@@q>4@@` 的"树侧"，共同绘出 FK 地图的几何相图；但论文明确说明姊妹篇只提供背景、并非证明的输入。证明在有限律下直接完成，双射、生成函数估计与概率极限的细节均在正文中完整给出。

{% endraw %}
