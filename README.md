# TSNForge Pro (v1.0.0)

**IEEE 802.1Qbv / 802.1Qbu Time-Aware Shaper, Frame Preemption & Gate Control List (GCL) Synthesis Studio**

---

## Executive Summary

**TSNForge Pro** is an industrial-grade, client-side engineering workbench and command-line utility for designing, synthesizing, auditing, and provisioning deterministic **Time-Sensitive Networking (TSN)** schedules.

Targeting automotive zonal Ethernet architectures (ECUs, ADAS, radar/camera backbones) and converged industrial automation networks (robotics, CNC, motion control, OPC UA FX, CC-Link IE TSN), TSNForge Pro automates the complex mathematical modeling required by:

- **IEEE 802.1Qbv**: Time-Aware Shaper (TAS) with cyclical Gate Control Lists (GCL).  
- **IEEE 802.1Qbu & IEEE 802.3br**: Interspersed express traffic & frame preemption.  
- **IEEE 802.1AS-2020**: Generalized Precision Time Protocol (gPTP) clock bounds.  
- **IEEE 802.1Qcp**: NETCONF YANG data model export for Centralized Network Controllers (CNC).  
- **Linux TSN**: `tc-taprio` and flower command script generation for embedded Linux targets (Intel i210/i225/i226, NXP S32G, TI AM64x).

---

## Key Features & Capabilities

1. **Deterministic GCL Schedule Synthesis**:  
     
   - Synthesizes exact 8-bit gate state vectors across IEEE 802.1Q Priority Code Points (PCP 0 to 7).  
   - Generates microsecond-accurate time intervals and verifies full cycle time conservation.  
   - Calculates real-time bandwidth allocations and guarantees non-zero best-effort throughput to prevent network management starvation.

   

2. **IEEE 802.1Qbu Preemptive Guard Band Optimization**:  
     
   - Calculates traditional full-MTU guard bands (12.336 µs at 1 Gbps).  
   - Computes preemptive fragment guard bands (0.640 µs at 1 Gbps).  
   - Recovers up to **94.8%** of wasted bandwidth, eliminating jitter for high-frequency motion loops.

   

3. **Multi-Hop Bridge Latency & WCRT Sizer**:  
     
   - Models store-and-forward and cut-through switching across multi-switch bridged topologies.  
   - Computes physical fiber/copper propagation delays and bridge processing latency.  
   - Proves zero-queuing delay for Scheduled Traffic (ST) streams.

   

4. **10-Point Determinism Compliance Auditor**:  
     
   - Automated rules engine checking gPTP clock accuracy, guard band margins, zero-queuing isolation, fragment sizes, and hardware GCL memory limits (max 1024 entries).

   

5. **Multi-Format Export Engine**:  
     
   - Produces standard IEEE 802.1Qcp YANG XML configuration files.  
   - Generates drop-in Linux `tc-taprio` bash provisioning scripts.

---

## File Structure

product\_218/

├── README.md

├── test\_tsnforge.py

├── source-code/

│   ├── index.html

│   ├── tsnforge.css

│   ├── app.js

│   ├── tsn-engine.js

│   ├── tsn-sizer.js

│   └── tsn-auditor.js

├── build/

│   ├── tsnforge-cli.py

│   └── tsnforge-pro-v1.0.0.zip

├── documentation/

│   ├── ARCHITECTURE.md

│   ├── USER\_GUIDE.md

│   ├── MONETIZATION\_AND\_MARKETING\_PLAYBOOK.md

│   └── PROGRESS\_REPORT.md

└── screenshots/

    └── tsnforge-studio-preview.svg

---

## Getting Started

### Web Interface

Simply open `source-code/index.html` in any web browser. No server or backend dependencies required.

### Command-Line Interface

cd build

./tsnforge-cli.py \--cycle 1000 \--speed 1000 \--preemption

./tsnforge-cli.py \--cycle 1000 \--speed 1000 \--export-yang

---

## License & Commercial Rights

Distributed under the Commercial Engineering License. See `documentation/MONETIZATION_AND_MARKETING_PLAYBOOK.md` for commercial distribution terms and enterprise support tiers.