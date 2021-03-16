# Usage

`codebench-cli` is a tool that collect the results from your benchmarks and publish them on [codebench.cloud](https://www.codebench.cloud).

To process, you will need the project's `token` to publish the benchmark result.

## Testing on the CI

To do so, you'll need to download the binary available on [our server](https://app.codebench.cloud/static/bin/codebench-cli-amd64).

```bash
# using wget
wget --output-document codebench-cli https://app.codebench.cloud/static/bin/codebench-cli-amd64
# using curl
curl --output codebench-cli https://app.codebench.cloud/static/bin/codebench-cli-amd64
# and then
chmod +x codebench-cli
./codebench-cli --token $CODEBENCH_TOKEN $PATH_TO_REPORT
```

## Testing with criterion

Once you ran your benchmarks with [criterion](https://github.com/bheisler/criterion.rs), a folder `criterion` should be created into the `target` folder.
You can export it by running `codebench-cli --token <your-token> target/criterion` and you should see a message reporting the export was successful.

## Testing with hyperfine

When you will run your benchmarks with [hyperfine](https://github.com/sharkdp/hyperfine/), add the arguments `--export-json hyperfine.json`.
A JSON file containing the report of your benchmark will be created, allowing you to export it.
You can export it by running `codebench-cli --token <your-token> hyperfine.json` and you should see a message reporting the export was successful.

## Testing with something else

We only implement publishers for [criterion](https://github.com/bheisler/criterion.rs) and [hyperfine](https://github.com/sharkdp/hyperfine/).

If you need another publisher, feel free to contact us on [Twitter](https://twitter.com/CodebenchCloud).

