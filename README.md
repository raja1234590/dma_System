CPU-Based Memory Transfer Analysis (Without DMA)
📌 Overview

This project demonstrates how CPU-based memory transfer works and analyzes why it is slower compared to hardware-based approaches like DMA.

The implementation uses Python to simulate how a CPU copies data element by element, similar to how memcpy() works in embedded systems.

🎯 Objective
Understand CPU-based memory transfer
Measure execution time
Analyze why CPU transfer is slower
Build foundation for comparing with DMA
🧠 Concept
🔹 CPU Memory Transfer
CPU copies data one element at a time

Data flow:

Memory → CPU → Memory
CPU is fully occupied during transfer
💻 Code Explanation
def cpu_transfer(src, dst):
    for i in range(len(src)):
        dst[i] = src[i]
What happens here?
Loop runs for all elements
For each element:
Read from source array
Write to destination array

👉 This is sequential processing

🧪 Example Data
src = [1,2,3,4,5,6,7,8]
dst = [0,0,0,0,0,0,0,0]
⏱ Execution Time
t0 = time.time()
cpu_transfer(src, dst)
t1 = time.time()
Result:
CPU Transfer Time ≈ 111 µs (can vary slightly)
❗ Why CPU Transfer is Slow
🔴 1. Sequential Processing
Copies data one by one
No parallelism
🔴 2. Multiple Memory Accesses
Each element requires:
1 read + 1 write
High memory latency
🔴 3. CPU Fully Busy
Cannot perform other tasks
🔴 4. Loop Overhead
Iteration adds extra delay
📊 Key Takeaways
CPU-based transfer is simple but inefficient
Performance decreases with larger data sizes
Not suitable for high-speed data movement
🛠 Technologies Used
Python
NumPy
Jupyter Notebook
📂 Project Structure
├── Without_Dma.ipynb
└── README.md
