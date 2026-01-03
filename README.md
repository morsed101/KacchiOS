
# kacchiOS 🍛

**A Minimalistic Baremetal Operating System**

kacchiOS is a lightweight, baremetal operating system designed to demonstrate core kernel concepts including memory management, process lifecycle handling, and preemptive scheduling. Starting from a basic Null Process and a serial `io.c` driver, this project implements a functional multitasking environment.

## 🚀 Features

### 1. Memory Manager

Efficiently handles system resources to ensure processes have isolated workspace.

* **Stack & Heap Allocation:** Dynamic allocation for process execution and data storage.
* **Deallocation:** Robust cleanup of memory upon process termination to prevent leaks.
* **Optimization:** Implemented using a **First-Fit** allocation strategy to minimize fragmentation.

### 2. Process Manager

Tracks and maintains the lifecycle of all system tasks.

* **Process Table:** Centralized tracking of all active Process Control Blocks (PCBs).
* **States:** Full support for `CURRENT`, `READY`, and `TERMINATED` states.
* **Utilities:** Includes helper functions for PID retrieval and process status reporting.
* **Bonus - IPC:** Basic Inter-Process Communication (IPC) support for message passing between tasks.

### 3. Scheduler

The heart of kacchiOS multitasking capabilities.

* **Policy:** A **Round-Robin** scheduling algorithm ensuring fair CPU time.
* **Context Switching:** Low-level assembly routine to save and restore CPU registers during task swaps.
* **Configurable Time Quantum:** Adjustable execution slices for fine-tuned performance.
* **Aging:** Logic to prevent process starvation by gradually increasing the priority of long-waiting tasks.

---

## 🛠 Project Structure

* `/src/kernel`: Core kernel logic.
* `/src/drivers`: Hardware drivers (including `io.c` for serial communication).
* `/src/mem`: Memory management implementation.
* `/src/proc`: Process management and scheduling logic.
* `/include`: Header files defining the PCB and system constants.

## 💻 Getting Started

### Prerequisites

* `i686-elf-gcc` (Cross-compiler)
* `nasm` (Assembler)
* `qemu-system-x86` (Emulator)

### Building and Running

1. **Clone the repo:**
```bash
git clone https://github.com/yourusername/kacchiOS.git
cd kacchiOS

```


2. **Compile the kernel:**
```bash
make

```


3. **Run in QEMU:**
```bash
make run

```


*Note: Output is directed to the serial console.*

---

## 📊 Technical Requirements Checklist

| Requirement | Status |
| --- | --- |
| Stack/Heap Allocation & Deallocation | ✅ |
| Process Table & State Transitions | ✅ |
| Round-Robin Scheduling & Context Switch | ✅ |
| Configurable Time Quantum | ✅ |
| IPC & Process Aging | ✅ |

---

## 🤝 Acknowledgments

* Developed as part of a baremetal OS study.
* Special thanks to the `kacchiOS` base image and the `io.c` driver contributors.

---
