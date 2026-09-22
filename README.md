# Asynchronous FIFO Design using Verilog HDL

A 16×8 asynchronous FIFO designed and functionally verified using Verilog HDL and Xilinx Vivado.

## What is an Asynchronous FIFO?

An asynchronous FIFO is used to safely transfer data between two different clock domains.

In this project:

- Data is written using a **write clock**
- Data is read using a **read clock**
- The two clocks can operate at different frequencies
- Gray-coded pointers are used for safe clock-domain crossing
- Synchronizers are used to transfer pointer information between clock domains

## FIFO Specifications

| Parameter | Value |
|-----------|-------|
| Data Width | 8 bits |
| FIFO Depth | 16 |
| Write Clock | Independent |
| Read Clock | Independent |
| HDL | Verilog |
| Simulation Tool | Xilinx Vivado 2024.1 |

## Design Features

- Separate read and write clock domains
- Binary read/write pointers
- Binary-to-Gray code conversion
- Clock-domain crossing using synchronizers
- `FULL` flag generation
- `EMPTY` flag generation
- Overflow protection
- Underflow protection
- FIFO pointer wraparound
- Correct data ordering during read/write operations

## Design Structure

```text
                WRITE CLOCK DOMAIN
                       |
                       v
              +------------------+
              | Write Controller |
              +------------------+
                       |
                Write Pointer
                       |
                  Gray Pointer
                       |
                       v
                +-------------+
                | Synchronizer|
                +-------------+
                       |
                       v

                 +-----------+
                 | FIFO RAM  |
                 |   16 × 8  |
                 +-----------+
                       ^
                       |
                Read Pointer
                       |
                  Gray Pointer
                       |
                       v
                +-------------+
                | Synchronizer|
                +-------------+
                       ^
                       |
              +------------------+
              |  Read Controller |
              +------------------+
                       ^
                       |
                  READ CLOCK DOMAIN