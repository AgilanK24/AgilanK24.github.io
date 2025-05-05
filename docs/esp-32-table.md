---
title: ESP32 Table
---

| ESP Info                                      | Answer | Help                                                                                                      |
| --------------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------- |
| Model                                         |ESP32-S3-WROOM-1-N4| Include the entire part number (leave off any letters at the end that specify the package type)           |
| Product Page URL                              | No     | Found on Espressif.com                                                                                    |
| ESP32-S3-WROOM-1-N4 Datasheet URL             |[link to product](https://www.espressif.com/sites/default/files/documentation/esp32-s3-wroom-1_wroom-1u_datasheet_en.pdf)      | Do not paste links directly into the table.                                             |
| ESP32 S3 Datasheet URL                        | Yes    | Has more detail on functions                                                                              |
| ESP32 S3 Technical Reference Manual URL       | Yes    | Has details on I/O multiplexing, USB, and others                                                          |
| Vendor link                                   |[link to product](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639)      | Digikey, Jameco, etc.  Do not paste links directly into the table.                       |
| Code Examples                                 | ?      | url(s) for libraries on github or other sites related to the microcontroller and your planned peripherals |
| External Resources URL(s)                     | No     | Search on Google and YouTube for other resources for each specific microcontroller.                       |
| Unit cost                                     | $5.06  | Find on Digikey, Jameco, MPJA, or octopart                                                                |
| Absolute Maximum Current for entire IC        | 97mA   | Find in the microcontroller datasheet                                                                     |
| Supply Voltage Range                          | 3V-3.6 | Min / Nominal / Max / Absolute Max, as found in datasheet                                                 |
| Absolute Maximum current <br> (for entire IC) | 355mA  | as found in datasheet                                                                                     |
| Maximum GPIO current <br> (per pin)           | 355mA  | as found in datasheet                                                                                     |
| Supports External Interrupts?                 | Yes    | as found in datasheet                                                                                     |
| Required Programming Hardware, Cost, URL      | $0     | as found in datasheet                                                                                     |

| Module         | # Available | Needed | Associated Pins (or * for any)     |
| -------------- | ----------- | ------ | ---------------------------------- |
| UART           | 3           | 2      | * (GPIO1–GPIO21, remappable)       |
| external SPI*  | 4 (SPI, HSPI, VSPI, FSPI) | 1 | * (GPIOs remappable, FSPI used for Flash) |
| I2C            | 2           | 2      | * (GPIOs remappable)               |
| GPIO           | 45 total (but ~30 usable) | 10 | GPIO0–GPIO46 (varies per usage)    |
| ADC            | 20 channels | 3      | GPIO1–GPIO20 (ADC1/2 groups)       |
| LED PWM        | 8 channels  | 2      | * (via LEDC, any GPIO)             |
| Motor PWM      | 6 groups x 4 timers = 24 channels | 0 | * (via MCPWM, any GPIO)    |
| USB Programmer | 1 (USB-OTG native) | 1      | GPIO19 (D+) and GPIO20 (D−)        |




\* The ESP32-S2 has multiple SPI interfaces, but some are for internal use
