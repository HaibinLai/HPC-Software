# HPCG简介 (Introduction to HPCG)

Source code Repo:

https://github.com/hpcg-benchmark/hpcg.git

Official Website:

https://www.hpcg-benchmark.org/


**中文**  

学习难度：简单

HPCG（High Performance Conjugate Gradient，高性能共轭梯度）基准测试用于评估超级计算机在解决稀疏线性系统问题上的性能，模拟科学计算中常见的数值模拟任务。它主要计算以下内容：  
1. **稀疏矩阵-向量乘法（SpMV）**：处理大型稀疏矩阵与向量的乘法，测试内存带宽和计算效率。  
2. **共轭梯度（CG）求解器**：通过迭代法求解 \( Ax = b \) 形式的线性方程组，评估系统的数值稳定性和收敛速度。  
3. **多重网格（MG）预条件器**：加速CG求解，测试多层次网格上的计算和通信效率。  
4. **向量操作（DDOT, WAXPBY）**：包括点积和向量加减法，衡量基本线性代数运算性能。  

HPCG强调内存访问效率和分布式并行性能，反映实际应用（如气候建模、流体力学）的计算需求，结果以**GFLOPS**（每秒十亿次浮点运算）表示。

**English**  

Learning Difficulty: Easy

HPCG (High Performance Conjugate Gradient) is a benchmark designed to evaluate supercomputer performance in solving sparse linear systems, mimicking common numerical simulation tasks in scientific computing. It primarily computes:  
1. **Sparse Matrix-Vector Multiplication (SpMV)**: Performs multiplication of large sparse matrices with vectors, testing memory bandwidth and computational efficiency.  
2. **Conjugate Gradient (CG) Solver**: Solves linear systems of the form \( Ax = b \) iteratively, assessing numerical stability and convergence speed.  
3. **Multigrid (MG) Preconditioner**: Accelerates CG solving, evaluating computation and communication efficiency across multi-level grids.  
4. **Vector Operations (DDOT, WAXPBY)**: Includes dot products and vector addition/subtraction, measuring basic linear algebra performance.  

HPCG emphasizes memory access efficiency and distributed parallel performance, reflecting real-world applications (e.g., climate modeling, fluid dynamics). Results are reported in **GFLOPS** (gigaflops, billions of floating-point operations per second).