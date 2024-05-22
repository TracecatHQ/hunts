# Threat Hunting with Polars

[![Made with Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?logo=Jupyter)](https://jupyter.org/try)
[![nbviewer](https://raw.githubusercontent.com/jupyter/design/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.org/github/TracecatHQ/hunts/blob/main/notebooks/aws_flaws.ipynb)
[![Polars](https://img.shields.io/badge/polars-%23DDD6FE.svg?logo=polars&logoColor=black)](https://github.com/pola-rs/polars)
[![Discord](https://img.shields.io/discord/1212548097624903681.svg?logo=discord&logoColor=white)](https://discord.gg/AqWkW8gJzM)

Threat hunting with [Polars](https://github.com/pola-rs/polars) and [flaws.cloud](https://summitroute.com/blog/2020/10/09/public_dataset_of_cloudtrail_logs_from_flaws_cloud/) AWS CloudTrail datasets.
Check out threat hunting notebook in [`nbviewer`](https://nbviewer.org/github/TracecatHQ/hunts/blob/main/notebooks/aws_flaws.ipynb) or rerun the hunt yourself in Jupyter lab.

## Motivation

Polars is a OLAP query engine written in Rust. It's highly memory efficient, uses Apache Arrow as its memory model, and consistently tops [database speed benchmarks](https://pola.rs/posts/benchmarks/) against distributed OLAP engines e.g. PySpark and Snowflake.

At [Tracecat](https://tracecat.com/), we use Polars as an alternative to `jq` or `grep` for quick-and-dirty threat hunting.

## Why Polars for log analysis?

- Ridiculously fast and efficient [string operations](https://pola.rs/posts/polars-string-type/)
- [Piped query language](https://docs.pola.rs/user-guide/concepts/expressions/)
- Highly parallelized [window operations](https://docs.pola.rs/user-guide/expressions/window/)
- Powerful aggregation functions to compute metrics
- Small binary with zero dependencies (~70ms import time)

If your logs fit in memory and you are using Python / Jupyter Notebooks as part of your threat hunting process, Polars should be your goto tool for threat hunting.

Note: for every 1GB of gzipped JSON logs on disk, you can expect Polars in-memory data model to take up approximately ~500MB of RAM.

## Getting Started

### Prerequisites

Requires `python>3.9`, `pip`, and `git lfs` to be installed.s

First clone the repository and download datasets from git lfs (large file system).

```bash
git clone git@github.com:TracecatHQ/hunts.git
cd hunts
git lfs fetch
git lfs pull
```

Create a new python environment using `pip` or `conda` (optional), then install the required dependencies via `pip install -r requirements.txt`.

Finally, spin up Jupyter lab using `jupyter lab` to view the `aws_flaws.ipynb` and `aws_flaws_2.ipynb` notebooks inside the `notebooks` directory.

## Contact Us

Interested in our work bringing low-cost, but powerful data engineering tools to cybersecurity? We'd love to hear your thoughts over email [founders@tracecat.com](mailto:founders@tracecat.com) or find us in the Tracecat [Discord community](https://discord.gg/AqWkW8gJzM)!

## License

[MIT License](LICENSE)
