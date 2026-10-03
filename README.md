# Arduino Ultrasonic Radar

An Arduino-based radar system that uses an ultrasonic sensor and a servo motor to detect objects at different angles. The detected distance and angle are sent to the computer through serial communication and displayed in real time using Processing.

## About the Project

I built this project using an **Arduino Uno, ultrasonic sensor, and a servo motor**.

The ultrasonic sensor is attached to the servo motor, which rotates it through different angles. At each angle, the sensor measures the distance of an object in front of it.

The Arduino then sends the angle and distance values to the computer. I used **Processing** to receive this data and display it as a radar screen.

So the basic flow is:

```text
Servo rotates
      ↓
Ultrasonic sensor measures distance
      ↓
Arduino processes the reading
      ↓
Angle + distance sent through serial
      ↓
Processing displays the radar
```

## Components Used

* Arduino Uno
* Ultrasonic Sensor
* Servo Motor
* Breadboard
* Jumper Wires
* USB Cable

## Software Used

* Arduino IDE
* Processing

## Connections

### Ultrasonic Sensor

| HC-SR04 | Arduino Uno |
| ------- | ----------- |
| VCC     | 5V          |
| GND     | GND         |
| TRIG    | Pin 10      |
| ECHO    | Pin 11      |

### Servo Motor

| Servo  | Arduino Uno |
| ------ | ----------- |
| VCC    | 5V          |
| GND    | GND         |
| Signal | Pin 9       |

## How It Works

The servo moves the ultrasonic sensor from one angle to another. At every position, sends an ultrasonic pulse and measures the time taken for the echo to return.

Using this time, the Arduino calculates the distance.

The Arduino sends data in the form of:

```text
angle,distance
```

For example:

```text
45,32
90,18
120,50
```

Processing reads these values and uses them to update the radar display.

The Processing window shows the scanning movement and the detected objects according to their position and distance.

## Project Files

```text
Arduino-Ultrasonic-Radar/
│
├── Arduino/
│   └── radar.ino
│
├── Processing/
│   └── radar_visualization.pde
│
├── Images/
│   ├── radar_hardware.jpg
│   ├── radar_detection.png
│   └── radar_demo.gif
│
└── README.md
```

## How to Run

1. Connect the components according to the circuit connections.
2. Open the Arduino code in Arduino IDE.
3. Select the correct board and COM port.
4. Upload the code to the Arduino Uno.
5. Open the Processing sketch.
6. Set the correct serial port in the Processing code.
7. Run the Processing sketch.
8. Place an object in front of the sensor and observe the detection on the radar.

## What I Learned

Working on this project helped me understand:

* Arduino programming
* Ultrasonic sensor interfacing
* Servo motor control
* Serial communication
* Real-time data visualization using Processing

## Future Improvements

Some things that can be added later are better visualization, longer detection range, multiple sensors, and wireless communication.
