# ECMAScript Analyzer Benchmark (npm)

How fast the JavaScript and TypeScript analyzers on npm build the semantic model of real codebases: every scope and binding, every reference resolved to its declaration, and every import linked across files.

## Summary

Median time to analyze a whole codebase. The fastest in each row is bold, and every other time shows how many times it is of the fastest.

| | Files | Yuku | TypeScript | typescript-eslint |
|---|---:|---|---|---|
| [TypeScript compiler](#typescript-compiler) | 77 | **108 ms** | 693 ms · 6.40× | 1,102 ms · 10.2× |
| [Excalidraw](#excalidraw) | 618 | **85.4 ms** | 612 ms · 7.17× | 920 ms · 10.8× |
| [three.js](#threejs) | 755 | **45.1 ms** | 394 ms · 8.74× | 460 ms · 10.2× |
| [Vue](#vue) | 473 | **60.7 ms** | 437 ms · 7.20× | 663 ms · 10.9× |
| [Zod](#zod) | 332 | **39.5 ms** | 277 ms · 7.02× | 533 ms · 13.5× |
| [date-fns](#date-fns) | 1,643 | **46.1 ms** | 405 ms · 8.78× | 351 ms · 7.62× |
| [Svelte](#svelte) | 416 | **27.1 ms** | 267 ms · 9.82× | 261 ms · 9.60× |
| [Preact](#preact) | 33 | **2.6 ms** | 26.5 ms · 10.2× | 45.7 ms · 17.6× |

On single files:

| | Files | Yuku | TypeScript | typescript-eslint |
|---|---:|---|---|---|
| [typescript.js](#typescriptjs) | 1 | **87.1 ms** | 627 ms · 7.20× | 1,028 ms · 11.8× |
| [checker.ts](#checkerts) | 1 | **29.3 ms** | 222 ms · 7.60× | 344 ms · 11.7× |
| [lib.dom.d.ts](#libdomdts) | 1 | **7.2 ms** | 69.4 ms · 9.69× | 143 ms · 20.0× |
| [react.js](#reactjs) | 1 | **0.35 ms** | 4.7 ms · 13.5× | 5.6 ms · 16.1× |

## Projects

### [TypeScript compiler](https://github.com/microsoft/TypeScript/tree/050880ce59e30b356b686bd3144efe24f875ebc8)

77 files · 9.0 MB · TypeScript

![Bar chart of the time each analyzer takes on TypeScript compiler](charts/typescript.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **108 ms** | **±1.44%** | **96.4 ms** | **164 ms** | **baseline** |
| TypeScript | 693 ms | ±1.85% | 648 ms | 1,038 ms | 6.40× slower |
| typescript-eslint | 1,102 ms | ±1.52% | 987 ms | 1,470 ms | 10.2× slower |

### [Excalidraw](https://github.com/excalidraw/excalidraw/tree/1919728724a1b71af73cb7e6d2d1a418a1415b1c)

618 files · 7.6 MB · declarations, JavaScript, TypeScript, TSX

![Bar chart of the time each analyzer takes on Excalidraw](charts/excalidraw.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **85.4 ms** | **±1.41%** | **73.0 ms** | **121 ms** | **baseline** |
| TypeScript | 612 ms | ±1.20% | 584 ms | 1,040 ms | 7.17× slower |
| typescript-eslint | 920 ms | ±1.32% | 785 ms | 1,123 ms | 10.8× slower |

### [three.js](https://github.com/mrdoob/three.js/tree/157f0885b8428b5ffe8f6f7309b2d6f59faa1497)

755 files · 4.4 MB · JavaScript

![Bar chart of the time each analyzer takes on three.js](charts/three.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **45.1 ms** | **±1.80%** | **35.3 ms** | **60.3 ms** | **baseline** |
| TypeScript | 394 ms | ±0.43% | 377 ms | 485 ms | 8.74× slower |
| typescript-eslint | 460 ms | ±1.55% | 399 ms | 1,119 ms | 10.2× slower |

### [Vue](https://github.com/vuejs/core/tree/4ab865a848a1da3d10fb674f857e5fff13094644)

473 files · 4.1 MB · declarations, JavaScript, TypeScript

![Bar chart of the time each analyzer takes on Vue](charts/vue.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **60.7 ms** | **±1.08%** | **54.7 ms** | **97.9 ms** | **baseline** |
| TypeScript | 437 ms | ±2.33% | 403 ms | 654 ms | 7.20× slower |
| typescript-eslint | 663 ms | ±2.21% | 584 ms | 1,058 ms | 10.9× slower |

### [Zod](https://github.com/colinhacks/zod/tree/004d800c9e3cd4c79930f55aa4ad080225b22efd)

332 files · 2.9 MB · TypeScript

![Bar chart of the time each analyzer takes on Zod](charts/zod.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **39.5 ms** | **±1.20%** | **32.4 ms** | **58.4 ms** | **baseline** |
| TypeScript | 277 ms | ±1.12% | 248 ms | 349 ms | 7.02× slower |
| typescript-eslint | 533 ms | ±2.43% | 452 ms | 891 ms | 13.5× slower |

### [date-fns](https://github.com/date-fns/date-fns/tree/717ce0a807ea4c6b540d015b5c408723175b2838)

1,643 files · 2.8 MB · declarations, JavaScript, TypeScript

![Bar chart of the time each analyzer takes on date-fns](charts/date_fns.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **46.1 ms** | **±1.62%** | **32.9 ms** | **69.4 ms** | **baseline** |
| typescript-eslint | 351 ms | ±1.35% | 310 ms | 769 ms | 7.62× slower |
| TypeScript | 405 ms | ±1.58% | 365 ms | 573 ms | 8.78× slower |

### [Svelte](https://github.com/sveltejs/svelte/tree/020242d6bef059df9ae8c13dc8dbff4c9b31e0ff)

416 files · 1.9 MB · declarations, JavaScript, TypeScript

![Bar chart of the time each analyzer takes on Svelte](charts/svelte.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **27.1 ms** | **±1.62%** | **20.0 ms** | **51.0 ms** | **baseline** |
| typescript-eslint | 261 ms | ±1.84% | 230 ms | 380 ms | 9.60× slower |
| TypeScript | 267 ms | ±1.99% | 241 ms | 406 ms | 9.82× slower |

### [Preact](https://github.com/preactjs/preact/tree/3fcc391adc243d479ab10b4cf70fa609708c9348)

33 files · 0.3 MB · declarations, JavaScript

![Bar chart of the time each analyzer takes on Preact](charts/preact.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **2.6 ms** | **±0.64%** | **2.2 ms** | **13.5 ms** | **baseline** |
| TypeScript | 26.5 ms | ±0.82% | 23.1 ms | 46.6 ms | 10.2× slower |
| typescript-eslint | 45.7 ms | ±4.22% | 36.5 ms | 359 ms | 17.6× slower |

## Single files

### [typescript.js](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/typescript.js)

1 file · 7.8 MB · JavaScript

![Bar chart of the time each analyzer takes on typescript.js](charts/typescript_js.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **87.1 ms** | **±3.19%** | **64.5 ms** | **171 ms** | **baseline** |
| TypeScript | 627 ms | ±1.13% | 584 ms | 887 ms | 7.20× slower |
| typescript-eslint | 1,028 ms | ±1.35% | 910 ms | 1,482 ms | 11.8× slower |

### [checker.ts](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/checker.ts)

1 file · 3.0 MB · TypeScript

![Bar chart of the time each analyzer takes on checker.ts](charts/checker.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **29.3 ms** | **±1.86%** | **23.4 ms** | **67.0 ms** | **baseline** |
| TypeScript | 222 ms | ±1.11% | 202 ms | 272 ms | 7.60× slower |
| typescript-eslint | 344 ms | ±1.51% | 306 ms | 611 ms | 11.7× slower |

### [lib.dom.d.ts](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/lib.dom.d.ts)

1 file · 2.2 MB · declarations

![Bar chart of the time each analyzer takes on lib.dom.d.ts](charts/lib_dom.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **7.2 ms** | **±1.41%** | **6.2 ms** | **20.1 ms** | **baseline** |
| TypeScript | 69.4 ms | ±1.04% | 62.9 ms | 111 ms | 9.69× slower |
| typescript-eslint | 143 ms | ±1.54% | 128 ms | 186 ms | 20.0× slower |

### [react.js](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/react.js)

1 file · 0.1 MB · JavaScript

![Bar chart of the time each analyzer takes on react.js](charts/react.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **0.35 ms** | **±0.16%** | **0.32 ms** | **2.5 ms** | **baseline** |
| TypeScript | 4.7 ms | ±0.83% | 3.9 ms | 26.9 ms | 13.5× slower |
| typescript-eslint | 5.6 ms | ±0.44% | 4.9 ms | 13.2 ms | 16.1× slower |

## Analyzers

| Analyzer | Packages | What it is |
|----------|----------|------------|
| [Yuku](https://github.com/yuku-toolchain/yuku) | `Yuku Analyzer` | Computed natively in Zig, in the same pass as the parse. |
| [TypeScript](https://github.com/microsoft/typescript-go) | `typescript@7` | The TypeScript compiler, written in Go, through its API. |
| [typescript-eslint](https://github.com/typescript-eslint/typescript-eslint/tree/main/packages/scope-manager) | `@typescript-eslint/typescript-estree` + `@typescript-eslint/scope-manager` | The parser and scope analysis behind typescript-eslint, linked across files by the benchmark. |

## Methodology

### The work

Every analyzer does the same job on a whole codebase, the job an editor, linter, or bundler needs done:

1. Parse every file into an AST of JavaScript objects.
2. Bind its scopes and declarations, with TypeScript's declaration merging and its separate value, type, and namespace spaces.
3. Resolve every reference to its declaration.
4. Follow every import and re-export across files to the declaration it names.

### Codebases

Each project is its source directories at a pinned commit, the files its own `tsconfig` covers. The single files are the [parser benchmark files](https://github.com/yuku-toolchain/parser-benchmark-files).

### Measurement

Every analyzer × codebase runs in its own freshly spawned Node.js process, so JIT state and garbage from one never affect another. Timing uses [Tinybench](https://github.com/tinylibs/tinybench), with warmup iterations followed by timed iterations, in 3 independent runs per analyzer. The reported median is the median across those runs, which is robust to GC pauses and scheduling blips. RME is the relative margin of error (99% confidence) within a run.

## System

| Property | Value |
|----------|-------|
| OS | macOS 25.6.0 (arm64) |
| CPU | Apple M5 Max |
| Cores | 18 |
| Memory | 64 GB |
| Runtime | Node.js v24.20.0 |

## Run the benchmarks

Requires [Node.js](https://nodejs.org/) 24 and [Bun](https://bun.sh/).

```bash
git clone https://github.com/yuku-toolchain/ecmascript-analyzer-benchmark-js.git
cd ecmascript-analyzer-benchmark-js
bun install
bun load-files
bun bench
```

`bun load-files` downloads the benchmark files and the pinned projects. `bun bench` measures every codebase on Node.js, saves the results to `result/`, and regenerates this README. Measure some codebases only by naming them, as in `node scripts/bench.ts vue zod`.

| Variable | Default | Meaning |
|----------|---------|---------|
| `BENCH_TIME` | 10000 | Timed duration per run, in ms |
| `BENCH_WARMUP` | 2000 | Warmup duration per run, in ms |
| `BENCH_RUNS` | 3 | Independent runs per analyzer |

For the most stable numbers, run on AC power with nothing else running.
