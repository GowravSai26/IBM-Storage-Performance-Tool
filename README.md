# IBM-Storage-Performance-Tool
Storage performance benchmarking tool measuring read/write speed, IOPS, and latency — built to analyze disk behavior and support systems-level PM insights.
---

# 📘 **Storage Performance & Reliability Logger**

A lightweight, systems-focused storage benchmarking utility that measures **disk read/write throughput, IOPS, and latency**, and logs results into **CSV** and **JSON** for analysis.

This tool is designed to help developers, infra engineers, and product managers quickly diagnose storage performance bottlenecks and understand disk behavior across repeated runs.

> ⚡ **Why this project exists**
> To demonstrate structured, systems-level product thinking and technical curiosity aligned with **IBM’s Storage Solutions division** (FlashSystem, Storage Scale, Fusion).
> It showcases understanding of **performance metrics, reliability, diagnostics, and enterprise storage fundamentals** — core expectations for an APM Intern in IBM Infrastructure.

---

## 🚀 **Features**

* 📈 Read throughput measurement (MB/s)
* 📉 Write throughput measurement (MB/s)
* ⚡ Latency calculation (ms)
* 🔁 IOPS measurement
* 🔍 Multiple-run benchmarking for reliability
* 🗂️ CSV logging for all runs
* 📦 JSON summary output
* 💡 Command-line arguments (file size, run count, output directory)
* 🧩 Proper error handling

---

## 🧠 **What This Tool Demonstrates (PM Perspective)**

This project highlights:

* Understanding of **storage performance metrics** (IOPS, latency, throughput)
* Ability to reason about **diagnostics & reliability**
* Skill in communicating technical insights clearly
* System-design thinking applicable to **enterprise infrastructure**
* Ownership of a complete micro-product with real utility
* Alignment with IBM’s deep-tech, storage-focused environment

---

## 📂 **Project Structure**

```
storage-performance-logger/
│
├── storage_logger.py         # Main benchmarking script
├── utils/
│   ├── benchmarks.py         # Read/write tests & metrics
│   ├── logger.py             # CSV/JSON logging utilities
│   └── helpers.py            # Error handling & validation
│
├── outputs/                  # Benchmark results
│   ├── results.csv
│   └── summary.json
│
└── README.md                 # Documentation
```

---

## 🛠️ **Tech Stack**

* **Python 3.x**
* Built-in modules only:

  * `time`
  * `os`
  * `tempfile`
  * `argparse`
  * `json`
  * `csv`

Lightweight. Cross-platform. Zero external dependencies.

---

## 🧪 **How It Works**

1. Generates a temporary file of configurable size
2. Runs **write tests** and records throughput
3. Runs **read tests** and records throughput
4. Calculates:

   * average latency
   * IOPS
5. Repeats the tests for N runs (default: 3)
6. Logs each run in **CSV**
7. Produces a final **summary.json**

---

## 🧱 **Architecture Diagram**

```
              +------------------------------+
              |       Command Line Input     |
              +---------------+--------------+
                              |
                              v
                  +-----------+-----------+
                  |     Benchmark Runner   |
                  |  (read, write, latency)|
                  +-----------+-----------+
                              |
                              v
             +----------------+----------------+
             |     Metrics Collector            |
             | (iops, throughput, reliability)  |
             +----------------+----------------+
                              |
                +-------------+--------------+
                |                            |
                v                            v
        +-------+-------+           +--------+--------+
        |   CSV Logger   |           |   JSON Summary  |
        +---------------+           +------------------+
```

---

## ▶️ **Usage**

### **Run with defaults (3 runs, 100MB file):**

```
python storage_logger.py
```

### **Custom file size (MB):**

```
python storage_logger.py --file-size 500
```

### **Custom number of runs:**

```
python storage_logger.py --runs 5
```

### **Specify output directory:**

```
python storage_logger.py --output ./results/
```

---

## 📊 **Sample Output (CLI)**

```
[Run 1]
Write Speed: 482.31 MB/s
Read Speed : 521.09 MB/s
Latency    : 3.12 ms
IOPS       : 312

[Run 2]
Write Speed: 475.90 MB/s
Read Speed : 518.77 MB/s
Latency    : 3.27 ms
IOPS       : 305

Summary saved to outputs/summary.json
Detailed logs saved to outputs/results.csv
```

---

## 🎯 **Why This Project Matters**

This tool is intentionally small but highly aligned with:

* **Enterprise storage diagnostics**
* **Performance engineering**
* **Reliability testing**
* **Data-driven product decisions**

It reflects the mindset of a **deep-tech, systems-oriented Product Manager**, which is essential in roles like:

* IBM Storage APM Intern
* Infrastructure PM
* AI Infrastructure PM
* System-level PM

---

## 🧩 **Future Improvements**

* Visualization dashboard (Plotly/Matplotlib)
* Random/sequential I/O tests
* Network storage benchmarking (NFS/SMB)
* Prometheus exporter
* S3-compatible storage tests

---

## 👤 **Author**

**Gowrav Sai Veeramallu**
Product-minded engineer exploring storage systems, performance metrics, and enterprise infrastructure.

---


