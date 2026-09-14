# ebpf-common

CMake wrapper that vendors eBPF toolchain dependencies for Dynatrace eBPF projects.

## What's inside

| CMake target   | Source                          | What it provides                              |
|----------------|---------------------------------|-----------------------------------------------|
| `bpftool`      | [`bpftool`][bpftool] submodule  | Imported `bpftool` bootstrap binary            |
| `libbpf`       | bundled inside `bpftool`        | Static `libbpf.a` + headers                   |
| `libpf-tools`  | `bcc/libbpf-tools/`             | `btf_helpers`, `trace_helpers`, `uprobe_helpers` |

[bpftool]: https://github.com/libbpf/bpftool

## Usage

Add as a git submodule, then include in your `CMakeLists.txt`:

```cmake
add_subdirectory(ebpf-common)

target_link_libraries(my_target PRIVATE libbpf libpf-tools)
```

The `bpftool` target is used at build time (e.g. for skeleton generation via `bpf_object__open`).

## Requirements

- Linux with eBPF support (kernel ≥ 5.10 recommended)
- `clang` / `llvm`
- `cmake` ≥ 3.22
- `libelf`
- `make`

## Build

```sh
git submodule update --init --recursive
cmake -B build
cmake --build build
```

The build compiles bpftool and libbpf from source into `build/bpftool/` and `build/libbpf/` respectively.
You can control parallelism with `-DTHIRDPARTY_MAKE_JOBS_COUNT=N` (default: `1`).

## License

See [LICENSE](LICENSE). Vendored components retain their own licenses (bpftool/libbpf: LGPL-2.1, BCC libbpf-tools: Apache-2.0).
