# Assignment3



## Part 1 

## Question 1

# Validation of McPAT : 

The main focus of McPAT is to provide an accurate power and area model, with timing giving as a design constraint. There are two kinds of accuracy, especially important for the power modeling: *absolute* and *relative*.
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



## Question 3:

If we use the 35 W processor, the battery life may be longer, if it is more energy( or power ) efficient than the 25 W , or it uses techniques for reducing power.

Energy efficient means that it uses the least possible energy for a program. 

When the power is constant, less energy for a task means less running time for this task, so we can reduce running time and save the energy of the battery , or we can run more programs and tasks until the battery energy finishes, so we gain to the effectiveness.

Using tecniques for reducing power dynamically, such as dynamic voltage or frequency scaling, low power state for dram , we can adjust the power to the activation state of the program, which means that we can reduce power when it is not needed.


////////// McPAT ------------ the results






## Question 4 : Why Xeon can't be more energy efficient than ARM A9 although it performs better?

After taking into consideration that Xeon performs 40 times faster than ARM A9 we can understand that this fact might affect its energy efficiency level.Energy efficiency means using as lower energy as possible.Data shows that Dynamic power can be decreased by
1. Decrease in the total gate number
2. Decrease of clock frequency 

![Screenshot from 2022-01-11 16-53-42](https://user-images.githubusercontent.com/94965416/148965858-ed5e4459-ad73-4daf-ab85-924a04778231.png)

A small value of clock frequency simultaneously means a low performance.That is the reason why Xeon can't be as energy efficient as wanted.


## Part 2

### Question 1 : How can we find AREA,DELAY and ENERGY metrics?

#### AREA

**Core** : total area is: 121.7895454 mm^2  **L2** : total area is: 16.0033 mm^2

#### DELAY

#### ENERGY

Energy = (leakage + dynamic)*runtime (formula from print_energy.py)

Leakage can be found by "total leakage", dynamic can by found by "Runtime Dynamic" and runtime by statistics.


--------------------------------------------------------------------------------------------------------------------------


Runtime dynamic is equal to the energy consumed divided by the time elapsed.
the timing model uses
both resistance and capacitance to compute RC delays

To measure the delay (latency), we can use the Runtime Dynamic = Energy/Time elapsed



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

![image](https://user-images.githubusercontent.com/94965416/149552651-1748aac5-470d-452a-8b80-427bb64a62c6.png)

![image](https://user-images.githubusercontent.com/94965416/149556133-02db8972-4d5e-43ec-86e2-c1c11a70b0a1.png)








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







wikipedia

https://www.ijert.org/research/energy-efficiency-in-processors-a-survey-IJERTCONV3IS21013.pdf

https://www.edaboard.com

https://www.slideshare.net/sdpable/power-consumption

https://www.iue.tuwien.ac.at/phd/stockinger/node17.html
