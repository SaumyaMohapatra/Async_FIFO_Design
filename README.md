# Asynchronous FIFO Design

This repo contains verilog code for an asynchronous FIFO.

## Table of Contents
1. [Author](#authors)
2. [Introduction](#introduction)
3. [Design Space Exploration and Design Strategies](#design-space-exploration-and-design-strategies)
4. [Testbench Case Implementation](#testbench-case-implementation)
5. [Implementation Challenges](#implementation-challenges)
6. [Results](#results)
7. [Conclusion](#conclusion)
8. [References](#references)
   
## Author
[UJJWAL CHAUDHARY](https://www.linkedin.com/in/ujjwal-chaudhary-4436701aa/), M. Tech. ESE 2023-25, IISc Bangalore

## Introduction

- FIFO stands for "First-In, First-Out." It is a type of data structure or buffer in which the first data element added (the "first in") is the first one to be removed (the "first out"). This structure is commonly used in scenarios where order of operations is important.
- Async FIFO, or Asynchronous FIFO, is a FIFO buffer where the read and write operations are controlled by independent clock domains. This means that the writing process and the reading process are driven by different clocks, which are not synchronized. Async FIFOs are used to safely transfer data between these asynchronous clock domains.
- <img src=".\Assets\FIFO_in_system.png" alt="Alt Text" width="500">
- Async FIFOs are used in various applications where data needs to be transferred between two parts of a system that operate on different clock frequencies. Some common use cases include:

    - Interfacing between different clock domains: For example, transferring data between a high-speed processing unit and a slower peripheral.
    - Communication between different modules: In a system-on-chip (SoC) where different modules might operate at different clock rates.
    - Buffering data: To handle variations in data flow rates between producer and consumer components in digital systems.
    - Bridging clock domains: In FPGA designs and other digital circuits where subsystems run at different clock speeds

## Design Space Exploration and Design Strategies

The block diagram of async. FIFO that is implemented in this repo is given below. 

<img src=".\Assets\Async_FIFO.png" alt="Alt Text" width="700">

For implementing this FIFO, I have divided the design into ___ modules:-

1. **``FIFO.v``**: The top-level wrapper module includes all clock domains and is used to instantiate all other FIFO modules. In a larger ASIC or FPGA design, this wrapper would likely be discarded to group the FIFO modules by clock domain for better synthesis and static timing analysis.
2. **``FIFO_memory.v``**: This modules contains the buffer or the moeory of the FIFO, which has both the clocks. This is a dual port RAM.
3. **``Two_ff_sync.v``**: This module consist of two flip-flops that are connected to each other to form a 2 flip-flop synchronizer. This module will have two instances, one for write to read clock pointer synchronization and other for read to write clock pointer synchronization
4. ***``rptr_empty.v``**: This modlue consist of the logic for the Read pointer handler. It is completely synchronized by read clock and consist of the logic for generation of FIFO empty signal.
5. ***``wptr_empty.v``**: This modlue consist of the logic for the Write pointer handler. It is completely synchronized by write clock and consist of the logic for generation of FIFO full signal.

## Testbench Case Implementation

## Results

## Conclusion

## References
1. [Sunburst Design: Simulation and Synthesis Techniques for Asynchronous FIFO Design](http://www.sunburst-design.com/papers/CummingsSNUG2002SJ_FIFO1.pdf)
2. [VLSI verify Blog - Asynchronous FIFO]()