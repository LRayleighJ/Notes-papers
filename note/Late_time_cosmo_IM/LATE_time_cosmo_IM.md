# intensity mapping的特征尺度和红移演化

对于星系红移巡天，Fisher矩阵的形式为
$$
F_{ij}^{galaxy}=\frac{1}{2}\int_{k_{min}}^{k_{max}}\frac{d^3k}{(2\pi)^3}[\partial_i\ln P_{tot}(\vec{k})\partial_j\ln P_{tot}(\vec{k})]V_{eff}\\
V_{eff}=V_{bin}[\frac{\bar{n}(z)P_{tot}(\vec{k})}{1+\bar{n}(z)P_{tot}(\vec{k})}]
$$
可以有一个很知名的结果，即
$$
<(\frac{\Delta P_a}{P_a})^2>=[\frac{1}{2}\int_{V_n}\frac{d^3k}{(2\pi)^3}V_{eff}(\vec{k})]^{-1}
$$
对等的，对于Intensity mapping而言，
$$
(\frac{\Delta P_a}{P_a})^2=[\frac{1}{2}U_{bin}\int_{V_n}\frac{d^2qdy}{(2\pi)^2}(\frac{C^S(\vec{q},y)}{C^T(\vec{q},y)})^2]^{-1}
$$
可以定义有效体积$V_{eff}^{IM}$和一个等效数密度$\bar{n}^{IM}P(\vec{k})=\frac{C^S}{C^N}$，即
$$
\bar{n}^{IM}(z,\vec{k})=(\frac{T_b}{T_{sys}})^2\frac{t_{tot}\Delta\nu}{U_{bin}}B_{\perp}^2B_{\parallel}\mathcal{L}^{-1}
$$
暂时没有考虑前景项的影响。对于上述出现的各个物理量，有以下性质

* $V_{eff}^{IM}$是高度各向异性的，对于SD survey，小于beam角分辨率的信息都会被冲掉。IF可以看到更为细微的角分辨率结构
* 在径向，前景消除带来的信息损失是在带宽的尺度损失的。在小尺度上，非线性速度抹除了$k\geq 0.15Mpc^{-1}$的信息。

总结：在大尺度之上，宇宙学变量和调查尺度是主要影响的因子。

* 对于SD survey，最大波长的模在径向和横向可以很好地辨识出来，$\frac{\Delta P}{P}^2\propto k^{-3}$，对于较小的尺寸，beam size限制了横向分辨率，$\frac{\Delta P}{P}^2\propto k^{-1}$。径向最终会遇见非线性速度效应，抹掉小于$\sigma_{NL}$的信息。
* 对于IF survey，情况和SD相反且互补，由于较长的基线，$IF$可以有更好的角分辨率，$\frac{\Delta P}{P}^2\propto k^{-3}$，直到达到non linear scale。越过这个极限之后只有横向分辨率的贡献，直到达到最大分辨率。对于IF对应的上限，IF无法探测到大于其最小基线对应的尺度，对应构成干涉阵的单碟的直径，SD模式之下的beam大小（所以说SD和IF模式可以很好地衔接）。

对应的几个特征尺度为

* 在径向，带宽限制k的下限$k_{\parallel}^{min}=\frac{2\pi}{r_{\nu}\Delta\widetilde{\nu}_{tos}}$，非线性尺度限制k的上限$k_{\parallel}^{max}\sim 1/\sigma_{NL}$
* 在切向，对于SD survey而言，k的下限（对应最大的尺度）由调查面积决定，$k_\perp^{min}=2\pi/\sqrt{r^2S_{area}}$，k的上限（对应最小的尺度）则由beam size 决定，$k_{\perp}^{max}=2\pi D_{dish}/r\lambda$
* 在切向，对于IF survey而言，k的下限（对应最大的尺度）为$k_\perp^{min}=2\pi D_{min}/r\lambda$，k的上限（对应最小的尺度）为$k_\perp^{max}=2\pi D_{min}/r\lambda$，由干涉仪的性能决定

思考一下我们应该怎么做性能评估

除了限制观测范围之外，还需要使用Fisher矩阵进行参数的不确定度估计。

此外其他的性能问题，比如我们达到预期的观测效果需要多长的观测时间。具体的参数限制需要怎样，即在不同的红移区间段对各个参数的约束，以及对应的观测时间限制。需要再回去看那几篇文章。

不涉及前景和噪声的因素。
