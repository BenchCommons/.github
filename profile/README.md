# Benchmarks Commons

Open benchmarks, methodologies and tools for the web. Every benchmark here is reproducible: the code, the inputs, the pinned versions and the raw results are public.

## Projects

| Repository | What it is |
|---|---|
| [benchmark-tool](https://github.com/BenchCommons/benchmark-tool) | The toolset behind **SSGBerk**, the static site generator benchmark. It builds the same reference site with every generator in Docker, times cold builds, and records wall time, CPU, peak RSS and output size. It also audits the output with Lighthouse, axe, html-validate and lychee. Suites P, M, G and GG cover 50 to 100,000 pages. |
| [ssg-frameworks](https://github.com/BenchCommons/ssg-frameworks) | The generators SSGBerk measures: 63 static site generators in 20 languages. Each one has a pinned Dockerfile, a canonical `build.sh`, the reference site and its metadata in `generators.json`. |
| [perfratio](https://github.com/BenchCommons/perfratio) | A command-line benchmarking tool in Rust, built on hyperfine. It adds hardware performance counters, RAPL energy (joules and watts), peak memory and bootstrapped confidence intervals. |
| [professor-website-exemple](https://github.com/BenchCommons/professor-website-exemple) | A Jekyll example site: a multilingual CV for a fictional professor. |

## Run a benchmark

```sh
git clone --recurse-submodules https://github.com/BenchCommons/benchmark-tool.git
cd benchmark-tool
./ssgberk --test hugo -nf 50          # one generator, 50 pages
./ssgberk --suite P --quality         # the small suite with the output audit
```

The methodology, the suites and the results format are specified in [`benchmark-tool/docs/specs`](https://github.com/BenchCommons/benchmark-tool/tree/master/docs/specs). Results of each round are in [`docs/results`](https://github.com/BenchCommons/benchmark-tool/tree/master/docs/results).

## Contributing

To add a generator, follow [How to add a generator](https://github.com/BenchCommons/ssg-frameworks#how-to-add-a-generator). Issues and pull requests are welcome in each repository.
