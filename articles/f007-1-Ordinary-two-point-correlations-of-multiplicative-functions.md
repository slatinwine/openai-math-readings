---
layout: default
title: "Ordinary two-point correlations of multiplicative functions"
family: "007"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Ordinary two-point correlations of multiplicative functions

> 结果族 007：Ordinary two-point correlations and the corrected Elliott conjecture　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在无对数加权的普通平均下证明了二元 Chowla 猜想：对固定非比例仿射形式，\(\sum_{n\le X}\lambda(a_1n+b_1)\lambda(a_2n+b_2)\ll X/(\log X)^c\)，\(c>0\) 为绝对常数；并对一般有界乘性函数确立了二元修正 Elliott 猜想。

## 问题背景

刘维尔函数（Liouville function）\(\lambda(n)=(-1)^{\Omega(n)}\) 记录 \(n\) 的素因子个数（计重数）之奇偶。Chowla 在 1965 年预测 \(\lambda\) 的各阶相关平均趋于零，二元情形即问：\(n\) 与 \(n+h\) 的素因子个数奇偶性是否渐近不相关？Elliott 把问题推广到有界乘性函数（multiplicative function），而 Matomäki–Radziwiłł–Tao 指出原始条件须加修正：一个函数可在相继尺度上模仿不同的 \(n^{it}\) 扭转，却全局上不模仿任何固定扭转。此前进展分两支：对数加权平均下，Tao（2016）证明了修正 Elliott 定理，Helfgott–Radziwiłł 与 Pilatte 先后把 \(\sum_{n\le x}\lambda(n)\lambda(n+1)/n\) 控制到 \((\log x)^{1-c_0}\)，但都保留对数权；普通平均下，Tao–Teräväinen 与 Klurman–Mangerel–Teräväinen 只能排除一个例外尺度集。普通估计必须在每一个截止点 \(X\) 控制终端尺度本身，这正是长期未被跨越的门槛。

## 主要结果

论文证明两条定理。定理 A（定量）：存在绝对常数 \(c>0\)，对每组固定整数 \(a_1,a_2\ge1\)、\(b_1,b_2\ge0\) 且 \(a_1b_2-a_2b_1\ne0\)（仿射形式非比例），有
\[\Bigl|\sum_{1\le n\le X}\lambda(a_1n+b_1)\lambda(a_2n+b_2)\Bigr|\le C\frac{X}{(\log X)^c}\qquad(X\ge3),\]
指数 \(c\) 与形式无关，截止可为任意实数，系数无须互素。取 \(a_1=a_2=1\)、\(b_1=0\)、\(b_2=h\) 即普通两点 Chowla 猜想；证明先在每个固定剩余类（residue class）模 \(l\) 上建立同型估计，再以完全乘性推出仿射结论。定理 B（二元修正 Elliott 猜想，binary corrected Elliott conjecture）：设 \(f_1,f_2:\mathbb N\to\mathbb D\) 乘性，至少一个一致非伪装（uniformly nonpretentious）——即对每个固定 Dirichlet 特征 \(\chi\)，\(\inf_{|t|\le N}D(f,\chi n^{it};N)\to\infty\)，其中 \(D(f,\chi n^{it};X)^2=\sum_{p\le X}\frac{1-\mathrm{Re}(f(p)\overline{\chi(p)p^{it}})}p\) 是素值距离——则 \(\frac1N\sum_{n\le N}f_1(n+h_1)f_2(n+h_2)\to0\)。函数可取复值、模长可小于一、无须完全乘性；同样的极限在固定剩余类与固定非比例仿射形式下成立。又因 \(\mu(p)=\lambda(p)=-1\) 而距离只依赖素值，Möbius 函数（Möbius function）亦满足该条件，故 Möbius 及 Möbius–Liouville 混合两点相关同样趋于零（此路不给速率）。

## 证明思路

两个证明共用同一骨架：乘性膨胀（multiplicative dilation）——比较 \(n,n+h\) 与 \(dn,d(n+h)\) 两处的相关，得到边位移为 \(hd\) 的整数图；用短区间傅里叶估计把整除指示子换成带符号因子；再以闭游走（closed walk）估计界住所得图算子。差别在顶点权重与取极限的次序。

定量证明先在固定剩余类处理 \(\lambda(n)\lambda(n+h)\)。每步引入来自 \(J\) 个互不相交素数供应的素数，各供应倒数质量约为大常数 \(W\)，贡献均值恰为零的因子 \(\mathbf 1_{p\mid n}-1/p\)；另以平方自由的"填充除子"控制除子权重在短乘性区间内的集中。这些中心化供应贡献质量 \(W^J\)，而在算子界中只占 \((C\sqrt W)^J\)：取 \(W\) 足够大便得随 \(J\) 的指数衰减，而 \(J\) 与 \(\log\log X\) 成比例，故得对数幂节约。两大障碍各有对策：其一，素数供应随 \(X\) 增长，无法遍历其联合周期，于是把剩余测试与独立剩余模型比较，先将编码的比特律修正为精确有界独立（bounded independence），再援引 Braverman 的电路定理；其二，素数在游走中重复会锁死步履——独立算术关系足够多时直接得节约，所剩无几时改用森林（forest）编码重复模式，其计数对填充值一致，可事后在同一剩余环境中合并。最后谱分析把图估计传回普通相关，完全乘性完成仿射演绎。

定性证明面对发散速率未知的非伪装距离，故次序倒置：先固定图尺度 \(B\)、取长平均极限，最后令 \(B\) 增大。反设偏置 \(|S(N_j)|\ge\gamma N_j\) 存在。在尺度 \(B\) 取权重 \(A>1\) 的核心带（core band）与权重 \(1\) 的中心带（center band）两组素数，鸽笼选出一个承载约 \(L_0/B\) 倒数质量的除子区间；取系数 \(\overline{f_1(d)f_2(d)}\)，原始和的下界为 \(c_\gamma L_0/B\)。把指示子换成 \(\mathbf 1_{p\mid n}-\theta/p\)（\(\theta=1/4\) 与顶点归一化匹配，本身并非均值零）的中心化代价，经傅里叶反转化为粗糙数（rough number）上的乘子 \(Q_M\)，筛法给出其上确界与四阶矩界，再结合 MRT 短区间指数和定理及"大频率集测度小"的频率分裂，合计 \(o(L_0/B)\)。另一方面，图估计对任意有界序列给出 \(O(L_0B^{-1-c_*/2})\)：额外的幂来自核心带除子区间之短与素数个数下截断，而中心带在闭游走积中贡献相消——游走按首次访问树（tree of first visits）组织，先展开顶点删除条件、让中心素数剩余保持无条件，其带符号平均在取绝对值之前完成。三项合并得 \(c_\gamma\le C(B^{-c_*/2}+B^{-\epsilon}+BJe^{-B^{1-\epsilon}})\)，令 \(B\to\infty\) 便与偏置矛盾。剩余类与仿射形式最后经特征正交与膨胀的有限局部展开（\(2^{\omega(a)}\) 项带符号乘性函数）归约到定理 B；\(\lambda,\mu\) 的一致非伪装由 MRT 的距离估计直接验证。

## 可信度与备注

任务元信息标记本篇为未形式化：主结果暂无 Lean 证明，OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。定理 A 与定理 B 互相支撑——前者是后者在 \(\lambda\) 情形的定量强化，后者把同一图方法推广到一般有界乘性函数，两者共享乘性膨胀与闭游走骨架，作为结果族 007 的核心论文与其他手稿围绕修正 Elliott 猜想互为印证。证明对已有文献（MRT 短区间定理、Braverman 定理、筛法估计）逐一注明出处，新构造部分（素数供应、森林计数、首次访问树展开）在论文内自证完毕。

{% endraw %}
