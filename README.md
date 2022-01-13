# Assignment3



## Part 1 
### Question 2

**Dynamic power:** CPU 's logic gates are responsible for dynamic power consumption due to their activation.As the logic gates are toogling, energy flows while the capacitors inside them charge and discharge.Dynamic power is equal to: 


![Screenshot from 2022-01-07 18-14-38(1)](https://user-images.githubusercontent.com/94965416/148574062-e5f4d777-60b1-43ad-b84c-5868ddc9d902.png)

C is the switched load capacitance, f is frequency, V is voltage


**Static power:** In contrary to dynamic power, static power is consumed while there is no circuit activity.It can be characterised as fixed or stationary. In CMOS, it is defined as power consumption due to constant current from VDD to the ground in the absence of switching activity.


![Screenshot from 2022-01-07 18-50-09](https://user-images.githubusercontent.com/94965416/148578033-6eaa7d3c-c8b1-4f42-ada7-20887b200ca2.png)




**Short-circuit power:** Short circuit power refers to the theoritical current that will run in the event of a short circuit without protection.It can be found by the following formula:

![image](https://user-images.githubusercontent.com/94965416/148650172-8d4c1f73-1507-4ec4-818b-a5da88fe416f.png)

**SHORT CIRCUIT DISPLAY**

![image](https://user-images.githubusercontent.com/94965416/148650779-1dd92035-dd02-49d3-9c7b-fdf983751325.png)


**Leakage:** leakage is the gradual transfer of electrical energy across a boundary normally viewed as insulating, such as the spontaneous discharge of a charged capacitor, magnetic coupling of a transformer with other components, or flow of current across a transistor in the "off" state or a reverse-polarized diode.It can also mean an unwanted transfer of energy from one circuit to another.**GATE LEAKAGE**:As the continuous down-scaling of the device size has lead to very thin gate oxides, the leakage current that can flow from the channel to the gate comes into the order of the subthreshold leakage current and the gate cannot be considered as an ideally insulated electrode anymore. This affects the circuit functionality and increases the standby power consumption due to the static gate current. It consists of subthreshold and gate leakage.Two tunneling mechanisms are responsible for the gate leakage.The gate leakage drastically reduces the maximum clock cycle time. **SUBTHRESHOLD LEAKAGE**: It is a leakge that is inadequate to produce a response subthreshold dosage a subthreshold stimulus.It is mainly due to drain-induced barrier lowering or DIBL.The source is then able to inject charge carriers into the surface of the channel resulting in subthreshold leakage current. DIBL is pronounced in high drain voltages and short channel devices.



![Screenshot from 2022-01-07 18-14-38](https://user-images.githubusercontent.com/94965416/148578165-f41179eb-9081-444b-8461-3318f6b3b317.png)


*IF WE RUN DIFFERENT PROGRAMS IN THE SAME CPU, WHICH OF THE ABOVE WILL BE AFFECTED? DOES IT MATTER HOW BIG IS A PROGRAM?*

![image](https://user-images.githubusercontent.com/94965416/148652805-28d6ef3f-8435-4e00-8e09-f2e61d67bc27.png)

If we observe this diagram, we can realise that in a specific CPU the dynamic power changes if we run a different program.As we reduce the area, we understand that the difference in energy between them becomes bigger.

### Question 4 : Why Xeon can't be more energy efficient than ARM A9 although it performs better?

After taking into consideration that Xeon performs 40 times faster than ARM A9 we can understand that this fact might affect its energy efficiency level.Energy efficiency means using as lower energy as possible.Data shows that Dynamic power can be decreased by
1. Decrease in the total gate number
2. Decrease of clock frequency

![Screenshot from 2022-01-11 16-53-42](https://user-images.githubusercontent.com/94965416/148965858-ed5e4459-ad73-4daf-ab85-924a04778231.png)

A small value of clock frequency simultaneously means a low performance.That is the reason why Xeon can't be as energy efficient as wanted.


## Part 2

RESULTS 

#### AREA

**Core** : total area is: 121.7895454 mm^2


**L2** : total area is: 16.0033 mm^2


#### ENERGY

Energy = (leakage + dynamic)*runtime

Leakage can be found by "total leakage", dynamic can by found by "Runtime Dynamic" and runtime by statistics.

dynamic = runtime dynamic

runtime = taken from StatsFile











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

wikipedia

https://www.ijert.org/research/energy-efficiency-in-processors-a-survey-IJERTCONV3IS21013.pdf

https://www.edaboard.com

https://www.slideshare.net/sdpable/power-consumption

https://www.iue.tuwien.ac.at/phd/stockinger/node17.html
