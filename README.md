# Web Serial Terminal for microcontrollers

A modern web-based serial terminal for ESP32, Arduino, and other microcontrollers using the Web Serial API. This terminal provides a clean, terminal-style interface with customizable baud rates and line endings, compatible with any USB serial device.

## Features

- **Web Serial API Integration**: Connect directly to ESP32, Arduino, and other microcontroller devices through your browser
- **Multiple Baud Rate Support**: 9600, 57600, 74880, 115200, 230400, 460800, 921600, and custom rates
- **Line Ending Options**: None, LF (\n), CRLF (\r\n), CR (\r)
- **Terminal-style Interface**: Green-on-black color scheme with monospace font
- **Command Input**: Dedicated input area for sending commands
- **Auto-scroll**: Automatically scrolls to show latest output
- **Clear Command**: Type "clear" to clear the terminal
- **Real-time Communication**: Bidirectional communication with connected devices

## Browser Compatibility

This application requires a browser that supports the Web Serial API:
- Google Chrome (version 89+)
- Microsoft Edge (version 89+)
- Brave Browser
- Other Chromium-based browsers

**Note**: Firefox and Safari do not currently support the Web Serial API.

## Usage

1. **Open the Terminal**
   - Open `index.html` in a supported browser
   - No web server required - works as a local file

2. **Connect to Device**
   - Click "Connect" button
   - Select your microcontroller device from the browser's device picker
   - Choose appropriate baud rate (default: 115200)
   - Select line ending format if needed

3. **Send Commands**
   - Type commands in the input field at the bottom
   - Press Enter to send
   - Commands will appear in the terminal with a ">" prefix

4. **Monitor Output**
   - All device output appears in the main terminal area
   - Terminal auto-scrolls to show latest messages
   - Use "clear" command to clear the terminal

5. **Disconnect**
   - Click "Disconnect" when finished
   - Connection status is shown in the top-right corner

## Configuration Options

### Baud Rates
- 9600 (common for basic Arduino projects)
- 57600
- 74880 (ESP8266/ESP32 boot messages)
- 115200 (default, most common)
- 230400
- 460800
- 921600
- Custom (enter any valid baud rate)

### Line Endings
- None: No line ending characters
- LF (\n): Unix-style line ending
- CRLF (\r\n): Windows-style line ending
- CR (\r): Classic Mac-style line ending

## Supported Devices

This terminal works with any device that communicates over USB serial, including:

**ESP Family:**
- ESP32 (all variants)
- ESP8266 (NodeMCU, Wemos D1, etc.)

**Arduino Boards:**
- Arduino Uno, Nano, Mini
- Arduino Mega, Leonardo, Micro
- Arduino Pro, Pro Mini

**Other Compatible Devices:**
- STM32 development boards
- Raspberry Pi Pico
- Teensy boards
- Any microcontroller with USB-to-serial conversion

## File Structure

```
ESP32-Web-Serial-Terminal/
├── index.html          # Main application file
└── README.txt          # This documentation file
```

## Technical Details

- **Language**: HTML5, CSS3, JavaScript (ES6+)
- **API**: Web Serial API
- **Dependencies**: None (vanilla JavaScript)
- **File Size**: ~8KB (single file)
- **Framework**: None (pure web technologies)

## Common Commands

Here are some useful commands you can try once connected:

**ESP32/ESP8266 Commands:**
```
AT                      # Test AT command response (if AT firmware)
AT+GMR                  # Get firmware version (if AT firmware)
help                    # Show available commands (device-dependent)
ls                      # List files (if filesystem enabled)
reboot                  # Restart the device
```

**Arduino Commands:**
```
help                    # Show available commands (sketch-dependent)
status                  # Get device status (if implemented)
reset                   # Reset device (if implemented)
```

**Universal Commands:**
```
clear                   # Clear the terminal (web terminal command)
```

*Note: Available commands depend on the firmware/sketch running on your device.*

## Troubleshooting

### Connection Issues
- Ensure your device is properly connected via USB
- Check that no other serial monitor is using the same port
- Try different baud rates if communication appears garbled
- Make sure your browser supports Web Serial API

### Display Issues
- If text appears wrapped, the terminal uses horizontal scrolling
- Use browser zoom controls if text is too small/large
- Terminal maintains monospace formatting for proper alignment

### Permission Issues
- Some browsers may require HTTPS for Web Serial API
- Try using a local web server if file:// protocol causes issues

## Development

This is a single-file application built with vanilla web technologies. To modify:

1. Edit the HTML, CSS, or JavaScript directly in `index.html`
2. No build process or dependencies required
3. Test by opening the file in a supported browser

## License

This project is open source and available for modification and distribution.

## Contributing

Feel free to submit issues, feature requests, or pull requests to improve this terminal.

## Version History

- v1.0: Initial release with basic serial communication
- v1.1: Added command input area and improved terminal interface
- v1.2: Enhanced text handling and clear command functionality

---

**Note**: This terminal is designed for development and debugging purposes. Always ensure your ESP32/Arduino code handles serial communication appropriately to avoid infinite loops or excessive output that might overwhelm the browser.
