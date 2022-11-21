# Forecast for FAST: from galaxies survey to intensity mapping

> 在本文中，我们通过模拟观测对FAST的HI大尺度结构观测进行了预测。我们考虑用L波段19波束接收器进行漂移扫描观测，这可能与脉冲星搜索和银河系HI观测相适应。我们还考虑了在较低频率下的调查，使用目前的单馈宽频接收器或未来的超高频波段的多波束相控阵馈电（PAF）。我们估计了探测到的HI星系的数量密度，并使用Fisher矩阵和模拟观测对位置的测量误差和调查的精度进行了评估。我们估计了HI星系功率谱的测量误差，发现即使在中等红移的情况下，误差也比较大，因为随着红移的增加，正面探测到的星系数量急剧下降。然而，良好的宇宙学测量可以通过强度绘图技术获得，在这种技术中，大尺度的HI分布被测量，而不需要解析单个星系。我们估算了不同观测时间下暗能量状态方程的优点，发现利用现有的L波段多波束接收器，可以获得对低红移大尺度结构的良好测量，这是对现有光学观测的补充。用超高频波段的PAF，约束可以更强，达到暗能量任务组第四阶段实验的水平。
>
> 中性氢（HI）的21厘米线为射电波段的观测提供了一个很好的替代方法。一些HI星系调查也已经开展，例如HIPASS调查（Meyer等人，2004；Zwaan等人，2004），ALFALFA调查（Giovanelli等人，2005；Giovanelli等人，2007；Saintonge，2007），以及JVLA深度调查Jarvis等人（2014）。然而，受限于望远镜的灵敏度，这些调查的红移范围要比目前的光学调查小很多。
>
> 在本文中，我们通过模拟观察到的星系做了更详细的调查，同时也比较了星系调查和强度图。本文的布局如下。在第2节中，我们描述了我们的望远镜及其接收器的模型。 在第3节中，我们介绍了HI星系的建模和它们的观测，以及模拟的强度图。在第4节中，我们用HI星系观测和强度图观测对功率谱测量的精度进行了Fisher矩阵预测，同时也用数字模拟进行了测量。第5节讨论了HI星系调查和HI强度测绘调查的利基以及前景的影响。最后，我们在第6节中总结了这些结果。

使用19beam L-band接收机进行了观测，对于IM在高红移的时候用了1-beam wide-band接收机。将HI Galaxy Survey和HI intensity mapping的结果进行了对比，基于Fisher矩阵对测量误差进行了评估。

请注意，本工作采用的是模拟观测数据。

## FAST的接收机

现在有三个接收机

![](E:\LRayleighJ\NAOC\WORK\note\receiverofFAST.png)

beamsize按照下式估算
$$
\theta = 1.22\times\frac{21cm(1+z)}{300m}=2.94(1+z)arcmin
$$

## 积分时间 和 噪声分析

drift scan survey的速度和地球自转速度相关，漂移过单个pixel所用的时间为
$$
t_{pix} = 2.9(1+z)/(\omega_e\cos \delta)
$$
双偏振单波束的热噪声可以估计为
$$
\sigma_{noise} = \sqrt{2}\frac{k_BT_{sys}}{A_{eff}}\frac{1}{\Delta \nu t}
$$
t为总积分时间，$\Delta \nu$为频道的频率带宽。天线效率大概有70%，对应的$A_{eff}\sim 50000m^2$，系统温度为$T_{sys}=T_{rec}+T_{sky}$。$T_{sky}$可以建模为
$$
T_{sky}=2.73+25.2\times(0.408/\nu_{GHz})^{2.75}K
$$
如果假设velocity line width 为$5kms^{-1}$，每个beam的积分时间为48s，beam的瞬时敏感度为$0.86mJy$。噪声模型可以按照下面的步骤进行建模，设时间流数据和信号的关系可以写成下面的形式
$$
d=As+n
$$
d为时序数据矢量，维度为$19N_t$，$N_t$为时间序列数据的长度，time pixel向量的维度为$N_{pix}$，

对sky的最小方差估计为
$$
\hat{s}=(A^tN^{-1}A)^{-1}A^tN^{-1}s
$$
N为噪声的时序数据的协方差矩阵，sky map covariance matrix矩阵如下
$$
C_N = (A^TN^{-1}A)^{-1}
$$

## 数值模拟

### 星系模型

使用S^3-sax的catalog。

![114514](E:\LRayleighJ\NAOC\WORK\note\simulation.png)

蓝线是mock catalogue的$\Omega_{HI}(z)$，红色是对应smooth之后的结果。绿色虚线来源于MUFASA宇宙学流体模拟给出的结果，即$\Omega_{HI}=10^{-3.45}\times(1+z)^{0.74}$

星系的HI的质量分布可以按照下式进行估计
$$
\Sigma_{HI}(r)=\frac{\tilde{\Sigma}_He^{-r/r_{disk}}}{1+R_{mol}^ce^{-1.6r/r_{disk}}}
$$
$\Sigma_H=M_H/(2\pi r_{disk}^2)$，$R_{mol}^c$是星系中心的$H_2/HI$质量比。

星系的环绕速度按照Polyex analytic function来模拟
$$
V_{PE}(r)=V_0(1-e^{-r/r_{PE}})(1+\frac{\alpha r}{r_{PE}})
$$
HI Flux按照下式给出
$$
\frac{M_{HI}}{M_{\bigodot}}=2.36\times 10^5(\frac{D_L}{Mpc})^2\frac{S_i}{Jy}\frac{dv}{km}s^{-1}(1+z)^{-2}
$$
$S_i$是chnnel i以Jy为单位的flux density，dv是channel的速度宽度，$D_L$是目标星系以Mpc为单位的光度距离。dv是按intrinsic velocity定义的，如果换成observed velocity，后面要换成$(1+z)^{-1}$。使用Obreschkow & Meyer（2014）模拟的光锥目录，该目录横跨天空中10×10 deg2的区域，红移范围为0.0-1.2。该目录包含19210309个星系，总HI质量为$2.065\times 10^{16}M_{\bigodot}$。

### HI Galaxy Detection

为了模拟HI星系的探测，首先将全尺寸的合成数据在RA和DEC中re-bin，使其角度分辨率达到0.08度，相当于FAST beam半峰宽度（FWHM）的2倍。假设每个beam的噪声是高斯的，那么每个像素的噪声就被重新标定为
$$
\sigma_{noise}^{pixel}=\sigma_{noise}^{beam}\times\sqrt{\frac{A_{pix}}{A_{beam}}}
$$
A代表sky area。

在分析频率的时候，在频率轴上，合成数据立方体被重新分档为0.1MHz的分辨率，对应于z=0时的20公里/秒的速度宽度。由于通量和噪声的尺度会随着带宽的变化而变化，如果全尺寸的合成数据被平滑为$W_skms^{-1}$的速度宽度，一个velocity bin的信噪比为
$$
S/N=\frac{F_0/N/W_s}{\sigma_0}\frac{W_s}{5kms^{-1}}^{1/2}
$$
$F_0$是星系的总的按速度积分的HI flux，N是星系所占的所有的速度bin的数目，$\sigma_0$是速度展宽为$5kms^{-1}$的热噪声。

模拟星系探测的步骤如下

* 粗略的分辨率搜索。将充满噪音的数据重新组合为0.08度的角度分辨率（FAST的FWHM的2倍）和0.473MHz的频率分辨率（对应于红移0时100公里/秒的速度分辨率），设置3%的阈值，并检测阈值以上的voxel。
* 精细分辨率拟合。对于在粗略搜索中检测到的星系，使用更精细的频率分辨率（0.0236MHz，对应于红移0时的速度分辨率为5公里/秒），在数据立方体中用参数化的剖面函数拟合其光谱。如果得到一个合理的HI profile，我们就对HI profile进行积分，如果总通量超过5%，就把这个候选者选为星系。在第一步发现的候选星系中，大约20%通过了第二步，其他的可能是大的噪声。
