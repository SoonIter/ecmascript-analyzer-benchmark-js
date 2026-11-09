# ECMAScript Analyzer Benchmark (npm)

How fast the JavaScript and TypeScript analyzers on npm build the semantic model of real codebases: every scope and binding, every reference resolved to its declaration, and every import linked across files.

## Summary

Median time to analyze a whole codebase. The fastest in each row is bold, and every other time shows how many times it is of the fastest.

| | Files | Yuku | TypeScript | typescript-eslint |
|---|---:|---|---|---|
| [TypeScript compiler](#typescript-compiler) | 77 | **103 ms** | 669 ms · 6.48× | 1,030 ms · 9.96× |
| [Excalidraw](#excalidraw) | 618 | **82.1 ms** | 582 ms · 7.09× | 863 ms · 10.5× |
| [three.js](#threejs) | 755 | **43.8 ms** | 408 ms · 9.33× | 431 ms · 9.86× |
| [Vue](#vue) | 473 | **57.1 ms** | 394 ms · 6.90× | 595 ms · 10.4× |
| [Zod](#zod) | 332 | **38.3 ms** | 263 ms · 6.86× | 496 ms · 12.9× |
| [date-fns](#date-fns) | 1,643 | **43.5 ms** | 382 ms · 8.79× | 326 ms · 7.50× |
| [Svelte](#svelte) | 416 | **25.0 ms** | 250 ms · 9.99× | 244 ms · 9.76× |
| [Preact](#preact) | 33 | **2.3 ms** | 24.3 ms · 10.6× | 40.7 ms · 17.8× |

On single files:

| | Files | Yuku | TypeScript | typescript-eslint |
|---|---:|---|---|---|
| [typescript.js](#typescriptjs) | 1 | **71.0 ms** | 603 ms · 8.48× | 994 ms · 14.0× |
| [checker.ts](#checkerts) | 1 | **28.1 ms** | 217 ms · 7.74× | 325 ms · 11.6× |
| [lib.dom.d.ts](#libdomdts) | 1 | **6.8 ms** | 67.2 ms · 9.82× | 146 ms · 21.3× |
| [react.js](#reactjs) | 1 | **0.35 ms** | 4.3 ms · 12.1× | 5.5 ms · 15.8× |

## Projects

### [TypeScript compiler](https://github.com/microsoft/TypeScript/tree/050880ce59e30b356b686bd3144efe24f875ebc8)

77 files · 9.0 MB · TypeScript

![Bar chart of the time each analyzer takes on TypeScript compiler](charts/typescript.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **103 ms** | **±0.76%** | **99.8 ms** | **193 ms** | **baseline** |
| TypeScript | 669 ms | ±1.03% | 631 ms | 867 ms | 6.48× slower |
| typescript-eslint | 1,030 ms | ±1.87% | 940 ms | 1,456 ms | 9.96× slower |

### [Excalidraw](https://github.com/excalidraw/excalidraw/tree/1919728724a1b71af73cb7e6d2d1a418a1415b1c)

618 files · 7.6 MB · declarations, JavaScript, TypeScript, TSX

![Bar chart of the time each analyzer takes on Excalidraw](charts/excalidraw.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **82.1 ms** | **±1.36%** | **73.2 ms** | **110 ms** | **baseline** |
| TypeScript | 582 ms | ±1.88% | 552 ms | 875 ms | 7.09× slower |
| typescript-eslint | 863 ms | ±1.96% | 797 ms | 1,164 ms | 10.5× slower |

### [three.js](https://github.com/mrdoob/three.js/tree/157f0885b8428b5ffe8f6f7309b2d6f59faa1497)

755 files · 4.4 MB · JavaScript

![Bar chart of the time each analyzer takes on three.js](charts/three.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **43.8 ms** | **±1.72%** | **35.5 ms** | **82.9 ms** | **baseline** |
| TypeScript | 408 ms | ±1.14% | 388 ms | 589 ms | 9.33× slower |
| typescript-eslint | 431 ms | ±1.22% | 407 ms | 589 ms | 9.86× slower |

### [Vue](https://github.com/vuejs/core/tree/4ab865a848a1da3d10fb674f857e5fff13094644)

473 files · 4.1 MB · declarations, JavaScript, TypeScript

![Bar chart of the time each analyzer takes on Vue](charts/vue.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **57.1 ms** | **±1.11%** | **52.3 ms** | **87.1 ms** | **baseline** |
| TypeScript | 394 ms | ±0.74% | 375 ms | 479 ms | 6.90× slower |
| typescript-eslint | 595 ms | ±1.02% | 550 ms | 726 ms | 10.4× slower |

### [Zod](https://github.com/colinhacks/zod/tree/004d800c9e3cd4c79930f55aa4ad080225b22efd)

332 files · 2.9 MB · TypeScript

![Bar chart of the time each analyzer takes on Zod](charts/zod.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **38.3 ms** | **±1.58%** | **31.5 ms** | **55.3 ms** | **baseline** |
| TypeScript | 263 ms | ±1.06% | 250 ms | 373 ms | 6.86× slower |
| typescript-eslint | 496 ms | ±1.38% | 455 ms | 770 ms | 12.9× slower |

### [date-fns](https://github.com/date-fns/date-fns/tree/717ce0a807ea4c6b540d015b5c408723175b2838)

1,643 files · 2.8 MB · declarations, JavaScript, TypeScript

![Bar chart of the time each analyzer takes on date-fns](charts/date_fns.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **43.5 ms** | **±1.40%** | **33.1 ms** | **117 ms** | **baseline** |
| typescript-eslint | 326 ms | ±1.17% | 310 ms | 474 ms | 7.50× slower |
| TypeScript | 382 ms | ±0.79% | 361 ms | 439 ms | 8.79× slower |

### [Svelte](https://github.com/sveltejs/svelte/tree/020242d6bef059df9ae8c13dc8dbff4c9b31e0ff)

416 files · 1.9 MB · declarations, JavaScript, TypeScript

![Bar chart of the time each analyzer takes on Svelte](charts/svelte.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **25.0 ms** | **±1.42%** | **20.0 ms** | **36.2 ms** | **baseline** |
| typescript-eslint | 244 ms | ±1.20% | 227 ms | 301 ms | 9.76× slower |
| TypeScript | 250 ms | ±0.78% | 237 ms | 289 ms | 9.99× slower |

### [Preact](https://github.com/preactjs/preact/tree/3fcc391adc243d479ab10b4cf70fa609708c9348)

33 files · 0.3 MB · declarations, JavaScript

![Bar chart of the time each analyzer takes on Preact](charts/preact.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **2.3 ms** | **±0.67%** | **2.0 ms** | **5.5 ms** | **baseline** |
| TypeScript | 24.3 ms | ±0.65% | 22.9 ms | 39.1 ms | 10.6× slower |
| typescript-eslint | 40.7 ms | ±1.23% | 35.8 ms | 78.7 ms | 17.8× slower |

## Single files

### [typescript.js](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/typescript.js)

1 file · 7.8 MB · JavaScript

![Bar chart of the time each analyzer takes on typescript.js](charts/typescript_js.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **71.0 ms** | **±3.12%** | **63.8 ms** | **107 ms** | **baseline** |
| TypeScript | 603 ms | ±0.77% | 575 ms | 716 ms | 8.48× slower |
| typescript-eslint | 994 ms | ±1.32% | 914 ms | 1,228 ms | 14.0× slower |

### [checker.ts](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/checker.ts)

1 file · 3.0 MB · TypeScript

![Bar chart of the time each analyzer takes on checker.ts](charts/checker.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **28.1 ms** | **±1.69%** | **23.3 ms** | **46.5 ms** | **baseline** |
| TypeScript | 217 ms | ±0.66% | 202 ms | 234 ms | 7.74× slower |
| typescript-eslint | 325 ms | ±1.37% | 307 ms | 453 ms | 11.6× slower |

### [lib.dom.d.ts](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/lib.dom.d.ts)

1 file · 2.2 MB · declarations

![Bar chart of the time each analyzer takes on lib.dom.d.ts](charts/lib_dom.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **6.8 ms** | **±1.06%** | **6.1 ms** | **20.7 ms** | **baseline** |
| TypeScript | 67.2 ms | ±0.74% | 62.0 ms | 97.1 ms | 9.82× slower |
| typescript-eslint | 146 ms | ±1.60% | 130 ms | 213 ms | 21.3× slower |

### [react.js](https://raw.githubusercontent.com/yuku-toolchain/parser-benchmark-files/refs/heads/main/react.js)

1 file · 0.1 MB · JavaScript

![Bar chart of the time each analyzer takes on react.js](charts/react.svg)

| Analyzer | Median | RME | Min | Max | Relative |
|----------|--------|-----|-----|-----|----------|
| **Yuku** | **0.35 ms** | **±0.19%** | **0.33 ms** | **4.5 ms** | **baseline** |
| TypeScript | 4.3 ms | ±0.79% | 3.9 ms | 24.0 ms | 12.1× slower |
| typescript-eslint | 5.5 ms | ±0.57% | 4.8 ms | 14.1 ms | 15.8× slower |

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
