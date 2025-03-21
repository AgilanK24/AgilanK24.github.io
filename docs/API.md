---
title: HMI API
---

# HMI Subsystem API

## Introduction
The HMI Subsystem processes user interactions using the ESP32-S3-WROOM-1 and an OLED display.

## Message Structure
**General Message Format**
| Byte | Description | Example Value |
|------|------------|--------------|
| Byte 1 | Message Type | 0x10 |
| Byte 2 | Source ID | 0x01 (ESP32) |
| Byte 3 | Destination ID | 0x02 (OLED) |
| Byte 4 | Display Command (LSB) | 0x7A |
| Byte 5 | Display Command (MSB) | 0x00 |
| Byte 6 | End Byte | 0x42 |

**ESP32 Sends Data to OLED**
| Byte | Variable Name | Data Type | Example Value |
|------|--------------|----------|--------------|
| 1 | Message Type | `uint8_t` | 0x20 |
| 2 | Source ID | `uint8_t` | 0x01 |
| 3 | Display Text (LSB) | `uint8_t` | 0x7A |
| 4 | Display Text (MSB) | `uint8_t` | 0x00 |
| 5 | Checksum | `uint8_t` | 0xA1 |
| 6 | End Byte | `uint8_t` | 0x42 |

**ESP32 Handles User Input from Buttons**
| Byte | Variable Name | Data Type | Example Value |
|------|--------------|----------|--------------|
| 1 | Message Type | `uint8_t` | 0x30 |
| 2 | Source ID | `uint8_t` | 0x01 |
| 3 | Button ID | `uint8_t` | 0x02 |
| 4 | Button Pressed | `uint8_t` | 0x01 (Pressed) |
| 5 | Checksum | `uint8_t` | 0xA1 |
| 6 | End Byte | `uint8_t` | 0x42 |

## Communication Flow
1. The ESP32 receives button inputs from the HMI subsystem.
2. The ESP32 processes the command and updates the OLED.
3. The OLED displays the corresponding information.
4. The system logs the user interaction over UART for external monitoring.

## Conclusion
The HMI subsystem follows structured message formats, ensuring clear data transmission.

