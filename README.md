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



## Testbench Case Implementation

## Results

## Conclusion

## References
1. [Sunburst Design: Simulation and Synthesis Techniques for Asynchronous FIFO Design](http://www.sunburst-design.com/papers/CummingsSNUG2002SJ_FIFO1.pdf)
2. [VLSI verify Blog - Asynchronous FIFO]()