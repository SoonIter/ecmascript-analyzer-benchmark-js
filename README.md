# ECMAScript Analyzer Benchmark (npm)

How fast the JavaScript and TypeScript analyzers on npm build the semantic model of real codebases: every scope and binding, every reference resolved to its declaration, and every import linked across files.

## Summary

Median time to analyze a whole codebase. The fastest in each row is bold, and every other time shows how many times it is of the fastest.

| | Files | Yuku | TypeScript | typescript-eslint |
|---|---:|---|---|---|
| [TypeScript compiler](#typescript-compiler) | 77 | **99.8 ms** | 627 ms · 6.28× | 950 ms · 9.52× |
| [Excalidraw](#excalidraw) | 618 | **77.9 ms** | 551 ms · 7.07× | 803 ms · 10.3× |
| [three.js](#threejs) | 755 | **42.8 ms** | 402 ms · 9.40× | 422 ms · 9.87× |
| [Vue](#vue) | 473 | **56.1 ms** | 398 ms · 7.10× | 593 ms · 10.6× |
| [Zod](#zod) | 332 | **37.8 ms** | 274 ms · 7.25× | 491 ms · 13.0× |
| [date-fns](#date-fns) | 1,643 | **41.8 ms** | 395 ms · 9.46× | 321 ms · 7.68× |
| [Svelte](#svelte) | 416 | **25.2 ms** | 256 ms · 10.1× | 249 ms · 9.85× |
| [Preact](#preact) | 33 | **2.4 ms** | 24.7 ms · 10.4× | 39.3 ms · 16.5× |

On single files:

| | Files | Yuku | TypeScript | typescript-eslint |
|---|---:|---|---|---|
| [typescript.js](#typescriptjs) | 1 | **69.8 ms** | 605 ms · 8.66× | 966 ms · 13.8× |
| [checker.ts](#checkerts) | 1 | **27.2 ms** | 216 ms · 7.96× | 321 ms · 11.8× |
| [lib.dom.d.ts](#libdomdts) | 1 | **6.8 ms** | 65.2 ms · 9.53× | 137 ms · 20.0× |
| [react.js](#reactjs) | 1 | **0.34 ms** | 4.3 ms · 12.5× | 5.2 ms · 15.0× |

## Projects

### [TypeScript compiler](https://github.com/microsoft/TypeScript/tree/050880ce59e30b356b686bd3144efe24f875ebc8)

77 files · 9.0 MB · TypeScript

![Bar chart of the time each analyzer takes on TypeScript compiler](charts/typescript.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **99.8 ms** | **±0.24%** | **97.8 ms** | **113 ms** | **baseline** |
| TypeScript | 627 ms | ±0.22% | 616 ms | 686 ms | 6.28× slower |
| typescript-eslint | 950 ms | ±0.71% | 915 ms | 1,049 ms | 9.52× slower |

### [Excalidraw](https://github.com/excalidraw/excalidraw/tree/1919728724a1b71af73cb7e6d2d1a418a1415b1c)

618 files · 7.6 MB · declarations, JavaScript, TypeScript, TSX

![Bar chart of the time each analyzer takes on Excalidraw](charts/excalidraw.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **77.9 ms** | **±1.25%** | **73.0 ms** | **99.5 ms** | **baseline** |
| TypeScript | 551 ms | ±0.28% | 536 ms | 643 ms | 7.07× slower |
| typescript-eslint | 803 ms | ±0.70% | 780 ms | 872 ms | 10.3× slower |

### [three.js](https://github.com/mrdoob/three.js/tree/157f0885b8428b5ffe8f6f7309b2d6f59faa1497)

755 files · 4.4 MB · JavaScript

![Bar chart of the time each analyzer takes on three.js](charts/three.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **42.8 ms** | **±1.28%** | **35.2 ms** | **53.3 ms** | **baseline** |
| TypeScript | 402 ms | ±0.43% | 380 ms | 416 ms | 9.40× slower |
| typescript-eslint | 422 ms | ±0.70% | 405 ms | 1,386 ms | 9.87× slower |

### [Vue](https://github.com/vuejs/core/tree/4ab865a848a1da3d10fb674f857e5fff13094644)

473 files · 4.1 MB · declarations, JavaScript, TypeScript

![Bar chart of the time each analyzer takes on Vue](charts/vue.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **56.1 ms** | **±0.96%** | **53.0 ms** | **74.4 ms** | **baseline** |
| TypeScript | 398 ms | ±0.65% | 383 ms | 482 ms | 7.10× slower |
| typescript-eslint | 593 ms | ±1.49% | 560 ms | 744 ms | 10.6× slower |

### [Zod](https://github.com/colinhacks/zod/tree/004d800c9e3cd4c79930f55aa4ad080225b22efd)

332 files · 2.9 MB · TypeScript

![Bar chart of the time each analyzer takes on Zod](charts/zod.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **37.8 ms** | **±1.16%** | **31.3 ms** | **52.1 ms** | **baseline** |
| TypeScript | 274 ms | ±1.35% | 251 ms | 345 ms | 7.25× slower |
| typescript-eslint | 491 ms | ±1.94% | 460 ms | 763 ms | 13.0× slower |

### [date-fns](https://github.com/date-fns/date-fns/tree/717ce0a807ea4c6b540d015b5c408723175b2838)

1,643 files · 2.8 MB · declarations, JavaScript, TypeScript

![Bar chart of the time each analyzer takes on date-fns](charts/date_fns.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **41.8 ms** | **±1.47%** | **32.5 ms** | **69.7 ms** | **baseline** |
| typescript-eslint | 321 ms | ±1.25% | 307 ms | 446 ms | 7.68× slower |
| TypeScript | 395 ms | ±1.59% | 369 ms | 612 ms | 9.46× slower |

### [Svelte](https://github.com/sveltejs/svelte/tree/020242d6bef059df9ae8c13dc8dbff4c9b31e0ff)

416 files · 1.9 MB · declarations, JavaScript, TypeScript

![Bar chart of the time each analyzer takes on Svelte](charts/svelte.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **25.2 ms** | **±1.86%** | **20.1 ms** | **49.6 ms** | **baseline** |
| typescript-eslint | 249 ms | ±1.54% | 226 ms | 316 ms | 9.85× slower |
| TypeScript | 256 ms | ±1.21% | 239 ms | 328 ms | 10.1× slower |

### [Preact](https://github.com/preactjs/preact/tree/3fcc391adc243d479ab10b4cf70fa609708c9348)

33 files · 0.3 MB · declarations, JavaScript

![Bar chart of the time each analyzer takes on Preact](charts/preact.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **2.4 ms** | **±0.98%** | **2.2 ms** | **9.9 ms** | **baseline** |
| TypeScript | 24.7 ms | ±0.94% | 22.6 ms | 48.4 ms | 10.4× slower |
| typescript-eslint | 39.3 ms | ±0.85% | 35.3 ms | 63.7 ms | 16.5× slower |

## Single files

### [typescript.js](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/typescript.js)

1 file · 7.8 MB · JavaScript

![Bar chart of the time each analyzer takes on typescript.js](charts/typescript_js.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **69.8 ms** | **±3.62%** | **62.8 ms** | **109 ms** | **baseline** |
| TypeScript | 605 ms | ±1.00% | 581 ms | 779 ms | 8.66× slower |
| typescript-eslint | 966 ms | ±0.97% | 908 ms | 1,199 ms | 13.8× slower |

### [checker.ts](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/checker.ts)

1 file · 3.0 MB · TypeScript

![Bar chart of the time each analyzer takes on checker.ts](charts/checker.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **27.2 ms** | **±1.75%** | **24.2 ms** | **41.1 ms** | **baseline** |
| TypeScript | 216 ms | ±1.32% | 200 ms | 271 ms | 7.96× slower |
| typescript-eslint | 321 ms | ±0.99% | 303 ms | 407 ms | 11.8× slower |

### [lib.dom.d.ts](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/lib.dom.d.ts)

1 file · 2.2 MB · declarations

![Bar chart of the time each analyzer takes on lib.dom.d.ts](charts/lib_dom.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **6.8 ms** | **±0.78%** | **6.2 ms** | **22.3 ms** | **baseline** |
| TypeScript | 65.2 ms | ±0.60% | 61.8 ms | 85.7 ms | 9.53× slower |
| typescript-eslint | 137 ms | ±0.79% | 124 ms | 162 ms | 20.0× slower |

### [react.js](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/react.js)

1 file · 0.1 MB · JavaScript

![Bar chart of the time each analyzer takes on react.js](charts/react.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **0.34 ms** | **±0.12%** | **0.31 ms** | **2.3 ms** | **baseline** |
| TypeScript | 4.3 ms | ±0.73% | 3.9 ms | 23.5 ms | 12.5× slower |
| typescript-eslint | 5.2 ms | ±0.31% | 4.8 ms | 21.1 ms | 15.0× slower |

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
