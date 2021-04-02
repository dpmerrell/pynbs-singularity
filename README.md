# pynbs-singularity

A singularity container recipe for the [PyNBS](https://github.com/idekerlab/pyNBS) method.

## Usage

The container's `runscript` exposes a subset of [pyNBS's command line interface](https://github.com/idekerlab/pyNBS/wiki/pyNBS-Command-Line-Manual).

(For now we exclude plotting due to unresolved Matplotlib compatibility issues.)

For example, you can use the container to run pyNBS in your terminal like this:
```
$ ./pynbs-singularity.simg --help
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
