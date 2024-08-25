# AMBA AXI Implementation in SystemVerilog

This project implements the AMBA (Advanced Microcontroller Bus Architecture) AXI (Advanced eXtensible Interface) protocol using SystemVerilog. It includes both the design implementation and verification using a UVM testbench.

## Overview

The AMBA AXI protocol is a high-performance, high-frequency system interface for connecting and managing functional blocks in a System-on-Chip (SoC) design. This implementation focuses on the AXI slave interface and includes the following key components:

- Write Address Channel
- Write Data Channel
- Write Response Channel
- Read Address Channel
- Read Data Channel

## Features

- Full implementation of AXI slave interface
- Support for different burst types: FIXED, INCR, and WRAP
- Handling of various transfer sizes
- Proper address alignment and boundary calculations
- Error handling for unsupported sizes and out-of-range addresses

## Implementation Details

The main module `axi_slave` implements the AXI slave interface with the following key features:

- FSMs (Finite State Machines) for each channel to manage the AXI protocol
- Functions to handle different burst types and transfer sizes
- Memory array to store and retrieve data
- Proper handling of AXI signals including valid, ready, and last signals

## Testbench Overview

The testbench is built using a modular, class-based approach in SystemVerilog. It implements a complete verification environment for the AXI slave interface, including:

- Generator
- Driver
- Monitor
- Scoreboard

### Key Components

1. **Transaction Class**: Defines the structure of AXI transactions, including constraints for randomization.

2. **Generator Class**: Creates randomized transactions and sends them to the driver.

3. **Driver Class**: 
   - Implements the reset logic
   - Handles different write modes: Fixed, Incremental, and Wrap
   - Handles different read modes: Fixed, Incremental, and Wrap

4. **Monitor Class**: Observes the interface signals and captures transactions.

5. **Scoreboard Class**: 
   - Receives transactions from the monitor
   - Implements a simple memory model
   - Compares read data with expected data

6. **Testbench Module**: 
   - Instantiates and connects all components
   - Sets up the simulation environment
## Usage

To use this implementation:

1. Ensure you have a SystemVerilog compatible simulator (e.g., ModelSim, VCS, etc.)
2. Compile the design files and testbench
3. Run the simulation and analyze the results
