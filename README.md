GSM-Based Digital Notice Display with Emergency Alert using LPC2129 :-

1. Project Overview

The "GSM-Based Digital Notice Display with Emergency Alert using LPC2129" is an embedded systems project designed to display messages received through SMS on a 16×2 LCD.

The system uses an LPC2129 ARM7 microcontroller as its main processing unit and a SIM800C GSM module for wireless communication.

A user can send an SMS to the SIM card inserted in the GSM module. The microcontroller receives the message through UART communication, processes the received data, and displays the message on the LCD.

The system provides two types of notifications:

- **Normal Notification:** When a normal SMS is received, the message is displayed on the LCD and the green LED indicates normal message reception.
- **Emergency Notification:** When an emergency message is received, the LCD displays the emergency message, the red LED turns ON, and the buzzer produces an alert sound.

A push button is provided to turn OFF the buzzer after an emergency alert.

This project demonstrates wireless communication, UART interfacing, LCD interfacing, and real-time alert generation using an ARM7 microcontroller.

2. Objectives

- To develop a wireless digital notice display system using GSM technology.
- To receive SMS messages and display them on an LCD.
- To implement normal and emergency message identification.
- To provide visual alerts using red and green LEDs.
- To generate an audible emergency alert using a buzzer.
- To provide a push-button mechanism to turn OFF the buzzer.
- To understand UART communication and GSM interfacing with the LPC2129 microcontroller.

3. Features

- Wireless message reception through GSM technology.
- SMS-based digital notice display.
- Real-time message processing using the LPC2129 ARM7 microcontroller.
- 16×2 LCD for displaying received messages.
- Green LED indication for normal messages.
- Red LED indication for emergency messages.
- Buzzer activation during emergency conditions.
- Push-button control to turn OFF the buzzer.
- UART-based communication between the GSM module and microcontroller.
- Simple and cost-effective notice display solution.

4. Hardware Requirements

| Component | Purpose |
|---|---|
| LPC2129 ARM7 Development Board | Main microcontroller |
| SIM800C GSM Module | Wireless SMS communication |
| SIM Card | GSM network connectivity |
| 16×2 LCD Display | Display received messages |
| Green LED | Normal message indication |
| Red LED | Emergency message indication |
| Buzzer | Audible emergency alert |
| Push Button | Turn OFF the buzzer |
| Power Supply | Power for the controller and GSM module |
| Connecting Wires | Hardware interfacing |

5. Pin Connections

The following table represents the main interfacing signals. Refer to the actual source code and hardware wiring for the complete pin configuration.

| Function | LPC2129 Interface |
|---|---|
| GSM TX | P0.1 (RXD0) |
| GSM RX | P0.0 (TXD0) |
| LCD RS | As configured in LCD driver |
| LCD EN | As configured in LCD driver |
| LCD Data Pins | As configured in LCD driver |
| Green LED | As configured in alert driver |
| Red LED | As configured in alert driver |
| Buzzer | As configured in alert driver |
| Push Button | As configured in alert driver |

**Note:** The GSM module TX must be connected to the microcontroller RX, and GSM RX must be connected to the microcontroller TX. Ensure proper voltage-level compatibility and a common ground.

6. Software Requirements

| Software / Tool | Purpose |
|---|---|
| Keil µVision4 | Embedded C programming and compilation |
| Flash Magic | Flashing the HEX file into LPC2129 |
| Embedded C | Firmware development |
| UART Communication | Serial communication with GSM |
| GSM AT Commands | GSM module configuration and SMS handling |

7. Working Principle

The project works based on SMS communication between a mobile phone and the GSM module connected to the LPC2129 microcontroller.

Step 1: System Initialization

- The LPC2129 microcontroller is powered ON.
- UART communication is initialized.
- The LCD is initialized.
- LED, buzzer, and push-button configurations are initialized.
- The GSM module is configured using AT commands.
- The LCD displays the project title and waiting message.

Step 2: SMS Reception

- A user sends an SMS to the mobile number of the SIM card inserted in the SIM800C GSM module.
- The GSM module receives the SMS through the cellular network.
- The received SMS is transferred to the LPC2129 through UART communication.

Step 3: Normal Message Display

When a normal message is received:

- The microcontroller reads and processes the SMS.
- The received message is displayed on the 16×2 LCD.
- The green LED indicates normal message reception.
- The red LED and buzzer remain inactive.

Step 4: Emergency Alert

When an emergency message is received:

- The microcontroller identifies the emergency message.
- The LCD displays the emergency notification.
- The red LED turns ON to indicate an emergency condition.
- The buzzer turns ON to generate an audible alert.

Step 5: Buzzer Control

- A push button is provided to turn OFF the buzzer.
- When the button is pressed, the buzzer is deactivated.
- This allows the user to acknowledge the emergency alert.

8. GSM Module – SIM800C

The SIM800C is a GSM/GPRS module used for wireless communication.

In this project, the SIM800C module is responsible for receiving SMS messages and transferring the received data to the LPC2129 microcontroller through UART.

* Important GSM AT Commands:-

| AT Command | Function |
|---|---|
| `AT` | Checks communication with the GSM module |
| `ATI` | Displays module information |
| `AT+CSQ` | Checks signal quality |
| `AT+CMGF=1` | Selects SMS text mode |
| `AT+CNMI` | Configures new SMS notifications |
| `AT+CMGL` | Lists received SMS messages |
| `AT+CMGR` | Reads a received SMS |

9. Communication Protocol

### UART (Universal Asynchronous Receiver Transmitter)

UART is used for serial communication between the LPC2129 microcontroller and the SIM800C GSM module.

- GSM TX is connected to LPC2129 RXD0.
- GSM RX is connected to LPC2129 TXD0.
- UART is used to transmit AT commands and receive SMS data.
- Serial communication enables the microcontroller to process incoming messages.

10. Expected Output

Normal Message:-

When a normal SMS is sent to the GSM module:

- The received message appears on the LCD.
- The green LED indicates normal message reception.
- The buzzer remains OFF.

Emergency Message:-

When an emergency SMS is received:

- The LCD displays the emergency message.
- The red LED turns ON.
- The buzzer generates an audible alert.
- Pressing the push button turns OFF the buzzer.

11. Applications

- Digital notice boards in colleges and educational institutions.
- Emergency announcement systems.
- Industrial notification systems.
- Hospitals and healthcare institutions.
- Railway and transportation information displays.
- Public information and alert systems.
- Wireless communication-based notice boards.

12. Advantages

- Wireless communication without physical notice-board updates.
- Remote message transmission using SMS.
- Simple and user-friendly operation.
- Real-time emergency notification.
- Visual and audible alert mechanisms.
- Low-cost embedded system implementation.

13. Limitations and Future Enhancements

- The system depends on GSM network availability.
- SMS delivery may be affected by network delays.
- The 16×2 LCD has limited display capacity.
- Scrolling messages can be implemented for longer notifications.
- Multiple authorized mobile numbers can be supported.
- Message sender authentication can be added.
- Additional sensors can be integrated for industrial monitoring.
- IoT-based remote monitoring can be implemented.

14. How to Run the Project

1. Clone or download this repository.
2. Open the project in Keil µVision4.
3. Add all required Embedded C source and header files.
4. Build the project and verify that there are no compilation errors.
5. Connect the LCD, GSM module, LEDs, buzzer, and push button to the LPC2129 board according to the circuit connections.
6. Insert an active SIM card into the SIM800C GSM module.
7. Ensure that the GSM module has proper power supply and network connectivity.
8. Configure UART communication between LPC2129 and SIM800C.
9. Generate the HEX file using Keil µVision4.
10. Flash the HEX file into the LPC2129 using Flash Magic.
11. Power ON the complete system.
12. Send an SMS to the SIM800C module's registered mobile number.
13. Observe the received message and corresponding LED/buzzer indications on the hardware.

15. Conclusion

The "GSM-Based Digital Notice Display with Emergency Alert using LPC2129" successfully demonstrates the integration of GSM technology with an ARM7 microcontroller.

The project enables wireless SMS-based message reception and display while providing separate visual and audible indications for normal and emergency notifications.

It provides a practical application of embedded C programming, UART communication, GSM interfacing, LCD interfacing, and hardware control.

16. Technologies Used

- Embedded C
- ARM7 LPC2129
- SIM800C GSM Module
- UART Communication
- 16×2 LCD
- LED and Buzzer Interfacing
- Keil µVision4
- Flash Magic

