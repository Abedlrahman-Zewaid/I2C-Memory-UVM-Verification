# I2C Memory with UVM-Based Verification

## 📌 Overview
This project implements an **I2C-based memory module** in SystemVerilog and verifies it using a **UVM (Universal Verification Methodology) testbench**.  
It demonstrates RTL design and functional verification concepts including drivers, monitors, sequences, scoreboard, and environment integration.

---

## ⚡ Design (DUT)
- **Module**: `i2c_mem`
- **Functionality**:
  - Implements a simple I2C memory slave
  - Supports read and write transactions
  - Uses an internal 128x8 memory array
  - Provides a `done` signal after each operation

---


## 🧪 Verification Environment
The testbench is built using **UVM** with the following components:

- **Transaction** → Defines fields (`addr`, `din`, `datard`, `op` type).
- **Sequences** → Generate different operations:
  - Write sequence
  - Read sequence
  - Reset sequence
- **Driver** → Drives stimulus to the DUT via the interface.
- **Monitor** → Samples DUT inputs/outputs and forwards them to the scoreboard.
- **Scoreboard** → Checks functional correctness by comparing expected vs. actual data.
- **Agent** → Wraps sequencer, driver, and monitor.
- **Environment** → Integrates agent and scoreboard.
- **Test** → Runs different sequences in order.
