# 第五次作业：课后题1.6
## 摘要：
  用欧拉方法解决如下问题：
  ![1](http://7xrn0b.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-03-25%20%E4%B8%8B%E5%8D%882.03.30.png)
  用python编程，以matplotlib作图，之后求出解析解作图与近似图像比较
## 正文：
###  编程如下：
        import numpy as np
        import matplotlib.pyplot as plt
        import math
        x= np.arange(0, 30, 0.01)
        y= np.arange(0, 1000,1)
        x, y = np.meshgrid(x,y)
        
        plt.figure(figsize=(8,4))
        na=float(raw_input('choose na='))
        u=na
        t=0
        dt=float(0.001)
        a=float(raw_input('choose a='))             #we choose different constant a 
        b=float(raw_input('choose b='))             #we choose different constant b
                                     
        for i in range(2000):                       #use 'for'loop to Euler mothed
        	na=float(na+dt*na*a-dt*(na**2)*b)
        	t=float(t+dt)
        	x1=float(t)
        	y1=float(na)
        	i=i+1
        	plt.plot(x1,y1,'y.-',linewidth=5)               
        
        	
        
        e=math.e
        plt.contour(x,y,e**(a*x)*(a/b-y)-y*(a/b-u)/u,0) #use contour to draw the picture  
        plt.xlabel("year")           
        plt.ylabel("Population")
        plt.title("population ")
        plt.ylim(0,1000)
        plt.xlim(0,5)
        plt.legend()
        plt.show()
### 运行程序
  首先选择人口初始值100，a=10,b=1,做出图像为：
  ![2](http://7xrn0b.com1.z0.glb.clouddn.com/100101.png)
  
  之后选择初始值1000,a=10,b=0.1,做出图像为：
  ![3](http://7xrn0b.com1.z0.glb.clouddn.com/10001001.png)
### 图像分析：
     可以看出，用欧拉方法描点做出的图像和精确解的图像很好的重合，这说明用欧拉方法做的近似还是
  比较精确的。
    主观上可以看出，N的增长趋势开始为负增长，因为N和N的平方成反比，所以N一开始急剧下降，但是
    b比a要小，所以当N 减小到一定数值时，N对t的全微分逐渐为为0，此时N趋于稳定。这符合人口数量
    的变化规律，最后一定趋于某一稳定值。
## 结论： 欧拉方法在步长较小的情况下的近似效果很好。
   不足：两条曲线的覆盖顺序不知如何调整。
