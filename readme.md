# BudgetCam QR Generator

A simple, client-side web tool to generate QR codes for configuring device settings, primarily for Wi-Fi setup.

This tool is particularly useful for many models of cheap, unbranded security cameras that can be purchased on online marketplaces like **Amazon** or **eBay**. These cameras often use a QR code scanning mechanism for their initial network configuration.

## Compatible Camera Brands and Models

This tool is designed to work with a wide variety of security cameras that use a QR code to receive Wi-Fi credentials during setup. While it's impossible to list every compatible device, many cameras sold under different brand names on Amazon and eBay use this method.

Well-known brands that often use QR code setup include:
*   **Blink**
    *   *Note: Blink cameras (e.g., Mini, Outdoor, Indoor) typically have a QR code on the device itself that you scan with the app to begin setup, rather than the camera scanning your phone.* [17, 21, 46]
*   **Eufy**
    *   Indoor Cam Series (e.g., C24, P24) [15, 52]
    *   SoloCam Series (e.g., L20, L40, S40) [15, 22]
    *   Floodlight Cam Series [26]
*   **Reolink**
    *   Argus Series (Battery) [1, 38]
    *   E1 Series [1, 33]
    *   Lumus Series [1]
    *   TrackMix WiFi & Battery Series [1, 33]
*   **Tapo**
    *   *Note: Tapo cameras are configured within the Tapo app, which may use a direct Wi-Fi or Bluetooth connection for setup rather than having the camera scan a QR code from your phone.* [2, 4]
*   **Wansview**
    *   Q Series (e.g., Q5, Q6) [40, 42]
    *   W Series (e.g., W4, W5, W6) [10, 13, 32]
    *   Y Series (e.g., Y1, Y4) [3, 7]
    *   G Series (e.g., G2, G7) [7, 24]
*   **Wyze**
    *   Wyze Cam v2, v3, v3 Pro [30, 36, 62]
    *   Wyze Cam Pan v1, v2, v3 [23, 34, 62]
*   **Yi / Kami**
    *   Yi Home Camera (various models) [11, 12, 44]
    *   Yi Dome Camera [65]
    *   Kami Wire-Free Outdoor Camera [47]
*   Many generic/unbranded cameras powered by Tuya.

**Note:** This is not an exhaustive list. If your camera's setup process involves scanning a QR code from your phone screen to connect to Wi-Fi, this tool may work for you.

## Features

*   **Easy Wi-Fi Setup**: Quickly generate a QR code with your Wi-Fi SSID and password.
*   **Multiple Payload Formats**: Choose from three different syntax options to match your device's requirements:
    1.  **Standard Wi-Fi**: `WIFI:S:<SSID>;T:WPA;P:<PASSWORD>;;`
    2.  **JSON**: A plain JSON string: `{"s":"<SSID>","p":"<PASSWORD>","t":"<TOKEN>"}`
    3.  **Base64**: A Base64-encoded version of the JSON string.
*   **Optional Token**: Includes a field for an extra token, which some cameras use for settings like "offline mode".
*   **Live Preview**: See the QR code and the raw payload data update in real-time as you type.
*   **Downloadable QR Code**: Download the generated QR code as a `camera-payload.png` file to use anytime.
*   **Purely Client-Side**: Runs entirely in your browser. No data is sent to any server, ensuring your credentials remain private.

## How to Use

1.  Open the `index.html` file in any modern web browser.
2.  Enter your **Wi-Fi Name (SSID)** and **Password** into the respective fields.
3.  If your camera requires an additional configuration token, enter it in the **Extra Token** field.
4.  Use the slider to select the payload format that your camera requires. If you are unsure, the standard `WIFI:S:` format or `JSON` are common choices.
5.  The QR code will be generated on the screen. You can now scan this directly with your camera during its setup process.
6.  Alternatively, click the **Download PNG** button to save the QR code as an image file. You can then display this image on a phone, tablet, or monitor for the camera to scan.

## Technical Details

*   **QRious**: This tool uses the QRious library for fast and efficient QR code generation.
*   **Dependencies**: All dependencies are loaded via CDN, so no local installation is required. Just open the HTML file.

---
*This tool is provided as-is. Always ensure you are using a trusted device when entering sensitive information like Wi-Fi passwords.*