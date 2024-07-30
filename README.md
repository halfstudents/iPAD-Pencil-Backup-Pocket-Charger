# iPAD-Pencil-Backup-Pocket-Charger
Charge your APPLE pencil anytime anywhere this small pocket charger. Plug and charge! With onboard charge control, boost and charge detect.
To know more detials see my hackster profile: https://www.hackster.io/sainisagar7294/ipad-pencil-backup-pocket-charger-3c0eec

I have a clone iPAD pencil which works in the similar way of Apple pencil, but this one comes with C type and is priced me 1/4th of the original one. It comes with a 50mAH battery which gives an on time of 4 hrs only. This is the problem with most of these clone pencils even also with apple certified ones. And that's why I built a pocket charger for it, so whenever I carry my iPAD in college I can take notes flawlessly. This apple pencil pocket charger is a direct plug and play device. USB type C is used to plug into the pencil and charge it.

![mini_IMG_6248](https://github.com/user-attachments/assets/bf9b4d21-35b5-4552-8d77-9f5f58434c6d)

USB type A on the other side is used to directly plug into any charger or laptop type A port and charge the external 300mAH battery attached to it. Which gives me a total backup of up to 24hrs of constant time. This Apple pencil although have a fast charging mechanism which only takes 10 minutes to charge the internal battery.

![Screenshot_2024_07_28-7](https://github.com/user-attachments/assets/5dbc1a36-4574-43b9-904e-1a3d07af7ffe)

This project is sponsored by PCBWAY, the leading PCB manufacturing company dealing in PCB related products and services. PCBWAY has 10 years experience of working with PCBA, PCB, Stencil, 3D printing and CNC services. https://www.pcbway.com/?from=circuitkicker

Components Required:

![mini_IMG_6230](https://github.com/user-attachments/assets/9b851503-3116-45bf-86d8-475d9c2ea02e)

LP7800K4 charging and booster IC

10uf, 1uf ceramic 603 capacitor

1K resistor 0603 package

0603 package LEDs

USB male type A/ type C

Li-Po battery 300-600mAH

PCBs from PCBWAY 
(https://www.pcbway.com/?from=circuitkicker)

Circuit  Description:
Usually USB devices use 5V charging, and the Li-Po battery is rated 3.7V. So an efficient boost and charge mechanism is required to charge the pencil. For this application an IC LP7800K4 is best suited. I can also make use of TP4056 charge and Mt3068 booster IC integrated on a PCB but then I have to add a lot more circuitry to the PCB.

![Screenshot_2024_07_10-1](https://github.com/user-attachments/assets/f0dea6e4-2cb4-4bf5-98a8-4f560728295c)

And to reduce all that effort of soldering and arranging parts I used this application specific IC available on digikey and LCSC. This IC has plug and play detection feature, which eliminates the need of any onboard switch. This charging detection function makes this device more convenient to use with any type C port.

![Schematic_LP7800K4-PENCIL_2024-07-28](https://github.com/user-attachments/assets/fb96d185-84ff-486f-9964-3d801bfd9815)

LP7800K4 comes with thermal, overcurrent, overvoltage, undervoltage protections. To know more about battery protection circuits check my previous tutorial about battery charging. And the IC features an inbuilt boost converter circuit to convert 3.7V to 5V, with charging optimisation. A very few onboard components are required to make this circuit. See the above modified schematics which is made as per this iPAD pencil charging application. 

PCB file:

![Screenshot_2024_07_28-5](https://github.com/user-attachments/assets/ebf6f6c3-8f2d-4bdb-a5b8-952c7a0171ed)

I turned my schematics into the PCB after completing the net routing. This PCB is sized 3cm X 2cm to fit in the pocket, standard USB ports are used for charging. It can be directly plugged in for charging the on board 300mAH battery or Pencil with its type C port. Two LED indicators show the remaining battery percentage and charge indication. Main IC is placed in the middle of the board surrounded by supported circuitry. Boost converter circuits need an external inductor and capacitor for the frequency generation, here we need a very small indicator with a small capacitor.

![entry](https://github.com/user-attachments/assets/c32a1605-f42f-4c6b-ae10-404d3bbf5759)

This is a 2 layer PCB and I covered all the basic precautions of EMI, Power tracks and Ground return paths. The power tracks and the signal tracks are routed manually for better signal propagation. The capacitors are placed near to the IC to support in power management and lower down input/output noise.

![PCB](https://github.com/user-attachments/assets/1a976cfc-918c-44f1-a03f-7833ed2d898f)

PCB Assembly:

I got the PCB from PCBWAY, which offers better price to performance ratio, has less turnaround time and ships the boards all over the world. After gathering all the components, I soldered them onto this PCB. Starting from the Type C port because it has very small pins, if other components are soldered first then it becomes difficult to solder this USB port on the PCB.

![show 2](https://github.com/user-attachments/assets/13fce144-daee-4569-8f5c-deeb17ccbe38)

I will suggest using a HOT plate in case of manual soldering because these SMT components are very hard to solder with hands. In case you have a microscope to look into the solder joints, hand soldering can be done quickly, otherwise I will suggest going with a Stencil service or assembly service from the manufacturer. Then I stick the battery on the back side of the PCB, with a double sided tape. The connection pins for the battery are given on the back panel and can be easily soldered there.

![battery](https://github.com/user-attachments/assets/ff31a969-d582-4e0a-9147-c3bcab08ccf4)

Modifying the PCB:

![mini_IMG_6250](https://github.com/user-attachments/assets/e1aed3bd-5410-4e7b-92dd-65681dd67985)

I tried many things but the onboard type C port doesn’t support charge detection feature in some cases. That’s why I opted to remove this port and mount a 2 wire USB C wire which comes with this pencil. I connected the red wire of USB C to the output of the IC and Black is grounded. I have changed the USB C port in the Geber file, and given an extra output port in case this thing happens with you. 

![failed 2](https://github.com/user-attachments/assets/4c52c9c7-072b-415b-a3fd-a16c8d4977d2)

Testing and working:

![voltages](https://github.com/user-attachments/assets/42d549d0-91b2-4877-ade6-dd7c88876d15)

I have run some charging tests with this unit after glueing everything in place. It supports a charging current of 250mA which can fully charge the onboard battery in an hour.

![success](https://github.com/user-attachments/assets/ca9cb58e-8709-4627-9570-fc905ae48fb7)

You can plug the device in any universal type A charger or in a laptop port. The device is very handy and easy to work with. Pencil changing detection function is also working on this unit and it can fully charge my pencil in 10 minutes. Now I can keep taking notes on my New iPAD with this small pocket friendly backup charging unit.

![pbank](https://github.com/user-attachments/assets/385e0157-9850-4dc0-990c-46d62f3fea52)

PCBWAY is celebrating its 10th anniversary, marking a decade of providing PCB manufacturing and assembly services. Just 3 days left, go sign-up and grab your reward. https://www.pcbway.com/activity/anniversary10th.html#zero

![Screenshot_2024_07_28-1](https://github.com/user-attachments/assets/453ade6d-c48f-45b2-b537-b7ba5a435af9)

They typically run special promotions, contests, and offer discounts to celebrate milestones like this. 
