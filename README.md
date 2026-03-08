# 🌀 Glitch Mesh Go

[![Go Version](https://img.shields.io/badge/Go-1.23.1-00ADD8?style=for-the-badge&logo=go)](https://golang.org)
[![Bazel](https://img.shields.io/badge/Bazel-powered-00CC00?style=for-the-badge&logo=bazel)](https://bazel.build)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

> A high-performance, experimental service mesh control plane and edge proxy implementation in Go, powered by Bazel.

---

## 🚀 Overview

**Glitch Mesh Go** is a next-generation exploration into service mesh architectures, focusing on resilience, observability, and "glitch" (fault-injection) testing. Built with a modern Go stack and the hermetic build power of Bazel, it aims to provide a robust yet flexible foundation for cloud-native networking.

## ✨ Features (Planned)

- [ ] **xDS Control Plane**: Full support for gRPC-based xDS APIs to configure sidecar proxies.
- [ ] **Real-time Observability**: SSE (Server-Sent Events) and gRPC streaming for live telemetry.
- [ ] **Fault Injection**: Built-in "Glitch" engine to simulate network latency, partitions, and errors.
- [ ] **Hermetic Builds**: Fully managed toolchains and dependencies via Bazel Bzlmod.
- [ ] **Cloud Native**: Designed for seamless deployment on Kubernetes and Google Cloud Run.

## 🛠 Tech Stack

- **Language**: [Go 1.23.1+](https://golang.org)
- **Build System**: [Bazel](https://bazel.build) (Bzlmod)
- **Communication**: gRPC, Protobuf, SSE
- **Automation**: Gazelle for Bazel metadata management

## 🏗 Getting Started

### Prerequisites

- [Bazelisk](https://github.com/bazelbuild/bazelisk) (recommended) or Bazel 7.x+
- Go 1.23.1 (managed automatically by Bazel)

### Building and Running

To build and run the main binary:

```bash
# Build the project
bazel build //:glitch-mesh-go

# Run the binary
bazel run //:glitch-mesh-go
```

### Managing Dependencies

This project uses **Gazelle** to manage Bazel build files. If you add new Go files or dependencies, run:

```bash
bazel run //:gazelle
```

## 📜 Development Workflow

We use a modern Bazel-first workflow. All dependencies are defined in `MODULE.bazel` and synchronized via `go.mod`.

1. **Add Dependency**: Add your import to `main.go`.
2. **Sync**: Run `go mod tidy`.
3. **Update Bazel**: Run `bazel run //:gazelle`.
4. **Build**: Run `bazel build //...`.

---

## 🗺 Roadmap

- [x] Initial Bazel + Go Project Setup
- [ ] Implement Basic SSE Streaming Server
- [ ] Integrate gRPC xDS Control Plane
- [ ] Add OCI Container Support for Cloud Run

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
