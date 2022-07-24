## Content of Repository
**DS18B20 Body Temperature Sensor**
|File|Content  |
|--|--|
|main.py  | Python script for reading the value of sensor and some logic |
|sensor.py| Python script that contains all neccessary functions to read the temperature for the sensor|
|wiringDiagram.jpg| Wiring diagram to install the sensor|
|wiringDiagramFritzing.fzz| Fritzing file of the wiring diagram shown in wiringDiagram.png |

## Wiring and Raspberry Pi Setup

**Used Material**
- Raspberry Pi 3
- DS18B20 Body Temperature Sensor
- Resistor 4,7k ohm

**Wiring to Raspberry Pi**

You can see the wiring diagram below
![Wiring Diagram](https://raw.githubusercontent.com/MuhammadNauvalDwiAfandi/sic-ta-w5/master/wiringDiagram.jpg)

Here's detailed information about wiring diagram:

|DS18B20|Raspberry Pi  |
|--|--|
|GND  |Raspberry Pi GND |
|DQ |Raspberry Pi GPIO 17|
|VDD |Resistor 4,7k ohm|
|Resistor|Raspberry Pi 3v3|

**Enable 1-Wire**
 - Open terminal, type `sudo raspi-config`
 - Select *Interfacing Option*
 - Enable *1-Wire*
 - Back to terminal, type `sudo modprobe w1_gpio` then `sudo modprobe w1_therm`

## Script Read Temperature
Here we are using Python to show the temperature. There are two Python scripts, one (sensor.py) contains all necessary functions to read temperature for the sensor, another one (main.py) contains function to read and some logic to determine health based on body temperature.

**Use Case**
- Suhu di bawah 36C = Error: Suhu terlalu rendah
- Suhu di antara 36 - 37,5C = Normal
- Suhu di antara 37,5 - 38,5C = Sakit ringan
- Suhu di atas 38,5C = Sakit parah

## How to Use
 - Hold the sensor using one of your hands
 - In Raspberry Pi, run terminal, navigate to where you put the script
 - Run the script by typing `sudo python main.py` *Note: this script must be run by the root user*

## About Repository
This repository is for Samsung Innovation Campus 3 Technical Assignment Week 5: IoT Hardware with Python

Here's the problem:
>Menggunakan sebuah sensor  _**selain sensor ultrasonic HC-SR04**_, buatlah hal-hal berikut:
>
>1.  Wiring diagram untuk sensor tersebut menggunakan fritzing ( upload dalam MD files screenshot wiring diagram tersebut )
>2.  Script sensor.py dan sebuah fungsi untuk mengambil data dari sensor tersebut
>3.  Sebuah script utama  [main.py](http://main.py/)  yang terdiri dari sebuah logic sederhana yang menjawab sebuah use case sederhana ( jelaskan use case tersebut dalam MD files! )
>4.  (Optional) Ambil sekitar 5 - 10 sample data dan tampilkan dalam sebuah grafik matplotlib dan screenshot hasil tersebut dan upload pada MD files.

Copied from: [SIC Stage 3 Technical Assignment Week 5](https://github.com/impactbyte/iot-with-python-technical-assignments/tree/main/05-IoT-Hardware-2)