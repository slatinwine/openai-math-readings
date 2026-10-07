---
layout: default
title: "Prescribed large-volume charges on threefolds with trivial canonical bundle"
family: "055"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Prescribed large-volume charges on threefolds with trivial canonical bundle

> 结果族 055：Gepner symmetry and large-volume stability on threefolds　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
在每个典则丛平凡（\(K_X\simeq\OO_X\)）的光滑投影复三维流上，作者对一切足够大的体积参数构造出中心荷精确等于普通与平方根 Todd 大体积荷的数值 Bridgeland 稳定性条件，且一个阈值统管实扭曲与丰富方向的一个开集；另在任意三维流上证明了一致强倾斜不等式。

## 问题背景
Bridgeland 稳定性条件由中心荷与切片给出，用来给导出范畴的对象排序。物理上的大体积极限预言：体积参数 \(t\to\infty\) 时中心荷应趋于陈特征的指数式 \(-\int_Xe^{-B-itH}\ch(E)\Theta\)（\(\Theta=1\) 或 \(\sqrt{\td(X)}\)）。所谓指定荷问题（prescribed-charge problem）问：这些特定表达式是否配有相容的心（heart）、有限的半稳定滤波与支撑界？Bayer 的多项式稳定性条件只在渐近意义下排序相位；要在每个有限体积处得到真正的 Bridgeland 条件，还得管住荷的核——皮卡秩大于一时，完整数值 Grothendieck 群（numerical Grothendieck group）里含有沿单一极化看不见的类。三维流的最大障碍在第三陈特征：它不进入经典 Bogomolov–Gieseker 不等式，Bayer–Macrì–Toda 为此提出双倾斜（double tilt）构造与第三陈特征不等式猜想；Bernardara–Macrì–Schmidt–Zhao 进而问是否存在带曲线类修正的版本，而无修正版本已被 Schmidt 等人的反例否定。一般三维流上稳定性条件的存在性近来由 Li 及 Li–Liu–Liu–Macrì–Perry–Stellari–Zhao 的框架解决，Cheng 亦证得全数值支撑；"精确指定中心荷"此前仍属空白。

## 主要结果
定理一（实扇形上的精确大体积荷）：设 \(X\) 光滑投影复三维流且 \(K_X\simeq\OO_X\)。对任意实除子类 \(B_*\) 与丰富类 \(H_*\)，存在邻域 \(V\ni B_*\)、\(W\ni H_*\) 与同一个阈值 \(T>0\)，使所有 \(B\in V\)、\(H\in W\)、\(t\ge T\) 同时满足：(i) 普通物理荷 \(Z_{B,tH}(E)=-\ch_3^B(E)+\tfrac{t^2}{2}H^2\ch_1^B(E)+i\bigl(tH\ch_2^B(E)-\tfrac{t^3}{6}H^3\ch_0(E)\bigr)\) 配上标准双倾斜心 \(\mathcal A_{B,tH}\)，构成几何（点层稳定）数值稳定性条件；(ii) 存在几何数值稳定性条件，其荷恰为 \(Z^{\mathrm{LV}}_{B,tH}(E)=-\int_Xe^{-B-itH}\ch(E)\sqrt{\td(X)}\)，其中 \(\sqrt{\td(X)}=1+c_2(X)/24\)。两例都在完整 \(\Knum(X)_\R\) 上满足支撑性质（support property）。假设只需要 \(K_X\) 平凡，不需要严格 Calabi–Yau 的额外消没。
定理二（一致强不等式，任意三维流）：对每个光滑投影复三维流、整极化 \(H\) 与有理类 \(B_0\)，存在仅依赖 \((X,H,B_0)\) 的 \(k\in\Q_{\ge0}\) 与 \(R_*>0\)，使每个零斜率、有限斜率的 \(\nu_{a,b}\)-半稳定对象满足 \(\ch_3^{B_0+bH}(E)\le\bigl(\tfrac{a^2}{6}+k\bigr)H^2\ch_1^{B_0+bH}(E)\) 对一切 \(a>0\)、\(b\in\R\)；且 \(a>R_*\) 时更强的无修正界成立。这正面回答了上述修正不等式问题。推论给出抛物区域 \(\alpha>(\beta^2+R_*^2)/2\) 上的二次型不等式 \(Q_{\alpha,\beta}(v_H(E))\ge0\)。

## 证明思路
全文有两条相互独立的论证线。

第一线是范畴构造，先在环境空间上做。作者选取张成 \(N^1(X)_\R\) 的极丰富线丛，把 \(X\) 嵌入射影空间之积 \(Y=\prod_h\mathbb P^{d_h}\)；三维时除子类的乘积张成完整数值群，故 \(i_*\) 在数值群上单射——环境支撑便能控制 \(X\) 的每个数值类。再在 \(Y\) 上借用椭圆曲线积与有限商构造稳定性条件（Liu 的配曲线乘积、Li 等的支撑归纳、Cheng 的两块构造），关键是在按 \((Rs_h)^{d_h-j_h}\) 缩放的坐标下支撑常数与体积 \(R\) 无关，而指数荷的任何固定正余维修正都随 \(R\to\infty\) 衰减为零。于是用固定多项式因子 \(\gamma=\td(Y)(1-\delta/12)\) 或 \(\td(Y)(1-\delta/24)\)（\(\delta\) 提升 \(c_2(X)\)）修正环境荷：Grothendieck–Riemann–Roch 保证限制到 \(X\) 后恰好得到指定的两种荷；缩放支撑配合变形估计 \(\|(U_t^{B,H}-U_t)\circ M_t^{-1}\|\le C_1\eta+C_2t^{-1}\)，让 Bayer 变形定理沿直线路径整体提升，一个阈值 \(T\) 覆盖整个开扇形。最后经有限映射限制准则（线丛扭曲的 Bayer 性质、点层本原类配合开邻域论证升级为稳定）把切片拉回 \(X\)。普通荷的心还需逐层识别：先在光滑曲面截口上用诱导荷的虚部认出倾斜心，再用正权截口夹出严格斜率界，把构造出的心安放在第一倾斜的相邻平移之间，最后在实轴边界区分第二倾斜的正斜率与零斜率，证得 \(\mathcal P(0,1]=\mathcal A_{B,tH}\)。

第二线是纯数值论证，证明定理二，全程不用 \(K_X\) 的假设。力量集中在一个固定体积 \(A\) 处：对零斜率半稳定对象证明顶点估计 \(z_B(E)-\tfrac{A^2}{6}d_B(E)\le C\bigl(d_B(E)-A|r(E)|\bigr)\)，右端度量与判别式等式的距离且不带任何秩项——这对 \(e=d_B-A|r|=0\) 的大秩对象也必须成立。先截断斜率滤波，把斜率落在 \([b+A,b+A+1]\) 窄带的尾部从余部剥离，余部的秩与前两个交度均为 \(O(e)\)；余部上同调由 Langer 限制不等式、Hermite–Einstein 理论与 Bochner 恒等式配合 Cwikel–Lieb–Rozenblum 型谱估计控制。再把有限个层与映射约化到特征 \(p\)，用 \(\ch_i(F^*E)=p^i\ch_i(E)\) 与 Riemann–Roch 极限 \(\lim_{p\to\infty}p^{-3}\chi(F^*E\otimes L_p)=h\,z_B(E)\)，使依赖具体对象的误差在除以 \(p^3\) 后消失，窄带贡献恰给出系数 \(A^2/6\)。最后是墙传输（wall transport）：沿零斜率双曲线支 \(d(a)=\sqrt{\Delta+a^2r^2}\) 有微分不等式 \(D_a'=-\tfrac a3S_a\)，三个比较函数保证严格违例朝向或背离顶点传播；遇墙则换成仍违例的稳定因子，离散判别式 \(\Delta\in N^{-1}\Z\) 每次严格下降，过程必然有限。由此得全体积修正界与 \(a>R_0=A+3C/A\) 处的无修正尾部。该步骤技术细节（特征 \(p\) 中的谱估计与伸缩求和）此处从略。

## 可信度与备注
本文与姊妹篇（同族中证明五次超曲面 Toda Gepner 猜想一文）共享三维流双倾斜稳定性这一框架：姊妹篇在五次超曲面上借 Xu 的更强 BG 不等式实现 \(2/5\) 相位对称，本文则自给一致强倾斜不等式并把大体积构造推进到一切平凡典则丛三维流。两文主结果均无 Lean 形式化证明；本文另含与 Schmidt、Martinez–Schmidt 反例的定量对照。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
