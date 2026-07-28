
# Pipelined MIPS32 Processor with UART MMIO

A Verilog HDL implementation of a **5-stage pipelined MIPS32 processor** integrated with a **memory-mapped UART (8N1)** peripheral for serial communication. The project demonstrates processor datapath design, instruction execution, and peripheral interfacing using Memory-Mapped I/O (MMIO).

---

## Features

- 5-stage pipelined MIPS32 processor
  - Instruction Fetch (IF)
  - Instruction Decode (ID)
  - Execute (EX)
  - Memory Access (MEM)
  - Write Back (WB)

- Two-phase clocking architecture (`clk1` and `clk2`)

- Memory-Mapped UART (8N1)
  - UART Transmitter
  - UART Receiver
  - Status Register
  - MMIO-based communication

- Basic instruction support
  - ADD
  - ADDI
  - LW
  - SW
  - Branch operations
  - HALT

- RTL simulation and waveform verification

---

## Architecture

The processor consists of the following major modules:

- Program Counter (PC)
- Instruction Memory
- Register File
- ALU
- Pipeline Registers
- Data Memory
- Control Logic
- UART MMIO Peripheral

The UART is connected through **Memory-Mapped I/O**, allowing the processor to communicate with external devices using standard load/store instructions.

---

## UART Memory Map

| Address | Description |
|----------|-------------|
| `0x00` | UART Transmit Data Register |
| `0x01` | UART Receive Data Register |
| `0x02` | UART Status Register |

---

## Repository Structure

```
├── top_soc.v
├── pipe_MIPS32_UART.v
├── uart_tx.v
├── uart_rx.v
├── uart_mmio.v
├── tb_pipe_MIPS32_UART.v
└── README.md
```

---

## Simulation

The design was verified using a Verilog testbench by:

- Applying reset and clock generation
- Executing sample instruction sequences
- Monitoring pipeline registers
- Verifying UART transmit and receive functionality
- Inspecting waveforms using GTKWave

The testbench also dumps key internal signals including:

- Program Counter (PC)
- Pipeline registers
- Register values
- UART transmit and receive signals
- MMIO interface signals

---

## Tools Used

- Verilog HDL
- EDA Playground
- GTKWave

---

## Future Improvements

- Data forwarding unit
- Hazard detection and pipeline stalling
- Branch hazard handling
- Extended MIPS32 instruction support
- Interrupt handling
- FPGA implementation on Xilinx devices

---

## Learning Outcomes

This project provided hands-on experience with:

- RTL design in Verilog HDL
- Processor datapath implementation
- Instruction pipelining
- Memory-Mapped I/O (MMIO)
- UART communication (8N1 protocol)
- Digital system verification using testbenches and waveform analysis

---

## License

This project is intended for educational and learning purposes.
