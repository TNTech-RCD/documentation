## Time Limits By Partition

Each job on the cluster has a time limit, which determines the 
maximum amount of time it is allowed to run. Below are the 
default and maximum time limits you can specify for each partition.
 
_The formats below read as `days-hours:minutes:seconds`._

| Partition       | Default Time Limit | Maximum Time Limit |
|-----------------|--------------------|--------------------|
| batch-impulse   | 1-00:00:00         | 7-00:00:00         |
| batch-warp      | 1-00:00:00         | 7-00:00:00         |
| gpu-warp        | 1-00:00:00         | 7-00:00:00         |
| any-interactive | 02:00:00           | 04:00:00           |
| interactive     | 02:00:00           | 04:00:00           |
| gpu-interactive | 02:00:00           | 04:00:00           |
| bigmem          | 1-00:00:00         | 7-00:00:00         |
| hugemem         | 1-00:00:00         | 7-00:00:00         |
| debug           | 00:30:00           | 00:30:00           |
| gpu-debug       | 00:30:00           | 00:30:00           |

: Partition Time Limits {.table .table-striped}


## My Job Exceeded the Time Limit

If your job reports a `TIMEOUT` state, your job has been prematurely stopped because your
allocated time ran out. By default, interactive jobs allocate 2 hours, and batch jobs
allocate 24 hours.

To specify a new time limit, use the `--time` SLURM directive:

```
--time=02:00:00   # For 2 hours
--time=04:00:00   # For 4 hours
--time=24:00:00   # For 24 hours
--time=1-00:00:00 # For 1 day
```

_Note that there are maximum time limits imposed depending on your
partition. See the section above._
