---
layout: default
title: "Ambiently homeomorphic isolated hypersurface germs in ℂ⁴ with multiplicities four and five"
family: "059"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Ambiently homeomorphic isolated hypersurface germs in ℂ⁴ with multiplicities four and five

> 结果族 059：Counterexamples to Zariski's multiplicity conjecture　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

上一篇在很高的维数导演了"拓扑一样、重数不同"的反例；这一篇把同一出戏搬上最小有趣舞台：四个复变量的 ℂ⁴。两个货真价实的收敛全纯函数芽，零集可以被环境同胚互变，重数却分别是 4 和 5——在最经典的环境维数里给 Zariski 问题以否定答案。

**关键词卡片**

- 收敛全纯芽（convergent holomorphic germ）：原点附近真的收敛的幂级数，不是形式玩具
- 重数（multiplicity）：最低次项的次数，这里一边是 4、一边是 5
- 环境同胚（ambiently homeomorphic）：由 ℂ⁴ 整体的连续变形实现互换
- 开书分解（open book）：把奇点邻域看作"书脊＋一页页纸"的拓扑结构
- 链环（link）：零集与小球面 S⁷ 的交，本维数里高维纽结分类不再适用

**看个具体例子**

两个芽都从六分支平面曲线 `@@M@@h(X,T)=T(X-T^2)(X-2T^2)@@` 出发，经四次有限映射拉到锥 `@@M@@yz=w^4@@` 的微小光滑化四重体上，初始形式分别是：

`@@M@@Df_4:\ s^{-4}yz\,X^2\ (\text{次数 }4)\qquad\text{与}\qquad f_5:\ T\,(s^{-4}yz)(s^{-4}yz-T^2)\ (\text{次数 }5)@@`

两者都以原点为孤立临界点、零集芽却环境同胚——最低次项差了一整次，拓扑浑然不觉。顺带一提：已有的家族定理说明，任何保持 Milnor 数常值的连续形变路径都会强制重数不变，所以这对反例不可能被那样的路径连接，必须从平面曲线数据另起炉灶重新构造。

**为什么值得关心**

ℂ⁴ 是嵌入链环落在七维球面中的最小维数，姊妹篇的高维纽结工具在此全部失效，反例必须靠"非球面开书＋数论逼近"的新路线达成，说明拓扑等价对重数彻底失明。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

在四个复变量中构造出两个约化的收敛全纯函数芽：原点都是孤立临界点，零集芽可由环境空间（ambient space）的同胚互变，重数却分别是 4 与 5——在最经典的环境维数 `@@M@@\mathbb{C}^4@@` 中给 Zariski 重数问题以否定答案。

## 问题背景

Zariski 于 1971 年明确提出：超曲面芽的嵌入拓扑是否决定其重数（multiplicity，定义函数最低次项次数）？平面曲线情形由分支特征数据理论肯定解决，高维一直悬而未决。形变方向有 Greuel–O'Shea 与 Bobadilla–Pełka 的家族定理：系数连续且 Milnor 数 `@@M@@\mu@@` 有限常值的路径必有常值重数，因此反例对不可能被这样的路径连接；McLean 证明链环接触同胚（contactomorphic）时重数相等；Koike–Parusiński 则提议用平面曲线的高次悬浮做试验。姊妹篇（本族另一论文）已在大维数 `@@M@@N\equiv0\pmod 8@@` 中造出重数 2 与 3 的反例，而 `@@M@@\mathbb{C}^4@@` 是嵌入链环落在 `@@M@@S^7@@` 的最小有趣维数，此处高维纽结分类不再适用，需要全新的非球面开书（open book）论证。

## 主要结果

定理：存在约化收敛全纯芽 `@@M@@f_4,f_5:(\mathbb{C}^4,0)\to(\mathbb{C},0)@@`，各以原点为孤立临界点（isolated critical point），`@@M@@\operatorname{ord}_0 f_4=4@@`、`@@M@@\operatorname{ord}_0 f_5=5@@`，且有环境对芽的同胚 `@@M@@(\mathbb{C}^4,V(f_4),0)\cong(\mathbb{C}^4,V(f_5),0)@@`。构造从平面曲线 `@@M@@h(X,T)=T(X-T^2)(X-2T^2)@@` 出发，取两个四次有限图映射 `@@M@@\pi_0,\pi_1@@`；在 `@@M@@\mathbb{C}^5@@` 中锥 `@@M@@yz=w^4@@` 的微小光滑化四重体 `@@M@@C_{i,s}@@` 上取 `@@M@@f_{i,s}=h+w(y^a+z^b)@@`，隐式求解后初始形式分别为 `@@M@@T(s^{-4}yz)(s^{-4}yz-T^2)@@`（次数 5）与 `@@M@@s^{-4}yzX^2@@`（次数 4）。

## 证明思路

先备平面数据：拉回 `@@M@@d_i=h\circ\pi_i@@` 是同一六分支嵌入类型的平面曲线（Milnor 数 51），通过插值到相同首项模型并用加权旋转的角场论证保持开书，得整 Seifert 形式同构；但两个映射在 `@@M@@h@@` 三分支上的分歧度模式不同（一侧为 `@@M@@(4),(1,1,2),(2,2)@@`，另一侧为 `@@M@@(1,1,1,1),(4),(4)@@`），故诱导的同调映射 `@@M@@\pi_{i*}@@` 与迁移映射 `@@M@@\pi_i^!@@`（`@@M@@\pi_{i*}\pi_i^!=4@@`）被单独保留——区分两个芽的正是这些映射，而非抽象同构。再做四重体与参数：以中国剩余定理取 `@@M@@n_0\equiv1\pmod{2^r}@@`、`@@M@@n_0\equiv2\pmod5@@`，令 `@@M@@a=(n_0^2-1)/4@@`、`@@M@@b=(n_1^2-1)/4@@` 且 `@@M@@\gcd(n_0,n_1)=1@@`；弧论证配合平面梯度估计 `@@M@@\nu\nabla h\le4m_0@@` 证明孤立临界点。继而计算真实 Milnor 页：把页切成内部光滑化区域与继承锥的外部，带符号 Mayer–Vietoris 切割与 Bockstein 计算给出关键格公式——整格点须满足模 4 剩余条件 `@@M@@\pi_*l\equiv(1\otimes\tau)z\pmod{4H}@@`，形式为 `@@M@@-s_d|_K\perp(s_h\otimes e)@@`，其中 `@@M@@E@@` 是锥页 `@@M@@w(y^a+z^b)@@` 的同调、`@@M@@\tau:E\to\mathbb{Z}/4@@` 由径向投影诱导；该剩余条件恰由具体图映射决定。然后进入算术：锥页两个边界向量 `@@M@@b_0,b_1@@`（`@@M@@y@@` 轴、`@@M@@z@@` 轴）自配对 `@@M@@-n_j^2/4@@`，归一化 `@@M@@v_j=b_j/n_j@@` 后范数同为 `@@M@@-1/4@@`，于是在 `@@M@@\ell\nmid n_j@@` 的素数处得到互补的整分裂及两个有理 Seifert 等距 `@@M@@J_0,J_1@@`（`@@M@@\gcd(n_0,n_1)=1@@` 保证覆盖全部素数）；其差由交换 `@@M@@v_0,v_1@@` 的反射生成，只作用在单项性（monodromy）特征值 1 与本原五次根两个扇区，行列式与旋量范数相消后可提升到 spin 群与特殊酉群；再用全纯微分 `@@M@@\omega_{i,j}=U^{i-1}V^{j-1}dU/\partial_V\widetilde P@@`（权指标 `@@M@@(bi+aj)/m=q/5@@`，`@@M@@q\in\{1,4\}@@`）与反全纯类给出相反的 cup 积符号，证明两扇区上的二次型与 hermitian 形均不定、群在实位置非紧，Kneser–Platonov 强逼近便给出一个有理点同时修正所有局部选择，合成一个整 Seifert 同余。最后用 Kato 的 `@@M@@S^7@@` 上简单可旋结构（simple spinnable structure）分类定理——它不要求 binding 是同伦球面——把整 Seifert 矩阵同余转化为链环的保定向微分同胚，再用 Łojasiewicz 解析锥定理把球面上的等价扩展成原点邻域的环境同胚芽。

## 可信度与备注

本结果未经 Lean 形式化；OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。文中构造是显式收敛方程，格计算、Bockstein 与算术提升均有完整推导，经典输入（Milnor、Sakamoto、Kato、Durfee、Platonov 等）引用前逐一核对了假设。与姊妹篇（高维、重数 2 与 3、加权齐次 + 球面纽结分类）论证路线完全独立、维数与重数互异，两文互相印证地否定 Zariski 问题；论文同时注明三变量情形两侧均未解决。

{% endraw %}
