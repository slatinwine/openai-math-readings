---
layout: default
title: "A group without fixed price"
family: "259"
discipline: "Group theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A group without fixed price

> 结果族 259：A group without fixed price　·　学科：Group theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文构造出一个有限生成群，它的两个本质自由（essentially free）的概率测度保持（p.m.p.）作用具有严格不同的代价（cost），从而对 Gaboriau 的一般固定代价（fixed price）问题给出否定回答：并非每个可数群都有固定代价。

## 问题背景

代价是度量等价理论的核心不变量，由 Levitt 于 1995 年引入、Gaboriau 于 2000 年系统发展。直观上，cost 回答"平均每个点需要多少条边，才能把群作用的轨道连通起来"。一个群称为具有固定代价，若其所有本质自由 p.m.p. 作用的 cost 相同。已知自由群的固定代价等于其秩，不少带交换或顺从结构的群有固定代价一，近期工作又证明了两个无限可数群的直积有固定代价一等；但"每个可数群是否都有固定代价"这一般性问题长期悬而未决。本文给出否定答案，是该方向的第一个反例。

## 主要结果

设 \(A=F(a,b_1,\ldots,b_{99})\) 为秩 \(100\) 的自由群，\(w=ab_1ab_2\cdots ab_{99}a\)，\(J=\langle b_1,\ldots,b_{99},w\rangle\)（引理证明这 \(100\) 个元素恰好自由生成 \(J\)）。取无限循环群 \(\langle t\rangle\)，定义融合自由积（amalgamated free product）
\[\Gamma=A*_J(J\times\langle t\rangle).\]
\(\Gamma\) 由 \(a,b_1,\ldots,b_{99},t\) 有限生成。\(a\) 的指数和给出同态 \(\chi:\Gamma\to\mathbb Z\)，满足 \(\chi(a)=1\)、\(\chi(w)=100\)。主定理：取 \(K=e^{96}96^{99}/95^{95}\)，选 \(0<\alpha<1/200\) 使 \(K\alpha^3<1/2\)，令 \(\eta=\alpha/100\)，则

- Bernoulli 作用 \(\Gamma\curvearrowright X\)（\(X\subseteq[0,1]^\Gamma\) 为自由点的不变余零集）满足 \(\operatorname{Cost}\ge 1+\eta\)；
- 有限高度扩张（finite height extension）\(Y_M=X\times\mathbb Z/M\mathbb Z\)，作用为 \((x,r)g=(xg,r+\chi(g)\bmod M)\)（\(M>100\)），满足 \(\operatorname{Cost}\le 1+99/M\)。

两个作用都自由且保测度，故取 \(M>\max\{100,99/\eta\}\) 即得同一有限生成群上两个 cost 严格不同的本质自由 p.m.p. 作用。

## 证明思路

上界完全显式。记 \(u_0=1\)、\(u_i=u_{i-1}ab_i\)，则 \(w=u_{99}a\)。先保留全部 \(t\)-边（代价 \(1\)），再把 \(J\) 的 \(100\) 个生成元限制在一个测度为 \(p\)、与每条 \(t\)-轨道都相交的 Borel 集 \(C_p\) 上——这是 Gaboriau 的乘积构造——便以代价 \(1+100p\) 生成子群 \(J\times\langle t\rangle\) 的整条轨道等价关系；随后只在高度 \(0,\ldots,98\) 处添加 \(a\)-边（代价 \(99/M\)）。关键是传播论证：对高度 \(k+99\) 的点 \(z\)，令 \(y=zu_{99}^{-1}\)，路径 \(y=yu_0\to yu_1\to\cdots\to yu_{99}=z\) 的每一步都先走一条已知高度上的 \(a\)-边、再走 \(b_i\)-边，而 \(za=yu_{99}a=yw\) 是 \(J\)-边；于是从 \(99\) 个连续高度出发归纳地免费获得其余所有高度的 \(a\)-边，令 \(p\downarrow 0\) 即得 \(1+99/M\)。

下界（Bernoulli 作用的 cost 至少 \(1+\eta\)）分三步。先做部署（deployment）与压缩（compression）：定义相对量 \(\delta_X=\inf\{C(\mathcal E):\mathcal R_J\vee\mathcal E=\mathcal R_A\}\)，把近似最优的 \(\Gamma\)-图（graphing）分解到更大的有限测度空间，反复使用压缩引理——当生成的关系被免费供给更大的关系时，重构图可精确回收 \(\kappa(\mathcal S)-\kappa(\mathcal T)\) 的代价节省——再结合融合积正规形，得 \(\operatorname{Cost}(\mathcal R_\Gamma)\ge 1+\delta_X\)。再传递到有限置换模型：对有限精确右 \(A\)-集 \(V\) 定义群 \(D_V=\langle x_v\ (v\in V)\mid x_vx_{vu_1}\cdots x_{vu_{99}}=1\ (v\in V)\rangle\)，利用上闭链（cocycle）\(\theta\)（\(\theta(v,a)=x_v\)、\(\theta(v,b_i)=1\)，行的定义保证 \(\theta(v,w)=1\)，故 \(\theta(v,J)=1\)）与柱面逼近，证明沿渐近自由序列恒有 \(\delta_X\ge\limsup\operatorname{rk}(D_V)/|V|\)；对自由基 \(a,u_1,\ldots,u_{99}\) 取独立均匀随机置换，可得到渐近自由、满足扩张性（expansion）\(|N(T)|>96|T|\)（\(|T|\le\alpha n\)）且坏行（bad row）数 \(o(n)\) 的模型序列，其联合概率界 \([K(s/n)^3]^s\) 正是条件 \(K\alpha^3<1/2\) 的来源。最后是确定性秩下界 \(\operatorname{rk}(D_V)>\alpha n/100\)，即 Arzhantseva–Ol'shanskii 式缩短论证：反设存在边数最少的标号图满射到 \(D_V\)，先以饱和程序把坏行与短弧上的字母吸收进系数群（coefficient group）\(H\)（\(H\) 不必有限表现，其嵌入由构造保证），再借助平面词引理在最短闭路中定位一段与某定义行匹配、含至少 \(88\) 个外部字母的长段，其补段至多 \(12\) 个字母，从而可用至多 \(12\) 条新边替换原路段中至少 \(31\) 条边；替换后图仍连通、秩不变、标签映射仍满射，而边数至少减 \(19\)，与极小性矛盾。三步串联得 \(\delta_X\ge\eta\)，完成主定理。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，而 OpenAI 官方声明"未经形式化的结果可能有问题"，结论请以社区核验为准。结果族 259 仅此一篇，证明被拆成三个输入输出自明的模块——相对压缩引理、从 Bernoulli 图到群秩的传递不等式、由扩张性导出的确定性秩下界——可分别审阅，最终在结论一节合流为主定理；其中部署与平面词引理两节的技术细节较强，此处从略。

{% endraw %}
