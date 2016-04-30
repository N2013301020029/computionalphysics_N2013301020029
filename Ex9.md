# 第九次作业
物基一班  李浩波  2013301020029
## level 1：
### 非线性受迫阻尼震动：
#### 摘要：
按照教材给出的非线性阻尼受迫震动的二阶微分方程
![1](http://7xrn0b.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-04-30%20%E4%B8%8A%E5%8D%8810.01.24.png)

像以前一样将他分解为两个微分方程：
![2](http://7xrn0b.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-04-30%20%E4%B8%8A%E5%8D%8810.01.15.png)

之后用euler-crom方法求它的近似解：
![3](http://7xrn0b.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-04-30%20%E4%B8%8A%E5%8D%8810.01.30.png)
 在初始条件w=0，theta=0.2，q=0.5，Wd=2/3，g=l=9.8的条件下求解，分别汇出w-t，theta-t和w-theta的图像，比较不同绘图条件下的异同。
 #### 正文：
 在Fd=1.2的条件下，首先画出theta-t的图像：
 ![4](http://7xrn0b.com1.z0.glb.clouddn.com/figure_1.png)
 
 可以看出将theta限制在【-pi，pi】的区间内其随t的图像无规律可循
 
 不对theta的取值进行限制，他的图像为：
 ![5](http://7xrn0b.com1.z0.glb.clouddn.com/1_2theta_t.png)
 
 同样是无规律的震动
 
 我们再画出theta和w的图像
 
 ![7](http://7xrn0b.com1.z0.glb.clouddn.com/allthetaw.png)
 
 出现明显的混沌现象，毫无规律可循。
 
为了更简单明了的分析 theta-w图像，我们将上图分成几部分画出，
也就是将受迫力相位为2pi整数倍的部分画出，再把受迫力峰值时的图像画出以及pi/4整
数倍的部分画出。

首先看受迫力相位为2pi整数倍时的图像：
![10](http://7xrn0b.com1.z0.glb.clouddn.com/2npi.png)

这个图像简单的多。随后我们设定不同的初始值，发现这个图像几乎是完全一样的！
就是说即使我们无法预测theta和t的关系，但是可以预知theta和w的关系。

在画出受迫力相位为峰值时的图像：
![11](http://7xrn0b.com1.z0.glb.clouddn.com/0_5pi.png)

这个图像呈现出明显的中心对称性，就是说，如果我们只需知道一半的图像就可以预知另一半的图像行为。

再画出受迫力相位为pi/4整数倍是的图像：
![12](http://7xrn0b.com1.z0.glb.clouddn.com/0_25pi.png)

容易看出这个图像当然是包括上一个图像的，但是复杂的多，但依然呈现出很高的中心对称性。
## level 2:
## 一、微调受迫力的的振幅和频率，观察吸引子图像的变化
首先对受迫力的振幅进行微调：
先把Fd逐渐减小，起初的图像变化不大，到Fd=1.5的时候出现明显变化，从这个点开始细微调节：
Fd=1.155
![a](http://7xrn0b.com1.z0.glb.clouddn.com/fd=1-155.png)
Fd=1.152
![x](http://7xrn0b.com1.z0.glb.clouddn.com/fd=1-152.png)
Fd=1.151
![c](http://7xrn0b.com1.z0.glb.clouddn.com/fd=1-151.png)
Fd=1.1505
![c](http://7xrn0b.com1.z0.glb.clouddn.com/fd=1-1505.png)
Fd=1.1504
![v](http://7xrn0b.com1.z0.glb.clouddn.com/fd=1-1504.png)
Fd=1.1503
![w](http://7xrn0b.com1.z0.glb.clouddn.com/fd=1-1504.png)
Fd=1.15025
![d](http://7xrn0b.com1.z0.glb.clouddn.com/fd=1-15025.png)
Fd=1.15024
![f](http://7xrn0b.com1.z0.glb.clouddn.com/fd=1-15024.png)
Fd=1.15022
![c](http://7xrn0b.com1.z0.glb.clouddn.com/fd=1-15022.png)
Fd=1.1502
![b](http://7xrn0b.com1.z0.glb.clouddn.com/fd=1-1502.png)
![n]()
![1]()
![w]()
![d]()
![f]()
![z]()
![n]()
![b]()
![n]()
![m]()
![k]()
![l]()
![h]()
 
 
 
 
 
 
 
