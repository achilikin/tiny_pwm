# tiny_pwm original project

Firmware for ATtiny45/85 based temperature dependent fan PWM controller

See project page at http://www.nomad.ee/micros/tiny_pwm/

# tiny_fan: modified for Ruideng power supply case with 5V fan.

See project page at [Making Ruideng DPH5005 Power Supply Case Silent](https://achilikin.blogspot.com/2019/01/making-ruideng-dph5005-power-supply.html)

Instead of PWM, simple voltage limiting circuit is used, so fan can be in one of three states:
* OFF
* HALF SPEED, with ~1.4V cut off by 1N4148 diode and 2N7000 FET
* FULL SPEED with ~0.8V cut off by BS170 FET

During the tests I've found that 2N7000 had a bigger voltage drop than BS170 (at least in the batches I have), so I used 2N7000 together with 1N4148 to limit fan speed to the HALF_SPEED mode.

Schematics
----------
![tiny_fan schematics](https://raw.github.com/achilikin/tiny_pwm/master/schematics.png)

Serial output example
---------------------
```
ADC:303 ADJ:300 T:25 Speed:0 %
ADC:304 ADJ:301 T:26 Speed:0 %
ADC:305 ADJ:302 T:27 Speed:0 %
ADC:307 ADJ:304 T:29 Speed:100 %
ADC:308 ADJ:305 T:30 Speed:50 %
ADC:307 ADJ:304 T:29 Speed:50 %
...
ADC:304 ADJ:301 T:26 Speed:50 %
ADC:304 ADJ:301 T:26 Speed:50 %
ADC:303 ADJ:300 T:25 Speed:50 %
ADC:302 ADJ:299 T:24 Speed:0 %
ADC:301 ADJ:298 T:23 Speed:0 %
ADC:301 ADJ:298 T:23 Speed:0 %
```

Board
-----

See details at http://achilikin.blogspot.com/2019/01/making-roudeng-dph5005-power-supply.html
