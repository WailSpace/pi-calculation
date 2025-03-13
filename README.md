# pi-calculation
Calculating π with Arbitrary Precision: Why GPU (CUDA) is Not Feasible and How mpmath Makes It Easier

I am exploring the computation of π to high precision (millions of digits) purely out of interest. While GPUs are excellent for parallel computation, they are not well-suited for arbitrary-precision arithmetic, which is required for high-precision π calculation. In this post, I compare two approaches:

1. GPU with CuPy: A simplified implementation using fixed-precision arithmetic.

2. CPU with mpmath: A highly optimized implementation using arbitrary-precision arithmetic.

Why GPU (CUDA) is Not Feasible
1. Fixed Precision:

GPUs are optimized for fixed-precision arithmetic (e.g., float32, float64).

The Chudnovsky algorithm involves extremely large numbers that exceed the limits of fixed-precision types, leading to overflow and incorrect results.

2. Arbitrary Precision:

Arbitrary-precision arithmetic requires dynamic memory allocation and complex algorithms, which are not well-suited for GPU architectures.

Libraries like mpmath are designed for CPUs and cannot be easily ported to GPUs.

3. Performance Overhead:

The overhead of launching CUDA kernels and transferring data between CPU and GPU outweighs the benefits of GPU acceleration for this task.
