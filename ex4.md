# The 4th Homework:exercise 1.4
## Summury:
  In this particle we will use python to edit a program to solve the 
  following radioactive decay problem approximatelly:
  
  ![problem](http://7xrn0b.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-03-21%20%E4%B8%8B%E5%8D%883.16.23.png)
  
  We will use a tool called 'matplotlib'which is designed for python to draw pictures.This will help 
  us to analyse our problem intuitively.
## Text:
  We will use Euler method to deal with this radioactive problem:
  this method is very simple which told us that f(t+∆t)=f(t)+(f(t))/dt ∆t
  According to the differencial equation given we can use Euler method to approximate Na and Nb little 
  by little.
### We write the following program:
  
        import numpy as np
        import matplotlib.pyplot as plt
        import math

        x = np.linspace(0, 60, 10000)

        plt.figure(figsize=(8,4))
        na=10000                              # we assume the initial number of A and B
                                              # particles are 10000
        nb=10000
        t=0
        dt=float(0.004)                       #the dt which we can change
        ta=float(0.1)                         #reciprocal of tao a.
        for i in range(10000):
                nb=float(nb-dt*nb+dt*ta*na)
                na=float(na-dt*ta*na)
                t=float(t+dt)
                x1=float(t)
                y1=float(na)
                x2=float(t)
                y2=float(nb)
                i=i+1
                plt.plot(x1,y1,'y.-')
                plt.plot(x2,y2,'y.-')
        
        x3=x
        y3=np.exp(0-ta*x)*10000          #analystic sollusion of Na
        plt.plot(x3,y3,label="analystic sollusion of na",color="blue",linewidth=2)
        x4=x
        y5=np.exp(0-x)*10000*0.5
        y4=ta/(1-ta)*y3+y5               #analysyic sollusion of Nb
        plt.plot(x4,y4,label="analystic sollusion of nb",color="red",linewidth=2)
        plt.xlabel("Time(s)")
        plt.ylabel("Number")
        plt.title("Radioactive Decay")
        plt.ylim(0,10000)
        plt.legend()
        plt.show()
  THERE is an attention we need to notice that when Ta comes to 1s,the Nb formula is no longer 
  right,and it should be Nb=10000(1+x)exp(-x).
### Run the program:
  We assume that tb=1s and it would remain 1s so that we need to only change the value of ta to change
  the ratio of ta and tb.
#### We take a serie of values of Ta and see how the pictures change:
    we take Ta=10s,5s,1.2s,1.0s,1.2s,1.5s,3.0s separately,and the pictures are:
    ![1](http://7xrn0b.com1.z0.glb.clouddn.com/t10.png)
    ![1](http://7xrn0b.com1.z0.glb.clouddn.com/t5.png)
    ![1](http://7xrn0b.com1.z0.glb.clouddn.com/t25.png)
    ![1](http://7xrn0b.com1.z0.glb.clouddn.com/t125.png)
    ![1](http://7xrn0b.com1.z0.glb.clouddn.com/t1.png)
    ![1](http://7xrn0b.com1.z0.glb.clouddn.com/t56.png)
    ![1](http://7xrn0b.com1.z0.glb.clouddn.com/t23.png)
    ![1](http://7xrn0b.com1.z0.glb.clouddn.com/t13.png)

