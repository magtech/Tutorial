# Claude Code Sandbox

This repo is a playground for learning Claude Code and trying new features
(skills, subagents, hooks, permissions, plan mode, PR workflows, etc.).
The C++ program is deliberately tiny so it can be changed, broken and rebuilt freely.

## Project

- `main.cpp` — the program; prints `Hello, World!`
- `CMakeLists.txt` — builds the `hello` executable (C++17) and registers a CTest output check
- `.github/workflows/build.yml` — CI on Linux and Windows: configure, build, run tests
- `.claude/` — shared Claude Code config: settings, skills, subagents

## Build and run

With CMake (Linux/macOS):

```bash
cmake -B build && cmake --build build && ctest --test-dir build --output-on-failure
./build/hello
```

Without CMake (just g++):

```bash
mkdir -p build && g++ -std=c++17 -Wall -Wextra -o build/hello main.cpp && ./build/hello
```

On Windows the binary is `build/Release/hello.exe` (multi-config generator, pass `--config Release`).

## Conventions

- Keep the code C++17 and warning-free with `-Wall -Wextra`.
- If you change the program's output, update the `PASS_REGULAR_EXPRESSION` in `CMakeLists.txt` too.
- Build output goes in `build/` (git-ignored); never commit binaries.
- Experiments are welcome: prefer doing them on a branch so `main` stays a clean baseline.
