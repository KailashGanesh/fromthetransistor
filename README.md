# From the Transistor to the Web Browser  

Hiring is hard, a lot of modern CS education is really bad, and it's hard to find people who understand the modern computer stack from first principles.

---

## Section 0: Prerequisites

- Terminal
- Git
- Python
- C Basic Syntax
- DSA

Everything else you learn as you go, or at least that's the plan.

## Section 1: Cheating Our Way Past the Transistor  
We aren't going to build a transistor from scratch. Instead, we'll study them, understand what they are, and move forward with tools that build on them.

| # | Unit Name                          | Essay/Notes Link | YouTube | Time Taken |
|---|-----------------------------------|------------------|---------|------------|
| 1 | What's a transistor anyway?       | [Essay](#)       |         |            |

#### Bonus Reading
| # | Title                                             | Paper Link | Notes Link | YouTube | Time Taken |
|---|---------------------------------------------------|------------|------------|---------|------------|
| 1 | Could a neuroscientist understand a microprocessor? | [Paper](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005268) | |  |     |
| 2 | Can a biologist fix a radio?                      | [Paper](https://www.cell.com/cancer-cell/pdf/S1535-6108(02)00133-2.pdf) | |  |       |

---

## Section 2: Bringup – What Language is Hardware Coded In?  

| # | Unit Name                     | Notes/Resources | YouTube | Time Taken |
|---|-------------------------------|------------------|---------|------------|
| 1 | Learn Verilog                 |                  |         |            |
| 2 | Blink an LED                  |                  |         |            |
| 3 | Build a UART (MMIO intro)     |                  |         |            |

**Details:**
- Blinking an LED (Verilog, ~10 lines) -- Your first little program! Getting the simulator working. Learning Verilog.
- Building a UART (Verilog, ~100 lines) -- An intro chapter to Verilog, copy a real UART, introducing the concept of MMIO, though the serial port may be semihosting. Serial test echo program and led control.

---

## Section 3: Processor – What is a Processor Anyway?  

| # | Unit Name                        | Notes/Resources | YouTube | Time Taken |
|---|----------------------------------|------------------|---------|------------|
| 1 | Code an Assembler (Python)       |                  |         |            |
| 2 | Build a RISC-V CPU (Verilog)     |                  |         |            |
| 3 | Code a Boot ROM (ASM)            |                  |         |            |

**Details:**
- Coding an assembler (Python, ~500 lines) -- Straightforward and boring, write in python. Happens in parallel with the CPU building. Teaches you RISC-V assembly. 
- Building a RISC-V CPU (Verilog, ~1500 lines) -- RV32IMF implementation with a simple pipeline (fetch, decode, execute), floating-point support (a little bit of mixed precision never hurt anyone), and all the basics you need.
- Coding a bootrom (Assembler, ~40 lines) -- This allows code download into RAM over the serial port, and is baked into the FPGA image.

---

## Section 4: Compiler – A "High" Level Language  

| # | Unit Name                            | Notes/Resources | YouTube | Time Taken |
|---|--------------------------------------|------------------|---------|------------|
| 1 | Build a C Compiler (Haskell)         |                  |         |            |
| 2 | Build a Linker (Python)              |                  |         |            |
| 3 | Write `libc` and `malloc` (C)        |                  |         |            |
| 4 | Build Ethernet Controller (Verilog)  |                  |         |            |
| 5 | Write a Bootloader (C)               |                  |         |            |

**Details:**
- Building a C compiler (Haskell, ~2000 lines) -- Cover the basics of compiler design. Write in Haskell.
- Building a linker (Python, ~300 lines) -- Output ELF files. Use for testing with QEMU, semihosting.
- libc + malloc (C, ~500 lines) -- Basic libc implementation with memory management.
- Building an ethernet controller (Verilog, ~200 lines) -- Talk to a real PHY.
- Writing a bootloader (C, ~300 lines) -- Write ethernet program to boot kernel over UDP.

---

## Section 5: Operating System – Software We Take for Granted  

| # | Unit Name                     | Notes/Resources | YouTube | Time Taken |
|---|-------------------------------|------------------|---------|------------|
| 1 | Build an MMU (Verilog)        |                  |         |            |
| 2 | Build a Unix-like OS (C)      |                  |         |            |
| 3 | SD Card Interface (Verilog)   |                  |         |            |
| 4 | FAT Filesystem (C)            |                  |         |            |
| 5 | init, shell, cat, ls, rm (C)  |                  |         |            |

**Details:**
- Building an MMU (Verilog, ~1000 lines) -- ARM9ish, explain TLBs and other fun things.
- Building an operating system (C, ~2500 lines) -- UNIXish, only user space threads.
- Talking to an SD card (Verilog, ~150 lines) -- The last hardware component.
- FAT (C, ~300 lines) -- A real filesystem implementation.
- Basic Unix utilities (C, ~250 lines) -- Your first user space programs.

---

## Section 6: Browser – Coming Online  

| # | Unit Name                         | Notes/Resources | YouTube | Time Taken |
|---|-----------------------------------|------------------|---------|------------|
| 1 | TCP Stack (C)                     |                  |         |            |
| 2 | telnetd (C)                       |                  |         |            |
| 3 | Dynamic Linking (C)               |                  |         |            |
| 4 | Text Web Browser (C + Terminal)   |                  |         |            |

**Details:**
- Building a TCP stack (C, ~500 lines) -- Kernel networking implementation.
- telnetd (C, ~50 lines) -- Multi-process network service.
- Dynamic linking (C, ~300 lines) -- Space-saving dynamic linking implementation.
- Text-based web browser (C, ~500+ lines) -- Using ANSI and terminal features.

---

## Section 7: Physical – Running on Real Hardware  

| # | Unit Name                              | Notes/Resources | YouTube | Time Taken |
|---|----------------------------------------|-----------------|---------|------------|
| 1 | Talk to FPGA via JTAG (C)              |                  |         |            |
| 2 | Build an FPGA Board                    |                  |         |            |
| 3 | Bringup and Flash                      |                  |         |            |

**Details:**
- FPGA communication (C, ~200 lines) -- USB MCU to bitbang JTAG.
- Hardware components include:
  - FPGA BGA reflow
  - 50mhz clock
  - USB JTAG port and flasher
  - LEDs and reset button
  - USB-FTDI serial port
  - SD card slot
  - Ethernet port
  - Expansion connector
  - PS/2 connector on the board to taunt you
