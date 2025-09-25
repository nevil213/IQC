**7.2 Memory Partitioning – Overview**

- The main job of memory management is to load processes into main memory so the CPU can run them.  
- Modern multiprogramming systems usually use **virtual memory**, which relies on **segmentation**, **paging**, or both.  
- Before virtual memory, simpler schemes were used: **fixed partitioning**, **dynamic partitioning**, **simple paging**, and **simple segmentation** (see Table 7.2).

---
<img width="576" height="746" alt="image" src="https://github.com/user-attachments/assets/0563645b-d1a9-41dc-8af1-3db6c95c9d76" />

<img width="721" height="509" alt="image" src="https://github.com/user-attachments/assets/6839803d-98ab-46ca-b467-4cf71ed9d706" />

### Fixed Partitioning
1. **Concept**
   - The OS reserves a fixed portion of RAM; the rest is divided into static partitions with predetermined sizes.
   - A process can only run if its size ≤ size of a partition.

2. **Equal‑size partitions (Fig 7.2a)**
   - All partitions have the same size.
   - Any process that fits can be placed in any free partition.
   - If all partitions are full, the OS must swap out a process to load another.

   **Problems**
   - **Too large a program**: cannot fit; programmer must use *overlays* (load only needed parts).
   - **Internal fragmentation**: a small program still occupies a whole partition, wasting space (e.g., a 2 MB program in an 8 MB partition).

3. **Unequal‑size partitions (Fig 7.2b)**
   - Partitions of different sizes (e.g., 8 MB, 12 MB, 16 MB) reduce internal fragmentation.
   - Larger programs can be placed without overlays; smaller programs use smaller partitions.

4. **Placement Algorithms**
   - **Smallest‑fit per partition**: each partition has its own queue of swapped‑out processes (Fig 7.3a). Minimizes internal fragmentation per partition but may leave large partitions empty when no suitably sized process exists.
   - **Single global queue**: when loading, choose the smallest available partition that fits the process (Fig 7.3b). Allows better overall utilization; swapping decisions may consider partition size, priority, or process state (ready vs. blocked).

5. **Strengths & Weaknesses (Table 7.2)**
   - *Strengths*: Simple to implement, low OS overhead.  
   - *Weaknesses*: Fixed number of active processes; internal fragmentation; inefficient for small jobs; largely obsolete today (except early OS/MFT on IBM mainframes).

---

### Dynamic Partitioning

<img width="842" height="897" alt="image" src="https://github.com/user-attachments/assets/593ac17f-ad0a-4b0b-b0eb-41c5560bb49b" />

<img width="681" height="775" alt="image" src="https://github.com/user-attachments/assets/e9926e7b-4ffa-4e6e-acce-10af7b93217b" />


1. **Concept**
   - Partitions are created **dynamically**; each process receives exactly the amount of memory it needs (no internal fragmentation).

2. **Operation (Fig 7.4)**
   - Memory starts with only the OS loaded.
   - Processes are loaded sequentially, each taking just enough space.
   - When a process finishes or is swapped out, a “hole” (free space) appears.
   - Over time many small holes accumulate → **external fragmentation** (free memory is split into many non‑contiguous pieces).

3. **Compaction**
   - To reclaim a large contiguous block, the OS can move processes together, merging holes into one big free area.
   - Requires **dynamic relocation**: program addresses must be adjustable without breaking references.
   - Compaction is CPU‑intensive and thus costly.

4. **Strengths & Weaknesses (Table 7.2)**
   - *Strengths*: No internal fragmentation; better memory utilization.  
   - *Weaknesses*: External fragmentation; needs compaction (processor overhead); limited number of active processes is still fixed by total memory.

5. **Historical Use**
   - Used by IBM’s OS/MVT (Multiprogramming with a Variable Number of Tasks).

---

### Simple Paging (non‑virtual)
- Memory split into equal‑size **frames**; each process split into equal‑size **pages** (same size as frames).  
- Pages can be placed in any free frame, not necessarily contiguous.  
- **Result:** No external fragmentation; only a small amount of internal fragmentation (last page may be partially unused).

### Simple Segmentation (non‑virtual)
- Each process divided into logical **segments** (code, data, stack, etc.).  
- Segments are loaded into dynamic partitions that need not be contiguous.  
- **Result:** No internal fragmentation; better memory utilization than fixed partitioning but still suffers from external fragmentation.

---

### Virtual Memory Extensions
| Technique | How it extends the simple version | Advantages | Disadvantages |
|-----------|-----------------------------------|------------|---------------|
| **Paging** | Only pages actually needed are resident; others are brought in on demand. | No external fragmentation, higher multiprogramming, large virtual address space. | Complex management overhead. |
| **Segmentation** | Only required segments are resident; others loaded later. | No internal fragmentation, large address space, supports protection & sharing. | Complex management overhead. |

---

### Summary of Memory Management Techniques (Table 7.2)

| Technique | Description | Strengths | Weaknesses |
|-----------|-------------|-----------|------------|
| Fixed Partitioning | Static partitions set at system generation. | Simple; low OS overhead. | Internal fragmentation; fixed number of active processes. |
| Dynamic Partitioning | Partitions created on‑the‑fly, exactly sized to process. | No internal fragmentation; efficient use of RAM. | External fragmentation; compaction needed → CPU waste. |
| Simple Paging | Equal‑size frames & pages; load any pages into any frames. | No external fragmentation; little internal fragmentation. | – |
| Simple Segmentation | Processes split into logical segments; loaded into dynamic partitions. | No internal fragmentation; better utilization vs. dynamic partitioning. | External fragmentation. |
| Virtual Memory – Paging | Load pages on demand, not all at once. | No external fragmentation; high multiprogramming; large virtual space. | Management overhead. |
| Virtual Memory – Segmentation | Load segments on demand. | No internal fragmentation; large virtual space; protection/sharing. | Management overhead. |

---

**Key Take‑aways**

- Fixed partitioning is simple but wastes memory (internal fragmentation) and limits the number of concurrent processes.  
- Unequal partitions improve waste but still suffer from rigid limits.  
- Dynamic partitioning eliminates internal waste but creates external fragmentation, requiring costly compaction.  
- Paging and segmentation introduce the ability to place non‑contiguous pieces, paving the way for virtual memory, which further reduces fragmentation and allows much larger address spaces at the cost of increased OS complexity.  
