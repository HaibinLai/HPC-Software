
# HPCG Compilation Guide

This guide provides step-by-step instructions for compiling the High Performance Conjugate Gradient Benchmark (HPCG) version 3.1, based on the provided installation script. It covers cloning or downloading the source code, configuring the build environment, building the executable, and testing the installation.

## Prerequisites

- A Linux-based system or compatible environment.
- C++ compiler supporting STL and MPI constructs (e.g., `g++`, `mpicxx`).
- MPI implementation installed (e.g., OpenMPI, MPICH).
- Optional: CMake or Autoconf for alternative configuration methods.
- Basic tools like `make`, `tar`, and `gunzip`.

## Step 1: Obtain the Source Code

### Option 1: Clone from GitHub

1. Clone the official HPCG repository from GitHub:
    
    ```bash
    git clone https://github.com/hpcg-benchmark/hpcg
    ```
    
2. Navigate to the cloned directory:
    
    ```bash
    cd hpcg
    ```
    

### Option 2: Download and Unpack

1. Download the tarball from [http://hpcg-benchmark.org](http://hpcg-benchmark.org/).
2. Uncompress and extract the tarball:
    
    ```bash
    gunzip hpcg.tar.gz
    tar -xvf hpcg.tar
    ```
    
3. Navigate to the extracted `hpcg` directory:
    
    ```bash
    cd hpcg
    ```
    

The `hpcg` directory is referred to as the **top-level directory** in this guide.

## Step 2: Configuration

HPCG supports three configuration methods: Make-based, CMake-based, and Autoconf-based. The Make-based method is described in detail below, as it is the most straightforward. Refer to the original script for CMake or Autoconf instructions if preferred.

### Make-Based Configuration

1. **Create a Configuration File**:
    
    - In the `setup` directory under the top-level directory, create a file named `Make.<arch>`, where `<arch>` is a user-defined name for your system (e.g., `Make.Linux`).
        
    - Example:
        
        ```bash
        cd setup
        cp Make.MPI_GCC Make.Linux
        ```
        
    - Edit `Make.Linux` to specify the following variables:
        
        - `MPdir`: Path to the MPI installation (e.g., `/usr/lib64/openmpi`).
        - `MPinc`: Path to MPI header files (e.g., `-I$(MPdir)/include`).
        - `MPlib`: Path to MPI libraries (e.g., `$(MPdir)/lib`).
        - `HPCG_OPTS`: Compiler optimization flags (e.g., `-O3`).
        - `CXX`: C++ compiler (e.g., `mpicxx`).
        - `CXXFLAGS`: Compiler flags (e.g., `-std=c++11`).
        - `LINKER`: Linker (e.g., `mpicxx`).
        - `LINKERFLAGS`: Linker flags (e.g., `-L$(MPdir)/lib`).
        
        Example `Make.Linux`:
        
        ```makefile
        MPdir = /usr/lib64/openmpi
        MPinc = -I$(MPdir)/include
        MPlib = -L$(MPdir)/lib
        HPCG_OPTS = -O3
        CXX = mpicxx
        CXXFLAGS = -std=c++11
        LINKER = mpicxx
        LINKERFLAGS = -L$(MPdir)/lib
        ```
        
2. **Choose Build Type**:
    
    - **In-Source Build**: Object files and the executable are built in the source directory. No separate configuration step is needed.
    - **Out-of-Source Build**: Create a separate build directory to keep source and build files separate.
        
        ```bash
        mkdir build
        cd build
        /path/to/hpcg/configure Linux
        ```
        
        Replace `/path/to/hpcg` with the absolute or relative path to the top-level `hpcg` directory, and `Linux` with the suffix of your `Make.<arch>` file.

## Step 3: Build

1. **In-Source Build**:
    
    - From the top-level directory, run:
        
        ```bash
        make setup/Make.Linux
        ```
        
    - This creates the executable `bin/xhpcg`.
2. **Out-of-Source Build**:
    
    - From the `build` directory, run:
        
        ```bash
        make
        ```
        
    - This creates the executable `bin/xhpcg` in the `build` directory.

## Step 4: Test

1. Navigate to the `bin` directory:
    
    ```bash
    cd bin
    ```
    
2. Run a quick test with the default `hpcg.dat` file using 8 MPI processes:
    
    ```bash
    mpirun -np 8 ./xhpcg
    ```
    
3. To specify custom problem dimensions (e.g., `NX=32`, `NY=24`, `NZ=16`):
    
    ```bash
    mpirun -np 8 ./xhpcg 32 24 16
    ```
    
4. To use command-line options for dimensions and runtime (e.g., `NX=NY=NZ=16`, 30-minute runtime):
    
    ```bash
    mpirun -np 4 ./xhpcg --nx=16 --rt=1800
    ```
    

## Step 5: Tuning (Optional)

Performance can be tuned by modifying the `hpcg.dat` file in the top-level directory. Refer to the `TUNING` file in the top-level directory for detailed instructions.

## Step 6: Compile-Time Options (Optional)

Add the following options to `HPCG_OPTS` in `Make.<arch>` to enable specific features:

- `-DHPCG_DEBUG`: Enable modest debugging.
- `-DHPCG_CONTIGUOUS_ARRAYS`: Allocate sparse matrix arrays contiguously for better prefetching.
- `-DHPCG_DETAILED_DEBUG`: Enable verbose debugging.
- `-DHPCG_NO_MPI`: Disable MPI support.
- `-DHPCG_NO_OPENMP`: Disable OpenMP support.
- `-DHPCG_DETAILED_TIMING`: Enable detailed timers.

By default, HPCG enables MPI and OpenMP support and disables detailed timing.

## Troubleshooting

- **MPI Errors**: Ensure `MPdir`, `MPinc`, and `MPlib` are correctly set to point to your MPI installation.
- **Compiler Errors**: Verify that `CXX` and `CXXFLAGS` are compatible with your system’s C++ compiler.
- **Missing Executable**: Check that the `bin` directory contains `xhpcg` after building.

## Further Information

For the latest updates and additional details, visit [http://hpcg-benchmark.org](http://hpcg-benchmark.org/).