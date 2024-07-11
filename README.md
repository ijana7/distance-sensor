## Distance Sensor with ESP32
 ## link 

 https://wokwi.com/projects/402788800054477825

This simple project demonstrates how to use an ultrasonic distance sensor to measure the distance between the sensor and surrounding objects using an ESP32 board.

## Description

The Distance Sensor project is an ESP32-based application that uses an HC-SR04 ultrasonic sensor to measure distance in centimeters. The sensor works by emitting an ultrasonic pulse and then detecting the time it takes for the pulse to reflect off nearby objects and return to the sensor. This time of flight is then used to calculate the distance.

# here i change the Distance Sensor to 259

<img width="1521" alt="‏لقطة الشاشة ١٤٤٦-٠١-٠٥ في ٩ ١١ ٠٩ م" src="https://github.com/ijana7/Controlling-the-robot-arm/assets/173642526/5dd3b8c9-04c8-4d49-8796-8af7ddc03b25">

## Components

- ESP32 development board
- HC-SR04 ultrasonic sensor
- Jumper wires

## How It Works

1. Connect the ESP32 board to the HC-SR04 ultrasonic sensor using the following pins:
   - Trig pin (GPIO 5)
   - Echo pin (GPIO 18)

2. The `setup()` function initializes the serial communication and sets the Trig and Echo pins as output and input, respectively.

3. In the `loop()` function:
   - The Trig pin is set to LOW for 2 microseconds to ensure a clean high pulse.
   - The Trig pin is then set to HIGH for 10 microseconds, which triggers the sensor to emit an ultrasonic pulse.
   - The Trig pin is set back to LOW.
   - The `pulseIn()` function is used to measure the time it takes for the ultrasonic pulse to reach the Echo pin.
   - The distance is calculated using the formula:

   ```
   dist_in_cm = duration * speed_of_sound / 2;
   ```

   where `duration` is the time it took for the pulse to travel to the object and back, and the constant `speed_of_sound` is 0.34 cm/microsecond.

4. The calculated distance is then printed to the serial monitor.

## Usage

1. Upload the Arduino sketch to your ESP32 board.
2. Open the serial monitor to view the measured distance in centimeters.
