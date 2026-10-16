# 5-Stage Pipelined MIPS32 Processor with UART MMIO

A cycle-accurate, 5-stage pipelined RISC processor implementation written in Verilog HDL, featuring complete instruction execution, pipeline registers, and a memory-mapped I/O (MMIO) UART peripheral interface.

## 🚀 Project Overview
This project implements a custom 5-stage pipelined MIPS32 architecture designed to execute standard arithmetic, memory load/store, and branching operations. It integrates a memory-mapped UART (8N1) communication interface to facilitate serial data transmission directly from processor instructions.

## 🛠️ Key Features & Architecture
* **5-Stage Pipeline Stages:** Implements Instruction Fetch (IF), Instruction Decode (ID), Execution (EX), Memory Access (MEM), and Writeback (WB) stages with pipeline registers.
* **Memory-Mapped UART (MMIO):** Features an integrated UART transmitter and receiver module (`uart_tx`, `uart_rx`, and `uart_mmio` wrapper) mapped to memory addresses for serial communication and status polling.
* **Instruction Execution:** Supports R-type arithmetic operations (`ADD`), memory data transfers (`LW`, `SW`), and system control instructions (`HALT`).
* **Verification & Simulation:** Verified via self-checking testbenches (`tb_pipe_MIPS32_UART`) utilizing waveform simulation for cycle-accurate debugging.

## 📁 Repository Structure
```text
MIPS32-Processor-with-UART-MMIO/
├── rtl/
│   └── mips_uart_soc.v      # Core CPU pipeline, UART modules, and top-level SoC
├── tb/
│   └── tb_pipe_mips32_uart.v # Testbench for cycle-accurate simulation and waveform dump
└── README.md                 # Project documentation
