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




wikipedia
https://www.edaboard.com
https://www.slideshare.net/sdpable/power-consumption![Uploading Screenshot from 2022-01-07 18-50-09.png…]()
https://www.iue.tuwien.ac.at/phd/stockinger/node17.html
