## HMI Functionality and Design Discussion

Our schematic implements an HMI using a 128x32 SPI OLED connected to an ESP32-S3-WROOM-1-N4. The display shows directions received via UART ("left", "right", "forward", "back"), providing real-time user feedback. A button and LED are included for testing and interaction. This setup meets product requirements by making system status visible and supporting debugging during development.

### Team Design Approach

We focused on a modular, easy-to-understand layout to support STEM education. Using the ESP32-S3 gave us access to SPI, UART, I2C, PWM, and Wi-Fi (for MQTT) in a single chip. Our goal was to teach students how HMI, color sensors, motor drivers, and communication protocols interact in real-world systems. The design is simple but effective for hands-on learning. We selected the ST7565R-based graphic LCD because it provided enough flexibility for both text and basic graphics without overwhelming the microcontroller or students with a complex GUI framework. However, we also considered the learning curve, which led to prioritizing simplicity in the schematic routing and using labeled headers for sensors and motors to encourage hands-on debugging.

### Version 2.0 Improvements

If we build a new version:
- **Add a distance sensor** to improve line-stopping accuracy and teach feedback-based control.
- **Use a simpler I2C LCD** to reduce code complexity while keeping HMI functionality.
- **Upgrade to larger motors** for more torque, allowing heavier loads and better performance.

These changes would make the system more powerful and easier to program, improving both learning and functionality.

