What is this? 
--- when working on my AMS solution i kept putting more and more stuff into a single box and everytime i needed to make a change it was $200 for a board that may or may not work so i decided to make it easier on myself to split the sensors up so that it isn't a bespoke solution for a single car application. 

these are the sensor hardware designs that match up with https://github.com/TJLTM/Automotive-Monitoring-System-CANBus-Sensor-FW repo so that i can keep the Hardware designs over here and the FW over there. mostly just so i'm not in some weird state where i'm working on a FW for one thing and the hardware for another and get into a screwed up merge situation. this has happened before in my other projects. 

If you look at the other repo you'll see i've made provisions for the following sensors 
* Temp (ADC)
* Voltage (ADC)
* Vacuum
* I/O
* RPM 

the ones marked as (ADC) are the same hardware but different firmware since the only thing that really changes in those setups are the sensor hooked up to the ADC and what scale is fed into the 10bit ADC 

The other boards ahve the hardware built on to the boards since those require some type of special sensor

Vacuum sensor 
This one is something that i've been working on for a while since there aren't many direct vacuum sensors out there and it took me a while to figure out this design as most vacuum sensors or MAPs so a bit of math to do it. They take the Barometric pressure and then making a few assumptions use the differential to standard atmospherical pressure to give you the vacuum. The design i am using is a direct measurement of the vacuum via the honeywell sensor. Yes it's expensive to build. In fact it costs more to make one of those then all the others combined. 

RPM sensor 
this one is a straight foreward design and i may make it an add on module for the ADC since really it's just a Freq to Voltage Sensor 

The I/O box... 
That one i'm making it a standard 8 in and 8 out setup. can be made to i don't know.... hook into power window units in older cars that can then be remotely controlled or in my case add power windows to some cars.



I'm using my other design for power https://github.com/TJLTM/LM2670SX-Carrier but if you don't like it. BYOPS
