# 第七次作业
 2013301020029 李浩波
## 摘要：
    上一次作业中模拟了炮弹的二维轨迹，本次作业将对棒球的飞行轨迹进行模拟。同样适
    用欧拉法进行逐步绘图，但本次要用vpython来实现简单的三维动画模拟，因为本次模拟
    不仅将空气阻力计入，而且将棒球的旋转引起的球的侧面受力不均计入，因此必须适用
    三维模拟。
## 正文：
### 1、原理：
	本次轨迹模拟依然使用欧拉近似法，通过前几次作业可以看出这个方法在模拟抛物轨迹中是
	极其精确的。不同的是，本次抛出的物体是一个粗糙的棒球，考虑到棒球在飞行过程中是带
	旋转的，因此会由于求得侧面气体流速不同而产生不同的压强导致球的轨迹不再仅限于二维
	平面内。此关系在课本中已经给出为
	
![1](http://7xrn0b.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-04-10%20%E4%B8%8B%E5%8D%889.16.50.png)

其中v和w是垂直的，里的方向同时和二者垂直。因此若果已知球在x,y,z轴方向上的旋转分量，
便可求得球在各个方向上的力的分量，以右手定则定义速度、力和角速度的方向，则

![2](http://7xrn0b.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-04-10%20%E4%B8%8B%E5%8D%889.24.44.png)

因此我们只需在炮弹代码中加入这些力和z方向的参数即可。上式中的常参数已由实验给出：

![3](http://7xrn0b.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-04-10%20%E4%B8%8B%E5%8D%889.24.52.png)

### 2、代码和代码运行：
运行python后，在vpython窗口中出现
![4](http://7xrn0b.com1.z0.glb.clouddn.com/Screenshot%20from%202016-04-10%2006:35:09.png)

同时命令界面中可以选择各个方向的角速度以及投出速度大小和方向

![5](http://7xrn0b.com1.z0.glb.clouddn.com/Screenshot%20from%202016-04-10%2006:41:59.png)

选择一些数值来看一下模拟的效果：
1、斜抛轨迹：
![11](http://7xrn0b.com1.z0.glb.clouddn.com/a.png)
![222](http://7xrn0b.com1.z0.glb.clouddn.com/%E8%B7%91%E9%A2%98.gif)

2、若球碰到墙壁则以相反速度反弹：
![22](http://7xrn0b.com1.z0.glb.clouddn.com/b.png)
![111](http://7xrn0b.com1.z0.glb.clouddn.com/%E6%92%9E.gif)

3、假设没有重力，将下旋转速设的很大，轨迹为：
![33](http://7xrn0b.com1.z0.glb.clouddn.com/wuzhonglizao.png)
![444](http://7xrn0b.com1.z0.glb.clouddn.com/%E6%97%A0%E9%87%8D%E5%8A%9B.gif)

看上去球沿该轨道一直运行下去，但实际上由于空气阻力的作用，每次运动的圈都会有所平移，较
长时间后轨迹明显变粗：
![44](http://7xrn0b.com1.z0.glb.clouddn.com/wuzhongliwan.png)

4、在有重力的情况下，相同的初速度和转速，轨迹变为：
![55](http://7xrn0b.com1.z0.glb.clouddn.com/youzhongli.png)
![12](http://7xrn0b.com1.z0.glb.clouddn.com/%E6%9C%89%E9%87%8D%E5%8A%9B.gif)
以上vpython动画视觉效果略矬，仍待改进。
