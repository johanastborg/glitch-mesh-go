# 🌀 Glitch Mesh Go

[![Go Version](https://img.shields.io/badge/Go-1.23.1-00ADD8?style=for-the-badge&logo=go)](https://golang.org)
[![Bazel](https://img.shields.io/badge/Bazel-powered-00CC00?style=for-the-badge&logo=bazel)](https://bazel.build)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

> A lightweight local xDS control plane for gRPC development, serving as a local-first alternative to Google Cloud Traffic Director.

---

**Glitch Mesh Go** is a specialized control plane designed to accelerate local gRPC development. It implements a subset of the xDS APIs to provide a seamless, local-first testing environment for services that would typically rely on **Google Cloud Traffic Director**. By cutting out cloud latency and configuration overhead, it allows developers to iterate on mesh networking logic directly on their workstations.

## ✨ Features (Planned)

- [ ] **xDS Control Plane**: Lightweight implementation of gRPC-compliant xDS APIs (LDS, RDS, CDS, EDS).
- [ ] **Traffic Director Alternative**: Drop-in local replacement for testing gRPC mesh configurations without GCP.
- [ ] **Live Debugging**: SSE (Server-Sent Events) and gRPC streaming for real-time traffic view.
- [ ] **Glitch Injection**: Simulate network failures and latency locally to test application resilience.
- [ ] **Bazel-Powered**: Hermetic, reproducible builds via Bzlmod for consistent dev environments.

## 🛠 Tech Stack

- **Language**: [Go 1.23.1+](https://golang.org)
- **Build System**: [Bazel](https://bazel.build) (Bzlmod)
- **Communication**: gRPC, Protobuf, SSE
- **Automation**: Gazelle for Bazel metadata management

## 📂 Project Structure

```text
.
├── BUILD.bazel          # Root build definitions & Gazelle config
├── MODULE.bazel         # Bazel module & dependency management
├── main.go              # Application entry point
├── go.mod               # Go module definition (mirrored in Bazel)
└── README.md            # You are here
```

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
- [ ] Implement Basic SSE Streaming Server for Observability
- [ ] Implement Core xDS APIs (LDS/RDS/CDS/EDS) for gRPC
- [ ] Docker Support for unified local development environments

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
