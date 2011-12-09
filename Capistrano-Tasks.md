# Task Listing

To get a list of the Capistrano tasks in a project, use `cap -T`. If you would like to see all the tasks (e.g. ones without descriptions or internal tasks), you can use `cap -vT`. To see more detail on an individual task, you can use `cap -e taskname`.

# Deploy Tasks

# Database Tasks

# Logging Tasks

## logging:tail_log

OVERVIEW:

```unix
------------------------------------------------------------
cap logging:tail_log
------------------------------------------------------------
Tail log.
```

USAGE:

`cap production logging:tail_log`

LIFECYCLE: 

This task does not run before or after other tasks.