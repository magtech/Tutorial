# Hello World - C++ Tutorial

A minimal C++ Hello World application built to learn the GitHub workflow with Claude.

## Prerequisites

- **Visual Studio** (with C++ desktop development workload) or any C++ compiler
- **CMake** 3.15+ (optional, for CMake builds)
- **Git** for version control

## Building

### Option 1: Visual Studio Developer Command Prompt

Open "Developer Command Prompt for VS" and run:

```bash
cl main.cpp /Fe:hello.exe
```

### Option 2: CMake

```bash
cmake -B build
cmake --build build
```

### Option 3: Visual Studio IDE

1. Open Visual Studio
2. File > Open > CMake... > select `CMakeLists.txt`
3. Build > Build All

## Running

```bash
./hello.exe
```

Output:
```
Hello, World!
```

## Project Structure

```
Tutorial/
  main.cpp          # Application source code
  CMakeLists.txt    # CMake build configuration
  .gitignore        # Files excluded from version control
  .github/
    workflows/
      build.yml     # GitHub Actions CI pipeline
  README.md         # This file
```

## License

MIT
