# pynbs-singularity

A singularity container recipe for the [PyNBS](https://github.com/idekerlab/pyNBS) method.

## How to get the container

You can get the pre-built container from [singularity-hub](https://singularity-hub.org/collections/5334) via `singularity pull`:

`$ singularity pull --name pynbs.simg shub://dpmerrell/pynbs-singularity:latest`

## Usage

The container's `runscript` exposes a subset of [pyNBS's command line interface](https://github.com/idekerlab/pyNBS/wiki/pyNBS-Command-Line-Manual).

For example, you can use the container to run pyNBS in your terminal like this:
```
$ ./pynbs.simg --help
usage: run_pyNBS.py [-h] [-params PARAMS_FILE] [-o OUTDIR] [-j JOB_NAME]
                    [-a ALPHA] [-k K] [-n NITER] [-surv SURVIVAL_DATA]
                    [-t THREADS] [-nv]
                    sm_data_file network_file

Perform network based stratification of tumors by binary somatic mutation
profile on given molecular network. Optional inputs will overrride any
corresponding values set by configuration parameters file (if it is given)

optional arguments:
  -h, --help            show this help message and exit
  -params PARAMS_FILE, --params_file PARAMS_FILE

[etc.]
```

## Other notes

* For now we exclude plotting and survival curves from the CLI. This decision results from package compatibility issues.
* The default build allows pyNBS to use 4 threads. Multithreading is controlled by a few environment variables
  which may be set in the Singularity file:
    - `MKL_NUM_THREADS`
    - `NUMEXPR_NUM_THREADS`
    - `OMP_NUM_THREADS`

## Licensing and attributions

The code in this repository is distributed under an MIT license (c) 2021 David Merrell.

[pyNBS](https://github.com/idekerlab/pyNBS) is distributed under an MIT license (c) 2018 Justin Huang.

The script `run_pyNBS.py` in this repository is modified from the original (c) 2018 Justin Huang.
