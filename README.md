# CacheSight // Microarchitectural Side-Channel Attack Explorer

> An interactive, web-based educational visualizer designed to help students and security enthusiasts understand microarchitectural side-channel timing attacks (Flush + Reload) and constant-time algorithmic defenses.

---

## Overview

Modern CPUs use memory caches to speed up data access. While caches significantly improve performance, they introduce a subtle hardware vulnerability: **data accessed recently can be retrieved much faster than uncached data**. 

**CacheSight** is a clean, single-page web app built to demonstrate how an attacker can measure memory read latencies to infer secret keys or sensitive user data—without ever accessing the secret data directly.

Designed for high schoolers and introductory computer science/cybersecurity students, CacheSight translates complex hardware mechanisms into an intuitive, visual, and step-by-step interactive lab.

---

## Educational Objectives

By exploring CacheSight, students will learn:
1. **The Memory Hierarchy Gap**: The dramatic latency difference between CPU L1/L2 Cache (~2–10ns) and Main RAM (~100–200ns).
2. **Flush + Reload Side-Channel Attack**:
   * **Flush**: Evicting target memory lines from the cache into RAM.
   * **Victim Execution**: Observing how a target application inadvertently loads secret-dependent memory lines into the cache.
   * **Probe / Measure**: Measuring access times ($RDTSC$) to identify cached memory lines and reconstruct the secret.
3. **Algorithmic Complexity & Vulnerabilities**: Why $O(\text{Secret})$ array indexing leaks information through memory access patterns, whereas $O(1)$ constant-time lookups mask secret accesses.
4. **Hardware-Level Countermeasures**: How constant-time algorithms and bitwise operations prevent timing side-channels.

---

## 🛠️ Key Features

* **Interactive Flush + Reload Attack Sandbox**:
  * Step-by-step attack execution or single-click full attack simulation.
  * Customizable victim secrets (A–H) to test different attack paths.
* **Live Microarchitectural Visualization**:
  * **Memory Line Grid**: Live visual status badges showing cached vs. uncached memory lines.
  * **Timing Oscilloscope**: Real-time line chart plotting probe latencies with a visual threshold dividing Cache Hits vs. Cache Misses.
* **Vulnerable vs. Defended Mode Toggle**:
  * **Insecure Lookup**: Secret-dependent memory access that leaks execution patterns.
  * **Constant-Time Defense**: Uniform memory scanning that eliminates timing side-channels.
* **Built-in Learning Tools**:
  * **Interactive Walkthrough**: Detailed breakdown of the 3 main attack phases.
  * **Complexity Analysis**: Visual breakdown of time/space complexity and security tradeoffs.
  * **Knowledge Check Quiz**: Embedded questions with instant feedback to reinforce key concepts.

---

## 🚀 Getting Started

CacheSight is a static web application built with zero external dependencies, making it light, fast, and easy to run in any browser.

1. Clone or download this repository:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/cache-sight-app.git](https://github.com/YOUR_USERNAME/cache-sight-app.git)
