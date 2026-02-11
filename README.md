# HP-ISP Engine

## High-Performance Image Signal Processing Benchmark Engine

A performance-oriented benchmark engine for analyzing and optimizing OpenCV-based image processing pipelines.

## 📌 Overview

**HP-ISP Engine** is a C++17-based high-performance benchmarking framework designed to:

- Analyze cv::Mat memory architecture

- Optimize SIMD and multi-threaded image processing

- Compare CPU vs OpenCL acceleration performance

- Provide measurable, reproducible performance metrics

This project focuses on low-level performance engineering, memory layout inspection, and cache-aware optimization strategies within OpenCV.

## 🎯 Project Objectives

The core goals of this project are:

- 🔍 Deep analysis of cv::Mat internal memory structure

- 🚀 SIMD-based performance optimization (SSE/AVX)

- 🧵 Multi-threading optimization (std::thread / OpenMP)

- ⚡ OpenCL acceleration benchmarking

- 📊 Performance comparison across execution backends

## 🛠 Tech Stack

|Component|Version|
|---------|---------|
|Language |C++17|
|IDE |Visual Studio 2017|
|OpenCV |4.10|
|OS |Windows 11 (x64)|


## 📂 Project Structure (Planned)

```bash
HP-ISP-Engine/
│
├── core/                # Benchmark core engine
├── analyzer/            # cv::Mat memory & refcount analyzer
├── simd/                # SIMD optimization modules
├── threading/           # Multi-threading benchmark modules
├── opencl/              # OpenCL acceleration comparison
├── benchmarks/          # Performance test cases
└── docs/                # Documentation
```

## 🚧 Development Roadmap
### ✅ Phase 1 — Memory Architecture Analysis (Completed)

- [x] Environment setup
- [x] OpenCV 4.10 integration
- [x] cv::Mat reference counting analyzer
- [x] Memory layout inspection (step, data pointer, continuity check)
- [x] Benchmark timing utility (high_resolution_clock)

### 🔄 Phase 2 — CPU Optimization

- [] SIMD optimization (SSE / AVX2)
- [] Cache-line alignment optimization
- [] False sharing mitigation
- [] Multi-threading benchmark (std::thread)
- [] OpenMP comparison
- [] Performance scaling test (1~N cores)

### ⏳ Phase 3 — Heterogeneous Acceleration

- [] OpenCL backend activation
- [] CPU vs OpenCL performance benchmark
- [] Memory transfer overhead analysis
- [] Kernel profiling
- [] Throughput comparison report generation

## ⚙️ Environment Setup Guide (Beginner Friendly)
### 1️⃣ Install Visual Studio 2017

Install with:

- Desktop development with C++

- MSVC v141 toolset

- Windows 10 SDK

### 2️⃣ Install OpenCV 4.10

Download OpenCV 4.10 (Windows prebuilt)
Extract to:

```makefile
C:\opencv\opencv410
```

### 3️⃣ Configure Environment Variable

Add to System Environment Variables → Path

```makefile
C:\opencv\opencv410\build\x64\vc15\bin
```

Restart your PC after setting.

### 4️⃣ Create Visual Studio Project

1. Create Empty Console Project

2. Set:

    - Configuration: x64

    - C++ Language Standard: ISO C++17

### 5️⃣ Include Directories

Go to:

```mathematica
Project → Properties → C/C++ → General → Additional Include Directories
```

Add:

```makefile
C:\opencv\opencv410\build\include
```

### 6️⃣ Library Directories

```mathematica
Project → Properties → Linker → General → Additional Library Directories
```

Add:

```vbnet
C:\opencv\opencv410\build\x64\vc15\lib
```

### 7️⃣ Link Required Libraries

```mathematica
Project → Properties → Linker → Input → Additional Dependencies
```

Add:

```vbnet
opencv_world4100.lib
```

### 8️⃣ Copy DLL Files (If Needed)

Copy:

```makefile
C:\opencv\opencv410\build\x64\vc15\bin\opencv_world4100.dll
```

into your project executable directory:

```php-template
<ProjectFolder>\x64\Debug\
<ProjectFolder>\x64\Release\
```

## 🧪 Example Benchmark Execution

```cpp
cv::Mat img = cv::imread("test.jpg", cv::IMREAD_COLOR);

auto start = std::chrono::high_resolution_clock::now();

// processing function
process(img);

auto end = std::chrono::high_resolution_clock::now();
std::cout << "Elapsed: "
          << std::chrono::duration<double, std::milli>(end - start).count()
          << " ms\n";
```

## 📊 Benchmark Philosophy

This engine emphasizes:

- Deterministic measurement

- Cache-aware design

- Memory locality optimization

- Hardware-conscious development

- Reproducible benchmarking methodology

## 📈 Future Improvements

- Automated benchmark result exporter (CSV/JSON)

- Visualization dashboard

- CI-based performance regression detection

- Cross-platform support (Linux, Clang)

## 🤝 Contribution

- Contributions are welcome, especially in:

- SIMD micro-optimizations

- OpenCL kernel tuning

- Performance profiling techniques

- Cross-platform benchmarking

## 📜 License

MIT License

## 👨‍💻 Author

C/C++ System Programmer
Performance & Memory Optimization Focused Developer @tomo