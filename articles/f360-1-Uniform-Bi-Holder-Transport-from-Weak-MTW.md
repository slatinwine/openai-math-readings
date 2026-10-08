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

## 入门导读 🐣

想象你开一家搬沙公司：把一堆沙重新堆成指定的形状，运费按"搬运距离的平方"计价，最省钱的方案就叫最优输运。这篇论文研究的是：在一个弯曲的空间里，最省钱的搬法会不会把相邻的两粒沙甩到天各一方？作者证明：只要空间弯曲得足够"温和"（满足一个很弱的曲率条件），相邻的沙搬完仍然相邻，而且这个保证对一整类沙堆统一成立。

**关键词卡片**

- 最优输运（optimal transport）：把一堆分布搬运成另一堆、使总费用最小的方案。
- 弱 MTW 条件（weak Ma–Trudinger–Wang condition）：弯曲空间上一种"搬运友好"的曲率条件，能防止最优方案折叠撕裂。
- Hölder 连续（Hölder continuity）：距离缩小若干倍，像的距离也按固定幂次缩小的温和连续性。
- 一致估计（uniform estimate）：连续性常数对上下有界的整类密度统一有效，不挑具体哪两堆沙。
- 共轭割点（conjugate cut point）：弯曲空间里多条最短路径汇合的奇异地点，以往的理论在此失效，本文允许它出现。

**看个具体例子**

把主定理代入数字：在满足弱 MTW 的曲面上，任取密度都介于 λ 与 Λ 之间的两堆沙，最优搬运图 T 的正反两个方向都满足 `@@M@@d(T(x),T(x'))\le C\,d(x,x')^{\alpha}@@`，常数 C 与指数 α 只依赖空间和 λ、Λ。比如若 `@@M@@\alpha=1/2@@`：两点相距 `@@M@@0.0001@@`，搬完至多相距 `@@M@@C\times 0.01@@`——近处的沙不会被甩飞。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><ellipse cx="150" cy="120" rx="115" ry="80" fill="none" stroke="#333" stroke-width="2"/><text x="150" y="232" font-size="16" text-anchor="middle" fill="#333">弯曲空间 M（弱 MTW）</text><circle cx="125" cy="115" r="4" fill="#333"/><text x="108" y="106" font-size="15" fill="#333">x</text><circle cx="147" cy="130" r="4" fill="#333"/><text x="156" y="148" font-size="15" fill="#333">x′</text><line x1="125" y1="115" x2="147" y2="130" stroke="#333" stroke-width="1.5"/><line x1="133" y1="118" x2="392" y2="89" stroke="#888" stroke-width="1.5"/><polygon points="392,89 381,94 380,86" fill="#888"/><line x1="152" y1="134" x2="408" y2="107" stroke="#888" stroke-width="1.5"/><polygon points="408,107 397,112 396,104" fill="#888"/><text x="265" y="72" font-size="15" fill="#555">最优搬运 T</text><circle cx="402" cy="86" r="4" fill="#333"/><text x="388" y="74" font-size="15" fill="#333">T(x)</text><circle cx="420" cy="104" r="4" fill="#333"/><text x="432" y="118" font-size="15" fill="#333">T(x′)</text><text x="100" y="262" font-size="15" fill="#333">像点依然贴近：d(Tx,Tx′) ≤ C·d(x,x′)^α</text></svg>

</div>

**为什么值得关心**

它把"什么样的弯曲空间上最优输运一定连续"这个问题钉死为弱 MTW 条件：弱 MTW 与输运连续性等价，而且正方向还是对整类密度一致的定量版本，连共轭割点都不再是障碍。

> 已 Lean 形式化

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
