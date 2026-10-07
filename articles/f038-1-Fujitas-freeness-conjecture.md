---
layout: default
title: "Fujita's freeness conjecture"
family: "038"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Fujita's freeness conjecture

> 结果族 038：Fujita's freeness conjecture　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文在最优界上证明了藤田自由性猜想（Fujita's freeness conjecture）：\(n\) 维光滑射影复簇 \(X\) 上，任意丰富线丛 \(L\) 拉伸 \(n+1\) 倍即可使伴随丛 \(K_X+(n+1)L\) 全球生成，且界不可改进。这个 1987 年提出的猜想首次在所有维数一并成立。

## 问题背景

线丛"全球生成"（globally generated）指每一点都存在不消失的截面。1987 年藤田猜想：即使丰富线束（ample line bundle）\(L\) 自身没有任何非零截面，\(K_X+(n+1)L\) 仍全球生成。曲线情形由 Riemann–Roch 给出，曲面由 Reider 定理，三维、四维由 Ein–Lazarsfeld 与 Kawamata，五维由 Ye–Zhu（2020）解决。一般维数长期停滞：Angehrn–Siu（1995）得 \(m\ge (n^2+n+2)/2\)，Heier 降到约 \(n^{4/3}\)，Ghidelli–Lacini（2024）得 \(n(\log\log n+2.34)\)，Han（2026）得 \(1.7763n\)；Chan 曾宣布证明更强的交点数形式，后因局部延拓论证无法保证所需消没阶而撤回。共同的卡点是：消没策略中所构造的中心可能正维数且奇异，切割它会损失正性。

## 主要结果

定理（主定理）：设 \(X\) 为光滑连通射影复簇，\(\dim X=n\ge1\)，\(L\) 为丰富线丛，则 \(K_X+(n+1)L\) 由整体截面生成。界是尖锐的：取 \(X=\mathbb P^n\)、\(L=\mathcal O(1)\)，则 \(K_X+(n+1)L\) 平凡，而 \(K_X+nL\) 没有非零截面。推论：对每个整数 \(m\ge n+1\)，\(K_X+mL\) 均全球生成（把定理用于 \(X\times\mathbb P^r\) 与 \(L\boxtimes\mathcal O(1)\) 即得）。注意结论只断言每点截面非零，不含分离点或切方向的极强丰富性（very ampleness）那一半。

## 证明思路

整体是反证法：设 \(P=K_X+(n+1)L\) 在闭点 \(x\) 处不生成，按论文图 1 分五步导出矛盾。先建立"普通阶数二择一"：在 \(x\) 处按全次数给 \(H^0(X,jL)\) 的截面排 Taylor 初指数集 \(H_j\)，消去论证给出 \(|H_j|=N_j\)，格点填充估计给出平均重数下界 \((L^n)^{1/n}\cdot n/(n+1)\)。论文进一步证明：若严格不等式不成立，则必有 \(L^n=1\) 且沿子列取等，此时可挑出初指数近似填满单纯形的截面组，在点爆炸（blowup）的例外除子 \(E\simeq\mathbb P^{n-1}\) 上，借助阈值半连续性从单项式特殊纤维转移，得到严格大于 \(1/h\) 的局部对数典范阈值（log canonical threshold），再用 Kawamata–Viehweg 消没（vanishing）从 \(E\) 提升一个非零纤维值并下降，与 \(x\) 是基点矛盾。因此基点的存在迫使严格空隙：平均阶除以次数的下极限大于 \(n/(n+1)\)。

再把这个空隙装进一个指数型目标泛函 \(F_{m,t}(v,\mathbf s)=\frac1{N_m}\sum_i\exp\big(\frac{A(v)}t-\frac{v(s_i)}m\big)\)（\(t<n+1\)），让基 \(\mathbf s\) 与带权单项式赋值 \(v\) 同时变动，\(A(v)\) 为对数差异（log discrepancy）。取 \(v=\lambda\operatorname{ord}_x\) 并利用严格空隙可使目标值 \(\le 1-\delta\)；由丰富性造出的低阶 jet 供给配合 \(\operatorname{lct}_x\ge 1/\operatorname{mult}\) 给出一致强制性：\(c\le f_{m,t}(x)\le 1-\delta\)，且次水平集上 \(a_*\le A(v)\le a^*\)。下确界的可达性是难点：作者不去紧致化"全体基与赋值"，而是把同时阶数下界编码为 \(X\times\) 旗簇（flag variety）上理想的闭阈值轨迹，嵌套闭集给出公共旗，再把一切证据收缩（retraction）到同一个单纯形交叠（SNC）模型上取权重的紧极限。

接着消灭正维数中心。设某极小对的中心 \(W\) 维数 \(d>0\)：在 \(W\) 的很一般点处对 \(v\) 作切向一阶变分（切参数赋权 \(\epsilon\)、纤维参数赋权 \(\epsilon^2\)），配合特殊化比较 \(f_{m,t}(y)\ge f_{m,t}(x)\)，得切向矩 \(T_m\le d/t\)。反向则依赖一个对所有 \(d\) 维子簇一致的限制空间维数下界 \((d!\,I_W(h))^{1/d}\ge h-C_d\)（只依赖 \((X,L)\)，与中心的次数和奇性无关），结合由立方包含 \(\{0,1\}^d\subset G_0\) 导出的离散 Brunn–Minkowski 不等式与分段 Riemann 和估计，得 \(\liminf T_m\ge dI_*\)，其中 \(I_*=\int_0^1s^n e^{(1-s)a_*/(n+1)}\,ds\)。选取 \(t<n+1\) 充分接近 \(n+1\) 使 \(I_*>1/t\)，两端矛盾。于是对固定的 \(t\)，任意大度数下所有极小对的中心恰为 \(\{x\}\)。

最后两步完成孤立与提升。点中心极小对的梯度给出正系数支撑泛函 \(b\)：\(b\cdot q=1\)、\(m\sum_ib_i=t<n+1\)；经有理化引理得到 \((q^0,b^0)\)，并精确保持"哪些多面体包含该轮廓"，经环面（toroidal）提取得到中心为 \(x\) 的素除子 \(F_0\)。以理想 \(\mathfrak c\) 的主理想化构造扰动边界 \(B\)，使 \((n+1)\rho^*L-B\) 为 nef 且 big，且在含 \(F_0\) 的约化除子 \(S\) 的每个分量上 \(B\) 的系数恰等于该分量的对数差异、相邻素除子上严格更小——这就是差异等式的刚性。对 \(D=K_T+(n+1)\rho^*L-\lfloor B\rfloor\) 用 Kawamata–Viehweg 消没得 \(H^1=0\)；因 \(S\) 既约且映到点 \(x\)，有 \(\rho^*P|_S\simeq P|_x\otimes\mathcal O_S\)，取纤维 \(P|_x\) 中的非零向量，乘上修正除子的典范截面（它在 \(S\) 附近有效且在 \(S\) 的分量上系数为零），经限制满射提升后由下降引理得到 \(s\in H^0(X,P)\) 且 \(s(x)\ne0\)，与基点假设矛盾。全程只需 \(x\) 附近的局部控制，无需全局 log canonical 边界。

## 可信度与备注

本结果族（038）由这一篇手稿独立承担全部论证，无其他姊妹篇互相支撑。任务元数据标明 formalized=false：主结果尚无 Lean 形式化证明，请以社区核验为准，且按 OpenAI 官方声明，"未经形式化的结果可能有问题"。论文自查痕迹较充分：图 1 概括五步路线，表 1 追踪各常数对 \((X,L)\) 的一致性与极限顺序；但鉴于 Chan（2024）宣布后又撤回的前车之鉴，局部延拓一步（差异等式的刚性与提升）尤其值得专家复核。

{% endraw %}
