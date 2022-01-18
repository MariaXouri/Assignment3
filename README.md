# Assignment3



## Part 1 

## Question 1

# Validation of McPAT : 

The main focus of McPAT is to provide an accurate power and area model, with timing given as a design constraint. There are two kinds of accuracy, especially important for the power modeling: *absolute* and *relative*.
- Absolute accuracy: it shows that the power of individual components of a cpu McPAT model design , computed within the thermal design power (TDP) limits and perhaps focused on saving power for the cpu or the whole system , is evaluated correctly and is near the results of the real cpu design.

- Relative accuracy: the changes in the McPAT model are relative to the changes of the in the real design, so the power weights of the cpu elements are estimated correctly, compared to the real cpu design.

For this reason, the McPAT model needs to be validated , with its output compared to the published results of real processors.
The processors that were used are:
1) 90 nm Niagara , 1.2 GHz, 1.2 V power supply
2) 65 nm Niagara2 , 1.4 GHz, 1.1 V 
3) 65 nm Xeon, 3.4 GHz, 1.25 V 
4) 180 nm Alpha 21364 , 1.2 GHz, 1.5 V

The validation is detailed, checking the McPat results from modeling in and out - of - order , single threaded , or multithreaded processors and is based on parameters, such as clock rate, working temperature and architectural parameters of real processors. Especially the clock rate is the upper bound for the timing design.

# Niagara :

Published power and area:  63 W / 378 nm2

McPAT result: 56.17 W / 295 nm2

Error: 10.84%

# Niagara2 :

Published power and area:  84 W / 342 nm2

McPAT result: 69.7 W / 248 nm2

Error: 17.02%

# Xeon :

Published power and area:  150 W / 435 nm2

McPAT result: 116.08 W / 362 nm2

Error: 22.61%

# Alpha :

Published power and area:  125 W / 396 nm2

McPAT result: 97.9 W / 324 nm2

Error: 21.68%

![Στιγμιότυπο οθόνης 2022-01-15 113810](https://user-images.githubusercontent.com/94965416/149617229-b6fb1e63-e2cd-42d6-8f15-98609f859798.png)



## Question 2


**Dynamic power:** CPU 's logic gates are responsible for dynamic power consumption due to their activation.As the logic gates are toogling, energy flows while the capacitors inside them charge and discharge.Dynamic power is equal to: 


![Screenshot from 2022-01-07 18-14-38(1)](https://user-images.githubusercontent.com/94965416/148574062-e5f4d777-60b1-43ad-b84c-5868ddc9d902.png)

C is the switched load capacitance, f is frequency, V is voltage


**Static power:** In contrary to dynamic power, static power is consumed while there is no circuit activity.It can be characterised as fixed or stationary. In CMOS, it is defined as power consumption due to constant current from VDD to the ground in the absence of switching activity.


![Screenshot from 2022-01-07 18-50-09](https://user-images.githubusercontent.com/94965416/148578033-6eaa7d3c-c8b1-4f42-ada7-20887b200ca2.png)




**Short-circuit power:** Short circuit power refers to the theoritical current that will run in the event of a short circuit through the pull up and pull down devices of the transistor without protection. It can be found by the following formula:

![image](https://user-images.githubusercontent.com/94965416/148650172-8d4c1f73-1507-4ec4-818b-a5da88fe416f.png)

**SHORT CIRCUIT DISPLAY**

![image](https://user-images.githubusercontent.com/94965416/148650779-1dd92035-dd02-49d3-9c7b-fdf983751325.png)


**Leakage:** leakage is the gradual transfer of electrical energy across a boundary normally viewed as insulating, such as the spontaneous discharge of a charged capacitor, magnetic coupling of a transformer with other components, or flow of current across a transistor in the "off" state or a reverse-polarized diode.It can also mean an unwanted transfer of energy from one circuit to another.**GATE LEAKAGE**:As the continuous down-scaling of the device size has lead to very thin gate oxides, the leakage current that can flow from the channel to the gate comes into the order of the subthreshold leakage current and the gate cannot be considered as an ideally insulated electrode anymore. This affects the circuit functionality and increases the standby power consumption due to the static gate current. It consists of subthreshold and gate leakage.Two tunneling mechanisms are responsible for the gate leakage.The gate leakage drastically reduces the maximum clock cycle time. **SUBTHRESHOLD LEAKAGE**: It is a leakge that is inadequate to produce a response subthreshold dosage a subthreshold stimulus.It is mainly due to drain-induced barrier lowering or DIBL.The source is then able to inject charge carriers into the surface of the channel resulting in subthreshold leakage current. DIBL is pronounced in high drain voltages and short channel devices.



![Screenshot from 2022-01-07 18-14-38](https://user-images.githubusercontent.com/94965416/148578165-f41179eb-9081-444b-8461-3318f6b3b317.png)


*IF WE RUN DIFFERENT PROGRAMS IN THE SAME CPU, WHICH OF THE ABOVE WILL BE AFFECTED? DOES IT MATTER HOW BIG IS A PROGRAM?*

![image](https://user-images.githubusercontent.com/94965416/148652805-28d6ef3f-8435-4e00-8e09-f2e61d67bc27.png)


![Στιγμιότυπο οθόνης 2022-01-15 120230](https://user-images.githubusercontent.com/94965416/149617989-833f1fbb-fc8b-44a9-9811-ef8648ff49e0.png)



If we observe these diagrams, we can realise that in a specific CPU the dynamic ( memory dynamic in the second diagram ), static ( memory standby of the second diagram ), leakage and system power change if we run a different program.As we reduce the area,we see that in each program , power,EDP, EDAP change and we understand that the difference in energy between the programs becomes bigger.
The IPC and the power are analog, so the running time of a program affects the power.

![image](https://user-images.githubusercontent.com/94965416/149622165-b6435507-b085-4099-9478-97efcfca3448.png)

For instance, we tried two different benchmarks: SPECHMMER and SPECBZIP

**SPECHMMER**


![Screenshot from 2022-01-16 20-24-25](https://user-images.githubusercontent.com/94965416/149682007-6925f5b9-02a3-4363-8a42-20d12576bf0b.png)


**SPECBZIP**

![Screenshot from 2022-01-17 01-07-52](https://user-images.githubusercontent.com/94965416/149682016-4f88705a-bd23-4ae1-8b21-1ea1905ccabb.png)


All the reuslts are different, which means that all powers are being affected by the program change.





## Question 3:

If we use the 35 W processor, the battery life may be longer, if it is more energy( or power ) efficient than the 25 W , or it uses techniques for reducing power.

Energy efficient means that it uses the least possible energy for a program. 

When the power is constant, less energy for a task means less running time for this task, so we can reduce running time and save the energy of the battery , or we can run more programs and tasks until the battery energy finishes, so we gain to the effectiveness.

Using tecniques for reducing power dynamically, such as dynamic voltage or frequency scaling, low power state for dram , we can adjust the power to the activation state of the program, which means that we can reduce power when it is not needed.


////////// McPAT ------------ the results






## Question 4 : Why Xeon can't be more energy efficient than ARM A9 although it performs better?


Xeon runs 40 times faster: Meaning that it has a better performance level.

Energy efficiency means as low energy consumption as possible.It is described by the following equation:
![image](https://user-images.githubusercontent.com/94965416/149975111-e7829102-631a-4027-8aec-8cc941a0cf2f.png)


 The easiest way to minimize energy consumption is to scale the supply voltage Vcc. However, in CMOS circuits scaling Vcc can lead Vth (threshold voltage) to operate below threshold level which can delay τSwitching which in turn causes leakage energy component to become the dominant contributor to ETotal.This fact shows that low energy consumption doesn't affect performance in a good way.
 
 Reverse Body Biasing (RBB) technique increases the threshold voltage and thus brings an exponential reduction in leakage power. However, the increase in threshold voltage reduces gate overdrive (VDD − Vt), reducing circuit's performance (VDD is voltage of the power supply and Vt threshold voltage). Either scaling VDD or increasing Vt slows down switching. Considering dynamic or leakage power independently, the performance can be traded for power by scaling either VDD or Vt. As in both cases, performance degradation is linear to the scaling of the VDD or Vt, whereas power savings are either quadratic or exponential, the resulting improvement in EDP is substantial.


**POWER CONSUMPTION**
To reduce power consumption we can:

1. Decrease in the total gate number
2. Decrease of clock frequency 

![Screenshot from 2022-01-11 16-53-42](https://user-images.githubusercontent.com/94965416/148965858-ed5e4459-ad73-4daf-ab85-924a04778231.png)




## Part 2

### Question 1 : How can we find AREA,DELAY and ENERGY metrics?

#### AREA

**Core** : total area is: 121.7895454 mm^2  **L2** : total area is: 16.0033 mm^2

#### DELAY

The CPU time = CPU cycles / Clock rate can be found in the xml files. For example, <stat name="total_cycles" value="118294773" /> describes the total CPU cycles.The clock rate can be found by <param name="clock_rate" value="2000"

#### ENERGY

Energy = (leakage + dynamic)*runtime (formula from print_energy.py)

Leakage can be found by "total leakage", dynamic can by found by "Runtime Dynamic" and runtime by statistics.


--------------------------------------------------------------------------------------------------------------------------





**TOTAL RUNTIME DYNAMIC**

**Core** : 149.740847 W/s

Time elapsed = Energy / Runtime Dynamic = 114,6457415 / 149,740847 = 0,765627708 s


**L2** : 7.23071 W/s

Time elapsed = Energy / Runtime Dynamic = 3.16559 / 7.23071 = 0,437797948 s


/////////// EDAP
------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Question 2 : How area and peak power are affected by cache size, associativity and block size? Show the results using diagrams.

#### CORE

![image](https://user-images.githubusercontent.com/94965416/149531931-ec92fd73-42ad-4c4f-80b0-3c6a56512a76.png)

![image](https://user-images.githubusercontent.com/94965416/149532680-bf8bdb50-331a-459b-a954-7dade4def70e.png)

![image](https://user-images.githubusercontent.com/94965416/149534755-b07e4d93-899c-4113-8194-38369351cbef.png)

![image](https://user-images.githubusercontent.com/94965416/149553711-8644b6f1-fb07-429d-80cc-2abe3d132e67.png)

![image](https://user-images.githubusercontent.com/94965416/149557503-2d13ec4a-dcd1-4516-9e86-d9275707707b.png)

![image](https://user-images.githubusercontent.com/94965416/149558988-b43f8ec3-2def-4a29-9244-cecb9f12ddb0.png)




![image](https://user-images.githubusercontent.com/94965416/149541585-57c20065-5969-4901-bc41-413ab06e47a8.png)

![image](https://user-images.githubusercontent.com/94965416/149542544-caecb1f7-a4fe-445a-bdb9-b03a3e3e54da.png)

![image](https://user-images.githubusercontent.com/94965416/149543098-18187301-fc42-46f0-9f9f-eac1947c5de4.png)

![image](https://user-images.githubusercontent.com/94965416/149621777-3b539669-1b1a-44d4-815b-7919c0571168.png)










#### L2

![image](https://user-images.githubusercontent.com/94965416/149537560-3639010d-5518-4335-9734-ee494f9117b0.png)

![image](https://user-images.githubusercontent.com/94965416/149539548-897e3122-ecb6-460a-b634-fdaf4cae644c.png)

![image](https://user-images.githubusercontent.com/94965416/149540495-938e95f0-3c17-439e-a4c3-79fbb0512420.png)

![image](https://user-images.githubusercontent.com/94965416/149554978-9a3486ae-3027-4673-9166-bcdf895f46ef.png)

![image](https://user-images.githubusercontent.com/94965416/149558141-98352a6a-40fd-47e6-a8dd-d9ad0e54369f.png)




![image](https://user-images.githubusercontent.com/94965416/149544440-33c3888f-482a-447d-8575-885eaebd55e1.png)

![image](https://user-images.githubusercontent.com/94965416/149545371-f2a24b99-86e5-4638-8265-8a24eb858a9a.png)

![image](https://user-images.githubusercontent.com/94965416/149545915-2a88c88d-701b-45c4-aabc-c2831694ee5f.png)

![image](https://user-images.githubusercontent.com/94965416/149556585-97a2f149-5e0e-4eb2-9cf2-42f76db3f01a.png)

![image](https://user-images.githubusercontent.com/94965416/149559516-fb462ccd-ca4b-43fb-80ba-fd0e70757d3b.png)


## Question 3:

We will try to notice how the area and the peak dynamic power are affected by the changes in the parameters l1 d , l1 i , l2 cache size, associativity, cacheline size. 

For the types, we will use ar for area and b = log(y / ymin) - 1 , where y is the value of the parameter ( l1d, l1i, l2, a, cl ) and ymin is the minimum value of this parameter.
l1d min=64 KB 
l1i min=64 KB
l2 min=512 KB 
a min=1,1,2
cl min=64 KB

We suppose that y>ymin.

bl1d=log(l1d / 64) -1
bl1i=log(l1i/64) -1
bl2=log(l2/512) -1
ba=log(a/1) -1
bcl=log(cl/64) -1


## Core:


* ## Area:
 
 * l1 i cache: ar = 9.61665 * 1.25 * 0.8936 ^ bl1i
 
 * l1 d cache: ar = 7.22483 * 0.6837 * 0.58 ^ bl1d
  
 * l2 cache:   ar is not affected .  ar = 7.22483
 
 * associativity :  ar = 7.15183 * 1.0102 * 0.9834 ^ ba

 * cacheline size : ar = 7.22483 * 1.528 * 1.59 ^ bcl


* ## Peak dynamic power:

 * l1 i cache: ar = 2.54945 * 1.1 * 0.966 ^ bl1i
 
 * l1 d cache: ar = 1.95501 * 1.108 * 0.96 ^ bl1d
  
 * l2 cache:   ar is not affected .  ar = 1.95501
 
 * associativity :  ar = 1.92264 * 1.017 * 1.15 ^ ba

 * cacheline size : ar = 1.95501 * 2.743 * 1.1857 ^ bcl


## L2:


* ## Area:

 * l1 i cache: ar is not affected . ar = 7.0038
 
 * l1 d cache: ar = 1.72115 * 4.069 * 0.245 ^ bl1d
  
 * l2 cache:   ar = 1.57638 * 6.056 * 0.314 ^ bl2 
 
 * associativity :  ar = 7.69091 * 1 * 0.91 ^ ba

 * cacheline size : ar = 7.038 * 5.4607* 0.3 ^ bcl


* ## Peak dynamic power:

 * l1 i cache: ar is not affected . ar = 0.539842
 
 * l1 d cache: ar = 0.539842 ^ ( - |bl1d | ) (absolute value)
  
 * l2 cache:   ar = 0.33841 * 1.5952 * 0.766 ^ bl2
 
 * associativity :  ar = 0.5397 * 1 * 1 ^ ba

 * cacheline size : ar = 0.539842 * 3.7 * 0.95 ^ bcl



We can observe that with some values of different parameters, the same area or peak dynamic power is achieved . This is the same as the area or peak dynamic power that is achieved when we change the parameters that can not affect them ( l2 cache for the core and l1 d cache for the l2 ).

## Core:

* ## area:
 
 * l1 d cache = 64 KB
 
 * l2 cache = 512 KB , 2 MB , 4 MB 
 
 * associativity = 1 , 1 , 2
 
 * cacheline size = 64 KB                            /////////// Area = 7.22483




* ## peak dynamic power:
 
 * l1 d cache = 64 KB
 
 * l2 cache = 512 KB , 2 MB , 4 MB 
 
 * associativity = 2 , 2 , 4
 
 * cacheline size = 64 KB                           //////////// peak dynamic power = 1.95501



## L2:

* ## area:

 * l1 i cache = 64 KB , 128 KB , 256 KB
 
 * l1 d cache = 128 KB , 256 KB 
  
 * l2 cache = 2 MB 
 
 * associativity = 4 , 4 , 8                        ///////////// Area = 7.0038


* ## peak dynamic power:

 * l1 i cache = 64 KB , 128 KB , 256 KB
 
 * l1 d cache = 64 KB , 256 KB 
  
 * l2 cache = 2 MB 
 
 * associativity = 4 , 4 , 8                      ////////////// peak dynamic power = 0.539842
                   
                   


When we set these values to the parameters, the area or the peak dynamic power are the best for the EDAP to be best optimized.
* For the core :

  EDAP = power * delay ^ 2 * area = 7.22483 * 1.95501 * delay ^ 2 = 14.1246 * delay ^ 2

* For the L2 :

  EDAP = power * delay ^ 2 * area = 7.0038 * 0.539842 * delay ^ 2 = 3.78 * delay ^ 2
   



The cost is analog to the area .


The cost function that we estimated in part 2 is:

## Cost = 5x + 5y + 5z + 3w + 1q 



The performance function is:

## Performance = 5x + 3y + 1.5z +1w + 1q 

In part 3 , it seems that the parameters that affect the area and the cost are :   associativity > cacheline > l1 i > l1 d > l2
The new function can be :


## Cost 


In part 3 , it seems that the parameters that affect the power and the performance are :  associativity > cacheline > l1 i > l1 d > l2
The new function can be :

## Performance 






The effectiveness , according to part 2 , is :

![image](https://user-images.githubusercontent.com/94965416/149675640-b2ae2d72-c402-45aa-947f-ed0691f08a79.png)


























 








 










wikipedia

https://www.ijert.org/research/energy-efficiency-in-processors-a-survey-IJERTCONV3IS21013.pdf

https://www.edaboard.com

https://www.slideshare.net/sdpable/power-consumption

https://www.iue.tuwien.ac.at/phd/stockinger/node17.html

https://hcis-journal.springeropen.com/articles/10.1186/s13673-015-0046-x
