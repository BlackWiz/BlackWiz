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

### Embedded Systems (Self-Taught, 2025-Present)
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

---

## 🚀 Projects

### 🌐 [HTTP-Ethernet-Assistant](https://github.com/BlackWiz/HTTP-Ethernet-Assistant)
**Network-controlled hardware assistant with dual-implementation strategy**

STM32 acts as HTTP server over Ethernet, receiving JSON commands from standard HTTP clients and executing hardware actions. Implemented twice—first with HAL for rapid prototyping, then rewritten in bare-metal C to master low-level driver architecture.

**Core Tech:** lwIP (NO_SYS) | ENC28J60 Ethernet | HTTP Server | JSON FSM | Bare-metal C | SPI

**[→ Full Technical Details](https://blackwiz.github.io/HTTP-Ethernet-Assistant/)**

---

### ⚙️ [CortexM0-RTOS-Kernel](https://github.com/BlackWiz/CortexM0-RTOS-Kernel)
**Preemptive priority-based RTOS built from scratch**

Complete Real-Time Operating System for ARM Cortex-M0+ (M.Tech dissertation). Implements task scheduling, context switching, synchronization primitives, and memory management entirely from first principles. O(1) scheduler with 4.81 µs context switch time.

**Core Tech:** STM32G071RB | Bare-metal C | ARM Assembly | Priority Scheduler | Mutexes | Semaphores | Message Queues

**[→ Full Technical Details](https://blackwiz.github.io/CortexM0-RTOS-Kernel/)**

---

### 📡 [Serial-JSON-Bridge](https://github.com/BlackWiz/Serial-JSON-Bridge)
**Bare-metal UART driver with JSON command parsing**

My first real embedded project. Built complete UART driver from scratch (no HAL), integrated JSON parser, and learned what "memory constraints" actually means. Foundation for understanding interrupt-driven architecture and hardware debugging.

**Core Tech:** STM32G071RB | Bare-metal C | UART (9600 baud) | JSMN Parser | 18 automated tests

**[→ Full Technical Details](https://blackwiz.github.io/Serial-JSON-Bridge/)**

---

### 💻 [STM32-Serial-Shell](https://github.com/BlackWiz/STM32-Serial-Shell)
**Interactive CLI framework for embedded systems**

Building on Serial-JSON-Bridge, this project adds human-machine interaction through a full command-line interface. Extensible command registration system with built-in commands and JSON support—serving as foundation for remote device management.

**Core Tech:** STM32G071RB | Bare-metal C | CLI Parser | Command Registration | UART | JSMN

**[→ Full Technical Details](https://blackwiz.github.io/STM32-Serial-Shell/)**

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
- [x] Complete custom RTOS kernel (DONE)
- [x] Complete Interactive CLI (DONE)
- [x] Complete HTTP-Ethernet-Assistant Phase 1 (Communication pipeline + LED validation)
- [ ] Complete HTTP-Ethernet-Assistant Phase 2 (Time-based scheduling + RTC)

**Near-term (3-6 Months):**
- [ ] Bootloader design and implementation

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
- ✅ Protocol design experience (networking stack with lwIP)

**What I'm looking for:**
Entry-level to junior embedded/firmware roles where I can apply software engineering fundamentals to hardware development and learn from experienced embedded engineers.

---

## 📫 Let's Connect

Currently building a portfolio for transition to embedded systems roles. Open to discussing firmware opportunities, embedded projects, or just talking about hardware.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sriharishankarsharma/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sriharijosyula@gmail.com)

---

*"After 7 years of working above abstractions, I'm learning what's below them. One register at a time."*
