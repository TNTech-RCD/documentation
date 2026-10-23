## Time Limits By Partition

Each job on the cluster has a time limit associated
with it, deciding the maximum amount of time it is allowed to
run. Below you will find the time limit set if not specified
(the default time limit) and the maximum time limit you can
specify for your requested partition.

| Partition       | Default Time Limit | Maximum Time Limit |
|-----------------|--------------------|--------------------|
| batch-impulse   | 1-00:00:00         | 7-00:00:00         |
| batch-warp      | 1-00:00:00         | 7-00:00:00         |
| any-interactive | 02:00:00           | 04:00:00           |
| interactive     | 02:00:00           | 04:00:00           |
| gpu-interactive | 02:00:00           | 04:00:00           |
| bigmem          | 1-00:00:00         | 7-00:00:00         |
| hugemem         | 1-00:00:00         | 7-00:00:00         |

_The formats above read as `days-hours:minutes:seconds`._

## My Job Exceeded the Time Limit

If your job reports a 'TIMEOUT' state, your job has been prematurely stopped because your
allocated time ran out. By default, interactive jobs allocate 2 hours, and batch jobs
allocate 24 hours.

To specify a new time limit, use the '--time' SLURM directive:

```
--time=00:02:00   # For 2 hours
--time=00:04:00   # For 4 hours
--time=00:24:00   # For 24 hours
--time=1-00:00:00 # For 1 day
```

_Note that there are maximum time limits imposed depending on your
partition. See the section above._
