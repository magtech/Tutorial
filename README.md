# Claude Code Sandbox

A tiny C++ "Hello World" project used as a sandbox for learning
[Claude Code](https://claude.com/claude-code) and trying out new features.
The code is intentionally minimal so you can change, break and rebuild it freely.

## Building

### CMake (Linux, macOS, Windows)

```bash
cmake -B build
cmake --build build
ctest --test-dir build --output-on-failure
```

Run with `./build/hello` (Linux/macOS) or `build\Release\hello.exe` (Windows / Visual Studio).

### g++ only (no CMake)

```bash
g++ -std=c++17 -Wall -Wextra -o hello main.cpp
```

### Visual Studio

Open "Developer Command Prompt for VS" and run `cl main.cpp /Fe:hello.exe`,
or open the folder in Visual Studio (File > Open > CMake...).

## Claude Code setup

| Path | What it is |
|------|------------|
| `CLAUDE.md` | Project memory: context and build commands Claude reads at session start |
| `.claude/settings.json` | Shared permissions (build commands pre-approved, force-push denied) |
| `.claude/skills/build-and-run/` | Example skill — try `/build-and-run` |
| `.claude/agents/cpp-reviewer.md` | Example subagent that reviews C++ diffs |

Personal overrides go in `.claude/settings.local.json` and `CLAUDE.local.md` (both git-ignored).

## Things to try

- **Skills:** run `/build-and-run`, then write your own skill in `.claude/skills/`.
- **Subagents:** after an edit, ask Claude to "use the cpp-reviewer agent on my changes".
- **Plan mode:** ask for a feature (e.g. "greet the user by name from argv") in plan mode and review the plan first.
- **Hooks:** add a `PostToolUse` hook in `.claude/settings.json` that rebuilds after every edit.
- **Permissions:** tweak the allow/deny lists and see how prompting changes.
- **Git workflow:** have Claude create a branch, commit, open a PR, and watch CI.
- **Memory:** tell Claude a preference and check what it remembers next session.

## Project structure

```
Tutorial/
  main.cpp                 # Application source code
  CMakeLists.txt           # CMake build + CTest output check
  CLAUDE.md                # Claude Code project memory
  .claude/
    settings.json          # Shared Claude Code settings
    skills/build-and-run/  # Example skill
    agents/cpp-reviewer.md # Example subagent
  .github/workflows/
    build.yml              # CI: build and test on Linux and Windows
```

## License

MIT
