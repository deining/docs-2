---
sidebar_position: 2
description: How to run the mergestat-lite CLI locally.
---

# Usage

Running:

```bash
mergestat -h
```

Will output the most up to date usage instructions for your version of the CLI.
Typically the first argument is a SQL query string:

```bash
mergestat "SELECT * FROM commits"
```

Your current working directory will be used as the path to the git repository to query by default.
Use the `--repo` flag to specify an alternate path, or even a remote repository reference (http(s) or ssh).
MergeStat Lite will clone the remote repository to a temporary directory before executing a query.

You can also pass a query in via `stdin`:

```bash
cat query.sql | mergestat
```

By default, output will be an ASCII table.
Use `--format json` or `--format csv` for alternatives.
Use `-v` to print execution logs to `stderr`.
This can be useful for understanding what API calls a query may be making, or similar runtime information.
See `-h` for all the options.
