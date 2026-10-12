# BenchCommons

Open benchmarks, methodologies and tools. Every benchmark here is reproducible: the code, the inputs, the pinned versions and the raw results are public.

## Repositories by role

**Catalogs** (`catalog-*`): the implementations that are measured.

| Repository | What it is |
|---|---|
| [catalog-ssg](https://github.com/BenchCommons/catalog-ssg) | 63 static site generators in 20 languages. Each one has a pinned Dockerfile, a canonical `build.sh`, the reference site and metadata in `generators.json`. |
| [catalog-algorithms](https://github.com/BenchCommons/catalog-algorithms) | Classic algorithms implemented in hundreds of languages. It started as Hello World in 452 languages, and 83% of them are run in CI. |
| [catalog-web-frameworks](https://github.com/BenchCommons/catalog-web-frameworks) | Web framework implementations. It continues the archived TechEmpower Framework Benchmarks. |

**Datasets** (`dataset-*`): inputs for the benchmarks.

| Repository | What it is |
|---|---|
| [dataset-names](https://github.com/BenchCommons/dataset-names) | Given names and surnames worldwide, with country, frequency, gender and script, from openly licensed official sources. |
| [dataset-commons](https://github.com/BenchCommons/dataset-commons) | Small shared datasets (texts, graphs, numbers) used by several catalogs. |

**Tools** (`tools-*`, plus perfratio)

| Repository | What it is |
|---|---|
| [tools-benchmark](https://github.com/BenchCommons/tools-benchmark) | Builds each catalog implementation in Docker, runs it and records reproducible results. Today it runs **SSGBerk**, the static site generator benchmark. |
| [perfratio](https://github.com/BenchCommons/perfratio) | A command-line benchmarking tool in Rust, built on hyperfine. It measures time, CPU, peak memory and RAPL energy, with in-depth statistics. |
| [tools-dataset](https://github.com/BenchCommons/tools-dataset) | Builds, validates and exports the datasets as pinned, checksummed inputs. |
| [tools-commons](https://github.com/BenchCommons/tools-commons) | Shared libraries and utilities used by the tools: contract checkers and common CLI helpers. |

**Sites**: [website-results](https://github.com/BenchCommons/website-results) (benchmark results) and [website-perfratio](https://github.com/BenchCommons/website-perfratio).

**Governance**:
- [.github](https://github.com/BenchCommons/.github): community files, templates, shared workflows and the AI agent rules.
- [.product](https://github.com/BenchCommons/.product): roadmap, cross-repo decisions and contracts.

## Run a benchmark

```sh
git clone --recurse-submodules https://github.com/BenchCommons/tools-benchmark.git
cd tools-benchmark
./ssgberk --test hugo -nf 50          # one generator, 50 pages
./ssgberk --suite P --quality         # the small suite with the output audit
```

The methodology, suites and results format are specified in [`tools-benchmark/docs/specs`](https://github.com/BenchCommons/tools-benchmark/tree/master/docs/specs).

## Contributing

Read [CONTRIBUTING](https://github.com/BenchCommons/.github/blob/main/CONTRIBUTING.md). To add a generator, follow [How to add a generator](https://github.com/BenchCommons/catalog-ssg#how-to-add-a-generator). Issues and pull requests are welcome in each repository.
