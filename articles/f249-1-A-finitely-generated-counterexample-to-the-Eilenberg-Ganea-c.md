---
layout: default
title: "A finitely generated counterexample to the Eilenberg–Ganea conjecture"
family: "249"
discipline: "Group theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A finitely generated counterexample to the Eilenberg–Ganea conjecture

> 结果族 249：A finitely generated Eilenberg–Ganea counterexample　·　学科：Group theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文构造了一个有限生成、剩余有限（residually finite）的群 \(G\)，其整上同调维数为 \(2\) 而几何维数为 \(3\)，从而否定 Eilenberg–Ganea 猜想：\(G\) 不存在任何二维分类空间，即便允许无穷多个胞腔。这一悬置近七十年的维数问题以否定方式告终。

## 问题背景

对离散群 \(\Gamma\)，整上同调维数（integral cohomological dimension）\(\cd_Z\Gamma\) 定义为平凡 \(\Z[\Gamma]\)-模 \(\Z\) 的最短投射消解长度；几何维数（geometric dimension）\(\mathrm{gd}\,\Gamma\) 是以 \(\Gamma\) 为基本群、万有覆盖可缩的 CW 复形——即分类空间（classifying space）\(K(\Gamma,1)\)——的最小维数。可缩万有覆盖的胞腔链给出自由消解，故恒有 \(\cd_Z\le\mathrm{gd}\)。1957 年的 Eilenberg–Ganea 定理证得 \(\cd_Z\ge 3\) 时两数相等；一维情形由 Stallings 与 Swan 解决（\(\cd_Z=1\) 的群必为自由群），唯独二维情形成为遗留猜想。Bestvina–Brady 的高度核（height kernel）例子提供了天然候选：他们证明，对 Poincaré 同调球面脊柱的适当 flag 三角剖分，Eilenberg–Ganea 猜想与 Whitehead 可缩性猜想至少一个不真，却无法判定孰假。症结在于：无环（acyclic，约化整同调消没）不等于可缩，即使证明某个二维无环模型不可缩，也堵不死"另换一个二维分类空间"的可能。

## 主要结果

主定理：存在有限生成、剩余有限的群 \(G\)，满足 \(\cd_Z G=2\)、\(\mathrm{gd}\,G=3\)。具体取法：设 \(L\) 是 presentation 复形 \(\langle x,y\mid x^2=y^5,\ x^2=(xy^{-1})^3\rangle\) 的有限无环 flag 三角剖分（该群亦以 \(a^5=b^3=(ab)^2\) 之形出现于 Hatcher 教材例 2.38），\(G\) 是右角 Artin 群（right-angled Artin group）\(A_L\) 在高度同态（height homomorphism，把每个标准生成元映为 \(1\)）\(\lambda:A_L\to\Z\) 下的核，即一个 Bestvina–Brady 群。论文证明 \(G\) 没有任何二维分类空间，无论胞腔多少；同时 \(G\) 属 type \(\mathrm{FL}\)（平凡模有长度二的有限生成自由消解），故为 \(\mathrm{FP}_\infty\)，但由 Bestvina–Brady 有限展示判据（\(\pi_1(L)\) 非平凡）它不是有限展示群。\(G\) 有限生成从而可数，故把猜想限定于可数群也于事无补。

## 证明思路

证明分"造模型—立接口—致矛盾"三段。

先造几何模型。种子复形的胞腔边界矩阵为 \(\begin{pmatrix}2&-5\\-1&3\end{pmatrix}\)，行列式为 \(1\)，故整无环；又能显式写出非平凡表示 \(\alpha:\pi_1(L)\to\SU(2)\)：取 \(\theta=\pi/5\)，令 \(x\mapsto u\)（虚单位四元数）、\(y\mapsto\cos\theta+v\sin\theta\)，其中 \(u\cdot v=1/(2\sin\theta)\)，则两个关系的像均为 \(-1\)。经顺序复形手续得 flag 三角剖分 \(L\)。在 \(A_L\) 的立方模型中，万有覆盖 \(E\) 三维可缩，水平集 \(X=\lambda^{-1}(0)\) 是以 \(G\) 为顶点集的二维单纯复形；其上升链与下降链（ascending/descending link）皆为 \(L\) 的重心重分，配合半空间形变收缩与 Mayer–Vietoris 序列证得 \(X\) 无环。于是 \(X\) 的胞腔链给出长度二的自由消解，\(\cd_Z G\le 2\)；而 \(L\) 含二维单形使 \(G\) 容纳子群 \(\Z^2\)，反向逼出 \(\cd_Z G\ge 2\)；\(E/G\) 则是现成的三维分类空间。剩余有限性由图群的顶点归纳证得。

再立两个互不相容的接口。比较定理说：若 \(G\) 有二维 \(K(G,1)\)，则存在 \(\eta>0\)，凡是与 \(1\) 距离小于 \(\eta\) 的 \(\SU(2)\) 边标号，只要在三角形边界字集 \(\mathcal D\) 的所有平移上乘积为 \(1\)，就在一切闭路上乘积为 \(1\)。小标号命题说：对任意 \(\epsilon>0\)，存在与 \(1\) 距离小于 \(\epsilon\)、逐三角形平坦、却使某闭路乘积非 \(1\) 的标号；而 \(\mathcal D\) 中的字恰是三角形边界，平坦性自动满足前一接口的前提。取 \(\epsilon<\eta\) 即矛盾。

比较定理是核心难点：边界链只记带符号计数、忘记顺序，须借助真实的 aspherical 展示。对可能无穷乃至不可数的生成元与 relator，先经剪切变换把 \(\mathcal D\) 的边界链精确排成特选 relator 的边界；边界同构的单射性随之给出精确的平移计数恒等式。四元数交换子估计 \(|ab-ba|\le 2|a-1|\,|b-1|\) 使线性误差全部相消，只剩二次误差 \(h\le C(h+\epsilon)h\)，自举地排除 \(h\) 越过阈值 \(\delta\)。有限商上解剩余 relator 方程组，用的是 Gerstenhaber–Rothaus 式词映射（word map）度方法：局部化度引理按模素数 \(p\) 计数共轭轨道上的不动点，证得共轭不变区域上映射度非零；再让已给标号沿短弧自 \(1\) 连续滑向目标值，度在变形中保持不变，解随之存在。最后，剩余有限性把任一有限组约束复制进有限商求解，Tychonoff 紧性把全部约束一次满足，二次估计逼出 \(h=0\)：一切 relator 平凡，闭路乘积只能为 \(1\)。

反驳一端靠传输（transport）：迹（trace）理论给出的方向映射 \(b(g)\) 每个生成元步至多变动约 \(2/n\)；把水平图平移至远离单位处，得映射 \(f_N:X\to L\)，一切边像直径 \(\le 4/N\)、三角形边界像 \(\le 8/N\)，而交换幂路径 \(d\,a_q^{-(N-j)}a_r^{-j}\) 恰好精确描出 \(L\) 的指定棱。把 \(\alpha\) 的等变提升（developing map）沿 \(f_N\) 拉回便得小标号：小像迫使逐三角形平坦，被精确追踪的闭路则保有非平凡和乐（holonomy）。矛盾完成证明。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。该结果族目前仅此一篇手稿，无姊妹篇交叉支撑，但论证自足：种子复形的无环性与 \(\SU(2)\) 表示是行列式为 \(1\) 的显式计算，四个模块（几何模型、展示比较、局部化度引理、传输构造）均给出完整证明，依赖的经典结果（Bestvina–Brady、Gerstenhaber–Rothaus、Dicks–Leary、Howie 等）一一注明。鉴于结论推翻了近七十年的公开猜想，严格的专家核验尤为必要。

{% endraw %}
