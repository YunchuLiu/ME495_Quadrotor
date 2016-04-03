##Description 

###connect to ROBOLAB wifi

We first tried to connect to ROBOLAB wifi just by selecting it from the Wifi Networks at the top right. However, it kept switching back to Northwestern Wifi. We then tried to mannually edit the IPV4 settings and it successfully connected at last.

###ssh 

Typing the following command line and enter the password, We connected to our pi wirelessly. The repo was: pi@raspberrypi 

`ssh pi@<our IP address>`

We ran **sample** and the LED turned on, which suggested the successful connection between our laptop and the Raspberry pi. 

###milestones 

The first step was to accomplish the PWM and test it with LED. We defined two variables that set the period to 255 and duty cycle in the range of (0,255) respectively. In the constantly running while loop, when the counter counts from 0 to the duty cycle value, the LED bit is set to HIGH and inverted to LOW in the rest of the period. The counter is reset to 0 when it reaches 255. We verified it working properly by setting different value for duty cycle and observing the change of the brightness. 

Compiled the read_struct.cpp and write_struct.cpp and ran them in separate terminals simultaneously. We tested it and observed that the up and down key press correspond to numbers 259 and 258 stored in shared memory and in read_struct.cpp, we adjusted the value of the duty cycle. The main challenge we met was we intially put the codes for adjusting the duty cycle in a seperate while loop from the pwm control. Since the loop never exited, no brightness change was observed. 

We are still working on the protection of the system, which should turn off the LED if there is no key press for a certain time. The sequence number should not be updated without a key press and there should be a counter/timer that counts the time as the sequence number maintains. Also , the key press value stored in memory should be set to an unrelated value so cover the old one and avoid wrong interpretation. 


##Documented code 

Please see the attached two files for code 


