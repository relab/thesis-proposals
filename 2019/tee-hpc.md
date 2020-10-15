# Trusted Execution for HPC

This project involves the understanding, evaluation, analysis, and development of trusted environments for securely and privately executing scientific software in high-performance computing environments.  It is a partnership with Dr. Sean Peisert at Lawrence Berkeley National Laboratory, which may also lead to possible summer student internships at the Berkeley Lab.

### Background

### Prerequisties / Desired Skills:

- Excellent programming skills (C / C++ / Python)
- Computer Architecture
- Operating Systems

#### Optional Skills:
- Scientific Computing

### Background

Scientific computing periodically involves "sensitive" data that must be protected with increased levels of security, for example, to conform with terms imposed by private industry to protect proprietary data, and/or government regulations imposed.  However, the environments created to protect those environments often has significant usability challenges.  For example, such data is often stored in a very isolated and locked-down environment, and for users to access and compute on that data.  It is the onerous usability requirements that are cumbersome for the scientific community which is mostly used to working in very open environments, be they their own desktop computing systems, all the way up to high-performance computing resources.

### Project Description

This project envisions a scientific computing environment --- ideally one that is capable of scaling to "high-performance" (HPC) scales and use cases --- that leverages trusted execution environments (TEEs) as a way of leveraging trusted hardware / software controls to maintain or even increase security, while also maintaining performance, and, importantly, potentially enabling security controls with high barriers to usability to be relaxed.  We envision that this would be achieved through the use of strategic combinations of hardware trusted execution environments, multiparty computation techniques, and/or blockchain smart contracts.

Note that although to the best of our knowledge, current TEEs focus on CPUs and possibly GPUs, a goal of this work is to support CPUs, GPUs, other types of accelerators, and possibly even FPGAs, as such chips are commonly used for the types algorithms used in scientific computing.

The architecture that we envision is one in which "sensitive" data cannot be computed upon unless via the TEE, and similarly, cannot be output unless via the TEE, which also enables output to be forced to protected through some kind of gating policy, such as differential privacy.  We imagine this involves some kind of software framework that forms an access control barrier with the sensitive data, forcing access to and computation over that data through the TEE.  

The core ideas are: (i) a thorough understanding of existing technologies, including their benefits and limitations, with an eye to the impact of those limitations on the needs of scientific computing (e.g., communication between processors, floating point, very large memory and data); (ii) a description of ways in which, for the technologies deemed appropriate for scientific computing, existing scientific computing software would need to be modified in order to run effectively, e.g., by leveraging one of the three technologies/techniques identified above in different ways; and (iii) ways in which the weaknesses and limitations identified in (ii) should be overcome in future designs, an examination of which of the “near future” designs currently being discussed (e.g.,  RISC-V).

### Use Cases / Data

Initial use cases are supporting the analysis of neuroimaging data for traumatic brain injuries, and analysis of road maps and vehicle patterns to identify congestion points and offer optimized routes.  Analysis techniques for the neuroimaging data are largely statistical machine learning techniques (not deep learning) over the images.  Analysis for the transportation data  is basically a shortest path algorithm, although there is also a parallel discrete event simulation that is required to run the graph analysis.  

Datasets for these use cases are available in "appropriate" form are available from the Berkeley Lab, including neuroimaging data (brain CT scans) and transportation data (graphs of routes and real-time GPS location data).  

Code that can serve as a proxy algorithm for testing is also likely available.

Compute systems, such as test systems preceding the new Cray / AMD / NVIDIA pre-exascale supercomputer, "NERSC-9" or "Perlmutter" will also be made available for testing, as are cloud services, such as TEEs present in AWS, Azure, and GCP (for SGX and AMD SME/SEV systems), and AWS's FireSim for FPGAs.

- [NERSC-9-doe](https://www.energy.gov/articles/doe-build-next-generation-supercomputer-lawrence-berkeley-national-laboratory)
- [NERSC-9-hpcwire](https://www.hpcwire.com/2018/10/30/cray-unveils-shasta-lands-nersc-9-contract/)

### Tasks / Milestones

- Analyze and evaluate different TEE technologies and practical limitations
- Write survey
- Analyze where non-TEE technologies (cryptography, blockchain smart contracts) can help
- Run and evaluate benchmarking experiments for HPC scientific computing using one or two initial TEEs identified as most promising
- Design trusted execution architecture based on key technologies identified
- Implement generalized software system for executing scientific codes without trusting the operating system or hypervisors
- Evaluate implementation using microbenchmarks
- Evaluate implementation using real scientific software and data
- Identify recommendations for future RISC-V architectures

### Reading Material

- [Intel SGX Explained](https://eprint.iacr.org/2016/086.pdf)
- [SGX2](http://caslab.csl.yale.edu/workshops/hasp2016/HASP16-16_slides.pdf)
- [Arm TrustZone explained](https://www.microcontrollertips.com/embedded-security-brief-arm-trustzone-explained/)
- [Komodo: Using verification to disentangle secure-enclave hardware from software](https://www.microsoft.com/en-us/research/wp-content/uploads/2017/10/komodo.pdf)
- [AMD Secure Encrypted Virtualization (SEV)](https://developer.amd.com/sev/)
- [AMD x86 Memory Encryption Technologies](https://www.usenix.org/conference/usenixsecurity16/technical-sessions/presentation/kaplan)
- [RISC-V ISA](https://riscv.org/2018/01/more-secure-world-risc-v-isa/)
- [Towards An Open-Source, Formally-Verified Secure Enclave](https://keystone-enclave.org/files/dawn-nsf-2018-v5.pdf)
