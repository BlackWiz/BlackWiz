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

### [STM32-Serial-Shell](https://github.com/BlackWiz/STM32-Serial-Shell)
Interrupt-driven command-line interface over UART. Type commands, STM32 executes them, sends response back.
What it does:

Command registration system with help, set, get built-in
Interrupt-driven UART with state machine (IDLE → TX_BUSY → IDLE)
Optional JSON parsing with JSMN
Hardware error detection and recovery

Architecture: 3 clean layers

Driver (uart.c) → Parser (em-cli.c) → Application (main.c)
Zero dynamic allocation, fixed buffers
ISR handles bytes, main loop processes commands

What I learned:

Debugged hard faults from stack overflow
Built state machines that don't lose data in interrupts
Separated driver logic from application properly

Tech: STM32G071RB | Bare-metal C | UART interrupts | Custom Makefile + OpenOCD

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
- Setting up ARM build toolchains
- Bootloader development
- Kernel Building

---

## Get In Touch

Open to firmware roles involving RTOS, bare-metal programming, or driver architecture. Let's talk if you're building something real.

 [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sriharishankarsharma/)
 [![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sriharijosyula@gmail.com)
