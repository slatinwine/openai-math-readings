---
layout: default
title: "Quenched SLE₃ Universality for the Weak Random-Bond Ising Model"
family: "218"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Quenched SLE₃ Universality for the Weak Random-Bond Ising Model

> 结果族 218：Conformal universality for weakly interacting and random-bond Ising models　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把磁铁想成一张格子布，每个格子住着一枚小箭头，相邻箭头爱保持一致。现在故意把格与格之间的"胶水"随机调稠调稀一点点：强度 `@@M@@1.1@@` 或 `@@M@@0.9@@` 各占一半。问：从边界裂开的那条蜿蜒大缝，放大之后还认得出完美格子里的那条随机曲线吗？本文证明：只要扰动足够小，认得出——裂缝的极限规律与无扰动情形是同一条曲线。

**关键词卡片**

- 伊辛模型（Ising model）：格子上的箭头模型，相邻箭头倾向同向，是研究磁铁相变的经典玩具。
- 随机键（random bond）：相邻箭头间的耦合强度独立随机地取 `@@M@@1\pm\varepsilon@@` 两个值，好比胶水稠稀不均。
- 临界温度（critical temperature）：磁铁"集体性格"突变的温度点，界面在此最摇晃。
- 弦 SLE₃（chordal SLE₃）：连接区域边界两点的随机曲线，纯 Ising 界面的已知极限。
- 固定环境（quenched）：先定死一套随机胶水取值再看规律；定理的收敛按环境概率成立。

**看个具体例子**

取 `@@M@@\varepsilon=0.1@@`。临界点由自对偶方程 `@@M@@(e^{2\beta\cdot1.1}-1)(e^{2\beta\cdot0.9}-1)=2@@` 解出，得 `@@M@@\beta_c\approx0.442@@`，比纯模型的 `@@M@@0.441@@` 略高。在此温度下，从 `@@M@@a@@` 到 `@@M@@b@@` 的界面虽在随机键上跌跌撞撞，宏观形状却收敛到同一条弦 SLE₃：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <rect x="60" y="40" width="440" height="200" fill="none" stroke="#333" stroke-width="2"/>
  <text x="150" y="64" font-size="18" fill="#c0392b">＋＋＋＋＋＋＋＋</text>
  <text x="150" y="228" font-size="18" fill="#2980b9">－ － － － － －</text>
  <text x="32" y="250" font-size="16" fill="#333">a</text>
  <text x="508" y="250" font-size="16" fill="#333">b</text>
  <path d="M60,240 C120,160 180,220 240,120 C300,60 360,180 430,120 C460,95 480,150 500,240" fill="none" stroke="#27ae60" stroke-width="3"/>
  <text x="330" y="200" font-size="15" fill="#27ae60">界面 → 弦 SLE₃</text>
</svg>

</div>

上边界的＋与下边界的－对峙，绿色界面随机漫游却整体可辨认：随机键只留下对数量级的痕迹，不足以改变极限曲线。

**为什么值得关心**

它把物理学家"二维弱无序处于边缘、不改变普适类"的重整化直觉，第一次升级成整条曲线层面的严格定理。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

对键强度取 `@@M@@1\pm\epsilon@@`（对称二值、独立同分布）的方格 Ising 模型，证明了只要 `@@M@@\epsilon@@` 足够小且固定，在自发磁化定义的临界温度处，固定环境下的 Dobrushin 自旋接口收敛到弦 `@@M@@\mathrm{SLE}_3@@`，并给出临界点的自对偶刻画。

## 问题背景

临界 Ising 接口的共形不变极限是严格数学的经典成果：Chelkak–Duminil-Copin–Hongler–Kemppainen–Smirnov 证明了纯方格模型的 Dobrushin 接口收敛到 `@@M@@\mathrm{SLE}_3@@`。若键强度带独立随机扰动（随机铁磁体），每个典型实现都破坏空间对称性，问题变成：固定环境（quenched）时宏观规律是否仍是同一条确定性曲线律？按 Harris 判据，二维恰处边缘情形：物理上 Dotsenko–Dotsenko、Shalaev、Shankar、Ludwig 等的重整化群分析预测"边缘不相关性"——弱无序在粗粒化下衰减，但慢到只剩对数修正。把这一图像变成整条接口的 quenched 定律，需要全新的几何控制，此前没有先例（Mahfouf 的 FK 接口结果要求无序强度随网格趋于零，而这里 `@@M@@\epsilon@@` 固定）。

## 主要结果

设 `@@M@@\xi_e=\pm1@@` 等概率独立，键 `@@M@@J_e=1+\epsilon\xi_e@@`，`@@M@@\epsilon@@` 固定。临界点 `@@M@@\beta_c(\epsilon)@@` 由自发磁化（spontaneous magnetization）阈值定义。定理断言：存在 `@@M@@\epsilon_0>0@@`，对每个固定 `@@M@@\epsilon\in(0,\epsilon_0)@@`、任意有界 Jordan 区域 `@@M@@D@@`、边界标记点 `@@M@@a,b@@` 及任意确定性容许格点逼近（网格 `@@M@@\delta_n\downarrow0@@`），在 `@@M@@\beta_c(\epsilon)@@` 处接口律 `@@M@@Q_{n,\omega}@@` 满足 `@@M@@\Prob_{\rm env}[d_{\rm BL}(Q_{n,\omega},\SLE_3(D;a,b))>\eta]\to0@@`。这里收敛是环境概率下的（quenched），拓扑是模去保向重参数化的完整定向曲线。证明还顺带识别出临界点满足 Kramers–Wannier 型自对偶方程 `@@M@@(e^{2\beta_c(\epsilon)(1+\epsilon)}-1)(e^{2\beta_c(\epsilon)(1-\epsilon)}-1)=2@@`。

## 证明思路

证明的脊柱是一套逐尺度的重整化构造。先把无序模型写成纯临界 Ising 加随机局部扰动势之和，再设计"局部尺度变换"：通过在参考 Gibbs 场中添加辅助公平硬币并对相隔的正方形逐块精确条件积分，把相互作用重新局部化到更大尺度；孤立的大扰动集中点单独处理，因此所有估计只要求环境矩而非环境一致界。核心坐标是能量荷（energy charge）`@@M@@Q@@`——一个在纯环带传输下恰好保持不变的线性泛函，度量扰动的能量分量；其环境协方差和 `@@M@@W@@` 是无序强度的主阶。关键计算是"边缘方差流"：取两个远离的归一化插入（insertion）乘积，其归一化分母在四阶产生负贡献 `@@M@@-2\kappa W^2\sum_{H<|y|\le LH}|y|^{-2}@@`（壳层和趋于 `@@M@@2\pi\log L>0@@`），于是多项式坐标 `@@M@@v_H@@` 满足 `@@M@@v'-v\le-cv^2@@`。配以打靶（shooting）论证选取温度，使平均荷被夹在两壁之间，得 `@@M@@v_k\le(v_0^{-1}+ck)^{-1}@@`：无序只按尺度对数衰减——边缘不相关性由此严格化。

接着把衰减中的扰动转移到局部交叉（crossing）估计：小方块要影响宏观测试，必须有多条路径从该方块伸远，纯通道（passage）界给出尺度比的正幂，几何加权求和后总误差趋于零，且只需对数衰减。临界点识别分两步：先在环面上用四扇区自旋扭转（holonomy）配分函数与非齐次 Kramers–Wannier 对偶 `@@M@@Z(K)=a(K)\mathsf H Z(K^*)@@`，配合 OSSS 决策树不等式对 FK 缠绕概率的严格单调性，证明尺度变换调出的参数必为自对偶点 `@@M@@h_*=0@@`；再用环形 FK 势垒（好环带以高概率出现）排除该点的渗流，并在其上温度用"每中心布大量独立环带 + 层探索压低 revealment + 决策树不等式"把对偶臂衰减推到任意多项式阶，从而证明磁化恰在此处转正——自对偶性本身从未被当作临界性判据。

最后从体估计走向整条曲线：把目标接口与略微位移的区域 `@@M@@A_h^\pm@@` 中的纯 Dobrushin 弦做条件耦合。技术上最要紧的一步是引理"固定环境下的条件与粘合"：它在每个固定环境中分别做比较耦合，因此纯边际在给定 `@@M@@\omega@@` 后仍是确定的纯律——正是这一条件边际把所有几何比较升级为 quenched 律的收敛。带符号条带势垒把目标迹夹在两条同律纯弦之间，初等平面论证（有序弦 + 面积比较）识别出迹的唯一极限；再以四通道估计排除沿极限弦来回折返的"倒行"模式，完成完整曲线度量下的收敛。个别几何构造的细节此处从略。

## 可信度与备注

本文主结果暂无 Lean 形式化证明。它是本结果族的技术基座：族内姊妹篇把这里的对称二值键推广到一般有界键律，另有配套篇（文中 [S]）提供纯模型传输与几何比较输入，三篇互相咬合。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
