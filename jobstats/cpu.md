## Low CPU Usage

Sometimes jobstats will report this message:

```
The overall CPU utilization of this job is 40%. This value
is low compared to the target range of
90% and above. Please investigate the reason for the low efficiency.
For instance, have you conducted a scaling analysis?
```

This can occur when your job may not be effectively using all of the CPUs
in your allocation. According to [Ahmdal's Law](https://en.wikipedia.org/wiki/Amdahl's_law),
adding more CPUs to a problem provides diminishing returns in the amount of speedup
gained. Oftentimes, it is beneficial to find a sweet spot of CPU allocation
that results in the highest amount of overall CPU utilization.

If you find yourself with this message, you can reduce your allocated cpus with
a combination of the `--ntasks` and `--cpus-per-task` parameters.

```bash
--ntasks=1 # Use 1 task
--cpus-per-task=16 # The one task uses 16 cpus
# This configuration results in 16 total cpus
```

```bash
--ntasks=4 # Use 4 tasks
--cpus-per-task=2 # Each task uses 2 cpus
# This configuration results in 8 total cpus
```

In lowering the amount of requested resources, you will find your jobs have
an easier time starting earlier, have more opportunities to run in general,
and others' jobs will have more opportunities to be scheduled.


## Zero CPU Usage on Multiple Nodes

If you view the jobstats output of a job, you may find a message like this:

```
This job did not use 1 of the 2 allocated
nodes. Please resolve this before running additional jobs. Please
consult the documentation for the software.
```

This indicates your job has not been configured to run across multiple
nodes. Oftentimes, it is not possible to for a program to use multiple
nodes in this way. If this is the case, you can adjust your allocation
parameters to specify one node and one node only.

```bash
--nodes=1 # Allocate one node only
```

In lowering the amount of requested resources, you will find your jobs have
an easier time starting earlier, have more opportunities to run in general,
and others' jobs will have more opportunities to be scheduled.

If you are sure your job can run across multiple nodes, but for
whatever reason it is not, feel free to schedule a meeting with us
at <https://www.rcd.tntech.edu/bookings/>.
We are happy to help diagnose issues like this!
