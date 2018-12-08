# ARM_experiments

I2C GPIO extension and SYSTICK interrupt experiment




I. Experimental purposes
-----

Understand the I2C bus standard and how to call the TM4C1294 chip.
Master the method of extending GPIO chip PCA9557 and TCA6424 with I2C bus.
Ability to output illuminating LEDs and dynamic digital tubes by extending GPIO.
Familiar with SYSTICK interrupt calling mode, master the method of simulating multitasking switching with soft timer.




II. Experimental requirements
-----
1. The routine is the initialization of two chips, PCA9557 lights all LEDs; TCA6424 controls the digital tube display 0 in the first place; read and understand.
2. Perform the marquee experiment of the LED. When the LED is lit at a certain position, the corresponding LED tube number is displayed at a certain position of the digital tube. For example, when LED marquee, LED1\~LED8 are illuminated from left to right, and then 1~8 is displayed on the digital tube.
3. 2-digits marquee:<br>
    First step shows 1,2
    Marquee display LED1, 2                
    The second step shows 2,3         
    Marquee display LED2, 3       
    . . .       
    Step 8 shows 8,1    
    Marquee display LED8,1       
    Step 9 Back to the first step        
    **code in ans2-4.c**        

4. Use USR_SW1 to control the frequency of the marquee：<br>
Press once, the interval is 1S      
twice, the interval is 2S      
thrice, the interval is 0.2S          
Press the 4th, return to the initial state of power-on, interval 0.5S.         
**code in ans2-5.c**

5. <br>Please program the clock function on the digital tube, and display the minute + second on the left end of the digital tube, where the minutes and seconds are 2 digits. For example, 12:00.
When the number of seconds reaches 60, the automatic minute is incremented by 1, and the number of seconds returns to 00. The minutes and seconds display range is 00~59


>>* When USR_SW1 is pressed, the number of seconds is automatically increased by 1

>>* When USR_SW2 is pressed, the minute is automatically incremented by 1

>>* When one or two of the above buttons are not released, the corresponding display jumps are automatically incremented by one every 200 mS. That is, press USR_SW1 1S as follows, then display the number of seconds to jump plus 5


>> **code in ans2-6.c**

III. Framework
--------------------
![framework](https://github.com/DanDanZee/ARM_experiments/raw/master/img/framework.png)
