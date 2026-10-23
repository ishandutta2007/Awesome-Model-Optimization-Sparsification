# Awesome-Model-Optimization-Sparsification

## Top Model Optimization & Sparsification Tools Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Pruning, Quantization & Hardware-Specific Compilation*  

**Last updated: March 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Model Optimization & Sparsification**. These tools reduce model size, latency, and power consumption — through pruning, quantization, distillation, and hardware-specific compilation — so models that were trained on datacenter GPUs can actually run on CPUs, NPUs, and edge devices.



**Examples** include TensorRT, OpenVINO, Apache TVM, Qualcomm AI Engine Direct, Apple Core ML, and ONNX Runtime (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, hardware-specific acceleration, and transparent optimization pipelines — with a critical caveat: **the Neural Magic ecosystem (SparseML, SparseZoo, DeepSparse) was deprecated on June 2, 2025** after Red Hat's acquisition, and several commercial optimization startups have been absorbed by larger vendors .



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **NVIDIA TensorRT** — **The reference inference optimizer for NVIDIA GPUs.** Compiles trained models into optimized engines with layer fusion, kernel auto-tuning, and precision calibration (FP16, INT8, FP8). **Best for any model that will run on NVIDIA hardware** — it's not optional if you want maximum GPU throughput.



- **Intel OpenVINO** — **The reference inference toolkit for Intel hardware** (CPUs, integrated GPUs, VPUs, NPUs). **Actively maintained and recommended as the CPU acceleration path** now that DeepSparse is deprecated . Supports model conversion, quantization, and heterogeneous execution across Intel devices.



- **Qualcomm AI Engine Direct (QNN)** — **The reference SDK for Snapdragon NPU, GPU, and CPU acceleration.** **Open-source JAX-QNN backend exists** for compiling StableHLO directly to QNN execution graphs, with **5.6x speedup on Hexagon NPU vs host CPU** for dense layers . **Best for Android and Windows on ARM deployments** targeting Snapdragon hardware.



- **Apple Core ML** — Apple's framework for on-device inference across Apple silicon, with automatic hardware dispatch to Neural Engine, GPU, or CPU. **Best for iOS and macOS applications** wanting native acceleration.



## Open-Source GitHub Projects



- **[Apache TVM](https://github.com/apache/tvm)** — **The open-source compiler stack for deep learning across diverse hardware.** Compiles models to optimized code for CPUs, GPUs, and custom accelerators. **Latest release 0.26.0** (August 2026) . **Best for teams targeting non-mainstream hardware** or building custom compilation pipelines.



- **[JAX-QNN](https://github.com/carrycooldude/JAX-QNN)** — **Qualcomm QNN backend for JAX** (Apache-2.0). Compiles StableHLO IR directly into native Qualcomm execution graphs with acceleration on Hexagon NPU, Adreno GPU, and Oryon CPU. **Benchmarks on Snapdragon X Elite**: 5.6x speedup on Hexagon NPU vs host CPU for 512×512 dense layers . **Best for JAX workloads targeting Snapdragon** without rewriting in a vendor-specific framework.



- **[ONNX Runtime](https://github.com/microsoft/onnxruntime)** — **The cross-platform inference engine** with execution providers for CUDA, TensorRT, OpenVINO, DirectML, CoreML, and more. **The actively maintained alternative** recommended when DeepSparse's deprecation forces a migration . **Best for teams wanting hardware flexibility** through provider selection without changing model code.



- **[OpenVINO Toolkit](https://github.com/openvinotoolkit/openvino)** — **Intel's open-source inference toolkit** (Apache-2.0). Model optimizer, runtime, and quantization tools for Intel hardware. **Best for self-hosted Intel CPU/GPU/NPU deployments.**



### Deprecated / End-of-Life Projects



**Do not start new projects on these.** They remain functional but receive no updates or support.



- **SparseML** — Neural Magic's sparsification recipe library. **Deprecated June 2, 2025** .

- **SparseZoo** — Neural Magic's sparse model repository. **Deprecated June 2, 2025** .

- **DeepSparse** — Neural Magic's CPU inference runtime. **Deprecated June 2, 2025** . **Was 5.8x faster than ONNX Runtime on pruned YOLOv5s**  — a reminder of what the ecosystem lost.

- **Sparsify** — Neural Magic's optimization UI. **Deprecated June 2, 2025** .



### Acquired / Absorbed Commercial Tools



- **Deci AI** — Acquired by **NVIDIA in May 2024** and dissolved as an independent entity .

- **OctoAI** — Acquired by **NVIDIA in September 2024** at $165M–$250M valuation .

- **Deeplite** — Acquired by **STMicroelectronics in April 2025** . Neutrino optimizer technology absorbed into ST's edge AI platform.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- **The Neural Magic ecosystem (SparseML, SparseZoo, DeepSparse, Sparsify) is deprecated** as of June 2, 2025, following Red Hat's acquisition . Existing pipelines still run, but **new projects should use OpenVINO or ONNX Runtime** for CPU acceleration .

- **Several commercial optimization startups have been acquired**: Deci AI by NVIDIA (2024) , OctoAI by NVIDIA (2024) , Deeplite by STMicroelectronics (2025) . Their standalone products are no longer independently available.

- Optimization techniques interact: pruning creates sparse weights that quantization compresses further, and hardware must actually support the resulting sparsity patterns for speedups to materialize — **block-sparse pruning with matching VNNI instructions outperformed unstructured sparsity** in DeepSparse benchmarks .

- Self-hosted open-source solutions require proper model conversion pipelines, calibration datasets for quantization, and validation that optimized output meets accuracy thresholds for your use case.



---



**Made for ML engineers deploying models to production hardware with real latency, memory, and power constraints.**

Let's make model optimization more open, hardware-aware, and migration-honest.
