# ebpf-common

Common utilities and shared components for building eBPF-based applications.

This repository provides reusable building blocks used across Dynatrace eBPF projects. It aims to simplify development of high-performance, kernel-level observability tools by abstracting common patterns and reducing boilerplate.

## 🚀 Overview

The **ebpf-common** library provides shared abstractions to:

- Interact with eBPF programs and maps  
- Handle kernel/user-space communication  
- Support portability across different kernel versions  
- Reduce duplication across multiple projects  

## ✨ Features

- **Reusable eBPF helpers**  
  Common utilities for loading and managing eBPF programs

- **Kernel compatibility layer**  
  Simplifies working across multiple Linux kernel versions

- **Event handling utilities**  
  Standardized mechanisms for processing kernel events

- **Data structures and serialization**  
  Shared models for consistent telemetry output


## 📦 Use Cases

This library is intended to be used as a foundation for:

- Observability agents  
- Network monitoring tools  
- Service discovery systems  
- Security and tracing solutions  

Projects built on top of eBPF often rely on common components like this to handle low-level kernel integration efficiently.

## 🛠️ Requirements

Typical requirements for building eBPF-based projects:

- Linux kernel with eBPF support (>= 5.10 recommended)  
- `clang` / `llvm`  
- `cmake`  
- `libelf`  

## 🔧 Build
Simply add ebpf-common to your cmake structure

```cmake
add_subdirectory(ebpf-common)