 📌Featured Projects

PicoRISCV-SoC — RISC-V SoC with ML Accelerator

PicoRV32 (RV32IM) CPU integrated with an 8x8 weight-stationary systolic array over AXI-Lite MMIO and a 4-wire SPI slave interface (390 to 4 pins). Full RTL-to-GDS on ASAP7 via OpenROAD: 47,051 cells, 5,431 µm², 500 MHz, 0 DRC violations. IRQ feedback from accelerator to CPU on computation complete.

<img width="257" height="248" alt="Screenshot 2026-05-23 144441" src="https://github.com/user-attachments/assets/f787e911-8dc6-43e5-bd1f-5e368f8543ba" />

Systolic Array Accelerator — RTL to GDS

8x8 weight-stationary systolic array, INT8 weights, INT32 accumulators. Full OpenROAD flow on two nodes:

<img width="596" height="164" alt="image" src="https://github.com/user-attachments/assets/2cce8406-5f85-47f7-b9cf-c5dcedb1dd29" />

<img width="257" height="248" alt="Screenshot 2026-05-22 233913" src="https://github.com/user-attachments/assets/fce2cc2d-ad93-492e-a621-37ab6e476d4d" />

<img width="251" height="238" alt="Screenshot 2026-05-22 234125" src="https://github.com/user-attachments/assets/04200e73-aed1-4242-83f2-627bd1ca3574" />

10x frequency, 67.1x area reduction across nodes.
Submitted to ChipFoundry CI2609 shuttle via Caravel wrapper.


UVM-Style Systolic Array Testbench

Structured SystemVerilog testbench for the 8x8 systolic array, built without a UVM library to run cleanly under Verilator 5.x. Per-PE scheduled checks using a timing model, constrained random stimulus, and 5 SVA properties checking protocol correctness every clock cycle.

1,337 functional checks, zero failures across 5 random seeds
15/15 functional coverage bins closed
Resolved a Verilator --timing coroutine limitation where post-NBA signal values are invisible inside tasks by moving psum checks into a dedicated always block

<img width="464" height="734" alt="Screenshot 2026-05-29 215116" src="https://github.com/user-attachments/assets/9e9c7001-9535-4470-8322-33e2d4f51135" />

<img width="570" height="331" alt="Screenshot 2026-05-29 215106" src="https://github.com/user-attachments/assets/395e8086-7368-4a70-9d06-36b424557eab" />


2 Warp SIMT GPU Core — RTL to GDS

2-warp, 8-lane SIMT execution engine in RV32I. Round-robin warp scheduler with load stall detection, per-lane register files, and 8-bank scratchpad memory. Verified with a directed testbench (34/34 passing) and Spike ISS co-simulation across all 8 lanes. Full RTL-to-GDS on ASAP7 via OpenROAD: 318 cells, 39 µm², 500 MHz, 0 DRC violations, 50.2 µW.

<img width="971" height="826" alt="Screenshot 2026-06-07 135004" src="https://github.com/user-attachments/assets/269d1cee-bc64-4c31-9a72-8120a6b65697" />

RV32I 5-Stage Pipelined CPU

Full RV32I pipeline in SystemVerilog with forwarding, load-use stall detection, branch resolution, and a 2-bit saturating counter branch predictor. 27/27 directed tests passing across ALU ops, RAW hazard chains, load-use hazards, branches, JAL, LUI, and SLTU.

ML-Based Physical Design Automation

Random Forest regression model predicting post-synthesis PPA from RTL features, achieving 92% accuracy. Automated via Python and TCL scripts integrated into the OpenROAD flow, cutting manual iteration cycles by 40%.

<img width="1943" height="907" alt="pdn_heatmap" src="https://github.com/user-attachments/assets/3b593806-f4e6-4d19-bd98-0f82d13fbaf9" />

📧 rakshithsuresh2001@gmail.com

