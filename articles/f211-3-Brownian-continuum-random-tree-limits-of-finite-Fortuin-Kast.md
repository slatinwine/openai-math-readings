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

## 一句话结论

对每个簇权 \(q>4\)，临界 Fortuin–Kasteleyn 平面图的图距离乘以 \(c(q)n^{-1/2}\) 后，连同度测度一起收敛到布朗连续随机树：有限体积下"随机曲面退化成树"的猜想被证明，且对所有正整数规模一致成立。

## 问题背景

Fortuin–Kasteleyn 随机簇模型（random-cluster model）通过给边子集赋权把渗流与 Potts 自旋系统联系起来。当承载它的图本身也是随机的平面图（planar map，即嵌入球面的连通图，允许环与重边）时，簇权会反过来重塑底层几何——这是二维量子引力中的基本问题：不同 \(q\) 的临界随机曲面究竟长什么样？Sheffield 的清单模型（inventory model）用两类汉堡、两类固定订单与弹性订单编码这种联合随机性，其参数 \(p=\sqrt q/(\sqrt q+2)\) 恰使 \(q=4\) 对应 \(p=1/2\)；他证明库存涨落在 \(q=4\) 处发生从二维到一维的相变，并在附录中预言 \(q>4\) 时有限体积图的度量极限是布朗连续随机树。Feng 把它重述为猜想并证明了无限体积的局部版本；有限体积、紧拓扑、带度测度的完整陈述此前仍是公开问题，本文将其证明。

## 主要结果

对固定实数 \(q>4\) 与 \(n\ge1\)，按
\[\P\big((M_n,A_n)=(M,A)\big)=\frac{1}{Z_{n,q}}\,q^{\,k_M(A)+(|A|-|V(M)|)/2}\]
采样 \(n\) 条边的根平面图 \(M_n\) 与边子集 \(A_n\)（等价地权为 \(q^{\ell/2}\)，\(\ell\) 为 FK 界面环数）。令 \(d_n\) 为使用 \(M_n\) 全部边的图距离，\(\mu_n(\{v\})=\deg_{M_n}(v)/(2n)\) 为归一化度测度（环贡献度数 2）。记 \(e\) 为标准布朗游程（Brownian excursion），\(\mathcal T_e\) 为由 \(d_e(s,t)=e(s)+e(t)-2\min_{r\in[s\wedge t,s\vee t]}e(r)\) 编码的布朗连续随机树（Brownian continuum random tree），\(\mu_e\) 为 Lebesgue 概率测度的推前。主定理断言：存在确定性常数 \(c(q)\in(0,\infty)\)，使得沿全部正整数 \(n\)，
\[\big(V(M_n),\,c(q)n^{-1/2}d_n,\,\mu_n\big)\ \Longrightarrow\ (\mathcal T_e,d_e,\mu_e)\]
在紧度量概率空间（模保测等距）的 Gromov–Hausdorff–Prokhorov 拓扑中成立。收敛中忘掉根与 FK 装饰；常数可依赖固定的 \(q\)，论文不主张 \(q\to4\) 时的一致性。

## 证明思路

证明分四步。先把 FK 权重精确改写为词事件：取 \(t=\sqrt q\)、\(p=t/(t+2)\)、\(u=(1-p)/16\)，长度 \(2n\) 的独立清单词完全匹配（空归约）的概率恰为 \(a_nu^n\)，其中 \(a_n\) 是 \(n\) 条边根平面图对装饰求和后的权重；恒等式经由"识别词 = 两个 Dyck 词的洗牌，对应带生成树的根平面图"的双射加删除–收缩递归的活动性展开证明。忽略汉堡类型后词变成简单对称随机游走，反射原理给出 Catalan 上界 \(a_nu^n=O(n^{-3/2})\)，故母函数 \(T\) 在 \(u\) 处有限。再证平方根下界：在双侧独立词中固定一条缝，向左回溯至库存首次达 \(+h\)、向右前伸至首次达 \(-h\)，缝区间分解为独立的梯段片（ladder piece）；先用后向首个幸存汉堡的平稳协方差论证证出严格漂移 \(\E K\le 1/(2p)<1\)，再借两类"截口"的正概率与供需频率比较，证明整段区间以不依赖 \(h\) 的概率归约为空词，配合击中时尾估计得 \(\sum_{n\ge1}na_nu^nx^n\ge c(1-x)^{-1/2}\)。然后进入块分解（block decomposition）：非平凡根平面图唯一分解为不可分的根块（nonseparable block）在各角（corner）处插入子图，得恒等式 \(T(z)=\Phi(zT(z)^2)\)；一个"二次逆判据"纯靠上述上、下界（无需解析延拓过收敛端点）迫使 \(\Phi(v)=\tau\)、\(2v\Phi'(v)=\Phi(v)\)、\(\Phi''(v)<\infty\)，即后代律 \(p_{2m}=b_mv^m/\Phi(v)\) 临界且方差有限；条件在 \(2n+1\) 个节点的带块标记 Galton–Watson 树精确再现 \(M_n\) 的分布。最后取极限：Broutin–Marckert 的联合编码定理给出探索游走与深度共同收敛到同一布朗游程；难点是块形状任意、其距离标记可能很大，作者把每个节点的子女次序反转得到第二条深度优先游走，两条游走夹住祖先路径上的后代总数，配合按后代数截断，仅用二阶矩便证得标记路径和的一致大数律；进而地图距离与 \((\beta/\nu)\big(W_j+W_{j'}-2\min W_r\big)\) 一致接近，非根节点上的均匀测度经角对应恰为度测度 \(\mu_n\)，最终由对应（correspondence）畸变估计拼装出 GHP 收敛，常数 \(c(q)=\sigma/(2\sqrt2\,\beta)\)。

## 可信度与备注

本篇主结果暂无形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。家族 211 的姊妹篇分别处理 \(0<q<4\) 的 LQG 球面极限与 \(q=4\) 的临界情形，本文补上 \(q>4\) 的"树侧"，共同绘出 FK 地图的几何相图；但论文明确说明姊妹篇只提供背景、并非证明的输入。证明在有限律下直接完成，双射、生成函数估计与概率极限的细节均在正文中完整给出。

{% endraw %}
