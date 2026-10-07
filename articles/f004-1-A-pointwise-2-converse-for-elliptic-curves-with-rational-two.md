---
layout: default
title: "A pointwise 2-converse for elliptic curves with rational two-torsion"
family: "004"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A pointwise 2-converse for elliptic curves with rational two-torsion

> 结果族 004：Hilbert’s tenth problem over ℚ　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文证明"点态 2-converse"：对每条带非零有理 2-扭点的椭圆曲线 \(E/\mathbb Q\)，只要其 \(2^\infty\)-Selmer 余秩（Selmer corank）为 0 或 1，就有 \(\mathrm{ord}_{s=1}L(E,s)=\operatorname{rank}E(\mathbb Q)\) 且 Shafarevich–Tate 群 \(\Sha(E/\mathbb Q)\) 有限，并且在素数 2 处允许任意约化类型。

## 问题背景

BSD 猜想（Birch–Swinnerton-Dyer conjecture）断言 \(L\) 函数在 \(s=1\) 的零点阶等于 Mordell–Weil 秩，且 \(\Sha\) 有限。解析阶为 0 或 1 时的"正向"结论由 Gross–Zagier 与 Kolyvagin 定理完成，而"converse"（逆问题）是从代数信息反推解析阶。已有结果都带额外假设：已知秩为 1 且 \(\Sha\) 有限时的 converse 对所有曲线成立（Kim）；Skinner、Zhang 等的 \(p\)-converse 需要好普通奇素数等条件；CM 曲线在 2 处有 Burungale–Tian、Kriz 等的特例；Smith 的定理只给出扭点族中 \(2^\infty\)-Selmer 余秩的 50/50 密度分布，管不了指定的某一条曲线。"在 2 处、对单条指定曲线、仅凭低 Selmer 余秩"的 2-converse 此前是空白，本文将其补上，并成为同族姊妹篇（希尔伯特第十问题在 \(\mathbb Q\) 上）证明中从双下降数据过渡到有理点的关键输入。

## 主要结果

定理 1.1：设 \(E/\mathbb Q\) 满足 \(E(\mathbb Q)[2]\ne0\)，记 \(s_2(E)=\operatorname{corank}_{\mathbb Z_2}\Sel_{2^\infty}(E/\mathbb Q)\)。若 \(s_2(E)\in\{0,1\}\)，则
\[\operatorname{ord}_{s=1}L(E,s)=\operatorname{rank}_{\mathbb Z}E(\mathbb Q)=s_2(E),\qquad \Sha(E/\mathbb Q)\ \text{有限}.\]
结论覆盖全有理 2-扭点、CM 与非 CM 曲线、任意有理同源构型以及坏素数处的任意约化；但不给出 BSD 的前导系数公式，且 \(\operatorname{rank}E(\mathbb Q)\le1\) 本身也不足以推出 Selmer 假设。作者另有去掉有理 2-扭点假设的更广 converse，本文独立自足，不以它为输入。

## 证明思路

核心困难在素数 2：\(E[2]\) 的残余表示完全退化（可约且迹为零），经典插值手段失灵，必须在 2-adic 世界重建一致的整性控制。策略是把原曲线嵌入二次扭点（quadratic twist）的二进制族：对 \(x\in\mathbb F_2^b\) 令 \(h_x=h_0\prod_q q^{\lambda_q(x)}\)，每个辅助素数 \(q\) 按一个线性型激活；先让每个非零地址都有已知的解析阶和一致的 normalized 估值界，再用整插值把值或导数"传回"缺失的地址 \(x=0\)。

先做余秩 0（偶）情形，对象是中心 \(L\) 值。一侧是 Kato 的 zeta 类：把辅助迹全部落入固定权 2 形式的整格，配合 Ferrero–Washington 消灭定理，得到群环 \(\mathbb Z_2[G]\) 上行列式坐标 \(u\) 的整性，其中心值与 \(v_2(\mathcal L(h_x))-2w(h_x)-s(h_x)\) 相差固定常数（\(w\) 是扭点在 \(E[2]\) 上的 Frobenius 权重，\(s\) 是 \(\Sha\) 的 2-长度）。另一侧是 Waldspurger 关系：半整权（half-integral weight）形式的系数度量中心 \(L\) 值，经 Gross 的定四元数 theta 构造给出显式的"偶单位符号"。在足够大的立方体上，Chevalley–Warning 型二进制同余保证存在 \(x\ne0\) 使 \(u_x(0)\equiv u_0(0)\pmod{2^M}\)，从而基点中心值非零且估值受控。所得"偶估计"还被复用：为奇数情形提供一致下界。

再做余秩 1（奇）情形，对象是导数。固定负判别式 \(h_*\)（\(L(E^{(h_*)},1)\ne0\)），genus 特征 Heegner 点和 \(P_h\) 的高度由显式 Gross–Zagier 公式度量 \(L'(E^{(h)},1)L(E^{(h_*)},1)\)。先取素数因子个数有界的伴随判别式 \(k'(h)\)，把偶估计与 ring-class 下界合并，证明 \(P_h\) 的 2-整除指数有与 \(h\) 的素数个数无关的下界；此后才正规化奇系数，得到有固定最小深度的"奇单位符号"——解析阶 1 的检测器。随后固定中心值非零的 \(k\)，令 \(K=\mathbb Q(\sqrt k)\)，由二次余秩恒等式 \(s_2(E/K)=s_2(E)+s_2(E^{(k)})=1\)；构造所有新素数在 \(K\) 中分裂的族，使每个非零地址上 \(E^{(h)}\) 有单零点、\(E^{(hk)}\) 中心值非零，奇偶两个测试联合给出 ring-class 指数 \(j_h(k)\) 的一致上界，最后经 ring-class 缺失顶点转移把 \(s=1\) 处的单零点传回原曲线。

两个关键配角值得点名。其一，单位符号本质上是辅助素数之间的二次互反符号（quadratic residue symbols），满足收缩规则；文中先用射线类（ray class）与 Chebotarev 定理证明任意有限符号模式都可由新鲜素数实现，再用有限"素数网络"（address 引理）使一到两个测试在每个非零地址同时取值 1，而地址 0 处不出现任何辅助素数。其二，坏素数处完整的整 Kummer 条件与 Kolyvagin 导数算子被全程保留，即使局部类被 2 整除也不损失行列式估值——这正是"2 处任意约化"的代价，也是其本事所在。

## 可信度与备注

本文未经 Lean 形式化，按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。它与结果族 004 的主篇互相支撑：主篇的极点奇偶条件直接调用本文定理 1.1 的直接推论（\(E(\mathbb Q)[2]\ne0\) 且 Selmer 余秩 \(\le1\) 即得 \(\Sha\) 有限），从而把 2-下降数据转化为有理点；而本文的证明不依赖那篇主篇，逻辑上自足。插值与图组合两套论证都相当新颖，细节繁多，是最需要社区复核的部分。

{% endraw %}
