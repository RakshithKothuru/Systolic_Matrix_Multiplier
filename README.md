# 4×4 Systolic Matrix Multiplication Accelerator

This project implements a **4×4 systolic array** for multiplying two 32-bit integer matrices using Verilog HDL. It showcases a fully **pipelined, parallel architecture** where each Processing Element (PE) performs a multiply-accumulate (MAC) operation. The systolic structure allows for high throughput and rhythmic data flow — making it suitable for acceleration in DSP and AI/ML workloads.

## 🚀 Why Systolic?

Unlike conventional matrix multipliers, this design uses a **systolic array architecture**, where data flows synchronously and locally between adjacent processing elements (PEs). The term "systolic" refers to the **rhythmic, pipelined movement of data**, inspired by the pulsing of blood in the heart.

Each PE:
- Receives one element of A from the **left**
- Receives one element of B from the **top**
- Performs a MAC operation
- Sends data **rightward** and **downward** to neighbors

This local communication model reduces global routing complexity and supports **full parallelism** with **minimal control overhead**.

## 🧠 Architecture Overview

- **Type**: 2D 4×4 Systolic Array
- **PE Count**: 16 MAC units (each: 1 multiplier + 1 accumulator)
- **Operands**: Two 4×4 matrices of 32-bit signed integers
- **Computation**: Each PE computes partial products and accumulates them
- **Dataflow**: Left-to-right and top-to-bottom propagation
- **Pipelining**: Each PE is registered (output pipelined), enabling concurrent computations


## 🛠️ Tools Used

- **Verilog HDL** – Hardware description and RTL implementation
- **Icarus Verilog** – Simulation tool
- **GTKWave** – Waveform visualization
- **VS Code** – Code editing and project organization

## ✅ Features

- Spatially pipelined matrix multiplication with parellelism using 16 MAC units
- Clocked MAC units with pipeline registers
- Local data reuse for efficient computation
- Clean modular design: PE → Row → Array

## 🔗 References

- Hennessy, J. L., & Patterson, D. A. (2017). *Computer Architecture: A Quantitative Approach*. Morgan Kaufmann.
- [Systolic array - Wikipedia](https://en.wikipedia.org/wiki/Systolic_array)
