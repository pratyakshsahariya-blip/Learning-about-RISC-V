# Learning-about-RISC-V
 In this repository we will be learning about RISC-V.

 We will be understanding **RISC-V** — where it came from, why it was created, how it evolved, what it is used for today, and the major projects being built around it.

---

 ## 1\. What is RISC-V?
  
    RISC-V stands for Reduced Instruction Set Computer V, where the "V" represents the Roman numeral for 5, indicating it is the fifth generation of the RISC architecture developed at the University of California, Berkeley. It is a free and open-standard **Instruction Set Architecture (ISA)**.
  
    Reduced Instruction Set Computer means that the instructions inside chips are drastically reduced and simplified, to make it more readable and easy to modify later on. Which was not done at that time by anyone else (like Intel or ARM).
  
    An ISA is essentially the contract between software and a processor. It defines things such as:
  
     - What instructions a CPU understands
     - How registers work
     - How memory is accessed
     - How software interacts with the processor
     - How privileged operating-system functions work
     - What optional capabilities a processor can support
  
    RISC-V is based on the **RISC — Reduced Instruction Set Computer** philosophy.
  
    The important distinction is:
  
    --> RISC-V is not one CPU.
  
    It is an open standard for the instruction set that a CPU can implement.
  
    That means different companies can build very different processors while speaking the same RISC-V instruction language.
  
    RISC-V International describes the ISA and its ratified extensions as open and royalty-free building blocks that organizations can use to create their own implementations.

---

 # 2\. When was RISC-V created?
 
   **RISC-V began at UC Berkeley in 2010.**
 
   The official RISC-V birthday is generally recognized as:
 
   **May 18, 2010**
 
   That was when the Berkeley team decided to create a new clean-slate ISA.
 
   The principal designers were:
 
    - Andrew Waterman
    - Yunsup Lee
    - Krste Asanović
    - David Patterson
 
   The work started as part of research at the **Parallel Computing Laboratory (Par Lab)**
 
   RISC-V International now describes May 18, 2010 as the project's official birthday.

---

 # 3\. Why was RISC-V created in the first place?

   This is probably the most important part of the history.
 
   RISC-V was not originally created to compete with Intel or ARM.
 
   It began as a research and education project.
 
   The Berkeley researchers wanted a processor architecture that they could freely modify, implement, teach, and experiment with.
 
   The official RISC-V specification explains that the Berkeley group wanted:
 
    - A flexible ISA for computer architecture research
    - A platform for university education
    - An ISA that could be implemented in real hardware
    - A simple base architecture
    - Optional extensions
    - Support for specialized accelerators
    - Support for different processor designs
    - An architecture that wasn't tied to a particular CPU implementation
 
   The researchers were particularly interested in **specialized and heterogeneous computing**.
 
   In other words:
 
  Instead of saying:
 
  --> "Every processor must use exactly the same instructions."
 
  they wanted something closer to:
 
  --> "Let's have a common foundation, and allow researchers to build specialized processors on top of it."
 
---

 # 4\. Why not just use an existing ISA?

   This was a major reason for creating RISC-V.
  
   Universities could use existing commercial architectures, but those architectures came with restrictions and design assumptions.
  
   For research, this creates a problem.
  
   Imagine you're a university researcher trying to invent a new CPU technique.
  
   You want to change:
 
    ```
    CPU
     ↓
    Instruction Set
     ↓
    Microarchitecture
     ↓
    Accelerator
    ```
 
   But if the ISA is controlled by someone else, experimenting with the instruction set itself becomes much harder.
  
   RISC-V provided a clean, open foundation.
  
   The Berkeley team could:
  
    - Modify it
    - Build processors from it
    - Teach it
    - Create simulators
    - Develop compilers
    - Add extensions
    - Fabricate chips
  
   This was particularly useful for research into accelerators and heterogeneous computing.

---

 # 5\. Why is it called RISC-V?

   The name is pronounced:
  
   **RISC-FIVE**
  
   The "V" means **five**.
  
   It refers to the fifth major RISC ISA project associated with UC Berkeley.
  
   The earlier projects included:
  
    1. RISC-I
    2. RISC-II
    3. SOAR
    4. SPUR
    5. RISC-V
  
   So RISC-V essentially means:
  
   --> Berkeley's fifth major RISC architecture.

---

 # 6\. What was RISC-V originally used for?

   Originally, RISC-V was mainly used for research purposes. 
 
   Researchers could experiment with:
  
    - CPU architecture
    - Parallel computing
    - Accelerators
    - New instruction-set ideas
    - Heterogeneous processors
    - Computer architecture
 
   ### Education
 
    Students could study an actual processor architecture and implement it in hardware.
   
    Berkeley used RISC-V processor RTL designs in university courses.
 
   ### Hardware experimentation
 
    One of the important differences from purely academic processor models was that RISC-V was intended to be implemented in real silicon.
   
    The Berkeley team eventually produced physical RISC-V chips.
   
    The first RISC-V chip tapeout occurred in **2011**, using 28 nm FDSOI technology donated by STMicroelectronics.
  
---

 # 7\. RISC-V's early timeline

  |      Year      |                                            Event                                                   |
  | -------------- | -------------------------------------------------------------------------------------------------- |
  | **2010**       | RISC-V project begins at UC Berkeley                                                               |
  | **2011**       | First RISC-V instruction-set publication                                                           |
  | **2011**       | First RISC-V chip tapeout                                                                          |
  | **2014**       | Major paper describing benefits of open instruction sets                                           |
  | **2015**       | First RISC-V Workshop                                                                              |
  | **2015**       | RISC-V Foundation established                                                                      |
  | **2016**       | Major companies begin joining the ecosystem                                                        |
  | **2017–2018**  | RISC-V ecosystem and open-source implementations expand                                            |
  | **2019**       | Major ISA components become ratified                                                               |
  | **2020**       | RISC-V celebrates 10 years                                                                         |
  | **2021–2023**  | Vector, profiles, embedded and application-class work expands                                      |
  | **2023**       | RISE software ecosystem initiative launched                                                        |
  | **2024**       | RVA23 and other ecosystem specifications mature                                                    |
  | **2025**       | Major growth in AI, automotive, data center, space and HPC                                         |
  | **2026**       | Ratified specification library lists January 2026 versions of the Unprivileged and Privileged ISAs |

---

 # 8\. How did RISC-V evolve?

   One of the most important things to understand is that RISC-V was deliberately designed to be modular.
  
   The basic idea is:

   '''
                 RISC-V
                    │
          ┌─────────┴─────────┐
          │                   │
       Base ISA           Extensions
          │                   │
     RV32 / RV64       M / A / F / D / C
                              │
                         Vector (V)
                              │
                     Other extensions
   '''

   A CPU can implement a relatively small instruction set or combine the base with many extensions.
 
---

 # 9\. RV32 and RV64

   Two important variants are:
  
   ### RV32
  
    A 32-bit architecture.
   
    Commonly useful for:
   
    - Microcontrollers
    - Embedded systems
    - Smaller processors
  
   ### RV64
  
    A 64-bit architecture.
   
    Useful for:
   
    - Linux systems
    - Application processors
    - Servers
    - High-performance computing
  
   The idea is that the basic architecture remains recognizable while implementations can target very different classes of hardware.

---

 # 10\. The RISC-V extension system

   RISC-V's modularity is one of its defining features.
  
   For example:
  
   ### I — Integer
  
    The basic integer instruction set.
  
   ### M — Multiply/Divide
  
    Adds multiplication and division instructions.
  
   ### A — Atomic
  
    Adds atomic memory operations useful for multitasking and synchronization.
  
   ### F — Single-precision floating point
  
    Adds 32-bit floating-point operations.
  
   ### D — Double-precision floating point
  
    Adds 64-bit floating-point operations.
  
   ### C — Compressed instructions
  
    Provides shorter instructions that can reduce program size.
  
   ### V — Vector
  
    Adds vector processing capabilities.
  
   This becomes particularly interesting for:
  
    - AI
    - Machine learning
    - Signal processing
    - Scientific computing
    - High-performance workloads
  
   The official specifications maintain the individual extensions and their ratification status.

---

 # 11\. The big change: from "research CPU" to "open industry ISA"

   This is the major story of RISC-V.
  
   ### Phase 1 — University research
        
        ```
        2010
          ↓
        UC Berkeley
          ↓
        Research + education
        ```
  
   ### Phase 2 — Open architecture
  
       ```
       2014–2015
         ↓
       Open ISA
         ↓
       Industry interest
         ↓
       RISC-V Foundation
       ```
  
   ### Phase 3 — Commercial processors
  
       ```
       2016+
         ↓
       CPU IP companies
         ↓
       Embedded processors
         ↓
       MCUs
         ↓
       SoCs
       ```
  
   ### Phase 4 — Large-scale adoption
        
        ```
        2020s
          ↓
        IoT
        Storage
        Automotive
        AI
        Security
        Space
        HPC
        Data centers
        ```
  
   RISC-V International now describes the ecosystem as having moved from a Berkeley research project into a global industry standard.

---

 # 12\. Why did companies become interested?

   The important word is:
  
   ## Openness
  
     RISC-V provides a standardized instruction set without requiring everyone to use one company's proprietary ISA.
    
     This can give chip designers more freedom to:
    
      - Build custom processors
      - Add specialized instructions
      - Create accelerators
      - Choose different CPU implementations
      - Develop their own silicon roadmap
      - Avoid dependence on a single CPU ISA vendor
  
   This is particularly useful when a company wants a processor designed around a very specific workload.

---

 # 13\. RISC-V today

   As of **2026**, RISC-V is no longer just an academic architecture.
  
   It is being used across multiple categories.
  
   ### Embedded systems
  
     Examples include:
    
      - Microcontrollers
      - Sensors
      - IoT devices
      - Industrial equipment
      - Consumer electronics
  
   ### Storage
  
     RISC-V has become particularly important in storage controllers.
    
     Western Digital, for example, announced a transition toward RISC-V processors and set a goal of shipping more than one billion RISC-V cores annually.
  
   ### Automotive
  
     RISC-V is being developed for:
  
      - Automotive microcontrollers
      - ADAS
      - Vehicle control
      - Safety systems
      - Infotainment
      - Software-defined vehicles
      - AI workloads
     
   Infineon announced a RISC-V automotive microcontroller family as part of its AURIX portfolio.
   
  ### Artificial intelligence
 
    RISC-V is being used as a control processor and as part of heterogeneous AI systems containing:
   
      ```
      RISC-V CPU
           +
      Vector engine
           +
      AI accelerator
           +
      Memory system
      ```
   
    The modular ISA makes it possible to combine a general-purpose processor with workload-specific accelerators.
 
  ### Data centers
 
    The ecosystem is moving beyond tiny embedded CPUs toward:
   
     - Server processors
     - Infrastructure processors
     - Security processors
     - Accelerators
     - High-performance computing
   
    RISC-V's RVA23 application-processor profile is an important step in defining a more standardized baseline for higher-performance systems.
 
  ### Space
 
    RISC-V is also being investigated and developed for space computing.
 
    The European Space Agency and Frontgrade Gaisler have worked on RISC-V processors intended for space applications.
 
  ### Security
 
    One particularly interesting application is using small RISC-V processors as dedicated security components.
 
    For example:
 
      ```
      Main CPU
         │
         ├── Application cores
         │
         └── Security subsystem
                │
             RISC-V
                │
           Root of trust
      ```
 
    Open Compute Project's **Caliptra** is an example of an open RISC-V-based root-of-trust design intended for use in infrastructure such as CPUs, GPUs and SSDs.

---

 # 14\. Some major RISC-V projects and players

   ## Western Digital
  
      Western Digital is one of the most significant early industrial adopters.
     
      The company announced that it was transitioning processor cores used in storage toward RISC-V.
     
      Why storage?
     
      Storage devices contain many embedded processors, making them a huge-volume application for CPUs.

---

 ## Google

    Google has participated heavily in the RISC-V ecosystem.
   
    One recent example is Google's open-sourcing of its **Coral/Kelvin neural processing unit**, a RISC-V-based low-power edge-AI platform.
   
    This illustrates where RISC-V is heading:
      
      ```
      Tiny processor
           ↓
      Sensor
           ↓
      Edge AI
           ↓
      Local inference
      ```
   
    rather than requiring every computation to go to a cloud server.

---

 ## NVIDIA

    NVIDIA is another major participant in the ecosystem.
   
    RISC-V processors can be useful around large GPU/AI systems as control and management processors.
   
    RISC-V International reported in its 2025 annual report that **NVIDIA CUDA was announced for RISC-V**, an important development for the broader software ecosystem.

---

 ## Qualcomm

    Qualcomm has worked on RISC-V for areas including embedded and wearable applications.
   
    RISC-V International has also reported Qualcomm's collaboration with Google around RISC-V-based wearable solutions.

---

 ## SiFive

    SiFive is one of the companies most directly associated with commercializing RISC-V processor IP.
   
    It was co-founded in 2015 by RISC-V co-creator Krste Asanović and others.
   
    The company provides RISC-V processor IP that other companies can integrate into their chips.
   
    Think of it as:
   
      ```
      SiFive CPU IP
            ↓
      Customer SoC
            ↓
      Custom chip
      ```
   
    rather than SiFive necessarily manufacturing every finished chip itself.

---

 ## Open-source CPU projects

    RISC-V has also enabled major open-source processor projects.
    
    One important example is **OpenHW Group's CORE-V** family.
    
    These projects are interesting because the RISC-V ISA is open while the processor implementation can also be openly developed.
    
    That means people can study the actual RTL.

---

 # 15\. Why RISC-V is particularly interesting for AI

   Modern chips increasingly look like this:
  
    ```
                  SoC
                   │
           ┌───────┼────────┐
           │       │        │
          CPU     GPU      NPU
           │       │        │
           └───────┼────────┘
                   │
                 Memory
    ```
  
   The CPU doesn't necessarily do all the computation.
  
   Instead:
  
    - CPU → general-purpose work
    - GPU → massively parallel computation
    - NPU → neural-network operations
    - DSP → signal processing
    - Custom accelerator → specialized workload
  
   RISC-V's extensibility makes it attractive as the CPU/control architecture around this heterogeneous hardware.

---

 # 16\. The Vector Extension

   One of the most important developments in RISC-V is the **V extension**.
  
   Traditional CPU processing might look like:
  
     ```
     A1 + B1
     A2 + B2
     A3 + B3
     A4 + B4
     ```
  
   A vector processor can operate on multiple elements as a group:
  
     ```
     [A1 A2 A3 A4]
             +
     [B1 B2 B3 B4]
             =
     [C1 C2 C3 C4]
     ```
  
   This is useful for workloads such as:
  
     - AI
     - Image processing
     - Scientific computing
     - Signal processing
     - Encryption
     - Multimedia
  
   Vector processing is therefore one of the bridges between RISC-V's original simple CPU philosophy and modern high-performance computing.

---

 # 17\. RISC-V Profiles

   As the ecosystem became larger, another problem appeared.
  
   If everyone implements different combinations of extensions, software compatibility becomes difficult.
  
   For example:
     
     ```
     CPU A:
     RV64 + M + A + F + D + C
     
     CPU B:
     RV64 + M + A + F + D + C + V
     
     CPU C:
     RV64 + custom extension X
     ```
  
   What can software safely assume?
  
   Profiles help establish standardized combinations of features for particular classes of processors.
  
   One important modern profile is:
  
     ## RVA23
    
        The RVA23 profile defines a baseline for application processors.
       
        The ratified specification library currently lists **RVA23 v1.0**, dated October 2024.

---

 # 18\. RISC-V in 2026

   The architecture has evolved substantially from the 2010 Berkeley research project.
  
   The current ratified specification library lists:
  
    - Unprivileged ISA — v20260120
    - Privileged ISA — v20260120
    - RISC-V Profiles
    - RVA23
    - RVB23
    - Numerous ratified extensions

 The industry is also working on:
 
   - AI
   - Automotive
   - Data centers
   - HPC
   - Embedded computing
   - Security
   - Aerospace
   - Software ecosystems
   - Virtualization
   - High-performance application processors
 
  RISC-V International's 2025 annual report describes 2025 as a major year for industry adoption, with progress in automotive, data centers, HPC, embedded systems, space and AI.

---

 # 19\. One important thing to understand

   RISC-V is **not automatically a faster CPU**.
  
   This is a common misconception.
  
   RISC-V describes the **instruction set**.
  
   Performance depends on the processor implementation.
  
   For example:
  
     ```
     RISC-V ISA
          │
          ├── Tiny MCU
          │
          ├── Simple embedded CPU
          │
          ├── Linux application CPU
          │
          ├── Vector processor
          │
          └── High-performance CPU
     ```
  
   All of them can use RISC-V.
  
   So when comparing processors, you need to distinguish:
  
      **ISA**
     
      from
     
      **microarchitecture**
     
      from
     
      **actual chip implementation.**

---

 # 20\. The big idea behind RISC-V

   The simplest way to remember the entire project is:
  
     --> **RISC-V separates the instruction-set standard from the company building the processor.**
    
     Historically, processor architectures were often tightly associated with particular companies.
    
     RISC-V tries to make the ISA an open common foundation.
    
     That enables:
    
       ```
                    RISC-V ISA
                         │
              ┌──────────┼──────────┐
              │          │          │
           Company A  Company B  University
              │          │          │
             CPU        CPU       Research
              │          │          │
              └──────────┼──────────┘
                         │
                     Software
       ```
  
   This is why RISC-V has become much bigger than the original Berkeley project.

---

 # 21\. What I should learn next

   A good learning path is:
    
     ### Level 1 — Understand the concept
    
     Learn:
    
      - What is an ISA?
      - RISC vs CISC
      - CPU vs ISA
      - Registers
      - Memory
      - Instructions
      - Machine code
    
     ### Level 2 — Learn RISC-V assembly
    
     Learn:
    
       ```
       add
       sub
       addi
       lw
       sw
       beq
       jal
       ```
    
     Understand registers such as:
    
       ```
       x0
       x1
       x2
       ...
       x31
       ```
    
     ### Level 3 — Understand RV32I
    
        Study the base integer ISA.
       
        Try writing tiny programs.
       
        For example:
       
          ```
          C code
             ↓
          Compiler
             ↓
          RISC-V assembly
             ↓
          Machine code
             ↓
          RISC-V CPU
          ```
    
     ### Level 4 — Understand extensions
    
         Study:
       
           ```
           I → Integer
           M → Multiply/Divide
           A → Atomic
           F → Float
           D → Double
           C → Compressed
           V → Vector
           ```
    
     ### Level 5 — Build something
    
         Use an FPGA or simulator.
         
         Build:
         
            ```
            Simple RISC-V CPU
                   ↓
            Run instructions
                   ↓
            Add memory
                   ↓
            Add peripherals
                   ↓
            Run C code
            ```
    
     ### Level 6 — Study real processors
    
         Then investigate projects such as:
         
           - Rocket
           - BOOM
           - CVA6
           - CORE-V
           - SiFive cores
           - T-Head cores
           - StarFive processors
     
   At this stage you start seeing the difference between the **ISA** and the **microarchitecture**.

---

 # 22\. The story in one timeline

   ```
   1980s
    │
    ├── Berkeley develops earlier RISC architectures
    │
    ↓
   2010
    │
    ├── RISC-V begins at UC Berkeley
    │
    ↓
   2011
    │
    ├── First RISC-V specification
    ├── First chip tapeout
    │
    ↓
   2014
    │
    ├── Research on benefits of open ISAs
    │
    ↓
   2015
    │
    ├── RISC-V Foundation
    ├── Industry begins getting involved
    │
    ↓
   2016–2019
    │
    ├── Commercial processors
    ├── Open-source CPUs
    ├── Embedded adoption
    └── ISA extensions mature
    │
    ↓
   2020–2023
    │
    ├── IoT
    ├── Storage
    ├── Automotive
    ├── AI
    ├── Security
    └── Linux/application processors
    │
    ↓
   2024–2025
    │
    ├── RVA23
    ├── Vector ecosystem
    ├── AI acceleration
    ├── Automotive expansion
    ├── Space projects
    ├── HPC
    └── Data-center development
    │
    ↓
   2026
    │
    ├── Mature ratified specification library
    ├── Application-class profiles
    ├── AI/ML
    ├── Automotive
    ├── Embedded
    ├── Security
    ├── HPC
    ├── Data centers
    └── Space
   ```

---

 # 23\. The question we should be able to answer after studying this repository

   By the end, we should be able to explain:
  
      --> **"RISC-V started at UC Berkeley in 2010 as an open, flexible ISA for computer-architecture research and education. Its designers wanted a clean foundation that could be implemented in real hardware and extended for specialized processors. It subsequently became an open industry standard, allowing companies and researchers to build processors ranging from tiny embedded cores to application processors and specialized AI/HPC systems. Its modular extensions, open governance and ability to support workload-specific silicon are major reasons for its expansion into embedded systems, storage, automotive, AI, security, aerospace and high-performance computing."**
  
   That is the **core story of RISC-V**.

---
