# ALINX AX7Z020 Vivado Board Definition

This Vivado board definition enables support for the ALINX AX7Z020 development board featuring a Zynq-7000 SoC (XC7Z020-2CLG400I).

It provides interfaces for:

- ✅ HDMI Output  
- ✅ RS485 (2 Channels)  
- ⚠️ CAN Bus (2 Channels) — *under development*  
- ✅ LEDs & Buttons  
- ✅ Clock Input  
- ✅ USB-to-UART Debugging

---

## 📷 Board Diagram with Interface Labels

![AX7Z020 Interfaces](images/ac7z020_annotated.png)

> The image above shows labeled positions of major hardware interfaces on the board.

---

## 📌 Status

| Interface    | Status              | Notes                              |
|--------------|---------------------|-------------------------------------|
| HDMI         | ✅ Working           | Verified with Digilent RGB2DVI     |
| RS485_1/2    | ✅ Working           | TX/RX/DE mapped correctly           |
| CAN_0/1      | ⚠️ Under Development | MIO pins mapped, needs testbench    |
| USB-UART     | ✅ Working           | CP2102-based, MIO48/49              |
| LEDs/Buttons | ✅ Working           | GPIO-mapped                         |

> ⚠️ **Some portions of the board configuration may still require validation and fixes.**

---

## 🧩 Interface Pin Mapping

| Interface      | Signal         | Zynq Pin   | MIO/PL | Description                   |
|----------------|----------------|------------|--------|-------------------------------|
| **HDMI OUT**   | TMDS+/-        | H16..A20   | PL     | HDMI transmitter              |
| **RS485_1**    | TXD / RXD / DE | C8 / C5 / B5 | MIO   | RS485 Transceiver 1           |
| **RS485_2**    | TXD / RXD / DE | W13 / V12 / U19 | PL | RS485 Transceiver 2           |
| **CAN_0**      | TX / RX        | C6 / E9     | MIO    | CAN Transceiver 0 (WIP)       |
| **CAN_1**      | TX / RX        | D9 / E8     | MIO    | CAN Transceiver 1 (WIP)       |
| **USB UART**   | TX / RX        | B12 / C12   | MIO    | Debug via CP2102              |
| **LEDs**       | [0:3]          | J14..H18    | PL     | 4 LEDs                        |
| **Buttons**    | [0:3]          | M15..L16    | PL     | 4 Push Buttons                |
| **System Clock** | CLK          | U18         | PL     | 50 MHz oscillator             |

---

## 🚧 To-Do / Known Issues

- [ ] ✅ RS485 tested and working
- [ ] ⚠️ CAN interfaces mapped — but not yet functionally tested
- [ ] 🛠️ Add presets and GUI labels for better IP integrator experience
- [ ] 🧪 Validate DDC lines for HDMI if needed

---

## 🧠 Usage

1. Extract this board file to your Vivado installation directory:

C:\Xilinx\Vivado\2023.1\data\boards\board_files\AX7Z020\

yaml
Copy
Edit

2. Launch Vivado and create a new project.

3. Select the **AX7Z020 Development Board** from the board list.

---

## 🧷 Reference Links

- [AX7Z020 Product Page](https://www.en.alinx.com/Product/SoC-development-Boards/Zynq-7000-SoC/AX7Z020B.html)
- [Silicon Labs CP2102 Datasheet](https://www.silabs.com/documents/public/data-sheets/cp2102n-datasheet.pdf)
- [AMD Board File Documentation](https://docs.amd.com/internal/api/webapp/print/381401f1-df3a-4f42-a09e-be3f0f3b70bc)

---

## 📝 License

MIT License  
© 2025 Hamed Torki