# 张新凯 / Ustinian1722

**Edge AI · Industrial AI · AI Inference & Deployment**

我主要关注 **边缘 AI 推理部署、工业多变量时序、异常检测与 PHM**，希望把模型从实验环境真正落到 Jetson / Rockchip 等边缘设备与工业场景中。

My work focuses on **Edge AI deployment, industrial time-series modeling, anomaly detection, and predictive maintenance**, with an emphasis on reproducible engineering and real-device inference.

---

## ⭐ Featured Open-Source Projects

### [Industrial Multivariate Time-Series Anomaly Detection Benchmark](https://github.com/Ustinian1722/industrial-anomaly-detection)

面向工业多变量时序异常检测、定位和诊断分流的可复现实验平台。

- PCA-SPE / Hotelling T² / Isolation Forest
- LSTM-AE / PatchTST / TimesNet-lite
- USAD-lite / TranAD-lite / Anomaly Transformer-lite
- TimesFM 2.5 / Chronos-2 adapters
- ROC-AUC / PR-AUC / F1 / FAR / MAR / detection delay
- leave-one-group-out generalization
- latency / throughput / memory / model-size profiling
- train-only scaling / threshold fitting / leakage audit

### [IndusTSFM — Industrial Time-Series Foundation Model Adaptation & Generalization](https://github.com/Ustinian1722/industrial-tsfm)

研究时间序列基础模型在工业场景中的迁移、跨工况泛化和计算成本权衡。

- C-MAPSS · UCI Gas Turbine · Tennessee Eastman · NASA IMS
- PatchTST · TimesFM 2.5 · Chronos · Chronos-2 · Moirai-2
- cross-regime / cross-domain evaluation
- target-support adaptation
- LoRA / PEFT
- shift / OOD analysis
- compute-aware model & strategy selection

---

## 🔧 技术栈

**Edge AI / Inference**
- PyTorch · ONNX · ONNX Runtime · TensorRT
- FP16 / INT8 · calibration · model conversion · inference validation
- NVIDIA DeepStream / GStreamer
- RKNN-Toolkit2 / RKNNLite2

**Platforms**
- NVIDIA Jetson Orin Nano
- Rockchip RK3588 / Rock 5B
- Linux · Docker · Shell · Git

**AI / Perception**
- Object Detection · Tracking · Depth / Pose-related pipelines
- OpenCV · Kalman Filter · multi-camera perception
- ROS 2 integration

**Industrial AI / Time Series**
- Multivariate time-series forecasting
- Anomaly detection · fault-oriented diagnostics · PHM
- Cross-domain / cross-regime generalization
- TSFM adaptation: TimesFM · Chronos · Moirai
- Leakage-aware evaluation and deployment profiling

**Programming**
- Python
- C / C++ / CMake 基础

---

## 🚀 Selected Edge AI Projects

> 部分 Edge AI 项目包含完整工程实现、设备适配与部署代码，目前保持私有；这里展示技术路线与可验证结果。

### Jetson Orin Nano — Edge Robot Vision Framework
- 构建 Camera → Detection → Tracking → Depth → Control 的实时视觉链路
- 完成 PyTorch / ONNX → TensorRT FP16 / INT8 部署与精度对齐
- 将 CSI 摄像头、TensorRT 推理和 OSD 接入 DeepStream / GStreamer
- 集成 ROS 2 输出供导航、跟随和避障模块使用
- **Jetson Orin Nano：约 2 FPS → 30 FPS**
- **端到端延迟：约 500 ms → 33 ms**

### RK3588 — RF-DETR Heterogeneous Inference
- 面向 Transformer-heavy 检测模型设计 **NPU Backbone + CPU Transformer Head** 异构执行方案
- 完成 ONNX 拆分、RKNN 转换、量化与 tensor shape / layout / dtype / scale 对齐
- 对 CPU 侧 Transformer Head 使用 ONNX Runtime dynamic quantization
- **Detection：约 1.35×–1.66× 加速**
- **Segmentation：约 1.57×–1.92× 加速**

### Multi-Camera Edge Perception Platform
- Jetson Orin Nano + TensorRT + FastAPI + WebSocket + React
- 多目标跟踪、Hungarian assignment、6-state Kalman Filter
- pixel ↔ world 坐标变换、速度估计与跨摄像头融合
- 单例推理流水线避免多客户端重复触发 GPU inference

---

## 🎯 Current Focus

目前重点在把以下能力组合成一条完整的 **Industrial Edge AI** 技术链：

```text
Sensors / Camera
      ↓
Signal Processing / Perception
      ↓
Time-Series / Anomaly / PHM
      ↓
ONNX / TensorRT / RKNN
      ↓
Jetson / RK3588
      ↓
ROS 2 / Industrial Integration
```

长期关注：

- Edge AI inference optimization
- Industrial anomaly detection & predictive maintenance
- Multimodal sensor fusion
- Robot perception integration
- Time-series foundation models on real industrial workloads

---

## 📌 Engineering Principles

- Real-device results over paper-only claims
- Reproducible and auditable evaluation
- No test-set leakage
- Measure latency, throughput, memory and model size — not accuracy alone
- Prefer complete **data → model → deployment → profiling** pipelines
