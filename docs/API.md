---
title: HMI Subsystem API
---

# HMI Subsystem API  

## Overview  
This page documents the communication protocol between the HMI Subsystem and other system components, including the Motor Driver, MQTT, and Sensor subsystems. It specifies the message types, data format, and handling procedures.  

---

## Message Protocol  

Each message follows the class messaging protocol, structured within the "message data" area. This section outlines the messages **sent and received** by the HMI.

### 1. Messages Sent by the HMI  

#### **Message Type 10 - HMI Command to Motor Driver**  
Used to send speed control commands to the **motor driver**.  

| Byte | Variable Name  | Type      | Min Value | Max Value | Example |
|------|--------------|-----------|-----------|-----------|---------|
| 1    | message_type | uint8_t   | 10        | 10        | 10      |
| 2    | motor_id     | uint8_t   | 1         | 4         | 1       |
| 3-4  | motor_speed  | int16_t   | -1000     | 1000      | 250     |

#### **Message Type 20 - HMI Request to Sensor Subsystem**  
Requests sensor data from the **sensor subsystem**.  

| Byte | Variable Name  | Type      | Min Value | Max Value | Example |
|------|--------------|-----------|-----------|-----------|---------|
| 1    | message_type | uint8_t   | 20        | 20        | 20      |
| 2    | sensor_id    | uint8_t   | 1         | 8         | 3       |

---

### 2. Messages Received by the HMI  

#### **Message Type 30 - Sensor Data Update**  
Received from the **sensor subsystem**, containing updated sensor readings.  

| Byte | Variable Name  | Type      | Min Value | Max Value | Example |
|------|--------------|-----------|-----------|-----------|---------|
| 1    | message_type | uint8_t   | 30        | 30        | 30      |
| 2    | sensor_id    | uint8_t   | 1         | 8         | 3       |
| 3-6  | sensor_value | float (C: float) | -100.0  | 100.0     | 25.75   |

#### **Message Type 40 - Acknowledgment from MQTT**  
Received when the **MQTT subsystem** successfully processes an HMI command.  

| Byte | Variable Name  | Type      | Min Value | Max Value | Example |
|------|--------------|-----------|-----------|-----------|---------|
| 1    | message_type | uint8_t   | 40        | 40        | 40      |
| 2    | command_id   | uint8_t   | 10        | 30        | 10      |
| 3    | status       | uint8_t   | 0 (Fail)  | 1 (Success) | 1   |

---
