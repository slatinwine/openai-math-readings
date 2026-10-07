---
layout: default
title: "Global quantum geometric Langlands at irrational level"
family: "069"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Global quantum geometric Langlands at irrational level

> 结果族 069：Global quantum geometric Langlands at irrational level　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了无理级别的量子几何朗兰兹等价：对任意连通单复代数群 \(G\)、任意光滑射影连通复曲线 \(X\) 与任意 \(c\in\mathbb C\setminus\mathbb Q\)（含非实级别），扭曲 \(D\)-模范畴 \(D_c(\operatorname{Bun}_G(X))\) 与对偶群在互反级别 \(-1/(rc)\) 处的范畴 \(D_{-1/(rc)}(\operatorname{Bun}_{G^\vee}(X))\) 等价，且保留给定的整体群形式与全部连通分支。

## 问题背景

几何朗兰兹纲领（geometric Langlands program）把主丛栈 \(\operatorname{Bun}_G(X)\) 上的 \(D\)-模与对偶群 \(G^\vee\) 的局部系统联系起来；其"量子"变形比较的是互反移位级别（shifted level）\(c\) 与 \(-1/(rc)\) 处的两族扭曲 \(D\)-模范畴。互反参数由 Kapustin–Witten 的电磁对偶解释，早期形式可溯至 Drinfeld 与 Stoyanovsky 的逆参数猜想，Gaitsgory 将其发展为以局部化与 Whittaker 系数为语言的纲领。级别 \(c=0\) 的经典等价已由 GLC 系列证明，Bogdanova 近来又在 Betti 侧构造了量子函子；但无理级别的全局 de Rham 等价一直悬而未决——谱描述在 \(c\neq 0\) 处失效，零级别的 Poincaré 余核只知其落在反温和（anti-tempered）部分。本文把这一缺口对所有无理级别补上。

## 主要结果

设 \(X\) 为光滑射影连通复曲线，\(G\) 为连通单复代数群，\(G^\vee\) 由完整根资料（root datum）的对偶给出。记 \(h^\vee\) 为对偶 Coxeter 数，\(r\in\{1,2,3\}\) 为按根长平方比定义的花边数（lacing number），\(L_G\) 为伴随行列式线丛（\(L_G|_E=\det R\Gamma(X,\mathfrak g_E)\)），按移位约定 \(D_c(\operatorname{Bun}_G(X)):=D(L_G^{(c-h^\vee)/(2h^\vee)})\)，即线丛复幂指定的扭曲微分算子范畴（无需取根）。主定理断言：对每个 \(c\in\mathbb C\setminus\mathbb Q\) 存在可呈现 \(\mathbb C\)-线性 DG 范畴的等价
\[D_c(\operatorname{Bun}_G(X))\simeq D_{-1/(rc)}(\operatorname{Bun}_{G^\vee}(X)).\]
该等价由"局部化–Whittaker 比较"刻画，与标点族及其碰撞相容，并把中心 torsor 的平移与 transgression 局部系 \(u_Q=\int_X\langle[Q]\cup\operatorname{obs}\rangle\) 交织。在中心特征 \(\eta\in X^*(Z_G)\) 与连通分支 \(p\in\pi_1(G)\) 的双重分解上，它按 \((\eta,p)\mapsto(p,-\eta)\) 交换两侧。

## 证明思路

证明围绕"两组比较加一次组装"展开。

先打地基：无理扭转自动切除不稳定方向。惯性和中的中心 \(\mathbb G_m\) 若以非零整权 \(m\) 作用在线丛上且 \(sm\notin\mathbb Z\)，则 Kummer 联络 \(d-s\,d\log t\) 在 \(\mathbb G_m\) 上没有 de Rham 上同调，相应的扭曲等变范畴为零（惯性消失引理）。结合 Harder–Narasimhan 分层与 Riemann–Roch 权重计算，这把 \(D(L^s)\) 压缩到某个拟紧开集上，从而可用 Drinfeld–Gaitsgory 的 QCA 框架：紧生成、Künneth 公式与以反扭转为对偶的范畴对偶。

第一组比较是 Plancherel 恒等式 \(J_sR_s\simeq\operatorname{Id}\)（\(s\notin\mathbb Q\)），\(R_s\) 为增强 Whittaker 系数函子，\(J_s\) 为经扭曲伪恒等（pseudo-identity）修正的 Poincaré 函子。零级别处其余核恰为反温和部分，Faergeman–Raskin 的有限 Whittaker 测试消灭它；论文证明同一测试（经相邻 Iwahori alcove 的星型缠绕子与有限单幂平均构造）在无理级别保守——Bruhat 层 \(w\neq 1\) 上的特征 \(s(w\nu-\nu)\) 非整，再次被 Kummer 惯性判据杀死。真正的难点是零级别的消失只在滤余极限意义下成立。作者先把有限极点界的逼近表为带单值 \(q\) 的 Kummer 局部系的普通几何复形，借助辅助仿射直线上的平移与 Fourier 变换造出指数特征；拟单值性使上同调维数与转移映射的秩在非单位根处常数。再引入对数系数变差 \(\mathcal L_n\)，配合 Deligne 分裂与 Nakayama 引理，把 \(q=1\) 处的余极限消失连同一致权上界传递到一切非挠 \(q\)。该一致上界的度数部分是全文唯一动用完整经典几何朗兰兹之处：谱侧化为 \(\operatorname{IndCoh}_{\operatorname{Nilp}}(\operatorname{LS})\) 的整体截面，再用 QCA 有限上同调维数封顶。

第二组比较处理标点族上的局部范畴：以 Feigin–Frenkel 与 Arakawa–Frenkel 的 \(W\)-代数对偶及 Campbell–Dhillon–Raskin 的局部等价为输入，把 Kac–Moody 模块与仿射 Grassmannian 上的 Whittaker 对象配对，并靠半单群的二维上同调使伴随单位在同伦层面同构，从而把等价跨越碰撞对角线延拓。随后 Ran 空间上的积分——核心是 Ran 的同伦可缩性——把局部配对收缩成全局周期恒等式 \(\langle R\Lambda(M),\check\alpha(\check M)\rangle\simeq\langle R'\Lambda'(\check M),\alpha(M)\rangle\)。

最后组装：周期恒等式给出 \(RL\simeq(M')^\vee(S')^\vee\)；四个局部化函子都是局部化（右伴随全忠实），其转置全忠实，故可从恒等式"约去"嵌入得到函子 \(f\)，令 \(\Phi=e_B f\)（\(e_B\) 为伪恒等等价）。两条 Plancherel 恒等式分别给出左逆与右逆，二者复合后相等，故 \(\Phi\) 既全忠实又本质满。中心 torsor 相容性的下降论证等技术步骤较强，此处从略。

## 可信度与备注

主结果暂无形式化证明；依 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。论文把 Feigin–Frenkel 对偶、Arakawa–Frenkel 约化、Raskin 的范畴化 Drinfeld–Sokolov 约化、Campbell–Dhillon–Raskin 局部等价、GLC 系列与 Lin 的比较及 Bogdanova 的 Betti 侧构造等重大既有结果作为输入，自创的两个机制是控制全局核滤形变的权论证、以及把局部配对延拓为跨碰撞凝聚比较的论证。本结果族（069）本批仅此一篇手稿，文内 Plancherel 恒等式、周期比较与局部比较三组件互为支柱，共同支撑主定理。

{% endraw %}
