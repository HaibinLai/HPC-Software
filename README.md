# HPC Learning Roadmap

Haibin Lai

12211612@mail.sustech.edu.cn


## 1. Foundations of HPC

After this step, you can connect to supercomputer and start your journey!

**Missing Semester of CS Education**:

- Strongly recommend you to learn all the videos:
[超算习堂](https://www.easyhpc.net/learning-path/1/step)

- [The Missing Semester of Your CS Education](https://missing-semester-cn.github.io/)
- Linux usage, IBM Spectrum LSF / Slurm usage
- git [learn_git_branching](https://learngitbranching.js.org/?locale=zh_CN)
- shell, vim, gdb

**Programming Basics**:
- Learn Python, C, or C++ (common in HPC).
- Suggested: CS50’s Introduction to Computer Science (Harvard, edX) or Learn Python the Hard Way (online book).


## 2. Computer Architecture and Systems

After this step, you will know how programs run on our computer!

**Digital logic**: 
- [geeks for geeks](https://www.geeksforgeeks.org/digital-electronics-logic-design-tutorials/)
- [UESTC](https://www.icourse163.org/course/UESTC-234014)

**Computer Organization**:
- CPU, memory hierarchy, caches, pipelining.
- [Computer Architecture: a quantitative approach](https://mxlol.gitbook.io/ji-suan-ji-ti-xi-jie-gou-liang-hua-yan-jiu-fang-fa-di-liu-ban-han-hua/qian-yan/nei-rong-gai-shu)

Suggested: Computer Organization and Design by Patterson & Hennessy (book or online lectures).

**Parallel Computing Fundamentals**:
- Concepts like Amdahl’s Law, parallelism types (task, data).
- [平行程式 周志远](https://ocw.nthu.edu.tw/ocw/index.php?page=mobile&type=chapter&cid=231&chid=2574)

Suggested: Introduction to Parallel Computing (online, University of Illinois via Coursera).

**Computer Systems**:

- How can C code runs on your machine?
- CSAPP [link](https://csdiy.wiki/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%B3%BB%E7%BB%9F%E5%9F%BA%E7%A1%80/CSAPP/)



## 3. Parallel Programming


- **OpenMP**:
    - Shared-memory parallel programming in C/C++ or Fortran.
    - Suggested: _OpenMP Tutorials_ (Lawrence Livermore National Lab) or OpenMP official [OpenMP](https://www.openmp.org/resources/tutorials-articles/)
- **MPI (Message Passing Interface)**:
    - Distributed-memory programming for clusters.
    - Suggested: _MPI Tutorial_ by Wes Kendall [MPI](https://mpitutorial.com/).

- **CUDA/Parallel GPU Programming**:
    - GPU programming for NVIDIA hardware.
    - Suggested: _CUDA Programming_ (NVIDIA Developer Program, free).
    - A must learn class if you want to do HPC research

- **Parallel Design Patterns**:
    - Divide-and-conquer, master-worker, stencil computations.
    - [PDP](https://opencsf.org/Books/csf/html/ParallelDesign.html)
    - [Intro](https://www.cnblogs.com/kaige/archive/2012/04/10/parallel_programming_patterns.html)


## 4. Deep into HPC's kernel

- **Database Principles**:

    -  (CMU 15-445/645 & 15-721): [CMU](https://15445.courses.cs.cmu.edu/fall2024/)
        
    - Key topics: Relational models, storage architectures (heaps, log-structured), indexing (B+ trees, hash tables), transaction processing (ACID, concurrency control), recovery (logging, checkpoints), and parallel/distributed query processing.

- **Operating System**:
    - Process management, memory management, scheduling.
    - Suggested: Operating Systems: Three Easy Pieces (free online book). [OSTEP](https://pages.cs.wisc.edu/~remzi/OSTEP/)
    - [MIT 6.1810](https://pdos.csail.mit.edu/6.828/2024/index.html)
    - [rCore](https://rcore-os.cn/rCore-Tutorial-Book-v3/chapter0/index.html)

- **System Tuning and Optimization**:
    - [[2009.06489] The Hardware Lottery](https://arxiv.org/abs/2009.06489)
    - TMA [top-down method](https://rcs.uwaterloo.ca/~ali/cs854-f23/papers/topdown.pdf)
    - [Performance Analysis and Tuning on Modern CPU](https://weedge.github.io/perf-book-cn/zh/)
    - USB including CPU, memory, and I/O tuning.
    - Profiling tools (e.g., perf, gprof, intel VTune), compiler optimizations (e.g., -O3, loop unrolling), and hardware-specific tuning (e.g., NUMA, cache-aware programming).

- **Machine Learning and Deep Learning Fundamentals**:

    - Understand ML and DL basics, focusing on models and architectures relevant to HPC, where parallel computing (e.g., GPU clusters) accelerates training and inference.
        
    - **Basic ML Models**:
        
        - **Decision Trees**, **Support Vector Machines (SVM)**
        - Key topics: Supervised learning (regression, classification), unsupervised learning (clustering), model evaluation (accuracy, precision, recall), and optimization (gradient descent).
            
        - Suggested: CS229: Machine Learning (Stanford, lecture notes) or Machine Learning Crash Course (Google, free).
            
    - **Deep Learning Papers**:
        
        - **AlexNet (2012)**: Introduces deep CNNs with ReLU, dropout, and GPU acceleration for image classification. Paper.
            
        - **VGG (2014)**: Deepens CNNs with small (3x3) filters for improved performance. Paper.
            
        - **ResNet (2015)**: Introduces residual connections to train very deep networks, reducing vanishing gradients. Paper.
            
        - **Transformer (2017)**: Proposes attention-based architecture for NLP, scalable for HPC with parallel processing. Paper.
            
        - Suggested: Read papers with focus on architecture design and HPC relevance (e.g., GPU parallelization in AlexNet, attention mechanisms in Transformer). Use Papers With Code for implementations.


## For scalable system



- **HPC Middleware and Frameworks**:

    - Explore middleware used in HPC clusters, such as job schedulers (Slurm, PBS Pro) and resource managers.
    - Key topics: Workflow orchestration, containerization (e.g., Singularity, Docker for HPC), and cloud-HPC integration.
    - Suggested: [Slurm Workload Manager Documentation](https://slurm.schedmd.com/) or [SingularityCE User Guide](https://docs.sylabs.io/guides/latest/user-guide/).

- **Distributed Systems (MIT 6.824/6.5840)**:

    - big data idea: [GFS](https://pdos.csail.mit.edu/6.824/papers/gfs.pdf) ; [big table](https://research.google/pubs/bigtable-a-distributed-storage-system-for-structured-data/#:~:text=In%20this%20paper%20we%20describe%20the%20simple%20data,we%20describe%20the%20design%20and%20implementation%20of%20Bigtable.) ; [map reduce](https://pdos.csail.mit.edu/6.824/papers/mapreduce.pdf)
        
    - Key topics: MapReduce, Raft consensus algorithm, key-value stores, sharding, and distributed file systems (e.g., GFS, HDFS).
        
    - Suggested: MIT 6.824: Distributed Systems (course website, includes lectures, labs, and papers) or YouTube Lectures. Labs involve implementing MapReduce, Raft, and a fault-tolerant key-value store in Go.


- **Advanced Parallel Algorithms**:
    - Study advanced algorithms for HPC, such as load balancing, fault tolerance, and scalable data structures.
    - Suggested: [Parallel and Distributed Computation: Numerical Methods](https://www.amazon.com/Parallel-Distributed-Computation-Numerical-Methods/dp/1886529019) (book by Bertsekas and Tsitsiklis) or [Introduction to High-Performance Scientific Computing](https://www.siam.org/publications/books/open-access-books/introduction-to-high-performance-scientific-computing/) (free online book).





## For kernel Development


- **eBPF (Extended Berkeley Packet Filter)**:
    - Learn eBPF for advanced performance monitoring, tracing, and system optimization in HPC environments.
    - Key topics: Writing eBPF programs, using tools like `bpftrace` and `BCC`, and monitoring system calls and network performance.
    - Suggested: [eBPF.io](https://ebpf.io/) (official eBPF resources) or [Brendan Gregg’s eBPF Guide](https://www.brendangregg.com/ebpf.html) (tutorials and tools for performance analysis).


- **Linux Kernel Programming**:
    - Key topics: Kernel modules, device drivers, memory management, and kernel-level debugging.
    - Suggested: [Linux Kernel Development](https://www.kernel.org/doc/html/latest/) (official Linux kernel documentation) or [Linux Kernel Programming](https://www.packtpub.com/product/linux-kernel-programming/9781789953435) (book by Kaiwan N Billimoria).




---

