---
layout: default
title: "An explicit obstruction to nuclear norm-ultrapower embeddings"
family: "292"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An explicit obstruction to nuclear norm-ultrapower embeddings

> 结果族 292：Kirchberg's \(\mathcal{O}_2\) norm-ultrapower embedding problem　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文构造了一个显式的可分幺全群 \(C^*\)-代数 \(A=C^*(G)\)，其中 \(G=\mathbb{Z}[1/2]^3\rtimes(\SL_3(\mathbb{Z})\times\mathbb{Z})\)，并证明 \(A\) 不能幺嵌入任何非零幺核型 \(C^*\)-代数的范数超幂 \(B^\omega\)；取 \(B=\mathcal{O}_2\)，即对 Kirchberg 的范数超幂嵌入问题给出否定回答。

## 问题背景

Cuntz 代数 \(\mathcal{O}_2\) 是由两个满足 \(s_1s_1^*+s_2s_2^*=1\) 的等距元（isometry）生成的泛幺 \(C^*\)-代数。Kirchberg–Phillips 嵌入定理断言：每个可分幺 exact（精确）\(C^*\)-代数都能幺嵌入 \(\mathcal{O}_2\)。Kirchberg 由此提出（见 Goldbring–Sinclair 的综述）：是否每个可分幺 \(C^*\)-代数都能幺嵌入范数超幂（norm ultrapower）\(\mathcal{O}_2^\omega\)？这里 \(\omega\) 是 \(\mathbb{N}\) 上的自由超滤子（free ultrafilter），\(B^\omega=\ell^\infty(\mathbb{N},B)/\{(b_n):\lim_\omega\|b_n\|=0\}\)。这一问题与 Kirchberg 张量范数猜想及 Connes 嵌入问题互不相同。此前的路线或推出可计算性方面的推论（Fox–Goldbring–Hart），或经由"弱显式极小张量范数"给出条件性否定方案（Goldbring–Sinclair），但所需性质至今未被证明。更麻烦的是，非有限性这类已知障碍在此完全无效：\(\mathcal{O}_2^\omega\) 本身就含有真等距元。

## 主要结果

**主定理**：令 \(G=\mathbb{Z}[1/2]^3\rtimes(\SL_3(\mathbb{Z})\times\mathbb{Z})\)，作用为 \((M,k)\cdot v=2^kMv\)，\(A=C^*(G)\) 为其全群 \(C^*\)-代数（full group \(C^*\)-algebra）。则 \(A\) 可分且含单位元，并且对每个非零幺核型 \(C^*\)-代数（nuclear \(C^*\)-algebra）\(B\) 与每个自由超滤子 \(\omega\)，都不存在幺嵌入 \(A\to B^\omega\)。特别地，\(A\) 不能幺嵌入 \(\mathcal{O}_2^\omega\)。群 \(G\) 可数且与 \(B\)、\(\omega\) 均无关，也不要求 \(B\) 可分。

借助 Goldbring–Sinclair 已发表的 KEP 等价刻画，文中还导出三条模型论推论：(1) \(\mathcal{O}_2\) 及任何 exact 或核型幺 \(C^*\)-代数都不是存在封闭的（existentially closed）；(2) 对每个自由 \(\omega\)，存在可分幺代数 \(D\) 与自同构 \(\alpha\)，使 \(D\) 可幺嵌入 \(\mathcal{O}_2^\omega\) 而交叉积（crossed product）\(D\rtimes_\alpha\mathbb{Z}\) 不可；(3) 某个可满足的有限条件组缺乏好核见证（good nuclear witnesses）：任何实现元组经有限维完全正压缩映射（completely positive contractive maps）的分解，误差都有一致正下界 \(\varepsilon_0\)。

## 证明思路

先看群构型。子群 \(\Gamma=\mathbb{Z}^3\rtimes\SL_3(\mathbb{Z})\) 具有 Kazhdan 性质 (T)（property (T)，de Cornulier）。记 \(t=(0,I,1)\)，则共轭 \(t\gamma t^{-1}=\theta(\gamma)\) 把 \(\Gamma\) 同构地映到其指标 8 的子群 \(\Lambda=2\mathbb{Z}^3\rtimes\SL_3(\mathbb{Z})\)，其中 \(\theta(v,M)=(2v,M)\)。取一个经由模 2 约化的有限维不可约表示 \(\pi_*\)，它对平移子群非平凡，而每个 \(\pi_*\circ\theta^j\)（\(j\ge1\)）对平移平凡，故 \(\pi_*\not\simeq\pi_*\circ\theta^j\)——这是全篇矛盾的种子。

再建立谱匹配工具。对含 Kazhdan 集的有限生成集 \(S\)，定义 Laplace 算子 \(L(\mathbf z)=\sum_{s\in S}(z_s-1)^*(z_s-1)\) 与匹配距离 \(d(\mathbf z,\pi)=\min\spec L\bigl((z_s\otimes\bar\pi(s))_{s\in S}\bigr)\)。当 \(\mathbf z\) 来自真表示时，谱隙（spectral gap）引理给出 \(\spec L\subseteq\{0\}\cup[\kappa,R]\)，且 \(d=0\) 恰好等价于 \(\pi\) 含于该表示之中。

接着是关键的核有限性引理（Wassermann 方法）：在核型代数 \(B\) 中任取一个幺正元组 \(\mathbf u\)——完全不要求它满足任何群关系——满足 \(d(\mathbf u,\pi)<a\)（\(a\) 为固定小阈值）的不可约表示类只有有限多个。若不然，取无穷多个两两不等价的 \(\pi_j\)，作矩阵代数商 \(Q=\prod_j M_j/\bigoplus_j M_j\)；利用约化密度算子（reduced density operator）与 Powers–Størmer 平方根迹不等式，得到一致的谱下界 \(b=\kappa^2/(4|S|)\)；核性（极小与极大张量范数相同，Takesaki–Lance）使该不等式经极大张量积传入坐标商，迫使 \(\liminf_j d(\mathbf u,\pi_j)\ge b\)，与 \(d<a<b\) 矛盾。

最后反证：设幺嵌入 \(\Phi:C^*(G)\to B^\omega\) 存在，将群幺正提升为坐标幺正 \(x_n(g)\in B\)，它们只渐近可乘——这正是"不要求群关系"的引理能派上用场的原因。令 \(D_n=\{[\pi]:d(\mathbf x_n,\pi)<a\}\)，由核有限性它是有限集。一方面，把 \(\pi_*\) 从 \(\Gamma\) 诱导（induction）到 \(G\) 再看限制，嵌入的忠实性保证在 \(\omega\)-大指标集上 \([\pi_*]\in D_n\)。另一方面，核心引理断言：在某个 \(\omega\)-大集上，\(D_n\) 的每个成员都有同属 \(D_n\) 的"前驱"，即存在 \(\pi'\) 使 \(\pi\prec\pi'\circ\theta\)。其证明把近不变向量经 \(x_n(t)\) 搬运到 \(\Lambda\) 一侧，再用八个陪集代表 \(r_a\)（\(a\in\{0,1\}^3\)）作有限指标诱导，由 Frobenius 互反（Frobenius reciprocity）取出前驱；所有误差界均与表示维数无关，故维数可随 \(n\) 增长。于是在有限集 \(D_n\) 内从 \(\pi_*\) 出发反复取前驱必然出现循环，初等的维数比较加上不可约性推出 \(\pi_*\simeq\pi_*\circ\theta^p\) 对某个 \(p\ge1\) 成立，与 \(\pi_*\) 的无周期性矛盾。

## 可信度与备注

按任务元数据，本篇主结果暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。本结果族 292 在本批中仅此一篇手稿，但其群构型直接沿用文中引用的 Sauers 与 Eckhardt 关于非有限性、非 MF 群的姊妹工作，本文新增的核有限性引理是把这些构型升级为范数超幂障碍的关键一环；模型论推论则经由 Goldbring–Sinclair 已发表的等价定理衔接，逻辑依赖清晰可查。

{% endraw %}
