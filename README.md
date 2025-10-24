# Hi, I'm Sri Hari Shankar Sharma 👋

Embedded Systems Engineer who learns by breaking things and fixing them. I write firmware that doesn't fall apart when it hits real hardware.


## 🛠️ What I Work With

| Category | Tech Stack |
|----------|------------|
| **Working Languages** | C, ARM Assembly |
| **Known Languages** | C++ |
| **Platforms** | STM32 (G0, F4 series) |
| **RTOS & Bare-metal** | FreeRTOS, Zephyr, Custom Kernel Development, Register-level Programming |
| **Protocols** | UART, SPI, I2C, CAN, USB, ADC, PWM |
| **Tools** | STM32CubeIDE, Keil, GDB, JTAG, Oscilloscope, Logic Analyzer, Git |

---

## Projects

### [Serial-JSON-Bridge](https://github.com/yourusername/serial-json-bridge)
Bare-metal UART driver with JSON parsing on STM32. No HAL. No dynamic allocation. Just registers and interrupts.

**What it does:** Takes hardcoded JSON, parses it with JSMN on the MCU, transmits parsed data over UART.

**What I learned:**
- Hit a stack overflow, debugged a hard fault, understood memory constraints
- Built interrupt-driven state machines that don't lose data
- Separated driver and application logic properly

**Tech:** STM32G0 | UART (9600 baud) | JSMN Parser | Bare-metal C

---

### Custom Preemptive RTOS Kernel
Building an RTOS from scratch on ARM Cortex-M to understand how task scheduling, context switching, and IPC actually work.

**Status:** Active development. Details coming soon.

---

## How I Build

- Start simple, validate on real hardware
- No magic numbers—document everything with datasheets
- Driver layer stays separate from application logic
- Test until it breaks, then fix it

---

## Currently Learning

- Advanced DMA for high-throughput transfers
- Power optimization for battery systems
- Bootloader development and OTA updates
- CMSIS-DSP for real-time signal processing

---

## Get In Touch

Open to firmware roles involving RTOS, bare-metal programming, or driver architecture. Let's talk if you're building something real.

 [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sriharishankarsharma/)
 [![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sriharijosyula@gmail.com)
