---
layout: default
title: "Global Support and Convex Injectivity Domains under Weak MTW"
family: "360"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Global Support and Convex Injectivity Domains under Weak MTW

> 结果族 360：Weak MTW curvature gives convexity and regular optimal transport　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

在紧致无边的连通黎曼流形上，弱 MTW 曲率条件本身就迫使每点的切单射域凸，从而在不假设非聚焦的前提下解决 Villani 猜想；同时证明任意势函数的次梯度都自带全局支撑山峰，为一致正则输运奠定几何基础。

## 问题背景

最优输运（optimal transport）研究如何以最小代价把一个概率分布搬运到另一个。当代价取紧黎曼流形上的平方测地距离 `@@M@@c(x,y)=d(x,y)^2/2@@` 时，输运映射的连续性严重依赖代价几何：距离函数在割迹（cut locus）处失去光滑。Ma–Trudinger–Wang 曲率条件正是为控制这种几何而生，其退化形式"弱 MTW"（又称 A3w）只要求代价在正交方向上的四阶交叉导数非负。Villani 猜想：弱 MTW 应蕴含每个切单射域（tangent injectivity domain）`@@M@@I(x)@@` 的凸性——这是支撑山峰方法成立的关键前提。此前 Loeper–Villani 在强 MTW 加非聚焦（nonfocality）下、Figalli–Gallouët–Rifford 在一般非聚焦下证明了该蕴含；共轭割点（conjugate cut point）情形始终是障碍：那里代价可能不光滑，而弱 MTW 只控制垂直于速度线段的方向，两个困难都无法靠在定义域之外延拓光滑凹性来绕过。

## 主要结果

论文证明两个定理。**定理一（单射域凸性）**：设 `@@M@@(M,g)@@` 为维数 `@@M@@n\geq2@@` 的光滑连通紧致无边界黎曼流形且满足弱 MTW，则对每点 `@@M@@x@@`，切单射域 `@@M@@I(x)@@`——测地线越过时刻 1 仍保持极小的初速度构成的开集——是凸的；闭极小域 `@@M@@G_x@@` 同样凸。结论是普通线性凸性，不需要非聚焦、严格 MTW、非正交方向的曲率条件或先验凸性，共轭割点被允许。**定理二（全局支撑与中间几何）**：对任意由连续数据定义的势函数（potential）`@@M@@u(x)=\max_y\{-c(x,y)-v(y)\}@@`，每个普通次梯度（subdifferential）`@@M@@p\in\partial u(x)@@` 都是极小速度，即 `@@M@@p\in G_x@@`，且满足全局支撑不等式 `@@M@@u(x')\geq u(x)+c(x,\exp_xp)-c(x',\exp_xp)@@`；对每个 `@@M@@0<t<1@@`，投影 `@@M@@F_t(x,p)=\exp_x(tp)@@` 是次梯度图到 `@@M@@M@@` 的同胚（homeomorphism）；提升间隙截面 `@@M@@\mathcal S_x(r)@@` 紧且凸，直径平方不超过 `@@M@@8(r+\operatorname{osc}v)@@`；中间势 `@@M@@Q_tu=-Q_{1-t}v@@` 具有只依赖流形与时刻 `@@M@@t@@` 的 `@@M@@C^{1,1}@@` 界与极点 Lipschitz 控制。全部结论不使用任何密度假设。

## 证明思路

证明把"支撑山峰"（supporting mountain）原则推过割迹，分三步。**第一步**建立无聚焦假设下的工具箱：在非共轭速度处定义光滑测地分支的分支 Hessian（branch Hessian）`@@M@@A_x(w)@@`，证明径向恒等式 `@@M@@A_x(w)w=w@@`、严格径向比较 `@@M@@A_x(sa)>\frac{s}{s'}A_x(s'a)@@`，并把弱 MTW 转化为横向凹性——沿速度线段 `@@M@@b_t@@`，当 `@@M@@\xi@@` 垂直于线段方向时 `@@M@@A_x(b_t)(\xi,\xi)@@` 是凹函数。**第二步**排除共轭性：设 `@@M@@[b_0,b_1]\subset G_x@@` 两端非共轭而内点 `@@M@@z@@` 共轭，先用指数映射的核向量构造两端为零的 Jacobi 场（Jacobi field），平行输运成试验场族，得 `@@M@@A_x(a)(\xi,\xi)\leq C_0-c_0/P(a)@@`，其中指标型（index form）`@@M@@P(a)@@` 在 `@@M@@a\to z@@` 时趋于零，Hessian 随之崩向 `@@M@@-\infty@@`；横向凹性迫使共轭核落入线段方向 `@@M@@e@@`，径向恒等式又给出方向 `@@M@@e@@` 上的下界 `@@M@@A_x(r(z+te))(e,e)\geq 1-C_2/t@@`，与径向收缩 `@@M@@r=1-t^2@@` 时的上界 `@@M@@C_1-c_1/(t^2+1-r)@@` 在 `@@M@@t\downarrow0@@` 时不相容。**第三步**是延拓论证：把次梯度图随时间 `@@M@@t@@` 放大，取首次触割时刻 `@@M@@t_*@@`；极小凸包经取极限仍极小，第二步的推论使其整体非共轭；局部单射引理再排除两个图点撞到同一像的情形——一阶不等式把正权积极小速度逼入垂直于碰撞方向的仿射超平面，线性项在除以碰撞距离平方之前于有限阶段被精确抵消，弱 MTW 与径向严格比较联立给出正二次间隙而矛盾；随后由区域不变性（invariance of domain）与"和短时同胚同伦的覆叠映射必单叶"的拓扑事实，把局部单射升级为整体同胚，再由"捕获每个极小对数"引理逼出与首次失败矛盾，故任何图向量在时间 1 之前都碰不到割。最后令 `@@M@@t\uparrow1@@` 取闭包极限得全局支撑；把它应用于两座山峰的极大值即得 `@@M@@G_x@@` 凸，进而 `@@M@@I(x)=\operatorname{int}G_x@@` 凸；截面凸性、直径界与 `@@M@@C^{1,1}@@` 中间正则性由分裂支撑、逆向测地流与双侧支架给出。

## 可信度与备注

论文声明主结果已有 Lean 形式化证明。本文是结果族 360 的几何基石：姊妹篇《Uniform Bi-Hölder Transport from Weak MTW》把本文的全部密度无关结论作为输入，两文合成"弱 MTW `@@M@@\Rightarrow@@` 凸单射域 `@@M@@\Rightarrow@@` 一致正则输运"的完整链条，补上了 Figalli–Rifford–Villani 当年需额外假设凸单射域才能得到的全局支撑原则。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，附录中的度数理论替代论证是可选路线，不影响主证明。

{% endraw %}
