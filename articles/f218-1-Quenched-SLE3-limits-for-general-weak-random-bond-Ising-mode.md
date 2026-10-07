---
layout: default
title: "Quenched SLE₃ limits for general weak random-bond Ising models"
family: "218"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Quenched SLE₃ limits for general weak random-bond Ising models

> 结果族 218：Conformal universality for weakly interacting and random-bond Ising models　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了方格 Ising 模型的键强度即使带上任意有界、均值零的独立同分布（iid）无序，只要强度 \(\varepsilon\) 足够小，在真正的物理临界温度处，固定环境（quenched）意义下的自旋接口仍收敛到弦 \(\mathrm{SLE}_3\)：二维无序虽是边缘情形，却不改变普适类。

## 问题背景

纯方格 Ising 模型在临界点是可积的，Smirnov、Chelkak 等人证明了其 Dobrushin 接口在尺度极限下收敛到 \(\mathrm{SLE}_3\)，这是共形不变普适性的标志性结果。自然的问题是：如果键强度 \(J_e\) 带随机扰动（随机铁磁体），微观无序会不会渗入宏观极限规律？按 Harris 判据，二维无序恰处边缘（marginal）情形：它既不被排斥也不被放大，故无法靠一次性的压缩论证，而需要逐尺度的衰减估计。此前的姊妹篇（文中引用 [R]）只处理对称二值键 \(1\pm\varepsilon\)，其分布在 Kramers–Wannier 对偶下对称，临界温度可由自对偶性直接锁定；一般键律不再自对偶，临界点的识别本身成为障碍。

## 主要结果

设无序律 \(\rho\) 支撑于 \([-1,1]\)、均值零且非退化（方差 \(\sigma_\rho^2>0\)），键取 \(J_e=1+\varepsilon\xi_e\)。临界点 \(\beta_c^\rho(\varepsilon)\) 由自发磁化（spontaneous magnetization）严格定义：使无穷体积加号态磁化的环境均值由零变正的阈值。定理断言：存在 \(\varepsilon_0(\rho)>0\)，对每个 \(0<\varepsilon<\varepsilon_0(\rho)\)、任意 Jordan 区域 \(D\) 与边界标记点 \(a,b\) 及其确定性格点逼近，临界点处的接口律 \(Q_{n,\omega}\) 满足 \(d_{\rm BL}(Q_{n,\omega},\mathsf S_{D;a,b})\to 0\)，收敛在环境概率下成立——即 quenched 收敛，且是完整定向曲线（oriented curve）拓扑。阈值 \(\varepsilon_0(\rho)\) 不依赖区域或逼近序列；并附赠 \(\beta_c^\rho(\varepsilon)=\tfrac12\log(1+\sqrt2)+O_\rho(\varepsilon^2)\)。

## 证明思路

整套论证分五步接力。先把无序模型改写为纯临界 Ising 加上一族随机局部扰动势，借入 [R] 的尺度重整化框架：以能量荷（energy charge）\(Q\) 度量扰动的能量分量，用坐标 \(X\)（范数矩）、\(Y\)（均值范数）、\(m\)（平均荷，扩张方向）与 \(W\)（环境方差密度，边缘方向）追踪迭代。由于一般分布不对称，三次项不必消失，方差坐标 \(v_H\) 需保留至四阶泰勒项；关键在于单步流 \(v'-v\approx-2\kappa W^2\sum_{H<|y|\le LH}|y|^{-2}\) 带严格负漂移，得 \(v_k\le (v_0^{-1}+ck)^{-1}\)，扰动在矩意义下逐尺度消失。

再对原始（primal）键族与精确对偶（dual）键族分别做"打靶"（shooting）：对温度参数 \(h\) 用连续性（尺度构造中的连续阈值恰好化解 \(\rho\) 有原子的困难）选出使轨迹始终困在区域 \(|m|\le Dv\)、\(X\le A\sqrt v\) 内的温度 \(\beta_{\rm p},\beta_{\rm d}\)。但二者未必相等，也不必自对偶。第三步在同一环境的环面上比较四个自旋扭转（holonomy）扇区的配分函数向量：非齐次 Kramers–Wannier 对偶给出 \(Z(K)=a(K)\mathsf H Z(K^*)\)，归一化向量在两个温度下都趋于纯临界向量，故 FK 缠绕概率 \(q_{N,\omega}(\beta)\) 在两点都渐近等于纯临界值；而 OSSS 决策树不等式加加权导数公式给出 \(q'(\beta)\ge c_1 q(1-q)\) 的严格单调性，迫使 \(\beta_{\rm p}=\beta_{\rm d}=:\beta_*\)。

第四步识别 \(\beta_*\) 就是物理临界点：先用环形 FK 势垒（"好"环带以大概率出现）排除 \(\beta_*\) 处的渗流；对 \(\beta>\beta_*\)，在每个中心布置大量键邻域不交的环带做环境放大，再用层探索（layer exploration）压低 revealment、由决策树不等式把对偶臂衰减升级为拉伸指数级，进而推出原始键上正磁化；最后 Edwards–Sokal 配合把磁化等同于渗流概率，得 \(\beta_*=\beta_c^\rho(\varepsilon)\)。全程未使用分布自对偶。

最后处理接口：把目标接口与略微外扩/内缩的位移区域 \(A_h^\pm\) 中的纯 Dobrushin 接口做条件耦合——耦合在给定原始环境下仍保持纯边际为其确定的纯律，这一条件边际正是把"平均收敛"升级为"quenched 收敛"的关键。带符号条带势垒把目标迹夹逼在 \(\overline{M(L)}\cap\overline{P(U)}\) 内，两条同律有序弦经初等平面拓扑论证相等，识别出迹；再用多通道（multi-passage）估计排除曲线沿迹来回折返，最终在完整定向曲线度量下闭环。其中"条带跨越对比"等技术性较强的细节从略。

## 可信度与备注

本文主结果暂无 Lean 形式化证明。它是族内姊妹篇——对称二值键情形的 quenched \(\mathrm{SLE}_3\) 结果（文中 [R]）与提供纯模型输入的 [S]——向一般键律的推广，尺度估计与边界比较两大工具均直接引自该姊妹篇，逻辑上层层递进、互相支撑。但按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
