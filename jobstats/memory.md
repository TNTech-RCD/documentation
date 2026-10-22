## CPU Memory

Occasionally, errors like this can occur that prematurely cancel your job:

```
[2026-10-22T09:27:41.161] error: Detected 1 oom_kill event in StepId=657111.interactive. Some of the step tasks have been OOM Killed.
srun: error: gpunode003: task 0: Out Of Memory
salloc: Relinquishing job allocation 657111
```

This means your job used more RAM than you had requested. By default, you are given 2 GB per CPU core requested with SLURM.
_If your job needs more or less than this default, you must explicitly provide it in your resource request._

For example, you can provide the following SLURM directives:

```
--mem-per-cpu=8G   # cpu memory per cpu-core
```

```
--mem=2G           # cpu memory per node
```

```
--mem-per-gpu=48G  # cpu memory per gpu
```

It is important to request accurate amounts of memory for your jobs. Excessive memory allocations will generally
result in longer queuing times.
