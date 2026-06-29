 📌Featured Projects

 Custom ISA accelerator

RV32I pipeline with custom RISC-V ISA extension (MLOAD/MMUL/MSTORE) offloading 8x8 matrix multiply to a weight-stationary systolic array over AXI-Lite. 27/27 tests passing, ASAP7 7nm PD: 11,562 cells, 1,515 µm², 756MHz.

<img width="351" height="339" alt="Screenshot 2026-06-11 183453" src="https://github.com/user-attachments/assets/1530f0b3-1648-417d-8bcc-6ecc278f9572" />

<img width="249" height="327" alt="Screenshot 2026-06-11 173309" src="https://github.com/user-attachments/assets/a7aaf37b-f55a-4179-84eb-d989323d340c" />

**2 Warp SIMT GPU Core — RTL to GDS**

2-warp, 8-lane SIMT execution engine in RV32I. Round-robin warp scheduler with load stall detection, per-lane register files, and 8-bank scratchpad memory. Verified with a directed testbench (34/34 passing) and Spike ISS co-simulation across all 8 lanes. 

Full RTL-to-GDS on ASAP7 via OpenROAD: 663 cells, 2,862.66 µm² core area, 500 MHz, 0 DRC violations. 8x fakeram7_256x32 SRAM macros visible on the right (2,808.96 µm², ~98% of die area), standard cell logic on the left (~54 µm²).

<img width="357" height="326" alt="Screenshot 2026-06-20 212816" src="https://github.com/user-attachments/assets/f149800e-582b-445e-b135-0fe83ed88eec" />


**PicoRISCV-SoC — RISC-V SoC with ML Accelerator**

PicoRV32 (RV32IM) CPU integrated with an 8x8 weight-stationary systolic array over AXI-Lite MMIO and a 4-wire SPI slave interface (390 to 4 pins). 

Full RTL-to-GDS on ASAP7 via OpenROAD: 47,051 cells, 5,431 µm², 500 MHz, 0 DRC violations. IRQ feedback from accelerator to CPU on computation complete.

<img width="357" height="348" alt="Screenshot 2026-05-23 144441" src="https://github.com/user-attachments/assets/f787e911-8dc6-43e5-bd1f-5e368f8543ba" />

**Systolic Array Accelerator — RTL to GDS**

8x8 weight-stationary systolic array, INT8 weights, INT32 accumulators. Full OpenROAD flow on two nodes:

<img width="796" height="164" alt="image" src="https://github.com/user-attachments/assets/2cce8406-5f85-47f7-b9cf-c5dcedb1dd29" />


<img width="257" height="248" alt="Screenshot 2026-05-22 233913" src="https://github.com/user-attachments/assets/fce2cc2d-ad93-492e-a621-37ab6e476d4d" />

<img width="251" height="238" alt="Screenshot 2026-05-22 234125" src="https://github.com/user-attachments/assets/04200e73-aed1-4242-83f2-627bd1ca3574" />

10x frequency, 67.1x area reduction across nodes.
Submitted to ChipFoundry CI2609 shuttle via Caravel wrapper.


**UVM-Style Systolic Array Testbench**

Structured SystemVerilog testbench for the 8x8 systolic array, built without a UVM library to run cleanly under Verilator 5.020. Per-PE scheduled checks using a timing model, constrained random stimulus, and 5 SVA properties checking protocol correctness every clock cycle.

1,337 functional checks, zero failures across 5 random seeds
15/15 functional coverage bins closed
Resolved a Verilator --timing coroutine limitation where post-NBA signal values are invisible inside tasks by moving psum checks into a dedicated always block

<img width="264" height="434" alt="Screenshot 2026-05-29 215116" src="https://github.com/user-attachments/assets/9e9c7001-9535-4470-8322-33e2d4f51135" />

<img width="270" height="231" alt="Screenshot 2026-05-29 215106" src="https://github.com/user-attachments/assets/395e8086-7368-4a70-9d06-36b424557eab" />

**RV32I 5-Stage Pipelined CPU**

Full RV32I pipeline in SystemVerilog with forwarding, load-use stall detection, branch resolution, and a 2-bit saturating counter branch predictor. 27/27 directed tests passing across ALU ops, RAW hazard chains, load-use hazards, branches, JAL, LUI, and SLTU.

Reran the testbench under Synopsys VCS: 26/27 checks passed identically to Verilator

<img width="312" height="340" alt="Screenshot 2026-06-29 114313" src="https://github.com/user-attachments/assets/b8981857-a725-4a46-a537-113692965ecf" />

<img width="472" height="298" alt="Screenshot 2026-06-29 115008" src="https://github.com/user-attachments/assets/f5c39e65-1d15-491b-9a6b-540ee771893d" />

**ML-Based Physical Design Automation**

Random Forest regression model predicting post-synthesis PPA from RTL features, achieving 92% accuracy. Automated via Python and TCL scripts integrated into the OpenROAD flow, cutting manual iteration cycles by 40%.

<img width="443" height="207" alt="pdn_heatmap" src="https://github.com/user-attachments/assets/3b593806-f4e6-4d19-bd98-0f82d13fbaf9" />

📧 rakshithsuresh2001@gmail.com

