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


## High level 

- **Parallel Design Patterns**:
Process management, memory management, scheduling.
Suggested: Operating Systems: Three Easy Pieces (free online book).

