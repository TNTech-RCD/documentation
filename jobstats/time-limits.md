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

_Note that there are time limits imposed on our partitions. See <KB Article> for more._

##
