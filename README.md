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
| **Peripherals** | UART (deep), GPIO, Timers, SPI (in progress), DMA (learning) |
| **Protocols** | UART, Custom network protocols, SPI (learning), I2C (learning) |
| **RTOS** | FreeRTOS (learning), Custom kernel development (completed) |
| **Tools** | ARM GCC, GDB, OpenOCD, ST-Link, Make, Unity (TDD), Oscilloscope (basic), Logic Analyzer (basic) |
| **Debugging** | JTAG (learning), Stack analysis, Hardware validation |
| **Standards** | MISRA C:2012 (learning), Test Driven Development |

### Software Engineering (Professional, 7 Years)
| Category | Skills |
|----------|--------|
| **Languages** | C (proficient), C++ (familiar), ARM Assembly (learning) |
| **Development** | Git, Requirements analysis, Testing (unit/integration/system) |
| **Domain** | Automotive software development |
| **Methodologies** | Agile, V-Model validation, TDD |

---

## 🚀 Learning Portfolio

### [Cortex-M0-RTOS-Kernel](https://github.com/BlackWiz/CortexM0-RTOS-Kernel)
**Preemptive Priority-Based RTOS from Scratch**

Built a complete Real-Time Operating System for ARM Cortex-M0+ as part of M.Tech dissertation. 
This was the deep dive—implementing task scheduling, context switching, synchronization primitives, 
and memory management entirely from first principles.

**Core Features Implemented:**
- **Scheduler:** O(1) priority-based preemptive scheduler with 8 priority levels
- **Context Switching:** Hand-written ARM Cortex-M0+ assembly (measured 4.81 µs @ 16 MHz)
- **Synchronization:** Semaphores, mutexes with priority inheritance protocol
- **IPC:** Message queues with blocking send/receive
- **Memory Management:** Fixed-block allocator with O(1) allocation/deallocation
- **Safety:** Stack overflow detection with canary values
- **Power:** Tickless idle mode for low-power operation
- **HAL:** Hardware abstraction layer for portability

**The Hard Parts:**
- Debugging context switch corruption (stack alignment issues took 3 days)
- Implementing priority inheritance without deadlock scenarios
- Hand-writing PendSV handler in ARM assembly for Cortex-M0+ constraints
- Managing 36KB RAM budget across 16 tasks with proper stack allocation
- Building comprehensive test suite (13 automated tests covering all features)

**Key Learnings:**
- Deep understanding of ARM Cortex-M exception model and interrupt priorities
- Stack frame layout and PSP/MSP register management
- Critical section design and interrupt masking strategies
- Trade-offs between O(1) scheduling vs memory overhead
- Hardware timer programming for RTOS tick generation

**Performance Metrics:**
- Context switch: 4.81 µs (target: <10 µs) ✅
- Memory allocation: O(1) constant time ✅
- Kernel footprint: ~8 KB FLASH ✅
- Stack overhead: 1 KB per task
- Tested with 6 concurrent tasks under stress

**Tech:** STM32G071RB | Bare-metal C | ARM Assembly | Cortex-M0+ | SysTick | PendSV | 13 automated tests

---

### [STM32-Embedded-HTTP-Server](https://github.com/BlackWiz/STM32-Embedded-HTTP-Server)

Bare-Metal Embedded HTTP Server with JSON Command Interface

A portfolio-grade embedded networking project where an STM32 microcontroller acts as a standalone HTTP server over Ethernet. A standard web browser communicates directly with the MCU using HTTP and JSON to control hardware in real time.

This project focuses on core embedded systems engineering, not web development — emphasizing protocol correctness, deterministic parsing, and system-level design under tight memory constraints.

**What It Does:**
- STM32 listens on a static IP as an HTTP server (port 80)
- Browser sends HTTP GET/POST requests with JSON payloads
- Firmware parses HTTP and JSON using FSMs (no dynamic memory)
- Commands are mapped to embedded application logic (LED control as baseline)
- STM32 responds with proper HTTP status and payloads

**Why This Project Matters:**
- Demonstrates embedded Ethernet bring-up and driver development
- Shows correct use of lwIP in bare-metal (NO_SYS) mode
- Highlights protocol layering: Ethernet → IP → TCP → HTTP → JSON → App
- Designed to scale cleanly into RTOS-based systems later

**The Hard Parts:**
- Porting lwIP without an RTOS and managing timers manually
- Writing a minimal but browser-compatible HTTP server
- FSM-based JSON parsing under tight RAM constraints
- Debugging TCP/IP behavior using Wireshark
- Ensuring deterministic behavior without malloc/free

**Key Learnings:**
- Embedded networking fundamentals and TCP/IP behavior
- Ethernet controller (ENC28J60) architecture and SPI integration
- Designing robust parsers for untrusted network input
- Tradeoffs between custom protocols vs standard stacks
- Writing interview-defensible embedded networking code

**Tech:** STM32F4 / STM32G0 | Bare-metal C | ENC28J60 (Ethernet) | lwIP (NO_SYS) | HTTP | JSON FSM | SPI | Static IP

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

### [STM32-Serial-Shell](https://github.com/BlackWiz/STM32-Serial-Shell)
**Interactive Command-Line Interface for Embedded Systems**

Building on Serial-JSON-Bridge, this project adds human-machine interaction through a full CLI framework. Created extensible command registration system with built-in commands (`help`, `set`, `get`) and JSMN parser integration for future JSON protocol support—serving as the foundation for TinyServe's Em-CLI remote management interface.

**The Hard Parts:** Designing memory-efficient command registration without dynamic allocation, handling user input edge cases (incomplete commands, buffer overflows), creating clean separation between UART driver layer and CLI parser logic, building extensible framework under STM32G0 constraints.

**Key Learnings:** User interface design for resource-constrained systems, command parsing and tokenization strategies, building frameworks in bare-metal C with zero malloc, importance of good CLI help systems in embedded tools.

**Tech:** STM32G071RB | Bare-metal C | UART | Command Parser | JSMN | Extensible Architecture

---

## 📖 How I Learn

**My approach:**
1. Start with fundamentals (datasheets, reference manuals)
2. Build from scratch (no HAL, no magic)
3. Test on real hardware (catch real-world issues)
4. Document failures (they teach more than successes)
5. Iterate and improve

**Current learning pattern:**
- UART driver (done) → CLI interface (done) → Custom protocols (in progress) → SPI + Ethernet → I2C
- Build depth in one peripheral before moving to next
- Each project builds on previous learnings
- Now focusing on networking and protocol design

---

## 🎯 Next Steps (My Roadmap)

**Immediate (Next 2-3 Months):**
- [x] Complete custom RTOS kernel (DONE - see Cortex-M0-RTOS-Kernel)
- [x] Complete Interactive CLI (DONE - foundation for TinyServe Em-CLI)
- [ ] Complete TinyServe-STM32 Phase 1 (Protocol Stack + Loopback Test)
- [ ] Complete TinyServe-STM32 Phase 2 (Full NAS functionality)
- [ ] Complete UART driver with DMA
- [ ] Build I2C driver + EEPROM interface

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
- ✅ Deep dive capability (built complete RTOS from scratch)
- ✅ Protocol design experience (custom networking stack in progress)

**What I'm looking for:**
Entry-level to junior embedded/firmware roles where I can apply software engineering 
fundamentals to hardware development and learn from experienced embedded engineers.

---

## 📫 Let's Connect

Currently building a portfolio for transition to embedded systems roles. 
Open to discussing firmware opportunities, embedded projects, or just talking about hardware.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sriharishankarsharma/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sriharijosyula@gmail.com)

---

*"After 7 years of working above abstractions, I'm learning what's below them. One register at a time."*
