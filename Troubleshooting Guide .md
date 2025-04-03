# 🛠️ Langflow Installation Troubleshooting Guide (Windows)

If you encounter errors while installing Langflow using uv, follow the steps below to resolve common issues.

---

## ❌ Error 1: Failed to Build webrtcvad==2.0.10

```
x Failed to build `webrtcvad==2.0.10`
  |-> The build backend returned an error
  `-> Call to `setuptools.build_meta:__legacy__.build_wheel` failed
      (exit code: 1)
```

## ✅ Solution: Install Microsoft C++ Build Tools
Download and open the installer:

👉 https://visualstudio.microsoft.com/visual-cpp-build-tools/

In the Workloads tab, select:

☑️ Desktop development with C++

Ensure the following components are checked:

    ✅ MSVC v14.x (latest version)

    ✅ Windows 10 SDK (or Windows 11 SDK, depending on your system)

    ✅ C++ CMake tools for Windows (optional but helpful)

Click Install (or Modify if it's already installed).

Restart your terminal and try again:

```
uv pip install langflow
```

---

## ❌ Error 2: Failed to Build jiter==0.5.0

```
x Failed to build `jiter==0.5.0`
  |-> The build backend returned an error
  `-> Call to `maturin.build_wheel` failed (exit code: 1)
```

## ✅ Solution: Install Rust
jiter requires Rust to build native extensions.

Install Rust from the official site:

👉 https://www.rust-lang.org/tools/install

After installation, restart your terminal or run:

```
cargo --version
```

To verify Rust is installed.

Then try installing Langflow again:

```
uv pip install langflow
```
