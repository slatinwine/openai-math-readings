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

## 入门导读 🐣

物理学家预言过一个极限：当"体积参数" `@@M@@t@@` 无限增大时，对象之秤（稳定性条件的中心荷）应趋向一个漂亮的指数公式。数学家追问：不能只要极限——能否在每个足够大的有限 `@@M@@t@@` 处都精确实现这个公式，并配上整套合法的排序系统（心、切片、支撑界）？本文在典则丛平凡的三维流形上给出肯定答案，而且一个阈值就管住一整片参数。

**关键词卡片**

- 典则丛平凡（trivial canonical bundle）：`@@M@@K_X\simeq\mathcal O_X@@`，例如 Calabi–Yau 型三维流形。
- 中心荷（central charge）：把导出范畴对象称成复数的线性函数，稳定性排序的秤。
- 大体积荷（large-volume charge）：形如 `@@M@@-\int_X e^{-B-itH}\mathrm{ch}(E)\sqrt{\mathrm{td}(X)}@@` 的物理预言公式。
- Todd 类（Todd class）：Riemann–Roch 公式里的修正项；`@@M@@K_X@@` 平凡时 `@@M@@\sqrt{\mathrm{td}(X)}=1+\tfrac{c_2(X)}{24}@@`。
- 支撑性质（support property）：数值类被中心荷的大小控制，使稳定性条件牢靠、可连续变形。

**看个具体例子**

数字版定理（设 `@@M@@K_X\simeq\mathcal O_X@@`）：存在同一阈值 `@@M@@T@@`，对所有 `@@M@@t\ge T@@` 及 `@@M@@B,H@@` 在固定开邻域内的取值，中心荷精确等于大体积公式

`@@M@@Z^{\mathrm{LV}}_{B,tH}(E)=-\int_X e^{-B-itH}\,\mathrm{ch}(E)\bigl(1+\tfrac{c_2(X)}{24}\bigr)@@`，

且在整个数值 Grothendieck 群上满足支撑性质、点层稳定；普通荷 `@@M@@Z_{B,tH}(E)=-\mathrm{ch}_3^B(E)+\tfrac{t^2}{2}H^2\mathrm{ch}_1^B(E)+i\bigl(tH\,\mathrm{ch}_2^B(E)-\tfrac{t^3}{6}H^3\mathrm{ch}_0(E)\bigr)@@` 也同样精确成立。

**为什么值得关心**

"指定荷问题"此前是空白：以往只能在渐近或多项式意义下排序，本文首次在一切典则丛平凡三维流形上逐点精确实现大体积荷，并附赠一条任意三维流上都成立的一致强倾斜不等式。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
在每个典则丛平凡（`@@M@@K_X\simeq\OO_X@@`）的光滑投影复三维流上，作者对一切足够大的体积参数构造出中心荷精确等于普通与平方根 Todd 大体积荷的数值 Bridgeland 稳定性条件，且一个阈值统管实扭曲与丰富方向的一个开集；另在任意三维流上证明了一致强倾斜不等式。

## 问题背景
Bridgeland 稳定性条件由中心荷与切片给出，用来给导出范畴的对象排序。物理上的大体积极限预言：体积参数 `@@M@@t\to\infty@@` 时中心荷应趋于陈特征的指数式 `@@M@@-\int_Xe^{-B-itH}\ch(E)\Theta@@`（`@@M@@\Theta=1@@` 或 `@@M@@\sqrt{\td(X)}@@`）。所谓指定荷问题（prescribed-charge problem）问：这些特定表达式是否配有相容的心（heart）、有限的半稳定滤波与支撑界？Bayer 的多项式稳定性条件只在渐近意义下排序相位；要在每个有限体积处得到真正的 Bridgeland 条件，还得管住荷的核——皮卡秩大于一时，完整数值 Grothendieck 群（numerical Grothendieck group）里含有沿单一极化看不见的类。三维流的最大障碍在第三陈特征：它不进入经典 Bogomolov–Gieseker 不等式，Bayer–Macrì–Toda 为此提出双倾斜（double tilt）构造与第三陈特征不等式猜想；Bernardara–Macrì–Schmidt–Zhao 进而问是否存在带曲线类修正的版本，而无修正版本已被 Schmidt 等人的反例否定。一般三维流上稳定性条件的存在性近来由 Li 及 Li–Liu–Liu–Macrì–Perry–Stellari–Zhao 的框架解决，Cheng 亦证得全数值支撑；"精确指定中心荷"此前仍属空白。

## 主要结果
定理一（实扇形上的精确大体积荷）：设 `@@M@@X@@` 光滑投影复三维流且 `@@M@@K_X\simeq\OO_X@@`。对任意实除子类 `@@M@@B_*@@` 与丰富类 `@@M@@H_*@@`，存在邻域 `@@M@@V\ni B_*@@`、`@@M@@W\ni H_*@@` 与同一个阈值 `@@M@@T>0@@`，使所有 `@@M@@B\in V@@`、`@@M@@H\in W@@`、`@@M@@t\ge T@@` 同时满足：(i) 普通物理荷 `@@M@@Z_{B,tH}(E)=-\ch_3^B(E)+\tfrac{t^2}{2}H^2\ch_1^B(E)+i\bigl(tH\ch_2^B(E)-\tfrac{t^3}{6}H^3\ch_0(E)\bigr)@@` 配上标准双倾斜心 `@@M@@\mathcal A_{B,tH}@@`，构成几何（点层稳定）数值稳定性条件；(ii) 存在几何数值稳定性条件，其荷恰为 `@@M@@Z^{\mathrm{LV}}_{B,tH}(E)=-\int_Xe^{-B-itH}\ch(E)\sqrt{\td(X)}@@`，其中 `@@M@@\sqrt{\td(X)}=1+c_2(X)/24@@`。两例都在完整 `@@M@@\Knum(X)_\R@@` 上满足支撑性质（support property）。假设只需要 `@@M@@K_X@@` 平凡，不需要严格 Calabi–Yau 的额外消没。
定理二（一致强不等式，任意三维流）：对每个光滑投影复三维流、整极化 `@@M@@H@@` 与有理类 `@@M@@B_0@@`，存在仅依赖 `@@M@@(X,H,B_0)@@` 的 `@@M@@k\in\Q_{\ge0}@@` 与 `@@M@@R_*>0@@`，使每个零斜率、有限斜率的 `@@M@@\nu_{a,b}@@`-半稳定对象满足 `@@M@@\ch_3^{B_0+bH}(E)\le\bigl(\tfrac{a^2}{6}+k\bigr)H^2\ch_1^{B_0+bH}(E)@@` 对一切 `@@M@@a>0@@`、`@@M@@b\in\R@@`；且 `@@M@@a>R_*@@` 时更强的无修正界成立。这正面回答了上述修正不等式问题。推论给出抛物区域 `@@M@@\alpha>(\beta^2+R_*^2)/2@@` 上的二次型不等式 `@@M@@Q_{\alpha,\beta}(v_H(E))\ge0@@`。

## 证明思路
全文有两条相互独立的论证线。

第一线是范畴构造，先在环境空间上做。作者选取张成 `@@M@@N^1(X)_\R@@` 的极丰富线丛，把 `@@M@@X@@` 嵌入射影空间之积 `@@M@@Y=\prod_h\mathbb P^{d_h}@@`；三维时除子类的乘积张成完整数值群，故 `@@M@@i_*@@` 在数值群上单射——环境支撑便能控制 `@@M@@X@@` 的每个数值类。再在 `@@M@@Y@@` 上借用椭圆曲线积与有限商构造稳定性条件（Liu 的配曲线乘积、Li 等的支撑归纳、Cheng 的两块构造），关键是在按 `@@M@@(Rs_h)^{d_h-j_h}@@` 缩放的坐标下支撑常数与体积 `@@M@@R@@` 无关，而指数荷的任何固定正余维修正都随 `@@M@@R\to\infty@@` 衰减为零。于是用固定多项式因子 `@@M@@\gamma=\td(Y)(1-\delta/12)@@` 或 `@@M@@\td(Y)(1-\delta/24)@@`（`@@M@@\delta@@` 提升 `@@M@@c_2(X)@@`）修正环境荷：Grothendieck–Riemann–Roch 保证限制到 `@@M@@X@@` 后恰好得到指定的两种荷；缩放支撑配合变形估计 `@@M@@\|(U_t^{B,H}-U_t)\circ M_t^{-1}\|\le C_1\eta+C_2t^{-1}@@`，让 Bayer 变形定理沿直线路径整体提升，一个阈值 `@@M@@T@@` 覆盖整个开扇形。最后经有限映射限制准则（线丛扭曲的 Bayer 性质、点层本原类配合开邻域论证升级为稳定）把切片拉回 `@@M@@X@@`。普通荷的心还需逐层识别：先在光滑曲面截口上用诱导荷的虚部认出倾斜心，再用正权截口夹出严格斜率界，把构造出的心安放在第一倾斜的相邻平移之间，最后在实轴边界区分第二倾斜的正斜率与零斜率，证得 `@@M@@\mathcal P(0,1]=\mathcal A_{B,tH}@@`。

第二线是纯数值论证，证明定理二，全程不用 `@@M@@K_X@@` 的假设。力量集中在一个固定体积 `@@M@@A@@` 处：对零斜率半稳定对象证明顶点估计 `@@M@@z_B(E)-\tfrac{A^2}{6}d_B(E)\le C\bigl(d_B(E)-A|r(E)|\bigr)@@`，右端度量与判别式等式的距离且不带任何秩项——这对 `@@M@@e=d_B-A|r|=0@@` 的大秩对象也必须成立。先截断斜率滤波，把斜率落在 `@@M@@[b+A,b+A+1]@@` 窄带的尾部从余部剥离，余部的秩与前两个交度均为 `@@M@@O(e)@@`；余部上同调由 Langer 限制不等式、Hermite–Einstein 理论与 Bochner 恒等式配合 Cwikel–Lieb–Rozenblum 型谱估计控制。再把有限个层与映射约化到特征 `@@M@@p@@`，用 `@@M@@\ch_i(F^*E)=p^i\ch_i(E)@@` 与 Riemann–Roch 极限 `@@M@@\lim_{p\to\infty}p^{-3}\chi(F^*E\otimes L_p)=h\,z_B(E)@@`，使依赖具体对象的误差在除以 `@@M@@p^3@@` 后消失，窄带贡献恰给出系数 `@@M@@A^2/6@@`。最后是墙传输（wall transport）：沿零斜率双曲线支 `@@M@@d(a)=\sqrt{\Delta+a^2r^2}@@` 有微分不等式 `@@M@@D_a'=-\tfrac a3S_a@@`，三个比较函数保证严格违例朝向或背离顶点传播；遇墙则换成仍违例的稳定因子，离散判别式 `@@M@@\Delta\in N^{-1}\Z@@` 每次严格下降，过程必然有限。由此得全体积修正界与 `@@M@@a>R_0=A+3C/A@@` 处的无修正尾部。该步骤技术细节（特征 `@@M@@p@@` 中的谱估计与伸缩求和）此处从略。

## 可信度与备注
本文与姊妹篇（同族中证明五次超曲面 Toda Gepner 猜想一文）共享三维流双倾斜稳定性这一框架：姊妹篇在五次超曲面上借 Xu 的更强 BG 不等式实现 `@@M@@2/5@@` 相位对称，本文则自给一致强倾斜不等式并把大体积构造推进到一切平凡典则丛三维流。两文主结果均无 Lean 形式化证明；本文另含与 Schmidt、Martinez–Schmidt 反例的定量对照。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
