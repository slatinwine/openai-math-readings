---
layout: default
title: "Uniform Bi-Hölder Transport from Weak MTW"
family: "360"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform Bi-Hölder Transport from Weak MTW

> 结果族 360：Weak MTW curvature gives convexity and regular optimal transport　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

在固定的紧致弱 MTW 流形上，对上下有界的可测密度类，平方距离最优输运映射及其逆有一致的 Hölder 连续同胚代表，常数只依赖流形与密度界，从而证明弱 MTW 与输运连续性等价。

## 问题背景

最优输运正则性理论的一个核心问题是：在有上下界约束的密度之间，二次代价的最优映射何时连续，且常数能否对整个密度类一致？Caffarelli 在欧氏空间给出肯定答案；Figalli–Kim–McCann 等在弱 MTW（weak Ma–Trudinger–Wang condition，代价在正交方向上的四阶交叉导数非负）框架下证明了代价光滑区域内的 Hölder 估计，但当地输运图逼近共轭点对时光滑代价论证失效，一致的局部化尺度没有着落。Loeper–Villani 在严格 MTW 加非聚焦（nonfocality）下、Figalli–Kim–McCann 在球面乘积空间上得到过类一致估计；对一般固定的弱 MTW 流形，这一直是公开问题。Figalli–Rifford–Villani 在紧曲面上证明输运连续性等价于"凸单射域加弱 MTW"，并在引言中提出仅用弱 MTW 刻画该等价性的问题，本文正是对它的回答。

## 主要结果

**主定理（一致双 Hölder 输运）**：固定满足弱 MTW 的 `@@M@@n\geq2@@` 维光滑连通紧致无边界流形 `@@M@@(M,g)@@` 与 `@@M@@0<\lambda\leq\Lambda<\infty@@`，存在只依赖 `@@M@@(M,g),\lambda,\Lambda@@` 的 `@@M@@\alpha\in(0,1]@@` 与 `@@M@@C<\infty@@`，使得对每对满足 `@@M@@\lambda\leq\rho_i\leq\Lambda@@` 的可测概率密度，其几乎处处唯一的最优映射有同胚代表 `@@M@@\widetilde T@@`，且两个方向同时满足 `@@M@@d(\widetilde T(x),\widetilde T(x'))\leq Cd(x,x')^\alpha@@` 与 `@@M@@d(\widetilde T^{-1}(y),\widetilde T^{-1}(y'))\leq Cd(y,y')^\alpha@@`。常数对整个密度类通用，不依赖单个密度或其导数；共轭割点（conjugate cut point）被允许，无需非聚焦、严格 MTW、割回避或密度正则性。结合 Figalli–Rifford–Villani 的必要性定理，可得弱 MTW 与输运连续性的等价，且前向方向被加强为类一致估计。指数由反证法得到，论文不给出显式指数，也不宣称对变化度量的一致性。

## 证明思路

证明以姊妹篇的密度无关几何为地基（全局支撑、凸单射域、凸提升截面、中间 `@@M@@C^{1,1}@@` 正则性），再把整个密度类压缩成单个标量：令 `@@M@@F(r)@@` 为该类中一切对偶势 `@@M@@v@@` 在高度 `@@M@@r@@` 的截面上振荡的上确界。先证"幂归结"：若 `@@M@@F(r)\leq C_0r^\beta@@`，则截面凸性经平方范数恒等式把振荡化为截面直径的幂界，两个方向的 Hölder 估计以 `@@M@@\alpha=\frac12\min\{\beta,1\}@@` 成立，逆映射来自反向密度对。再反设 `@@M@@F@@` 无幂上界，用"对数平台"引理选出几乎持平的两个尺度 `@@M@@r\ll b\ll R@@`。对极值端点施加两种标量修正：中心模板 `@@M@@B_c@@` 与外层模板 `@@M@@B_o@@`，后者在封顶区域内强凹（`@@M@@B_o''\leq-K@@`）。把极点沿低端对数推进，外层修正的山峰竞争必在 `@@M@@\tau_b\asymp b/D@@` 处发生切换，得到一低一高两个活跃端点；由全局支撑取范数居中的对数得一致正超额 `@@M@@E(b)\geq c_0b@@`，加惩罚 `@@M@@\pi(b)@@` 后正则化泛函 `@@M@@Q_tg_b+Q_{1-t}w_{c,b}-\pi(b)@@` 在参数 `@@M@@b@@` 的内点取正的最大值，并对每个正重心表示产生参数不等式 `@@M@@B_c(s)-\sum_im_iB_o(s_i)\geq c_1@@`。几何侧由谱比较补齐：固定拼接点把 Jacobi 矩阵分解为非奇异块与半正定的破作用 Hessian，径向缩短给出一致正定增益；横向 MTW 经精确共轭恒等式变成矩阵值凸性，配合对数分离尺度的秩论证，得到重心构造下中心与外侧指数映射 Jacobi 行列式的比较 `@@M@@\sigma_x(p)\geq c\,\sigma_x(p_i)@@`。最后在正则化最大值处做两阶段极限：先用半凸极大值原理与零集剔除，使中心点落入原始输运 Jacobian 方程成立的满测度集；极点矩阵恒等式把下 Taylor jet 传到活跃端点，接触体积比较与黏性行列式界控制两端行列式，而外层强凹经斜投影给出行列式增益 `@@M@@\det V_i\geq cK\det V@@`；与谱比较及径向行列式比较联立得 `@@M@@cK\sigma_x(p)\leq C'\sigma_x(p)@@`，其中 `@@M@@\sigma_x(p)>0@@`，于是 `@@M@@K@@` 被先于它固定的常数封顶，取大 `@@M@@K@@` 即矛盾。

## 可信度与备注

论文声明主定理已有 Lean 形式化证明。全部几何输入引自族内姊妹篇《Global Support and Convex Injectivity Domains under Weak MTW》（亦已形式化），两文构成"弱 MTW `@@M@@\Rightarrow@@` 凸性 `@@M@@\Rightarrow@@` 一致正则性"的闭环。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文反证结构层层嵌套、取极限顺序敏感，Lean 验证因此尤为关键。证明不给出显式 Hölder 指数，也不宣称对一族变化的度量一致。

{% endraw %}
