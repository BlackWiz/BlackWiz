# Sri Hari Shankar Sharma

**Senior Embedded Systems Engineer — 7 years**

I build things close to the metal. Register-level drivers, bare-metal kernels, network stacks on constrained hardware. Currently deepening into Linux kernel internals and driver development.

---

## Projects

### [CortexM0-RTOS-Kernel](https://github.com/BlackWiz/CortexM0-RTOS-Kernel)
**Preemptive RTOS built from scratch on ARM Cortex-M0+**

Complete kernel implementation on STM32G071RB — not a tutorial port, built from first principles.

- **Context switch in ARM assembly** — PendSV handler with explicit PSP/MSP management. Cortex-M0+ constraints required copying R8–R11 via R4–R7 (stmia only works with low registers) and popping LR via R0 — forced deep understanding of ARMv6-M vs ARMv7-M differences.
- **O(1) bitmap scheduler** — priority bitmap with per-priority ready lists. Task selection is constant time regardless of task count.
- **Priority inheritance mutex** — boost_priority() removes task from ready list, updates priority bucket, re-inserts. Prevents the Mars Pathfinder class of priority inversion bugs.
- **Fixed-block memory allocator** — four pool sizes (32/64/128/256 bytes), free-list based, O(1) alloc and free, zero fragmentation.
- **Stack canary** — 0xDEADBEEF at bottom of each task stack. Software overflow detection on M0+ which has no MPU.

**Stack:** STM32G071RB · Bare-metal C · ARM Assembly · ARM GCC · OpenOCD · Logic Analyzer

---

### [HTTP-Ethernet-Assistant](https://github.com/BlackWiz/HTTP-Ethernet-Assistant) *(In Progress)*
**HTTP server on STM32 within 36KB RAM**

Building an HTTP server over Ethernet using lwIP in NO_SYS (bare-metal polling) mode with ENC28J60 SPI Ethernet controller.

- **ENC28J60 silicon errata workaround** — identified silent packet drops caused by a documented MAC-layer errata. Diagnosed via logic analyzer capture. Patched SPI driver to enforce correct register sequencing.
- **36KB RAM constraint** — lwIP configured with custom memory pools, no dynamic allocation in hot path.
- **Parallel bare-metal SPI branch** — replacing HAL SPI driver with direct register-level control to eliminate abstraction overhead and validate timing assumptions.

**Stack:** STM32G071RB · lwIP NO_SYS · ENC28J60 · Bare-metal C · SPI · Logic Analyzer

---

## Technical Skills

| Area | Details |
|------|---------|
| **Languages** | C (primary), C++, ARM Assembly |
| **Architectures** | ARM Cortex-M (ARMv6-M, ARMv7-M), IFX Aurix TriCore |
| **Embedded** | Bare-metal firmware, Interrupt-driven architecture, Register-level drivers, DMA, SPI/UART/I2C/GPIO |
| **OS/RTOS** | Custom RTOS (built), FreeRTOS, AUTOSAR OS, Linux internals (in progress) |
| **Tools** | ARM GCC, GDB, OpenOCD, ST-Link, Make, Logic Analyzer, JTAG, DOORS, Rhapsody |
| **Standards** | MISRA C:2012, AUTOSAR, ASPICE SWE.1–SWE.6 |

---

## Currently Learning

Linux kernel internals — working through system programming from compilation and linking through process model, IPC, scheduling, and character driver development. Building toward kernel module and driver work.

---

## Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sriharishankarsharma/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sriharijosyula@gmail.com)
```
