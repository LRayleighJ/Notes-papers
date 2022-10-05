# 21 cm cosmology in 21st century

##  Atom Hydrogen（$H_{I}$）的21cm谱线的相关物理过程

氢原子核和电子磁矩的相互作用导致氢原子1S能级的超精细分裂（两个能级），从而产生21cm线，这两个能级的能量差为$\Delta E = 5.9\times 10^-6eV$，对应的频率为1420MHz，波长为21.1cm。这个频率是天体物理学中最精确的已知量之一。其他原子的超精细结构也可以提供用以进行宇宙学测量的谱线，例如$^3He^+$的8.7GHz谱线和21cm线的92cm氘类似物，但是这几种元素和中性氢相比丰度要低得多。

### 影响21cm谱线特征强度的物理机制

辐射强度（Intensity）的基本输运方程为
$$
\frac{dI_\nu}{ds} = -\alpha_\nu I_\nu+j_\nu
$$
第一项为吸收项，第二项为发射项。我们讨论的范围一般不会超越Rayleigh-Jeans极限的限制，即相关光子的频率远小于CMB黑体辐射的中心频率，于是我们可以定义一个亮度温度（Brightness Temperature）
$$
I_\nu = \frac{2k_BT\nu^2}{c^2}
$$
将辐射传输方程变形，即两边除以吸收系数$\alpha_\nu$，之后定义光学深度（optical depth）
$$
d\tau = \alpha_\nu ds
$$
对传输方程进行积分得到下面的结果
$$
T_b^{obs} = T_{ex}(1-e^{-\tau_\nu})+T_R(\nu)e^{-\tau_\nu}
$$
该式描述了辐射信号穿越光学深度为$\tau_\nu$的介质后亮度温度的变化。其中$T_R$为辐射源的亮度温度，$T_{ex}$为激发温度（uniform excitation temperature），$T_b^{obs}$为观察者观测到的亮度温度。

21cm线的激发温度也可以称作自旋温度(spin temperature)$T_S$，它通过两个超精细级（我们用下标0和1分别表示1S单简并态和1S三重简并态）中氢原子的数量密度之间的比率来定义。
$$
\frac{n_1}{n_0} = \frac{g_1}{g_0}\exp(-\frac{T_*}{T_S})
$$
其中$g_1/g_0=3$（直接使用玻尔兹曼分布的结论），$T_* = \Delta E/k_B = hc/k_B\lambda_{21cm}=0.068K$

根据以上定义，一团星系介质中的光学深度可以写成下面的形式
$$
\tau_\nu = \int ds[1-\exp(-E_{10}/k_BT_S)]\sigma_0\phi(\nu)n_0
$$
其中$n_0 = n_H/4$，即为处于1S超精细结构低能态的原子数目。标记21cm发射截面（指cross section）为$\sigma_nu = \sigma_0\phi(\nu)$，$\sigma_0 = 3c^2A_{10}/8\pi\nu^2$，其中$A_{10}=2.85\times 10^{-15}s^{-1}$为自旋翻转的自发衰减率，$\int \phi d\nu=1$。

为了计算上面这个积分，需要确定从发射处到观察者的路径长度$s(\nu)$。计算$s(\nu)$需要考虑到红移效应，即找到光经过的$ds$的频率变化$d\nu$，以确定在路径上各处的介质实际感受到的频率。这个物理图景可以通过以下两种方式中的任意一种理解：

* 将路径长度和宇宙学膨胀关联起来，即
  $$
  ds = -\frac{cdz}{(1+z)H(z)}
  $$
  并使用$\nu_{obs}=\nu_{em}/(1+z)$

* （在低红移区域）使用哈勃定律局域的线性速度近似$v=(dv/ds)s$并使用多普勒定律$\nu_{obs}=\nu_{em}(1-v/c)$

光深在所研究的范围内对亮温度的影响很小。亮温度对应的变化为
$$
\delta T_b = \frac{T_S-T_R}{1+z}(1-\exp(-\tau_\nu))\\
\sim \frac{T_S-T_R}{1+z}\tau\\
\sim 27x_{HI}(1+\delta_b)(\frac{\Omega_bh^3}{0.023})(\frac{0.15}{\Omega_mh^2}\frac{1+z}{10})^{1/2}(\frac{T_S-T_R}{T_S})[\frac{\partial_rv_r}{(1+z)H(z)}]mK
$$
$x_{HI}$是中性氢的占比组分，$\delta_b$是重子的部分超密度（fractional overdensity in baryons），最后一项由沿视线的速度梯度$\partial_rv_r$产生。

以下三个物理过程对自旋温度产生影响

* 来自CMB等背景辐射源的21cm光子的发射/吸收
* 氢原子和其他氢原子以及电子的碰撞
* $Ly\alpha$光子的共振散射，该效应通过一个中间激发态引起自旋翻转

这些过程的特征时间相比于中性氢原子的去激发时间是很短的，于是最终的自旋温度是这种效应的平衡。在这种近似之下，各种效应综合之后的自旋温度可以写成下面的形式
$$
T_S^{-1}=\frac{T_{\gamma}^{-1}+x_\alpha T_{\alpha}^{-1}+x_c T_{K}^{-1}}{1+x_\alpha+x_c}
$$
其中$T_{\gamma}$为周围环绕的辐射场的温度，通常等于CMB温度，$T_\alpha$为$Ly\alpha$频率下$Ly\alpha$辐射场的色温度（color temperature），在重复散射过程中通过反冲作用与气体动力学温度$T_K$（热运动温度）紧密耦合。$x_{i}(i=\alpha,c)$是碰撞和$Ly\alpha$散射的耦合系数。当$\sum x_i$大于1时，自旋温度和气体温度强耦合，当$\sum x_i$远小于1时自旋温度和背景辐射的温度近似相等。

对于21cm线，有两种背景射电源是重要的。第一种是CMB源。我们可以使用CMB作为背景射电源。在这种情况之下，$T_R = T_{CMB}$。由于CMB背景源的温度波动很小，约为$\delta T_{CMB}\sim 10^{-5}K$，于是CMB可以作为一个均匀的背景射电源。对不同红移的谱线进行观测可以绘制不同红移处的中性氢分布等性质，由此可以绘制出宇宙的三维分布图。intensity mapping也是21cm谱线观测的一项重要任务。

第二种重要的射电源是具有强辐射的点源，例如强辐射类星体。在这种情况下，背景源的辐射比弥散的氢原子的弱发射强得多，即$T_R>>T_S$，在这种情况之下气体展现出的性质为对背景源进行一个吸收。和背景源距离不同的一系列中性气体区会产生一系列吸收线，和“$Ly\alpha$森林”类似，这一系列吸收线可以被称作"21cm线森林"。背景源的高辐射强度使得可以以极高的分辨率研究21cm森林，从而探测IGM（星际间戒介质，Intergalactic Medium）的细微结构。

注意我们前面讨论的许多“温度”并不是真正的热力学温度，$T_R$和$\delta T_b$是辐射强度的测量，$T_S$度量了两个超精细结构能级氢原子的相对占据数，$T_\alpha$是描述$Ly\alpha$跃迁附近的光子分布的颜色温度。只有CMB的背景黑体辐射温度和气体的热运动温度$T_K$是真正的热力学温度

### 碰撞耦合

不同粒子之间的碰撞可能会引起氢原子的自旋翻转，并在气体密度较高的早期宇宙中主导耦合。有三个主要的渠道：两个氢原子之间的碰撞和一个氢原子与电子或质子之间的碰撞。碰撞耦合系数如下所示
$$
x_c^i=\frac{C_{10}}{A_{10}}\frac{T_*}{T_\gamma}=\frac{n_i\kappa_{10}^i}{A_{10}}\frac{T_*}{T_\gamma}
$$
$C_{10}$是碰撞激发率，$k_{10}^i$是与第i种组分碰撞产生的自旋脱激率系数。

总碰撞耦合系数可以写成下面的形式
$$
x_c = x_c^{HH}+x_c^{eH}+x_c^{pH}\\
=\frac{T_*}{A_{10}T_{\gamma}}[K_{1-0}^{HH}(T_K)n_H+K_{1-0}^{eH}(T_K)n_e+K_{1-0}^{pH}(T_K)n_p]
$$
其中$k_{1-0}^{HH}$为氢原子之间的散射率，$k_{1-0}^{eH}$为氢原子和电子之间的散射率，$k_{1-0}^{pH}$为氢原子和质子之间的散射率。确定这几个散射率需要进行量子力学计算，其中中性氢原子之间的碰撞和气体的动力学温度$T_K$相关。在实际应用中有用的拟合结果如下：

* H-H散射：（在$10K<T_K<10^3K$范围内是适用的）
  $$
  K_{1-0}^{HH}\approx 3.1\times10^{11}T_K^{0.357}\exp(-32/T_K) cm^3s^{-1}
  $$

* e-H散射：（$T_K<10^4K$，当$T_K>10^4K$时，$\kappa=\kappa(T_K=10^4K)$）
  $$
  \log(k_{1-0}^{eH}/cm^3s^{-1})=-0.967+0.5\log T_K\times \exp[-(\log T_K)^{4.5}/1800]
  $$

在宇宙早期的“黑暗年代”，耦合主要由碰撞作用主导。一些尚未被探明的碰撞物理过程对21cm线的细节是有影响的。例如，前文的计算全部假定碰撞散射截面和速度无关，但在真实的过程中，速度会对超精细能级的原子数分布带来影响，给21cm谱线强度带来的影响大概在5%左右。

### Wouthuysen-Field效应

当宇宙中的第一批星系开始形成之时，$Ly\alpha$光子带来的共振散射提供了另一个耦合的影响因素。中性氢原子跃迁的能级图如下

![HI energy](E:\LRayleighJ\NAOC\笔记\21cmCosmo\WFeffect.jpg)

 假设初始时氢原子处在超精细结构单态，吸收一个$Ly\alpha$光子后中性氢原子根据选择定则跃迁到2P中可能的超精细态，之后原子可以发射一个$Ly\alpha$光子重新回到1S态，在这个过程之中可能出现电子的自旋翻转，产生21cm线发射。这是该效应的物理图像。

经过计算，$Ly\alpha$的耦合系数由下式给出
$$
x_\alpha= \frac{4P_\alpha}{27A_{10}}\frac{T_*}{T_\gamma}
$$
其中$P_\alpha$是$Ly\alpha$光子的散射率。

单个中性氢原子散射$Ly\alpha$光子的散射率由下式给出
$$
P_\alpha = 4\pi \chi_\alpha\int d\nu J_\nu(\nu)\phi_{\alpha}(\nu)
$$
其中$\sigma_\nu=\chi_\alpha \phi_\alpha(\nu)$为局域吸收截面，$\chi_\alpha=\frac{\pi e^2}{m_ec}f_\alpha$为$Ly\alpha$跃迁的振动强度（oscallation strength of $Ly\alpha$ transition），$\phi_\alpha(\nu)$为$Ly\alpha$的吸收率曲线，$J_\nu(\nu)$为经过角平均之后的背景源的$Ly\alpha$的辐射强度（以光子数进行计量）。最后的耦合系数可以写成
$$
x_\alpha= \frac{16\pi^2T_*e^2f_\alpha}{27A_{10}T_\gamma m_ec}S_\alpha J_\alpha
$$
其中$S_\alpha=\int dx\phi_\alpha(x)J_\nu(x)/J_\infty$，$J_\infty$是去除吸收特征后的流量，作为一个定标的常数

根据上式可以计算一个使得$x_\alpha=S_\alpha$的特征流量，即$x_\alpha=S_\alpha J_\alpha/J_\alpha^C$，$J_\alpha^C=1.165\times 10^{10}[(1+z)/20]cm^{-2}s^{-1}Hz^{-1}sr^{-1}$，这个特征量可以用单个氢原子散射的$Ly\alpha$光子数目作为单位来表示，即$J_\alpha^C/n_H=0.0767[(1+z)/20]^{-2}$。根据经验，只要星体开始形成，这个条件就是满足的。

前面所述的物理学将自旋温度和辐射场的色温耦合起来。后者描述了辐射场在$Ly\alpha$线附近辐射场随频率的分布形状，由下式定义
$$
\frac{h}{k_BT_c}=-\frac{d\log n_\nu}{d\nu}
$$
即$n_\nu=n_0\exp(-h\nu/k_BT_c)$，玻尔兹曼分布的形式变换。其中$n_\nu=c^2J_\nu/2\nu^2$为光子的布居数（occupation number）。

一般情况之下，$T_C=T_K$，这是因为$Ly\alpha$散射的光学深度非常大，使得大量$Ly\alpha$光子将辐射场和气体带入了局域平衡。对于这个物理过程可以使用一种“光子流”的思想来理解，宇宙学红移使得一部分光子以固定的速率从高频率流向低频率，当光子流入$Ly\alpha$频率时，他们将被散射到较高或较低的频率。由于散射截面是对称的，可以认为光子流是守恒的。散射重新分配了光子，导致了频谱关于谱线的不对称性。这个不对称性最终引发了辐射场和色温的耦合。这个特征的形状决定了$S_\alpha$，并且由于反冲的来源是吸收特征，所以确保$S_\alpha<1$。在低温下，散射反冲的影响更大，对Wouthuysen-Field效应的抑制也最明显。如果IGM是温暖的，那么这种抑制就可以忽略不计了。上述讨论忽略了光子的分布被自旋交换所改变的过程，该过程会使$T_S$和$T_C$的确定相当复杂。然而，自旋翻转对光子分布的影响是很小的，水平不到10%。

对于上述参数的有效近似如下：$S_\alpha\approx\exp(-1.79\alpha)$，其中$\alpha = \eta(3a/2\pi\gamma)^{1/3}$，$a=\Gamma/(4\pi\Delta\nu_D)$，$\Gamma$是21cm线高能级的反转寿命，$\Delta\nu_D/\nu_0=(2k_BT_K/mc^2)^{1/2}$是多普勒参数，$\nu_0$是谱线的中心频率，$\gamma=1/\tau_{GP}$，$\eta=(h\nu_0^2)/(mc^2\Delta\nu_D)$是由于反冲引起的每次散射的平均频率漂移。

> 在天体物理学方面，我们将主要对从低于$Ly\beta$共振的频率红移到$Ly\alpha$共振的光子感兴趣。此外，$Ly\alpha$光子还可以通过原子级联(cascade)从光子红移到更高的Lyman系共振中产生。这些原子级联如图所示，其中$Lyn$光子转换为$Ly\alpha$光子的概率由原子速率系数设定。对于大的n，大约30%的转换是典型的。这些光子被注入$Ly\alpha$线，而不是从线外被红移。这改变了它们对耦合的贡献，因为现在的光子分布是单侧的。与上述类似的过程适用于这些光子的重新分布，它们可以导致$Ly\alpha$通量的放大。

$Ly\alpha$耦合对21cm信号的影响大约在10%左右。关于$Ly\alpha$辐射输运跃迁还需要更多的工作以理清细节。
