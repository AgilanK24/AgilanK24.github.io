## HMI Subsystem Power Budget

| Component              | Voltage (V) | Current Draw (mA) | Power (mW) | Notes                                      |
|------------------------|-------------|-------------------|------------|--------------------------------------------|
| ESP32-S3-WROOM-1-N4    | 3.3         | 160 (avg)         | 528        | Wi-Fi active, some peripherals enabled     |
| OLED SPI Display       | 3.3         | 10–15             | ~50        | NHD-C12832A1Z-FSW-FBW-3V3 (ST7565R)        |
| Debug LED              | 3.3         | 5                 | 16.5       | With 330Ω current-limiting resistor        |
| Pushbutton (idle)      | 3.3         | ~0                | 0          | No current when idle                       |
| Voltage Regulator Loss | 3.3         | —                 | ~100       | Estimated regulator dropout + switching loss |
| **Estimated Total**    | —           | **180–190 mA**    | **~700 mW**| Based on typical operating conditions      |

> ⚠️ This budget assumes 3.3V regulated supply. Power draw may spike if Wi-Fi and peripherals are active simultaneously.

