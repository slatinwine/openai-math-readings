---
layout: default
title: "Logarithmic Kodaira dimension and whole-fiber variation"
family: "033"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Logarithmic Kodaira dimension and whole-fiber variation

> 结果族 033：Iitaka subadditivity, variation, and logarithmic additivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文证明了 Popa 的对数 Iitaka–Viehweg 不等式：当基的开簇满足 \(\bar\kappa(V)\ge0\) 时 \(\bar\kappa(U)\ge\kappa(F)+\max\{\bar\kappa(V),\operatorname{Var}(f)\}\)，其中变异性按整个几何一般纤维的双有理定义域度量，且不设任何丰度或好极小模型假设。

## 问题背景

纤维化携带两类多重典范形式的来源：基自身的几何，与纤维随基点的双有理变化。Iitaka 次可加性只回答第一类；Iitaka–Viehweg 加细进一步问：一个纤维双有理地变化的族还要强迫出多少新方向？在开基上度量基的正确工具是对数 Kodaira 维数（logarithmic Kodaira dimension）\(\bar\kappa\)——允许沿约化 SNC 边界取极点的多重典范形式的增长维数。Viehweg 的弱正性（weak positivity）把双有理变异性（birational variation）纳入期望下界，此后 Kollár 证一般型纤维情形、Kawamata 证纤维有好极小模型情形；Cao–Păun 与 Hacon–Popa–Schnell 处理阿贝尔基与最大 Albanese 维数基；Hashizume 证一般纤维对数典范除子丰度的约化 SNC 情形。Popa 的猜想 3.8（2023 年 6 月版）要求在任意 \(\bar\kappa(V)\ge0\) 的基上给出变异性下界，此前没有无丰度假设的一般性结果。注意基假设本质是对数的：\(\bar\kappa(\mathbb C^*)=0\)，而其光滑射影紧化 \(\mathbb P^1\) 的普通 Kodaira 维数却是 \(-\infty\)，紧化论证必须保留系数一的逆像边界。

## 主要结果

设 \(f:U\to V\) 是光滑连通复准射影簇之间的射影满射连通纤维态射，\(F\) 为其几何一般纤维（geometric generic fiber）。其**双有理变异性**定义为
\[\operatorname{Var}(f)=\min_L\operatorname{trdeg}_{\mathbb C}L,\]
其中 \(L\) 取遍 \(\mathbb C\subseteq L\subseteq\Omega\)（\(\Omega\) 为 \(\mathbb C(V)\) 的代数闭包）的代数闭中间域，且 \(F\) 双有理等价于 \(L\) 上某个簇的基扩张。这是经典不变量的"定义域形式"，记录 \(F\) 的**整个**函数域，而不仅是典范环。

**定理（对数变异性）**：若 \(\bar\kappa(V)\ge0\)，则
\[\bar\kappa(U)\ge\kappa(F)+\max\{\bar\kappa(V),\operatorname{Var}(f)\}.\]
这正面解决 Popa 猜想 3.8（下界部分）；允许奇异纤维，不设丰度、好极小模型或半丰度假设。推论一：射影复 Iitaka–Viehweg \(C^+\) 猜想 \(\kappa(X)\ge\kappa(F)+\max\{\kappa(Y),\operatorname{Var}(f)\}\)（\(\kappa(Y)\ge0\)）在一切维数无好极小模型假设地成立。推论二（光滑族、闭纤维非单有理）：\(\bar\kappa(V)=-\infty\Rightarrow\operatorname{Var}(f)<\dim V\)；\(\bar\kappa(V)\ge0\Rightarrow\operatorname{Var}(f)\le\bar\kappa(V)\)；Campana-特殊（Campana-special）基上 \(\operatorname{Var}(f)=0\)，特别地 \(\bar\kappa(V)=0\) 时族双有理平凡（birationally isotrivial）。

## 证明思路

记 \(d=\kappa(F)\ge0\)。姊妹篇的对数次可加性已给 \(\bar\kappa(U)\ge d+\bar\kappa(V)\)，剩下的任务是证 \(\operatorname{Var}(f)\le\bar\kappa(U)-d\)。先取相容紧化 \(f:(X,D_X)\to(Y,D_Y)\)，\(U=f^{-1}(V)\)，并固定一个基上的对数形式 \(\xi\)。第一步构造"参数域"：取 \(K_X+D_X\) 的绝对 Iitaka 映射 \(q:X'\to Z\)（\(\dim Z=\bar\kappa(U)\)），在 \(\mathbb C(X)\) 中取 \(\mathbb C(Y)\mathbb C(Z)\) 的相对代数闭包并正规化合成像，得 \(X'\xrightarrow{x}W\) 与 \(g:W\to Y\)、\(h:W\to Z\)。用 \(\xi\) 沿 \(p_1\) 个切向的收缩证明 \(W_z\) 上对数维数非负，再用次可加性夹逼出一般 \(x\)-纤维 \(J\) 满足 \(\kappa(J)=0\)。像族 \(C_z=g(W_z)\subset Y\) 的 Hilbert 参数映射的微分秩恰为 \(p_1\)：收缩截影在每度一维的强制下成比例，Plücker 坐标比值随之常数。取参数空间的光滑射影模型 \(T_0\)，则 \(\dim T_0=p_1\)，且经域塔 \(\mathbb C(Y)=\mathbb C(S)\) 得到 \(\mathbb C(T_0)\subseteq\mathbb C(Y)\)，最终 \(\bar\kappa(U)=d+\dim T_0\)。第二步在 \(b=\overline{\mathbb C(T_0)}\) 上"抓住全纤维"：取 \(J\) 的最小指标根覆盖（第一个多重典范截影的 \(p\) 次根），其整体顶形式空间一维；把姊妹篇的伴随比较用于限制后的整变分，使 Hodge 线沿 \(h\)-纤维有理平凡，从而具有限特征。第三步是解析常值判据：对曲线上光滑射影族，若 \(\kappa(D)=0\)、\(h^0(K_D)=1\) 且整顶 Hodge 线平坦具有限单值特征，则有限扩域后族双有理常值（且可等变于 deck 群）。证明先取平坦顶形式 \(\Theta\) 之核方向提升基向量场 \(v\)，其极点被相对典范截影零除子控制；经 Demailly–Hacon–Păun 扩展定理与 Păun–Takayama 的相对多重典范 Bergman 度量 \(L^{2/m}\) 估计，每个极点除子对 \(K_D+\varepsilon H\) 有正的渐近固定阶；BCHM 的相对典范模型收缩这些极点后向量场正则，其流双全纯地等同邻近纤维；再以 Hilbert 图轨迹的可数构造从曲线散布到任意代数轨迹。第四步是代数下降：标记典范模型恢复相对 Iitaka 基在 \(b\) 上的有限规范化 \(V'\)，\(J\) 成为 \(k=b(V')\) 上某参考簇的形式（form）；把有限分裂上闭链常数化，并在随参数移动的除子处用实际相对形式阶找到达到阈值的重数一分支，迫使分裂覆盖在该处非分歧；经 purity 与有限 étale 覆盖的下降得到域 \(F_b\) 使 \(\operatorname{Frac}(\Omega\otimes_bF_b)\simeq\operatorname{Frac}(\Omega\otimes_{\mathbb C(Y)}\mathbb C(X))\)——即整个几何一般纤维已在 \(b\) 上双有理定义，故 \(\operatorname{Var}(f)\le\dim T_0\)。与第一步合并即得定理。文末两节还给出独立的数值延拓与普通 Iitaka 约化结果，但对数主证明不依赖它们。

## 可信度与备注

本篇主结果暂无形式化证明。其证明直接调用姊妹篇《Orbifold and logarithmic Iitaka subadditivity》的约化 SNC 次可加性与全周期伴随比较两个接口；与第三篇《The reverse logarithmic Kodaira inequality and additivity》互补——后者在层光滑设定给出反向不等式，光滑族情形两者合成分支 \(\operatorname{Var}(f)\le\bar\kappa(V)\) 的另一证法；推论二还调用另一姊妹篇的特征零对数丰度与 Taji 刚性定理。依照 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
