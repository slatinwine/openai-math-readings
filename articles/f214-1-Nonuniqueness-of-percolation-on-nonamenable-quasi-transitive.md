---
layout: default
title: "Nonuniqueness of percolation on nonamenable quasi-transitive graphs"
family: "214"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Nonuniqueness of percolation on nonamenable quasi-transitive graphs

> 结果族 214：The Benjamini–Schramm nonuniqueness conjecture　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明 Benjamini–Schramm 1996 年渗流非唯一性猜想：任何无限、连通、局部有限、非顺从而拟传递的图上，Bernoulli 键渗流必有一段参数使几乎必然同时出现无穷多个无穷开簇；并证得更强的 Hutchcroft 算子阈值猜想 \(p_c<p_{2\to2}\le p_u\)。

## 问题背景

Bernoulli 键渗流（bond percolation）让图中每条边以概率 \(p\) 独立开放；无穷开簇何时出现、何时唯一，分别由临界值 \(p_c\) 与唯一性阈值 \(p_u\) 刻画。在格点 \(\mathbb Z^d\) 上两者重合，而在非顺从（nonamenable，即顶点等周常数 \(h_V>0\)）的图上，指数扩张的几何可能让多个无穷簇长期共存。Benjamini 与 Schramm 在 1996 年猜想：轨道有限的非顺从图上必有 \(p_c<p_u\)，正则树即原型。此前肯定结果均需附加额外假设——平面性、大围长、Gromov 双曲、调和 Dirichlet 函数、恰当生成元集等；仅凭非顺从性本身打开间隙是三十年来的核心障碍。

## 主要结果

主定理：设 \(G\) 无限、连通、局部有限、拟传递（quasi-transitive，自同构群只有有限多条顶点轨道）且 \(h_V(G)>0\)，则两点连接核 \(T_p(x,y)=\mathbb P_p(x\leftrightarrow y)\) 作为 \(\ell^2(V)\) 上的算子在临界点有界，且 \(p_c(G)<p_{2\to2}(G)\le p_u(G)\)，其中 \(p_{2\to2}\) 是 \(T_p\) 在 \(\ell^2\) 上有界的阈值。由此存在 \(p_c<p_1<p_2<1\)，使标准耦合下对每个 \(p\in[p_1,p_2]\) 几乎必然同时出现无穷多个无穷开簇。推论：任何非顺从有限生成群、任何有限对称生成元集所给的 Cayley 图上同样有 \(p_c<p_{2\to2}\le p_u\)。并确立临界三角条件（triangle condition）\(\nabla_{p_c}(v)\le\|T_{p_c}\|_{2\to2}^3<\infty\) 与平均场指数：敏感度（susceptibility）\(\chi_v(p)\asymp(p_c-p)^{-1}\)、渗流概率 \(\theta_v(p)\asymp p-p_c\)、簇尺寸尾 \(\mathbb P_{p_c}(|C_v|\ge n)\asymp n^{-1/2}\)、内外蕴半径尾均 \(\asymp n^{-1}\)；且 \(p_c<p_{2\to2}\le p_{\exp}\)——无穷簇已出现的区间里连接概率仍指数衰减。

## 证明思路

证明分四步。先归约：非单模情形直接引用 Hutchcroft 的非单模算子定理，新论证只处理单模自同构群；再设图为简单图、临界簇几乎必然有限。

再证临界簇的"良态性"（goodness）：尺寸 \(\le M\) 的临界簇以 \(1-e^{-M^\epsilon}\) 的概率满足——任意删点后，各余块内分隔两点的桥（bridge）数被其与删除集的接触数乘 \(M^{1/2+\epsilon}\) 控制；证明以独立顶点标记（ghost field）与中心化边得分的集中不等式（Aizenman–Kesten–Newman 波动方法）控制关键边（pivotal edge）各阶矩，再移植成上述控制。

接着反证放大：设某个 \(0<\alpha<1/2\) 的临界尺寸矩发散，则在固定轨道上构造"局部端点映射"——读有限球内渗流位、在簇内选端点的协变规则，靠在独立渗流场间拼接有限簇块实现；良态性控制桥数，得端点核 \(K\) 满足 \((\log(1/u)+\log M)/\log(1/\|K\|)\to0\)。再在 \(p<p_c\) 运行该映射：小范数迫使迭代把端点质量推出按尺寸加权的独立采样簇，由此得敏感度的微分不等式，与矩发散矛盾，故 \(\sup_x\mathbb E_{p_c}|C_x|^\alpha<\infty\)，进而 \(\chi_{\max}(p)\le C_\eta(p_c-p)^{-1-\eta}\)；双探索比较另给三角图（triangle diagram）次幂界 \(\sup_x\nabla_p(x)\le C_\eta(p_c-p)^{-\eta}\)。

最后是走廊形变与谱矛盾：把 \(k\) 步对称懒游走经时序擦圈（loop erasure）得到简单路，凡整条成为连接之关键"走廊"（内部顶点无其他开边）者施以指数惩罚；校准权重使算子范数至多损失 \(2t\rho^k\|T_p\|^2\)（\(\rho<1\)），行和的下降率则由两端在删走廊后的形变敏感度下界控制，且路径两端常有短"逃逸"、删走廊影响甚小。若 \(\|T_{p_c}\|=\infty\)，洒水（sprinkling）比较给 \(\|T_p\|\ge c(p_c-p)^{-1}\)，结合前两步可取 \(k=o(\log(1/(p_c-p)))\) 使范数仍大而行和二次下降——行和兜不住残存范数，矛盾。再经洒水与比较得 \(p_c<p_{2\to2}\le p_u\)，有限修改补出同时区间。

## 可信度与备注

本文是该结果族的主证明：非唯一性猜想与更强的算子阈值猜想在同一框架内一并证明；临界行为推论以 Hutchcroft 早先的条件定理为输入，新贡献是验证算子条件对全类图成立。主结果暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。

{% endraw %}
