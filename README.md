\# Asynchronous FIFO Design using Verilog HDL



A 16×8 asynchronous FIFO designed and functionally verified using Verilog HDL and Xilinx Vivado.



\## Overview



This project implements an asynchronous FIFO for transferring data between two independent clock domains.



The design uses:



\- Separate read and write clock domains

\- Binary read/write pointers

\- Gray-coded pointers for clock-domain crossing

\- Two-stage synchronizers for CDC

\- Full and empty flag generation

\- Overflow and underflow protection

\- Pointer and memory wraparound handling



\## FIFO Specifications



| Parameter | Value |

|---|---|

| Data Width | 8 bits |

| FIFO Depth | 16 |

| Address Width | 4 bits |

| Design Type | Asynchronous FIFO |

| HDL | Verilog |

| Tool | Xilinx Vivado |



\## Project Structure



```text

├── async\_fifo.v

├── fifo\_mem.v

├── fifo\_write\_ctrl.v

├── fifo\_read\_ctrl.v

├── gray\_sync.v

├── tb\_async\_fifo.v

├── async\_fifo.v.xpr

├── .gitignore

└── README.md

