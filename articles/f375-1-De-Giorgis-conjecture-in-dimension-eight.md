---
layout: default
title: "A positive resolution of De Giorgi's conjecture in dimension eight"
family: "375"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A positive resolution of De Giorgi's conjecture in dimension eight

> 结果族 375：De Giorgi's conjecture in dimension eight　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

油和水倒进杯子会自动分层，中间出现一条界面。现在把整个空间想象成装满"两种状态"的介质，让界面可以任意弯曲盘绕——方程确实允许很复杂的形状。1979 年 De Giorgi 猜：只要解沿某个方向始终单调（永远"一边高一边低"），界面就只能是一张平面。这篇论文在最困难的第八维证明了这个猜想。

**关键词卡片**

- Allen–Cahn 方程（Allen–Cahn equation）：描述相变的基本方程 Δu=u³−u，解在 −1 与 +1 两"相"之间过渡。
- De Giorgi 猜想（De Giorgi's conjecture）：单调的有界整体解必为"平面波"——界面是一族平行平面。
- tanh 平面波（planar wave）：一维标准解 u=tanh((e·x−c)/√2)，水平集是一族平行平面。
- 稳定解（stable solution）：对任何小扰动都不"亏能量"的解，比单调解更宽泛；论文顺带完整分类了七维稳定解。
- 临界维数（critical dimension）：八维以下刚性成立、九维出现弯曲反例的分界，与极小曲面里 Simons 锥出现的维数同源。

**看个具体例子**

标准答案长这样：u(x)=tanh(x₁/√2)。当 x₁→−∞ 时 u≈−1（一相），x₁→+∞ 时 u≈+1（另一相），过渡层宽度固定，取值 0 的水平集恰好是平面 x₁=0。定理断言：八维空间里任何单调解最终都是这种形状，只允许换方向、挪位置，不许弯、不许卷。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<line x1="50" y1="150" x2="520" y2="150" stroke="#333" stroke-width="1.5"/>
<line x1="90" y1="30" x2="90" y2="255" stroke="#333" stroke-width="1.5"/>
<line x1="50" y1="60" x2="520" y2="60" stroke="#999" stroke-dasharray="6,4"/>
<line x1="50" y1="240" x2="520" y2="240" stroke="#999" stroke-dasharray="6,4"/>
<path d="M 50 238 C 200 238, 250 62, 520 62" fill="none" stroke="#c0392b" stroke-width="3"/>
<circle cx="287" cy="150" r="5" fill="#333"/>
<line x1="287" y1="150" x2="287" y2="66" stroke="#333" stroke-dasharray="4,3"/>
<text x="430" y="50" font-size="13">u=1（一相）</text>
<text x="430" y="262" font-size="13">u=−1（另一相）</text>
<text x="150" y="130" font-size="13">曲线：u = tanh(x₁/√2)</text>
<text x="300" y="100" font-size="13">交界是平面 x₁=0</text>
<text x="70" y="42" font-size="13">u</text>
<text x="498" y="170" font-size="13">x₁</text>
</svg>

</div>

**为什么值得关心**

这是 1979 年提出的著名猜想的最后一块缺口：此前八维的结果都要附加"方向极限"假设。八维正是"平面刚性"与反例的分界维数，与极小曲面的 Bernstein 问题遥相呼应——猜想为什么恰好停在八维，这里给出了终极答案。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文在临界维数八上肯定地解决 De Giorgi 猜想：`@@M@@\mathbb R^8@@` 上沿一个方向严格单调的有界整体解 `@@M@@\Delta u=u^3-u@@` 必为一维 `@@M@@\tanh@@` 平面波，且不需要 Savin 的方向极限假设；更强地，`@@M@@\mathbb R^7@@` 上稳定解只有常数阱与平面波两类。

## 问题背景

Allen–Cahn 方程 (Allen–Cahn equation) `@@M@@\Delta u=u^3-u@@` 刻画相变，其一维解 `@@M@@g(s)=\tanh(s/\sqrt2)@@` 的水平集是一族平行超平面。De Giorgi 于 1979 年猜想：维数 `@@M@@n\le8@@` 时，任何有界、整体定义、沿某固定方向严格单调的解都必是这种"平面波"。该猜想与极小曲面 (minimal hypersurface) 的 Bernstein 问题深刻平行：Modica–Mortola 理论把 Allen–Cahn 能量的变分极限化为表面张力乘周长 (perimeter)，而非平坦的极小化锥恰在八维出现（Simons 锥），非仿射的整极小图要到九维才出现（Bombieri–De Giorgi–Giusti）——这条几何分界正是猜想停在八维的原因。此前 `@@M@@n=2,3@@` 由 Ghoussoub–Gui 与 Ambrosio–Cabrè 解决；Savin 覆盖了 `@@M@@n\le8@@`，但附加"方向极限逐点为 `@@M@@\pm1@@`"的假设；del Pino–Kowalczyk–Wei 在 `@@M@@n\ge9@@` 构造了反例。八维的无条件情形因此成为最后的缺口。稳定解 (stable solution) 一侧同样尖锐：Pacard–Wei 在八维造出非平面稳定解，故七维是稳定刚性的临界维数。

## 主要结果

论文证明两个定理。**定理一（八维单调刚性）**：若 `@@M@@u\in C^2(\mathbb R^8,(-1,1))@@` 满足 `@@M@@\Delta u=u^3-u@@` 且 `@@M@@\partial_8u>0@@`，则存在 `@@M@@e\in\mathbb S^7@@`（`@@M@@e_8>0@@`）与 `@@M@@c\in\mathbb R@@`，使 `@@M@@u(x)=\tanh\big(\frac{e\cdot x-c}{\sqrt2}\big)@@` 处处成立；能量增长、整体极小性与阱极限都不是假设，而是论证的结论。**定理二（七维稳定刚性）**：若 `@@M@@v\in C^2(\mathbb R^7,[-1,1])@@` 是稳定解，即二阶变分 `@@M@@Q_v(\varphi)=\int_{\mathbb R^7}\big(|\nabla\varphi|^2+(3v^2-1)\varphi^2\big)\ge0@@` 对一切紧支测试函数成立，则 `@@M@@v\equiv1@@`、`@@M@@v\equiv-1@@`，或为平面异宿波 (planar heteroclinic)，无需任何能量增长假设。中间的有限密度定理指出：`@@M@@4\le n\le7@@` 时只要能量密度 (energy density) `@@M@@M_\infty@@` 有限，同类分类即成立——于是全部困难集中在排除无界密度。

## 证明思路

先做几何推演（论文第一部分）。`@@M@@\partial_8u>0@@` 满足线性化方程，基态恒等式直接给出稳定性；长圆柱测试再把稳定性传给两个方向极限 `@@M@@v_\pm\colon\mathbb R^7\to[-1,1]@@`，由定理二它们只能是常数阱或平面波，而这两类都经一维校准 (calibration) 成为整体极小化子。接着用 Alberti–Ambrosio–Cabrè 与 Jerison–Monneau 的滑动比较把 `@@M@@u@@` 夹逼成整体极小化子，并得到表面阶能量增长 `@@M@@\mathcal E(u;B_R)\le CR^7@@`。随后做伸缩取极限 (blow-down)：论文把 Modica–Mortola 恢复序列在薄环层中与原解拼接，对层取平均以消去对收敛速率的依赖，证得能量测度恰等于 `@@M@@s_0@@` 乘某极小化边界 (minimizing boundary) 的周长——这一"无剩余扩散能量"的精确等式是后续几何论证的根基。能量单调性使该边界缩放成一个锥，方向单调性使锥法向的第八分量非负；在锥的链环 (link) 上解 Jacobi 方程并分情况讨论：该分量为正则链环全测地、锥为超平面；恒为零则解沿第八方向平移不变，与锥至多只有孤立顶点奇点矛盾。于是极限密度恰为 `@@M@@1@@`，Wang 的近单位密度定理把解压回一维，常微分方程的首积分最终给出 `@@M@@\tanh@@` 剖面与定向 `@@M@@e_8>0@@`。

再看七维稳定分类（第二至四部分）。核心变量是逆剖面 `@@M@@U=g^{-1}(v)@@` 与缺陷 `@@M@@D=1-|\nabla U|^2@@`（Modica 界保证 `@@M@@D\ge0@@`）：`@@M@@D@@` 一旦在某点为零即得平面波；否则 `@@M@@D>0@@`，精确稳定性恒等式 `@@M@@\int q^2|\nabla\eta|^2\ge\int q^3D\eta^2@@`（`@@M@@q=1-v^2@@`）把"偏离平面"编码为可积质量，其法向平均 `@@M@@I_P@@` 以严格系数控制零集曲面的平均曲率 (mean curvature)。有限密度情形经 Florit-Simon–Serra 的约化与 Wang–Wei 层估计，化为相邻薄层间距的对数系数比较，在七维产生矛盾。排除无界密度则引入罚化到达距离 (penalized reach) `@@M@@d(z)@@`：它同时度量一张薄层的弯曲与邻近薄层的逼近；延迟的能量单调性在近乎 `@@M@@d@@` 的尺度开出有界密度窗口、局部孤立出单张图，奇偶投影改进平均曲率导数，切相球给出接触点的单侧曲率界，合并成 `@@M@@d@@` 的微分不等式；与薄层提升的稳定性测试结合，经 Simons 型曲率方法得到四阶矩估计：`@@M@@|A|^4+D^2+E^2@@` 的加权和被 `@@M@@K(R)R^{m-4}@@` 控制，白赚四个 `@@M@@R@@` 的幂。

最后的径向比较对同一径向权函数同时使用到达不等式与环境稳定性测试：相邻薄层间固定宽度的中带内以 `@@M@@\operatorname{sech}^2@@` 形最优插值振幅，切换代价被显式数值预算封顶；系数逐项比较留下一个正的径向积分剩余，而联合单射法管把能量转移为小到达距离处的面积下界，与剩余的消失性矛盾，无界密度就此排除。

## 可信度与备注

按任务标注，本文主结果尚无 Lean 形式化证明，应以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。论文结构模块化：第一部分把定理二当黑盒使用，第二至四部分的解析证明又不依赖该几何推演，族内两个定理由此互为支撑、可分别审读；附录还核对了与九维 del Pino–Kowalczyk–Wei 反例构造的相容性。与同期工作（Florit-Simon–Serra 四维带密度假设，LLWWW 与 CFFFS 的三四维结果）相比，本文同时推进了维数与假设去除，最终比较的数值容差均显式列出，便于逐步核查。

{% endraw %}
