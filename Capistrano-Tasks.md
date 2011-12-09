# Task Listing

To get a list of the Capistrano tasks in a project, use `cap -T`. If you would like to see all the tasks (e.g. ones without descriptions or internal tasks), you can use `cap -vT`. To see more detail on an individual task, you can use `cap -e taskname`.

# Deploy Tasks

# Database Tasks

## db:backup

OVERVIEW:

```unix
------------------------------------------------------------
cap db:backup
------------------------------------------------------------
Backup the remote database.
```

USAGE:

LIFECYCLE: 

This task does not run before or after other tasks.

## db:export

OVERVIEW:

```unix
------------------------------------------------------------
cap db:export
------------------------------------------------------------
Export the remote database to a named file on the local system.
```

USAGE:

LIFECYCLE:

This task does not run before or after other tasks.

## db:import

OVERVIEW:

```
------------------------------------------------------------
cap db:import
------------------------------------------------------------
Import a named file into the database on the remote system.
```

USAGE:

LIFECYCLE:

This task does not run before or after other tasks.

## db:load_config

OVERVIEW

```
------------------------------------------------------------
cap db:load_config
------------------------------------------------------------
There is no description for this task.
```

USAGE:

LIFECYCLE:

## db:restore

OVERVIEW:

```
------------------------------------------------------------
cap db:restore
------------------------------------------------------------
Restore database from backup.
```

USAGE:

LIFECYCLE:

## db:sync_development

OVERVIEW:
```
------------------------------------------------------------
cap db:sync_development
------------------------------------------------------------
Sync the local development database from the target rails_env.
```

USAGE:

LIFECYCLE:
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