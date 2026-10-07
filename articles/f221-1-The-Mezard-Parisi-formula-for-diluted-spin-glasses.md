---
layout: default
title: "The Mézard–Parisi formula for diluted spin glasses"
family: "221"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Mézard–Parisi formula for diluted spin glasses

> 结果族 221：The Mézard–Parisi formula for diluted spin glasses　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明了稀释自旋玻璃的 Mézard–Parisi 层级空腔变分公式：极限压强恰等于有限层级试探泛函在一切深度与试探律上的下确界，解决了 Panchenko–Talagrand（2004）提出的取等猜想，且仅要求相互作用与外场的一阶矩。

## 问题背景

稀释自旋玻璃（diluted spin glass）指每个自旋平均只参与有限个相互作用的无序系统：即使系统趋于无穷，自旋的局部环境仍是随机的，空腔方法（cavity method）用"局部场分布"来描述它。当大量竞争态共同主导配分函数（partition function）时，Mézard 与 Parisi（2001）为固定连通度的 Bethe 格点自旋玻璃提出层级空腔图像，其提议的序参量是局部场分布逐层再取分布所成的层级（hierarchy）。热力学核心问题是：该层级是否完全决定期望对数配分函数每自旋的极限值，即文中定义的压强（pressure）？对经典的 Viana–Bray 模型（1985），Franz–Leone（2003）把 Guerra 插值法（interpolation method）移植到稀释系统，得到复制对称与一步破缺的压强上界；Panchenko–Talagrand（2004）随后证得任意有限层级的上界。此后二十余年，"这些上界的下确界是否就等于真实压强"这一变分取等猜想（紧随其定理 4 陈述）悬而未决。障碍在于：从同一 Gibbs 系统抽取多个副本（replica）时，各副本自旋模式的概率涉及自旋任意子集乘积的空间平均，即多重复叠（multioverlap），仅靠两两交叠无法控制。

## 主要结果

固定偶数 `@@M@@p\ge2@@` 与密度 `@@M@@\alpha>0@@`。相互作用数 `@@M@@M_N\sim\Pois(\alpha N)@@`，每个作用独立、有放回地抽取 `@@M@@p@@` 个均匀位置并放置随机函数 `@@M@@\theta_k@@`，再加独立外场：

`@@M@@D-H_N(\sigma)=\sum_{k=1}^{M_N}\theta_k(\sigma_{i_{1,k}},\ldots,\sigma_{i_{p,k}})+\sum_{i=1}^N h_i\sigma_i,\qquad F_N=\frac1N\E\log\sum_{\sigma}e^{-H_N(\sigma)}.@@`

假设相互作用律满足 Panchenko–Talagrand 因式分解 `@@M@@e^{\theta(s)}=a\,(1+b\prod_{\ell=1}^p f_\ell(s_\ell))@@`（且 `@@M@@|b\prod_\ell f_\ell(s_\ell)|<1@@` 几乎必然）与正性条件 `@@M@@\E[(-b)^n]\ge0@@`（`@@M@@n\ge1@@`），并只要求一阶矩 `@@M@@\E B(\theta)+\E|h|<\infty@@`，其中 `@@M@@B(\theta)=\max_s|\theta(s)|@@`。

主定理断言热力学极限存在，且
`@@M@@D\lim_{N\to\infty}F_N=\inf_{r\ge0}\Phi_r,@@`
右端是对一切有限深度 `@@M@@r@@` 的层级试探律（根律 `@@M@@\zeta@@` 与指数 `@@M@@0<m_1<\cdots<m_r<1@@`）取下确界的幂均（power mean）泛函 `@@M@@\cB_r(\zeta,\mathbf m)=\log2+\E\log T_0V_{\rm s}-\alpha(p-1)\E\log T_0V_{\rm e}@@`。这里消息（message）是单个自旋上的概率分布：点项 `@@M@@V_{\rm s}@@` 把一个新自旋连同其 `@@M@@\Pois(\alpha p)@@` 条关联作用插入消息环境；边项 `@@M@@V_{\rm e}@@` 修正插入中重复计数的作用；`@@M@@T_0@@` 是沿层级逐层取幂均的算子。定理不假设下确界可取得，也不需要构造无穷深度的极限 Gibbs 态。

推论覆盖三类模型：Viana–Bray 模型（`@@M@@p=2@@`）及对称耦合的稀释偶自旋模型在一切正温的公式；加权软随机偶-`@@M@@K@@` 可满足性问题（soft random even-`@@M@@K@@` SAT，含单位权重情形）；以及零温极限——基态能量 `@@M@@g=\lim_N\frac1N\E\max_\sigma\mathcal E_N(\sigma)@@` 存在，且 `@@M@@g=\lim_{\beta\to\infty}\frac1\beta\inf_{r,\zeta,\mathbf m}\cB_{r,\beta}@@`，对单位权重 SAT，`@@M@@-g@@` 即每变量最少违反子句数的极限。

## 证明思路

上界是 Guerra–Franz–Leone–Panchenko–Talagrand 插值框架的推广：在参数 `@@M@@t@@` 处保留均值 `@@M@@t\alpha N@@` 的真实相互作用，并给每个格点配上均值 `@@M@@(1-t)\alpha p@@` 的独立空腔作用；对幂均递归后的期望根对数 `@@M@@\varphi(t)@@` 有 `@@M@@\varphi(1)=F_N@@`、`@@M@@\varphi(0)=\log2+\E\log T_0V_{\rm s}@@`。Poisson 微分把 `@@M@@\varphi'(t)@@` 写成一个真实作用的插入增量减去 `@@M@@p@@` 个空腔作用的插入增量；将增量按 `@@M@@\log(1+\lambda D)@@` 展开，其 `@@M@@n@@` 阶系数含因子 `@@M@@-\frac{\lambda^n}{n}\E[(-b)^n]@@` 与 `@@M@@P_{\cT}^p-pP_{\cT}B_{\cT}^{p-1}+(p-1)B_{\cT}^p@@`，后者由 `@@M@@x\mapsto x^p@@`（`@@M@@p@@` 为偶数）的凸性非负，前者由正性条件非负，故各阶系数非正、`@@M@@\varphi'(t)\le0@@`，积分即得上界。文中先做去乘子 `@@M@@a@@` 的归一化，配合 `@@M@@\lambda\uparrow1@@` 的正则化与控制收敛，完全不要求 `@@M@@\log a@@` 可积，从而把上界推广到一阶矩情形。

下界按 Aizenman–Sims–Starr 空腔比较方案分四步。第一步选水库（reservoir）：用一个公共 `@@M@@N@@` 自旋系统比较尺寸 `@@M@@N@@` 与 `@@M@@N+1@@`，并添加总数 `@@M@@\Pois(N^{3/4})@@`、取值于 `@@M@@[1/2,3/2]@@` 的有界 Poisson 扰动因子；它们对总压强的影响只有 `@@M@@o(1)@@`，却换来全部扰动得分的集中。Poisson 分裂给出增量恒等式 `@@M@@\Delta_N=\log2+\E\log Y_{0,\rm s}-\E\log Y_{0,\rm b}+o(1)@@`（点插入带 `@@M@@\Pois(\alpha p)@@` 条作用、键插入带 `@@M@@\Pois(\alpha(p-1))@@` 条），再选定使增量逼近压强下极限的尺寸与扰动参数。第二步用有限概率树的符号演算把插入量展开为新增副本路径上的带符号和；独立扰动标记可挑出任意预定的分支模式，得分集中便给出这些和的恒等式。第三步最关键：集中全部多重复叠。做法是先把目标树的每个内部分支深度整体推迟一层，每层第一次新鲜分裂恰好提供与归一化系数同阶的小因子，而系数绝对值之和的相对界保证相除后误差仍受控；再对副本数归纳地证明条件协方差衰减，并用第二个恒等式集中剩余的条件均值。妙处在于这些估计只需"对分支深度取平均"成立，而插入展开本身恰是对有限树取平均，例外树在展开中的概率趋于零，故无需对深度做一致集中。第四步把均匀选定的水库格点的整棵有限层级用逐级条件分布编码为一条消息过程；多重复叠集中使不同格点标号可换成该过程的独立副本，空腔插入于是收回到独立的层级消息，产出逼近所选增量的可采纳试探值。值得注意，下界论证只用到相互作用律有界且关于输入置换不变，不需要因式分解与正性；最后经归一化与一致的估计去有界化，即得定理的一阶矩版本。

## 可信度与备注

本文主结果标注为暂无形式化证明，OpenAI 官方亦声明"未经形式化的结果可能有问题"，请以社区核验为准。上界一侧继承 Panchenko–Talagrand 的既有插值框架并作一阶矩推广，基础扎实；下界的新技术——"延迟分支深度 + 按深度平均的多重复叠集中"——是全文核心，最值得审读。族内互补明显：文末备注指出偶数元假设排除了随机 3-SAT，配套论文对该模型用另一套试探泛函（符号索引消息对，不必构成概率分布）给出精确软压强公式，两篇并读可看清该方法的能力边界。

{% endraw %}
