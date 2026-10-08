---
layout: default
title: "The periodic spin-one Haldane gap"
family: "268"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The periodic spin-one Haldane gap

> 结果族 268：The spin-one Haldane gap　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把一串小磁铁珠连成首尾相接的圆环，相邻磁铁彼此"较劲"（反铁磁）。想把环从最安稳的状态扰动一下，得迈过一道能量门槛。Haldane 在 1983 年猜：自旋为整数的长环，这道门槛不会随环变长而塌到零。本文首次对纯自旋 1 模型完整证明了这个悬置四十多年的猜想。

**关键词卡片**

- 海森堡链（Heisenberg chain）：相邻自旋两两耦合的一维磁体模型
- 反铁磁（antiferromagnetic）：相邻自旋倾向反向排列的耦合方式
- 自旋（spin）：粒子的内禀磁性；这里每颗取整数 1
- 谱隙（spectral gap）：基态与上一能级的能量差，正的隙就是那道门槛
- 配分函数（partition function）：把一切能量按统计权重加起来的总和，本文证明的枢纽

**看个具体例子**

环长 L=2304 时，定理给出谱隙 γ_L>log20/784≈0.0038，且对一切更长的偶数环同样成立，基态还唯一。数值物理约 0.41——定理的 0.0038 小得多，但它的价值在于"对任意长度一致为正且完全显式"。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<circle cx="140" cy="150" r="72" fill="none" stroke="#999" stroke-width="2" stroke-dasharray="6 5"/>
<circle cx="212" cy="150" r="6" fill="#333"/>
<circle cx="198" cy="108" r="6" fill="#333"/>
<circle cx="162" cy="82" r="6" fill="#333"/>
<circle cx="118" cy="82" r="6" fill="#333"/>
<circle cx="82" cy="108" r="6" fill="#333"/>
<circle cx="68" cy="150" r="6" fill="#333"/>
<circle cx="82" cy="192" r="6" fill="#333"/>
<circle cx="118" cy="218" r="6" fill="#333"/>
<circle cx="162" cy="218" r="6" fill="#333"/>
<circle cx="198" cy="192" r="6" fill="#333"/>
<line x1="212" y1="150" x2="230" y2="150" stroke="#c0392b" stroke-width="2.5"/>
<line x1="198" y1="108" x2="184" y2="118" stroke="#333" stroke-width="2.5"/>
<line x1="162" y1="82" x2="168" y2="65" stroke="#c0392b" stroke-width="2.5"/>
<line x1="118" y1="82" x2="124" y2="99" stroke="#333" stroke-width="2.5"/>
<line x1="82" y1="108" x2="67" y2="97" stroke="#c0392b" stroke-width="2.5"/>
<line x1="68" y1="150" x2="86" y2="150" stroke="#333" stroke-width="2.5"/>
<line x1="82" y1="192" x2="67" y2="203" stroke="#c0392b" stroke-width="2.5"/>
<line x1="118" y1="218" x2="124" y2="201" stroke="#333" stroke-width="2.5"/>
<line x1="162" y1="218" x2="168" y2="235" stroke="#c0392b" stroke-width="2.5"/>
<line x1="198" y1="192" x2="184" y2="182" stroke="#333" stroke-width="2.5"/>
<text x="46" y="260" font-size="14" fill="#333">自旋 1 反铁磁环：相邻箭头交替</text>
<line x1="330" y1="120" x2="540" y2="120" stroke="#333" stroke-width="2.5"/>
<line x1="330" y1="220" x2="540" y2="220" stroke="#333" stroke-width="2.5"/>
<line x1="500" y1="120" x2="500" y2="220" stroke="#c0392b" stroke-width="2"/>
<polygon points="496,128 504,128 500,120" fill="#c0392b"/>
<polygon points="496,212 504,212 500,220" fill="#c0392b"/>
<text x="330" y="108" font-size="14" fill="#333">激发态 E₁</text>
<text x="330" y="242" font-size="14" fill="#333">基态 E₀（唯一）</text>
<text x="334" y="168" font-size="13" fill="#c0392b">谱隙 γ_L ≥ log20/784</text>
<text x="334" y="188" font-size="13" fill="#c0392b">≈ 0.0038，与 L 无关</text>
</svg>

</div>

**为什么值得关心**

整数与半整数自旋的一维磁体低温行为截然不同，这是量子磁性最基本的分野。半整数一侧早有严格的无隙定理，整数一侧却始终缺一块拼图；如今纯模型上的猜想成为定理，两种行为同框对比终成完整的数学事实。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了纯反铁磁自旋 1 海森堡链的偶周期 Haldane 猜想：偶数 `@@M@@L\ge60@@` 时基态唯一，谱隙有与长度无关的显式正下界，无穷体积隙 `@@M@@\Delta_1\ge\log(20)/784>0@@`。这一悬置四十余年的猜想首次在纯双线性模型上获得完整数学证明。

## 问题背景

1983 年 Haldane 猜想：一维反铁磁海森堡链（Heisenberg chain）的低能行为由自旋是否为整数决定——半奇整数自旋无隙，整数自旋有正的谱隙 (spectral gap)。半奇整数一侧早有 Lieb–Schultz–Mattis 与 Affleck–Lieb 的严格无隙定理；整数一侧却始终缺少对具体相互作用的证明。AKLT 模型在双线性项之外加入双二次项后可证有隙，Yarotsky 的稳定性定理只覆盖 AKLT 点的小邻域，延伸不到纯双线性哈密顿量 `@@M@@H_L=\sum_j\mathbf S_j\cdot\mathbf S_{j+1}@@`；而纯模型既非 frustration-free 又无可解结构，常用有限尺寸判据全部失效。数值与实验证据却很充分：White–Huse 的 DMRG 估计体隙约 `@@M@@0.4105@@`，准一维材料 CsNiCl`@@M@@_3@@` 的中子散射也支持有隙。严格证明因此成为数学物理的著名悬案。

## 主要结果

主定理：对偶数 `@@M@@L\ge60@@` 的周期环，基态唯一；记 `@@M@@\gamma_L=E_1(L)-E_0(L)@@`（`@@M@@E_1@@` 为下一个不同能量），则

`@@M@@D\gamma_L>\frac4{105}\log\frac{80}{79}\quad(L\ge60),\qquad \gamma_L>\frac{\log20}{784}\quad(L\ge2304).@@`

因此 `@@M@@\Delta_1=\liminf_{L\to\infty,\ L\text{ 偶}}\gamma_L\ge\log(20)/784\approx0.0038>0@@`——下界数值远小于物理值 `@@M@@0.41@@`，但一致为正且完全显式。谱结论对任何满足同样对易关系与 Casimir 规范的自旋 1 矩阵实现同样成立。推论进一步给出：周期基态的任何子列局部极限态 `@@M@@\omega@@` 都满足带隙 `@@M@@\log(20)/784@@` 的局域激发不等式 `@@M@@\omega(A^*[H,A])\ge\gamma\,(\omega(A^*A)-|\omega(A)|^2)@@`。

## 证明思路

全文枢纽是把同一个平移配分函数 (partition function) `@@M@@Z_n(b)=\Tr e^{-b(H_n+anI)}@@` 读两遍。物理读法：它是 Gibbs 权重之和；空间读法：用 Aizenman–Nachtergaele 型有序键展开构造紧自伴的空间迁移算子 (spatial transfer operator) `@@M@@X_b@@`，使 `@@M@@Z_n(b)=\sum_i\lambda_i(b)^n@@`。偶数 `@@M@@n@@` 时右端是 `@@M@@|\lambda_i|^n@@` 的非负和，于是同一配分函数导出两个概率分布，其纯度 (purity) 分别为 `@@M@@S(n,b)=Z_{2n}(b)/Z_n(b)^2@@`（空间）与 `@@M@@T(n,b)=Z_n(2b)/Z_n(b)^2@@`（物理）。核心引理：把权重平方再归一，纯度亏损从 `@@M@@u@@` 二次收缩到 `@@M@@f(u)=u^2/[2(1-u)^2]@@`；而平方空间权重恰等于长度加倍，平方物理权重恰等于温度倒数加倍，两条配分函数相消恒等式把两股力量耦合成递推，使两个亏损沿 `@@M@@(n,b)\mapsto(2n,2b)@@` 以双指数速度衰减。再用矩的插值不等式填满每个二进区间内部的全部偶数长度。最后回到物理谱：最大 Gibbs 权重超过 `@@M@@1/2@@` 迫使基态唯一；激发与基态权重之比被 `@@M@@r^{2^j}@@` 压住，取对数即得一致隙 `@@M@@\gamma_L>\log(1/r)/b_0@@`。

种子是两个有限初始化：`@@M@@(n_0,b_0)=(60,105/4)@@`（亏损 `@@M@@1/8@@`）与 `@@M@@(2304,784)@@`（亏损 `@@M@@1/100@@`，后者由 `@@M@@(36,49/4)@@` 出发经六次舍入更新到达）。有限输入全部是可复现的有理算术：其一，长度 4–12 的短链在恒等、`@@M@@P@@` 扭曲与循环旋转三种边界条件下的配分函数区间封闭，附录以条件化 Poisson 多项式与 Fox–Glynn 型估计控制矩阵指数迹；其二，周期矩阵积态 (matrix-product state) 变分向量给出 `@@M@@E_0(72)+72a<0@@`、`@@M@@E_0(120)+120a<0@@`，保证单个 Boltzmann 因子大于 `@@M@@1@@`。利用 `@@M@@D_2@@` 扭曲的扇区分解（不变扇区之外的每个空间权重至少出现两次或三次）与"多项式过滤器"（以非负多项式的矩和压制特征值模），即可锁定唯一主导空间特征值，凑齐两个种子所需的纯度。全程没有以任何浮点特征值估计为前提。

## 可信度与备注

本文与姊妹篇同属 OpenAI 的数学成果，主结果暂无 Lean 形式化证明；按 OpenAI 官方声明"未经形式化的结果可能有问题"，宜以社区核验为准。有限计算均为显式有理不等式，附录给出全部数据与可复现流程；姊妹篇（边界场开链）直接调用本文中段的空间谱信息而非仅最终隙，两文相互咬合，共同支撑自旋 1 Haldane 猜想的两种边界形式。

{% endraw %}
