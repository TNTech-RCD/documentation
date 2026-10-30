## Available GPU Resources

Below is the available GPU resources we offer per partition.
To get the total available GPUs in a partition, multiply
the available GPUs per node by the amount of available nodes.

Note that `batch-warp` and `any-interactive` will redirect to
`gpu-warp` and `gpu-interactive` if a GPU is allocated, respectively.

| Partition       | Avalable GPUs per node | Available nodes | GPU type |
| --------------- | ---------------------- | --------------- | -------- |
| gpu-warp        | 2                      | 10              | a100     |
| gpu-interactive | 2                      | 2               | a100     |

: GPU Allocation Limits {.table .table-striped}

To manipulate your job's GPU allocation, you can use any of the following:

```
--gpus=1
```

```
--gpus-per-task=1
```

```
--gpus-per-cpu=1
```

To specify a particular GPU type, you can use the following format:

```
--gpus=a100:1 # For an a100 GPU
```

_Note: At the time of writing, the only GPU type we support is the
[Nvidia A100 40GB](https://www.nvidia.com/content/dam/en-zz/Solutions/Data-Center/a100/pdf/nvidia-a100-datasheet-us-nvidia-1758950-r4-web.pdf)
GPU._

## Low GPU Usage

Whenever a job that uses a GPU spends only a small portion of
its time actually using that resource, you may be faced with
this message:

```
The overall GPU utilization of this job is only 5%.
This value is low compared to the cluster mean value of 50%. Please
investigate the reason for the low utilization.
```

There are a few potential scenarios that could be limiting your job's time
with the GPU:

1. Your job runs more on a CPU than on a GPU.
   If you find this to be the case, consider breaking your job into
   smaller ones, separating CPU-based and GPU-work into
   more granular jobs.

2. Your job is simply unable to fill a GPU.
   When you request a GPU, you get the entire GPU,
   even if your job only requires a portion of that
   GPU to do its work. It is worth noting that
   even if this is the case, there are still may be
   other, less obvious bottlenecks as to why your job is
   not effectively using its resources.

Regardless of which scenario you find yourelf in, you can
get help with diagnosing and working to solve your
resource usage issues by scheduling a meeting
with us at <https://www.rcd.tntech.edu/bookings/>.

## Zero GPU Usage

There are times where you may find this message after running
a job where a GPU has been allocated:

```
This job did not use the GPU. Please resolve this
before running additional jobs. Wasting resources
will cause your subsequent jobs to have a lower priority.
Is the code GPU-enabled?
Please consult the documentation for the software.
```

This means that even though your job has been specified to
use GPU resources, your program never wound up using a
GPU resource.

If this is the case but you are sure your program can
use a GPU, it would likely be in your best interest to
read the documentation for when and how your program uses
one. If you are having trouble with this process, feel free
to schedule a meeting with us at <https://www.rcd.tntech.edu/bookings/>.
We would be more than happy to help out!
