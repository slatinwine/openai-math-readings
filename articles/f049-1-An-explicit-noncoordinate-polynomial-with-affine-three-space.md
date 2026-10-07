---
layout: default
title: "An explicit noncoordinate polynomial with affine three-space zero fibre"
family: "049"
discipline: "Algebraic and complex geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | An explicit noncoordinate polynomial with affine three-space zero fibre

> 结果族 049：A stable-coordinate counterexample in four variables　·　学科：Algebraic and complex geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文在 \(\mathbb C[h,u,v,w]\) 中显式构造多项式 \(F\)：零超曲面同构于 \(\mathbb A^3\)（商环为 \(\mathbb C^{[3]}\)），但 \(F\) 不是坐标，从而否定 Abhyankar–Sathaye 嵌入猜想；添加变量即得一切环境维数 \(\ge4\) 的反例。

## 问题背景

Abhyankar–Sathaye 猜想（特征零）问：若 \(\mathbb C[z_1,\ldots,z_n]/(f)\cong\mathbb C^{[n-1]}\)，即零超曲面是仿射空间，\(f\) 是否必为坐标（coordinate），即仿射空间 \(\mathbb A^n\) 的某多项式自同构的第一分量？几何上等价于：\(\mathbb A^{n-1}\hookrightarrow\mathbb A^n\) 的超曲面嵌入能否被环境多项式自同构送到坐标超平面。\(n=2\) 由 Abhyankar–Moh–Suzuki 定理肯定。高维长期只有对受限形状方程的肯定结果：Sathaye 与 Russell 的线性平面、Kaliman–Vénéreau–Zaidenberg 与 Maubach 对 \(a(x)y+b(x,z,t)\) 型方程、以及 Ghosh 与 Ghosh–Gupta–Pal 的系列定理。卡点在于：商环有一个抽象的多项式呈现，并不自动给出环境多项式环的自同构；Sathaye 早已区分"坐标（满同态）问题"与更弱的"零纤维是仿射空间"问题。Shpilrain–Yu 进一步用环境临界轨迹（critical locus，梯度全为零的点集）区分同构超曲面的不等价嵌入，并问：零纤维同构于坐标超平面时，梯度是否必无处为零？本文在环境维数 4 给出否定回答。

## 主要结果

构造从尖点参数化 \((u^3,-u^2)\) 出发，用 \(h\) 的独立倍数扰动两个分量：
\[x=u^3+hv,\qquad y=-u^2+hw,\]
\[s=2u^3v+3u^4w+h(v^2-3u^2w^2)+h^2w^3,\]
它满足尖点恒等式 \(x^2+y^3=hs\)。令 \(p(x,y,s)=-2s^2x+3sy^2-3s^3y\)，定义 \(F=h-p(x,y,s)-1\in R=\mathbb C[h,u,v,w]\)。

主定理（Theorem 1.1）：\(R/(F)\cong\mathbb C^{[3]}\)，且梯度 \(\nabla F\) 在点 \(P=(2,0,-1/2,1/2)\) 处为零（\(P\) 位于纤维 \(F=-1\) 上）。多项式自同构的 Jacobi 矩阵处处可逆，其第一分量的梯度不能在任何点为零，故 \(F\) 不是坐标；零纤维因同构于 \(\mathbb A^3\) 而光滑。

推论（Corollary 1.2）：对每个 \(n\ge4\)，都存在 \(f\in\mathbb C[z_1,\ldots,z_n]\) 使商环为 \(\mathbb C^{[n-1]}\) 而 \(f\) 不是坐标——把 \(F\) 添加变量即可，临界点障碍保持。三变量情形本文未处理。

## 证明思路

证明分正反两步。第一步证零纤维是仿射空间，核心是一个对任意交换基环都成立的提升引理（lifting lemma）：若 \(B\) 中元素 \(h,x,y,s\) 满足 \(x^2+y^3=hs\) 且 \((h,y)=B\)，则 \(B[U,V,W]\) 模去三条关系 \(U^3+hV-x\)、\(-U^2+hW-y\)、\(S(h,U,V,W)-s\) 后同构于 \(B[T]\)。证明先做替换 \(G=V+UW\) 把关系线性化；再取 Bézout 系数 \(\alpha h+\beta y=1\)，把两条相容的线性方程（相容性恰由尖点关系保证）用系数组合生成 \(1\) 的方式、不经任何除法地解出第三个变量；最后 \(U=hT-\beta x\)、\(G=yT+\alpha x\) 与 \(T=\alpha U+\beta G\) 互逆，把代数等同于 \(B[T]\)。妙处在于基环允许零因子、方程系数并非单位，一切都在"生成单位理想"的层面完成。

应用时取辅助代数 \(B=\mathbb C[h,x,y,s]/(h-1-p,\,x^2+y^3-sh)\)。平移 \(X=x+s^3\)、\(Y=y-s^2\) 配合恒等式 \(X^2+Y^3=x^2+y^3-sp\) 恰好把 \(B\) 变成 \(\mathbb C[X,Y,s]/(X^2+Y^3-s)\cong\mathbb C[X,Y]\)；\((h,y)=B\) 由"模 \((h,y)\) 得 \(x^2=0\) 与 \(1=2s^2x\)，平方得 \(1=0\)"验证。把引理用在这个 \(B\) 上，三条关系恰好消去 \(x,y,s\)，剩下的一条正是 \(F=0\)，于是 \(R/(F)\cong B[T]\cong\mathbb C[X,Y,T]\)：零纤维显式同构于 \(\mathbb A^3\)，附录还给出双向多项式坐标和单位理想条件的多项式证书。

第二步证 \(F\) 不是坐标。回到环境环，同样的恒等式给出 \(X^2+Y^3=s(1+F)\)。在 \(P\) 处 \(x=-1\)、\(y=1\)、\(s=1\)、\(p=2\)，于是 \(X=Y=0\)、\(F=-1\)；微分上式得 \(2X\,dX+3Y^2\,dY=(1+F)\,ds+s\,dF\)，在 \(P\) 处退化为 \(dF=0\)，即 \(\nabla F(P)=0\)。这正是 Shpilrain–Yu 强调的临界点障碍：若 \(F\) 是某多项式自同构的第一分量，该自同构在 \(P\) 的 Jacobi 矩阵第一行全为零、行列式为零；但自同构有多项式逆，链式法则要求其 Jacobi 矩阵处处可逆——矛盾。添加变量后新变量的导数全为零，原四个导数在 \((P,0,\ldots,0)\) 仍为零，障碍保持，得到任意维数的反例。文中还指出 \(h,x,y,s\) 都落在三角导子（triangular derivation）\(h\partial_u-3u^2\partial_v+2u\partial_w\) 的核中，与 Maubach 的三角单项式核计算相呼应。

## 可信度与备注

主结果已 Lean 形式化。同族十月的姊妹篇进一步加强：构造出每条纤维都是 \(\mathbb A^3\)、添加一个变量即成坐标、却不是坐标的多项式，同时推翻稳定坐标猜想；那篇暂无形式化证明。按 OpenAI 官方声明，未经形式化的结果可能有问题。本文正面部分全为显式多项式恒等式（附录给出逆映射），反面部分只用一次 Jacobi 论证，结构简单、易于独立复核。

{% endraw %}
