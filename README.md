Featured Projects

PicoRISCV-SoC — RISC-V SoC with ML Accelerator

PicoRV32 (RV32IM) CPU integrated with an 8x8 weight-stationary systolic array over AXI-Lite MMIO and a 4-wire SPI slave interface (390 to 4 pins). Full RTL-to-GDS on ASAP7 via OpenROAD: 47,051 cells, 5,431 µm², 500 MHz, 0 DRC violations. IRQ feedback from accelerator to CPU on computation complete. Submitted to ChipFoundry CI2609 shuttle via Caravel wrapper.

Systolic Array Accelerator — RTL to GDS

8x8 weight-stationary systolic array, INT8 weights, INT32 accumulators. Full OpenROAD flow on two nodes:

<img width="896" height="164" alt="image" src="https://github.com/user-attachments/assets/2cce8406-5f85-47f7-b9cf-c5dcedb1dd29" />

10x frequency, 46.4x area reduction across nodes.

UVM-Style Systolic Array Testbench

Structured SystemVerilog testbench for the 8x8 systolic array, built without a UVM library to run cleanly under Verilator 5.x. Per-PE scheduled checks using a timing model, constrained random stimulus, and 5 SVA properties checking protocol correctness every clock cycle.

1,337 functional checks, zero failures across 5 random seeds
15/15 functional coverage bins closed
Resolved a Verilator --timing coroutine limitation where post-NBA signal values are invisible inside tasks by moving psum checks into a dedicated always block

RV32I 5-Stage Pipelined CPU

Full RV32I pipeline in SystemVerilog with forwarding, load-use stall detection, branch resolution, and a 2-bit saturating counter branch predictor. 27/27 directed tests passing across ALU ops, RAW hazard chains, load-use hazards, branches, JAL, LUI, and SLTU.

ML-Based Physical Design Automation

Random Forest regression model predicting post-synthesis PPA from RTL features, achieving 92% accuracy. Automated via Python and TCL scripts integrated into the OpenROAD flow, cutting manual iteration cycles by 40%.

📧 rakshithsuresh2001@gmail.com

