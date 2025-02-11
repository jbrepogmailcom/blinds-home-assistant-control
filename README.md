# Blinds Brain GPS

This project is an ESPHome-based solution for automating the control of exterior blinds using an ESP32 microcontroller. The system uses various sensors and GPS data to adjust the blinds based on environmental conditions such as light and wind. It is intended to be placed at western side of house, where sun sets down. The way it work is that you place light sensor inside room, where you want the shadow to begin. As the sun sets and direct sunlight would enter the room, the blinds drop down until the light sensor detects shadow again. If there is cloudy, blinds are rolled up. If there is wind prediction, blinds are also rolled up.

The project uses transmitter library to send codes to blinds motor with 433MHz receiver. It sends status and receives commands over mqtt, so can be integrated to Home Assistant.

## Features

- **Automatic Blinds Control**: Adjusts blinds based on light and wind conditions.
- **GPS Integration**: Uses GPS data to fetch weather information (for wind prediction).
- **WiFi Connectivity**: Connects to a WiFi network for remote control and monitoring.
- **MQTT Support**: Integrates with MQTT for communication with other smart home devices.
- **Over-the-Air Updates**: Supports OTA updates for easy firmware upgrades.
- **Logging**: Provides detailed logging for debugging and monitoring.

## Hardware Requirements

- ESP32 microcontroller
- BH1750 light sensor
- GPS module
- Radio - controlled blinds with motor control
- WiFi network

## Installation

1. **Clone the Repository**:
    ```sh
    git clone https://github.com/your_username/blinds-brain-gps.git
    cd blinds-brain-gps
    ```

2. **Configure ESPHome**:
    - Install ESPHome: [ESPHome Installation Guide](https://esphome.io/guides/installing_esphome.html)
    - Copy the `blinds-brain-gps-210619-commented.yaml` file to your ESPHome configuration directory.

3. **Update Configuration**:
    - Open `blinds-brain-gps-210619-commented.yaml` and update the following placeholders with your actual values:
        - `your_wifi_password`
        - `your_api_key`
        - `your_mqtt_broker`
        - `your_mqtt_username`
        - `your_mqtt_password`

4. **Upload Firmware**:
    - Connect your ESP32 to your computer.
    - Run the following command to upload the firmware:
        ```sh
        esphome run blinds-brain-gps-210619-commented.yaml
        ```

## Usage

- The system will automatically adjust the blinds based on the configured thresholds for light and wind.
- You can monitor and control the blinds remotely via the ESPHome dashboard or Home Assistant.
- Logs can be viewed in the ESPHome dashboard for debugging and monitoring purposes.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request with your improvements.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
