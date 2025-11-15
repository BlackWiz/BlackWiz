# Hi, I'm Sri Hari Shankar Sharma 👋

**Senior Engineer (7 years) transitioning from automotive application development to embedded systems engineering.**

I spent years working above hardware abstractions. Now I'm learning what's below them—by building bare-metal drivers, parsers, and kernels from scratch.

---

## 🎯 My Transition Journey

**Background:** 7 years as Senior Engineer in automotive software (application layer)
**Current Focus:** Teaching myself embedded systems fundamentals through hands-on hardware projects
**Goal:** Transition to firmware/embedded roles where I work directly with hardware

**Why the switch?** After years of promises about "hardware opportunities coming soon," I decided to create my own path. I'm investing my time learning register-level programming, interrupt-driven architecture, and real hardware debugging.

---

## 🛠️ Technical Skills

### Embedded Systems (Self-Taught, 2024-Present)
| Category | Skills |
|----------|--------|
| **Microcontrollers** | STM32 (G0 series - deep), F4 series (learning) |
| **Architecture** | Bare-metal C, Register-level programming, Interrupt-driven design |
| **Peripherals** | UART (deep), GPIO, Timers, DMA (in progress) |
| **Protocols** | UART, SPI (learning), I2C (learning) |
| **RTOS** | FreeRTOS (learning), Custom kernel development (in progress) |
| **Tools** | ARM GCC, GDB, OpenOCD, ST-Link, Make, Oscilloscope (basic), Logic Analyzer (basic) |
| **Debugging** | JTAG (learning), Stack analysis, Hardware validation |

### Software Engineering (Professional, 7 Years)
| Category | Skills |
|----------|--------|
| **Languages** | C (proficient), C++ (familiar), ARM Assembly (learning) |
| **Development** | Git, Requirements analysis, Testing (unit/integration/system) |
| **Domain** | Automotive software development |
| **Methodologies** | Agile, V-Model validation |

---

## 🚀 Learning Portfolio

### [STM32-Serial-Shell](https://github.com/BlackWiz/STM32-Serial-Shell)
**Interrupt-driven CLI with JSON command support**

Built a command-line interface on bare-metal STM32 that processes text and JSON commands over UART. 
Focused on learning parser integration, event-driven design, and clean driver/application separation.

**Key Learnings:**
- Integrated non-blocking CLI parser with interrupt-driven UART driver
- Designed command registration and dispatch mechanisms
- Implemented safe data handoff between ISR and main loop (no race conditions)
- Built modular firmware architecture (driver → parser → application layers)

**Tech:** STM32G071RB | Bare-metal C | UART interrupts | JSMN parser | Custom Makefile

---

### [Serial-JSON-Bridge](https://github.com/BlackWiz/Serial-JSON-Bridge)
**Bare-metal UART driver with JSON parsing**

My first real embedded project. Built UART driver from scratch (no HAL), integrated JSON parser, 
and learned what "memory constraints" actually means.

**The Hard Parts:**
- Debugged stack overflow that took 2 days (learned to read .map files)
- Built interrupt-driven state machines for concurrent TX/RX
- Handled all hardware errors (overrun, framing, parity, noise)
- Created 3-tier testing strategy (unit, integration, hardware validation)

**Key Learnings:**
- Register-level UART configuration (read 800+ page reference manual)
- Interrupt service routine design and optimization
- Memory management on resource-constrained systems (36KB RAM)
- Hardware debugging with real tools (not just printf)

**Tech:** STM32G071RB | Bare-metal C | UART (9600 baud) | JSMN Parser | 18 automated tests

---

### Custom Preemptive RTOS Kernel ⏳
**Building an RTOS from scratch on ARM Cortex-M**

Learning how task scheduling, context switching, and inter-process communication actually work 
by implementing them myself.

**Status:** Active development
**Goal:** Understand what FreeRTOS does under the hood

---

## 📖 How I Learn

**My approach:**
1. Start with fundamentals (datasheets, reference manuals)
2. Build from scratch (no HAL, no magic)
3. Test on real hardware (catch real-world issues)
4. Document failures (they teach more than successes)
5. Iterate and improve

**Current learning pattern:**
- UART driver (done) → UART with DMA (in progress) → SPI → I2C
- Build depth in one peripheral before moving to next
- Each project builds on previous learnings

---

## 🎯 Next Steps (My Roadmap)

**Immediate (Next 2-3 Months):**
- [ ] Complete UART driver with DMA
- [ ] Build SPI driver + sensor integration
- [ ] Build I2C driver + EEPROM interface
- [ ] Finish custom RTOS kernel basics

**Near-term (3-6 Months):**
- [ ] Multi-peripheral system integration
- [ ] Bootloader design and implementation
- [ ] Low-power mode optimization
- [ ] CAN bus driver (leverage automotive knowledge)

**Goal:** Build sufficient portfolio depth to transition into firmware/embedded engineering role.

---

## 💡 What I Bring

**From 7 years in automotive:**
- ✅ Professional maturity (meeting deadlines, working in teams)
- ✅ Software engineering discipline (testing, documentation, architecture)
- ✅ Domain knowledge (automotive requirements, safety mindset)
- ✅ Problem-solving methodology (systematic debugging)

**From self-teaching embedded:**
- ✅ Proven learning ability (projects speak for themselves)
- ✅ Genuine passion for hardware (not just career desperation)
- ✅ Hands-on experience (real hardware, real debugging)
- ✅ Growth mindset (document failures, iterate, improve)

**What I'm looking for:**
Entry-level to junior embedded/firmware roles where I can apply software engineering 
Fundamentals of hardware development and learn from experienced embedded engineers.

---

## 📫 Let's Connect

Currently building a portfolio for transition to embedded systems roles. 
Open to discussing firmware opportunities, embedded projects, or just talking about hardware.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sriharishankarsharma/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sriharijosyula@gmail.com)

---

*"After 7 years of working above abstractions, I'm learning what's below them. One register at a time."*
