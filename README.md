# HLS4ML VITIS UNIFIED BACKEND TUTORIAL

## 0.A Pre-requisite list

for using HLS4ML VITIS UNIFIED BACKEND 

- Python 3.XX
- VITIS (2023.2 version is tested in this tuturial)
- VIVADO (2023.2 version is tested in this tuturial)
- HLS4ML (with pull-request vitis unfied Backend)


## 0.B XPFM or XSA file

- **XPFM** (Xilinx Platform Metadata) or **XSA** (Xilinx Support Archive)
  - These files serve as the hardware skeleton for the project, defining essential components such as the main processor (PS), AXI interconnects, interrupt controllers, and DMA IPs.
  - The HLS4ML Vitis Unified backend uses this platform definition to integrate your neural network accelerator into the system.

- To create your own custom XSA/XPFM file, please follow the guide in the [`platform_setup_tutorial`](./platform_setup_tutorial) folder.

## 0.C Install HLS4ML VITIS UNIFIED BACKEND and virtual environment

- Since the Vitis Unified Backend is not yet merged into the main branch of HLS4ML, you must install it directly from the pending Pull Request (#1376).
- Run the following command:

```bash
pip install git+https://github.com/fastmachinelearning/hls4ml.git@refs/pull/1376/head
```

Alternatively, if you already have the repository cloned locally, you can fetch the PR branch:

```bash
git fetch origin pull/1376/head:pr-1376
git checkout pr-1376
pip install .
```

## 1. Model Creation and Prediction

- This is the first and most basic tutorial. Its main goal is to verify that the VitisUnified backend produces the exact same software simulation results as the traditional Vitis backend.

## 2. C Simulation (CSim)

- This tutorial runs a C simulation (`csim`) using the Vitis HLS compiler.
- It validates that the generated C++ HLS code behaves identically to the Python-based "bridge" prediction.
- If this passes, the HLS C++ code is functionally correct for synthesis.

## 3. RTL Co-Simulation

- This tutorial runs a full RTL co-simulation (`cosim`), where the C++ code is synthesized into RTL (Verilog/VHDL) and then simulated.
- It compares the cycle-accurate RTL simulation results against the software predictions.
- This step ensures that the synthesized hardware logic matches the software model within a strict tolerance (1e-4).

## 4. FIFO Depth Optimization

- This tutorial demonstrates the `vitisunified:fifo_depth_optimization` flow.
- It runs a special co-simulation pass to analyze data flow and automatically determine optimal FIFO sizes between layers.
- The result is a `fifo_depths.json` file, which helps minimize resource usage while preventing deadlocks.

## 5. Generate Unified Bitfile

- This covers the full end-to-end flow: from Keras model to a bitfile (`.xclbin` / `.bit`) for the ZCU102.
- It performs synthesis, place-and-route, and generates the final binary tailored for the platform.
- **Note:** This step is computationally intensive and takes significantly longer than the others.

