# arduino-Timer

The Timer module provides three different kind of Timers, based on standard timer schemes:

```c++
PulseTimer PT(1000);
OnDelayTimer TON(1000);
OffDelayTimer TOF(1000);
```

The `PulseTimer` returns HIGH during the defined time when a rising edge in the input is generated.

The `OnDelayTimer` returns HIGH when the input is HIGH during the defined time and until the input falls.

The `OffDelayTimer` returns LOW when the input is LOW during the defined time and until the input rises.


## Gettings started

### Prerequisites
1. The [Arduino IDE](http://www.arduino.cc) 1.8.0 or higher
2. The [Industrial Shields Arduino boards](http://blog.industrialshields.com/en/installing-industrial-shields-equipment-to-the-arduino-ide/) (optional, used in the examples)

### Installing
1. Download the [library](https://github.com/Industrial-Shields/arduino-Timer) from the GitHub as a "ZIP" file.
2. From the Arduino IDE, select the downloaded "ZIP" file in the menu "Sketch/Inlcude library/Add .ZIP library".
3. Now you can open any example from the "File/Examples/Timer" menu.


## Usage

```c++
#include <Timer.h>
```

### PulseTimer

```c++
PulseTimer PT(1000);

int in = digitalRead(I0_0);
if (PT.update(in) == HIGH) {
    // Enter here during 1000ms after in is rised
}
```

### OnDelayTimer

```c++
OnDelayTimer TON(1000);

int in = digitalRead(I0_0);
if (TON.update(in) == HIGH) {
    // Enter here after I0.0 is HIGH during 1000ms and until it becomes LOW
}
```

### OffDelayTimer

```c++
OffDelayTimer TOF(1000);

int in = digitalRead(I0_0);
if (TOF.update(in) == HIGH) {
    // Enter here after I0.0 is LOW during 1000ms and until it becomes HIGH
}
```
