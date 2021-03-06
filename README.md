# openneuro-py

A Python client for accessing [OpenNeuro](https://openneuro.org)
datasets.

![openneuro-py in action](openneuro-py.gif)

## Installation

### via conda

```shell
conda install -c conda-forge openneuro-py
```

### via pip

```shell
pip install openneuro-py
```

## Basic usage

### Download an entire dataset

```shell
openneuro-py download --dataset=ds000246
```

### Specify a target directory

To store the downloaded files in a specific directory, use the
`--target_dir` switch. The directory will be created if it doesn't exist
already.

```shell
openneuro-py download --dataset=ds000246 \
                      --target_dir=data/bids
```

### Continue an interrupted download

Interrupted downloads will resume where they left off when you run the command
again.

## Advanced usage
### Exclude a directory from the download

```shell
openneuro-py download --dataset=ds000246 \
                      --exclude=sub-emptyroom
```

### Download only a single file

```shell
openneuro-py download --dataset=ds000246 \
                      --include=sub-0001/meg/sub-0001_coordsystem.json
```

Note that a few essential BIDS files are **always** downloaded in addition.

### Download or exclude multiple files

`--include` and `--exclude` can be passed mulitple times:

```shell
openneuro-py download --dataset=ds000246 \
                      --include=sub-0001/meg/sub-0001_coordsystem.json \
                      --include=sub-0001/meg/sub-0001_acq-LPA_photo.jpg
```
