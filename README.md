# Optimized Polynomial Multiplier Architectures for Post-Quantum KEM Saber

This is the Verilog source code of three optimized architectures for polynomial multiplication in Saber, as described in the article "Optimized Polynomial Multiplier Architectures for Post-Quantum KEM Saber", published at DAC 2021 by Andrea Basso and Sujoy Sinha Roy.

### Brief introduction

We propose three optimized architectures:

* A high-speed variant (High-speed I) that reduces the area consumption by centralizing coefficient-wise multiplication. This streamlines the implementation, avoids the repetition of the same computations, and significantly reduces the overall area consumption with no impact on performance.
* A second high-speed variant (High-speed II) that offloads coefficient-wise multiplications to DSPs while still exploiting the small secret coefficients. Compared to regular DSP usage, we obtain 4x the performance by fitting four coefficient-wise multiplications inside a single DSP. Our design uses 128 DSPs to compute a full multiplication in 128 cycles.
* A lightweight polynomial multiplier that targets area and power reduction. To reduce power consumption andcycle count, we minimize the number of memory read/write accesses and do as much computation as possible on the read operand data before writing the result back into the memory. This implementation only consumes 541 LUTs and 301 flip-flops, but requires 19,471 cycles.

### How to use

The proposed architectures can be used as a drop-in replacement for the polynomial multiplier in the architecture proposed in [1], whose source code is available [here](https://github.com/sujoyetc/SABER_HW).


[1] Sinha Roy, S., & Basso, A. (2020). _High-speed Instruction-set Coprocessor for Lattice-based Key Encapsulation Mechanism: Saber in Hardware_. IACR Transactions on Cryptographic Hardware and Embedded Systems, 2020(4), 443-466. https://doi.org/10.13154/tches.v2020.i4.443-466