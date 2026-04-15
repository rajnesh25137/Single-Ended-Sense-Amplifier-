# 🔷 Single-Ended Sense Amplifier (SESA) for Multi-Voltage Memory Operation

## 📌 Overview
This project presents the **design, simulation, and layout implementation** of a **Single-Ended Sense Amplifier (SESA)** for memory applications.  

The design is validated across **multiple supply voltages (1.2V, 1.08V, 0.9V)** to ensure robust operation under varying conditions.  

The work includes:
- Circuit design and transistor sizing  
- Pre-layout and post-layout simulations  
- Offset analysis (Monte Carlo)  
- Layout design (Normal vs Common Centroid)  
- PVT variation analysis  

---

## 🎯 Objectives
- Design a **high-speed, low-offset sense amplifier**
- Ensure operation across:
  - 1.2V (nominal)
  - 1.08V (scaled)
  - 0.9V (low voltage)
- Maintain **offset within acceptable limits (3σ)**  
- Achieve **fast response time (~200 ps target)**  
- Compare **layout techniques for mismatch reduction**

---

## ⚙️ Circuit Architecture

The design consists of:
- Cross-coupled latch (core sensing)
- Precharge circuit
- Equalization circuit
- Pass transistors for bitline access
- Tail current transistor

### Key Blocks
- Sense Amplifier Latch  
- Precharge & Equalization  
- Bitline Access Network  
- Output Latch  

📌 The schematic and sizing details are shown in the project report :contentReference[oaicite:0]{index=0}  

---

## 🔄 Working Principle

1. **Precharge Phase**
   - Bitlines are precharged to VDD  
   - Equalization ensures balanced initial condition  

2. **Evaluation Phase**
   - Small voltage difference develops on bitlines  
   - Sense amplifier enabled (SAEN)

3. **Amplification**
   - Cross-coupled latch amplifies differential signal  
   - Output resolves to full logic level  

---

## 🧪 Simulation & Verification

### Control Signals
- Precharge  
- SAEN (Sense Enable)  
- PassON  
- SAEN_DELAY  

Waveforms confirm correct sequencing and operation across all voltages :contentReference[oaicite:1]{index=1}  

---

## 📊 Functional Verification

### ✔ Read Operation (All Voltages Tested)
- Verified for:
  - Read ‘0’
  - Read ‘1’

### Supply Voltages Tested:
- 1.2 V  
- 1.08 V  
- 0.9 V  

✔ Correct sensing observed in all cases :contentReference[oaicite:2]{index=2}  

---

## ⚡ Performance Results

### 📌 Offset Voltage (mV)

| VDD | Read 0 | Read 1 |
|-----|--------|--------|
| 0.9V | 145.05 | 139.16 |
| 1.08V | 52.69 | 44.34 |
| 1.2V | 24.55 | 35.24 |

👉 Offset reduces with increasing supply voltage :contentReference[oaicite:3]{index=3}  

---

### ⏱️ Response Time (SAEN → Output)

| VDD | Delay |
|-----|-------|
| 1.2V | 141.8 ps |
| 1.08V | 148.8 ps |
| 0.9V | 185.2 ps |

👉 Lower voltage increases delay (expected trade-off) :contentReference[oaicite:4]{index=4}  

---

## 📉 Monte Carlo Analysis (3σ Offset)

- Performed across:
  - 1.2V  
  - 1.08V  
  - 0.9V  

✔ Verified robustness under **process variations**  
✔ Offset remains within acceptable limits  

---

## 🧱 Layout Design

### 1️⃣ Normal Layout
- Area: ~35.9 µm²  
- Pros:
  - Simple design  
  - Compact  
- Cons:
  - Higher mismatch  
  - Poor symmetry → higher offset  

---

### 2️⃣ Common Centroid Layout
- Area: ~28.45 µm² (1.08V case)  
- Pros:
  - Excellent matching  
  - Reduced offset  
  - Balanced parasitics  
- Cons:
  - Higher design complexity  

👉 Clearly superior for analog precision design :contentReference[oaicite:5]{index=5}  

---

## ✅ Physical Verification
- ✔ DRC Clean  
- ✔ LVS Matched  

---

## 🔬 PVT Analysis

### Pre vs Post Layout (1.08V Example)

| Condition | Pre (mV) | Post (mV) |
|----------|----------|-----------|
| SS, -40°C | 49.95 | 55.80 |
| FF, 125°C | 2.90 | 4.10 |

👉 Post-layout includes parasitic effects  
👉 Slight degradation but within acceptable limits :contentReference[oaicite:6]{index=6}  

---

## 📊 Layout Comparison (Post-Layout Offset)

| Condition | Common Centroid | Normal |
|----------|----------------|--------|
| SS, -40°C | 55.80 | 83.28 |
| FF, 125°C | 4.10 | 6.12 |

👉 Common centroid significantly reduces offset  

---

## ⚖️ Design Trade-offs

| Parameter | Effect |
|----------|-------|
| Lower VDD | ↑ Delay, ↑ Offset |
| Better Layout | ↓ Offset, ↑ Complexity |
| Parasitics | Affect timing & accuracy |

---

## 🛠️ Tools Used
- Cadence Virtuoso  
- Spectre Simulator  
- Monte Carlo Analysis  
- Calibre (DRC/LVS)  

---

## 📂 Project Contents


---

## 📌 Key Learnings
- Sense amplifier design fundamentals  
- Impact of **voltage scaling on performance**  
- Importance of **layout symmetry (common centroid)**  
- Trade-offs between:
  - Speed  
  - Offset  
  - Area  
- Practical exposure to **analog VLSI flow**

---

## 🚀 Conclusion
- Successfully designed a **Single-Ended Sense Amplifier** operating across multiple voltages  
- Achieved:
  - Reliable sensing  
  - Acceptable offset  
  - Fast response  
- Demonstrated that **common centroid layout significantly improves performance**

---

## 👨‍💻 Author
**Rajnesh Kumar**  
M.Tech VLSI  

---

