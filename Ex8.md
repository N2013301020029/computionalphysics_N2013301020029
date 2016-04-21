# 第八次作业 习题2.8
## 摘要：
  按照习题2.8的要求，利用euler-chrom方法来求解一个非线性方程：
  ![1](http://7xrn0b.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-04-21%20%E4%B8%8A%E5%8D%8810.19.12.png)
  
  我们设定不同的初始值来满足不同振幅的要求，并探索振幅和周期的关系。
## 正文：
### 求解方程图像： 
按照euler-chrom法，我们首先将该方程分成两个一阶方程：
![2](http://7xrn0b.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-04-21%20%E4%B8%8A%E5%8D%8810.21.42.png)

之后如下简单的for循环代码：
        for i in range(5000):
		        w=w-np.sin(y)*b*dt
	        	y=y+w*dt
        		t=t+dt
	        	x=t
	        	plt.plot(x,y,".-r")
之后选取一系列振幅值，一下分别是振幅为0.1，0.2，0.5，0.8，1，1.1,1.5,
3,4,的图形：
![3](http://7xrn0b.com1.z0.glb.clouddn.com/01.png)
![4](http://7xrn0b.com1.z0.glb.clouddn.com/02.png)
![5](http://7xrn0b.com1.z0.glb.clouddn.com/05.png)
![6](http://7xrn0b.com1.z0.glb.clouddn.com/08.png)
![7](http://7xrn0b.com1.z0.glb.clouddn.com/11.png)
![8](http://7xrn0b.com1.z0.glb.clouddn.com/3.png)
![8](http://7xrn0b.com1.z0.glb.clouddn.com/4.png)

可以看出，对于不同的振幅，周期也不同，而且从列举的几个例子中看不出其中的规律，
为此要尝试将振幅-周期图徐昂画出来

### 振幅-周期图像：
基本方法是：找到相邻的一对波峰和波谷，将他们的横坐标相减即为周期的一半，
将他们的纵坐标相减即为振幅的两倍。：

      for q in range(10000):
    	      y1=A	
            my=y1
            ny=y1
    	      x1=t
            mx=x1
            nx=x1
    	
        	for i in range(2000):
        		w1=w
        		w=w-np.sin(y1)*b*dt
        		y1=y1+w*dt
        		t=t+dt
        		x1=t
        		if y1>my:
        			my=y1
        			mx=x1
        		else:
        			my=my
        			mx=mx      #此if条件找出波峰处的横纵坐标
        		if y1<ny:
        			ny=y1
        			nx=x1
        		else:
        			ny=ny
        			nx=nx      #此if条件找出波谷处的横纵坐标
        		if t>0.01:
        			  if w1*w>0:
        				  continue
        			  else:
        			  	break 
		        else:
			          continue     #这个if嵌套循环的意思是，由于欧拉法是离散的计算，因此不同周期
                                     中的峰值可能会略有不同，为防止寻峰过程一直持续下去，我们需要
                                     在找到一个锋后立即停止此次for循环，这样，我们就找到了相邻两                        
                                     个锋的横纵坐标，将他们的横坐标相减即为周期的一半。所以，我们
                                     在w即斜率变号的时候终止循环。
	A=A+0.005
	y=abs(nx-mx)*2
	x=A-0.005
	plt.plot(x,y,".-r")
