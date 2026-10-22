---
name: build-and-run
description: Build the hello program, run its tests, and show its output. Use when asked to build, run, test, or check that the project still compiles.
---

# Build and run

1. If `cmake` is available, run:
   ```bash
   cmake -B build && cmake --build build && ctest --test-dir build --output-on-failure
   ```
   Otherwise compile directly:
   ```bash
   mkdir -p build && g++ -std=c++17 -Wall -Wextra -o build/hello main.cpp
   ```
2. Run `./build/hello` (on Windows: `build/Release/hello.exe`).
3. Report: whether it compiled, any warnings, test results, and the program output.
   If something failed, show the relevant error lines and suggest a fix — don't apply it unless asked.
