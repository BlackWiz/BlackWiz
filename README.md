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
| **RTOS** | FreeRTOS (learning), Custom kernel development (completed) |
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

## [TinyServe-STM32](https://github.com/BlackWiz/TinyServe-STM32-Bare-Metal-Networked-File-Server) ⏳
**Bare-Metal Networked File Server (No OS, No TCP/IP)**

A collaborative system engineering project to build a remote file storage node on STM32G0. We are replacing standard heavy IP stacks (LwIP) with **"MiniProt"**, a custom lightweight (<8KB) transport protocol running over Raw Ethernet frames, to enable file management on an SD Card.

### My Role (Network & Protocol Lead)
Responsible for the communication stack—from the physical SPI driver for the ENC28J60 Ethernet controller up to the custom Transport Layer implementation.

### Current Status (Phase 1 - Foundation)
- 🚧 **Protocol Stack**: Designing "MiniProt" (L2/L4) state machine for packet framing and ARQ reliability
- 🚧 **TDD Framework**: Setting up Unity for unit testing protocol logic on PC before deployment
- 🚧 **Driver Integration**: Porting ENC28J60 driver to custom bare-metal SPI implementation
- 📅 **Target Milestone**: Reliable Loopback Test by Dec 15, 2025

### Key Technical Challenges
- **Architecting "MiniProt"**: Implementing a robust sliding-window protocol to handle packet loss without the overhead of TCP
- **Resource Contention**: Designing a mutex-free SPI arbiter to manage collisions between the Ethernet Controller and SD Card (both on SPI)
- **Constraint Compliance**: Adhering to MISRA C:2012 guidelines and Test Driven Development (TDD) workflow

**Tech**: STM32G071RB | Bare-metal C | ENC28J60 (Ethernet) | FatFs | SPI Arbitration | MISRA C | Unity (TDD)

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
- [x] Complete custom RTOS kernel (DONE - see Cortex-M0-RTOS-Kernel)
- [ ] Complete STM32-Serial-Shell with custom protocol
- [ ] Complete UART driver with DMA
- [ ] Build SPI driver + sensor integration
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
