Final Report: Swamp Cooler Project

CPE 301: Carter Eads, Prisha Malhotra, Kaitlin Wagoner

Introduction
This swamp cooler project uses evaporation to cool and humidify the air. Water stored in the cooler is used to soak a pad and water from outside the cooler is blown through the pad causing this water to evaporate which humidifies and cools the air. This system senses the surrounding temperature, when the temperature rises above 23° Celsius the system turns on, the system turns off after the temperature drops below 23°  Celsius. A water level sensor monitors the water in the reservoir and sends an error notification when the water sensor detects a value below 150.   
States
This system has four states, disabled, idle, running, and error. In the disabled state, all components are off, and the yellow LED is turned on. The system is completely inactive and will switch to the idle state after the start button is pressed. In the idle state the green LED is on, the temperature and water sensors and on but the fan is off. The system displays the water level reading and the temperature reading on the LCD and updates once a minute. In the running state the blue LED, temperature sensor, water sensor, and fan are all on. This state is triggered when the system is in the idle state, and the temperature goes above 28 degrees Celsius. In the running state the LCD monitor displays the temperature and water level sensor readings and updates every minute. The final state is the error state, in this state the red LED is on, the fan is off and the LCD displays an error message. This state is triggered when the water sensor reading drops below 250. Pressing the reset button in this state will return the system to the idle state. When the stop button is pressed in the idle, running, and error state the system returns to the disabled state.  
Components
Elegoo 2560 Mega
This is a microcontroller that controls the device. Code is uploaded to the device and the microcontroller is able to read sensor values from the input pins and control which output pin receives power.
https://admin.arsbook.it/stempdf/LS-ELEGOO-MEGA.pdf
28BYJ-48 Stepper Motor and driver
This is a 5-volt unipolar motor used to open and close the vent in the water cooler design. The motor operates at a frequency of 100Hz and has four phases. For our demonstration video we attached a straw wrapper to show the vent function working. The driver is used to provide enough current to the stepper motor to power it. The Arduino itself does not provide enough power to run the stepper motor so a driver is needed when it is used in the Arduino circuit.
https://www.mouser.com/datasheet/2/758/stepd-01-data-sheet-1143075.pdf?srsltid=AfmBOooQtkMxjRwJFc9SQg6_XWprMopA-PMV9JS0-z-Jq-G47GflLL5c
DHT11 Humidity and Temperature Sensor
This is a simple Arduino compatible temperature sensor that can detect temperatures ranging from 0-50° Celsius. The capacitive humidity sensing capability of this component is not used in this project. The temperature sensor is used to determine when the water cooler switches between the idle state and the running state.
https://www.mouser.com/datasheet/2/758/DHT11-Technical-Data-Sheet-Translated-Version-1143054.pdf?srsltid=AfmBOopUpHb9nxrp3kVVpdj1pPDmujc3p_1fUGoHvtwACA1cZmUGAR-v
Water Level Sensor
This component is a multi-pronged sensor that uses five power traces and five sense traces to determine the depth of water it is submerged in, it has a working current of less than 20mA. This is used in the water cooler to monitor water level and trigger the error state.
https://curtocircuito.com.br/datasheet/sensor/nivel_de_agua_analogico.pdf?srsltid=AfmBOopaBTEslwLYNG9udNQ2dF_uXyvNy7Co6UTbyiOTNOAgs9GxkdzO
Push Button
This tactile switch has a insulation resistance of 100MΩ when in the off state and 100mΩ when in the on state it is rated for up to 50mA and 12V. Four are used in the design the start button sets the system to the idle state from the disabled state and the reset button returns the system to the idle state after it does into the error state, one closes the vent and the other closes the vent.
https://www.arduino.cc/documents/datasheets/Button.pdf
LEDs
This standard LED has a maximum power dissipation of 80mW and a maximum forward current of 5V. Three are used in this device to show the state, red for error, green for running, and yellow for idle.
https://www.farnell.com/datasheets/1498852.pdf
Fan
This is an electric powered fan that is triggered when the system is in the running state. This is a 3v DC motor to power the fan.
https://www.farnell.com/datasheets/1863913.pdf
ds1307 RTC
This component is a real time clock. This provides the current time which is displayed on the LCD.
L293D
The L293D is a driver used to provide sufficient power to the fan motor. This driver increases the current supplied to the fan motor. The Arduino cannot provide enough current to power the fan alone so a driver is required when using the DC powered fan.
https://www.ti.com/lit/ds/symlink/l293d.pdf?ts=1765691444024&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FL293D
LCD 1602
This LCD screen has an operating voltage of -0.3V to 7.0V, a driver supply voltage of -12V to 0.3V, and a input voltage range of -0.3V to 0.3V. This is used to display the temperature recorded by the temperature sensor and the current state of the device.
https://www.waveshare.com/datasheet/LCD_en_PDF/LCD1602.pdf
Potentiometer
The potentiometer in the circuit is used to control the brightness of the LCD screen. A potentiometer is a circuit component that acts as a adjustable resistor. When the resistance is high less power goes to the LCD resulting in lower contrast and when the resistance is high more power goes to the LCD giving a higher contrast.
https://www.mouser.com/datasheet/2/13/RV24AF-1658492.pdf?srsltid=AfmBOooLtuPpD3yPzsqH3ytYJQesEJFnBI3gJpXagIMIzCD5-hIm11vM
Circuit Diagram
The circuit diagram to set up the physical part is below. Due to the evaporative cooling this system works best in dry environments.
 
Figure 1: Final System
 
Figure 2: Schematic Diagram
Environmental Impacts
Energy Efficiency
This system is much more energy efficient than conventional air conditioning systems. The motor used is rated for only 5-volts of energy while most air conditioning systems are rated for upwards of 100-volts. This system is also self-monitoring, it only goes into the running state once the temperature rises above 28° Celsius.
Design Safety
This design uses very little power; it operates at a low voltage and has a very small current. This makes it a very safe design from an electrical hazard perspective. All the circuit components operate in the milliamperes range which is a nondeadly current. 
Affordability
This color uses an electronics kit available on amazon for $65.99, the cooler is a standard Styrofoam cooler for as little as $5. This system is incredibly affordable; many conventional air conditioning units can cost over $100. The power used by this system is also much lower than traditional air conditioning units, meaning that it costs less to run per hour.
Sustainability
Due to the low power consumption this is a sustainable option for cooling a room. This device works using evaporation meaning that it works best in hot dry climates like those in Reno, Nevada. It takes around 2000 kWh per year to operate a conventional air conditioning unit, this unit has lower energy consumption and is ideal for the local climate.
Accessibility
This unit is reasonably accessible, it is easy to make with some knowledge of Arduino, moderate knowledge of C and minimal knowledge of circuit design. This unit is also accessible due to its low cost, making it a good alternative to conventional air conditioning.





[Circuit Diagram](https://app.cirkitdesigner.com/project/16be2c5e-03c9-4ea3-9797-0ab7ed4d2b68)
