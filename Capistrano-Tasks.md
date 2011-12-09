# Task Listing

To get a list of the Capistrano tasks in a project, use `cap -T`. If you would like to see all the tasks (e.g. ones without descriptions or internal tasks), you can use `cap -vT`. To see more detail on an individual task, you can use `cap -e taskname`.

# Deploy Tasks

## deploy

OVERVIEW:
```
------------------------------------------------------------
cap deploy
------------------------------------------------------------
Deploys your project. This calls both `update' and `restart'. Note that this
will generally only work for applications that have already been deployed once.
For a "cold" deploy, you'll want to take a look at the `deploy:cold' task, which
handles the cold start specifically.
```

USAGE:

LIFECYCLE:

## deploy:check

OVERVIEW:
```
------------------------------------------------------------
cap deploy:check
------------------------------------------------------------
Test deployment dependencies. Checks things like directory permissions,
necessary utilities, and so forth, reporting on the things that appear to be
incorrect or missing. This is good for making sure a deploy has a chance of
working before you actually run `cap deploy'.

You can define your own dependencies, as well, using the `depend' method:

  depend :remote, :gem, "tzinfo", ">=0.3.3"
  depend :local, :command, "svn"
  depend :remote, :directory, "/u/depot/files"
```

USAGE:

LIFECYCLE:

 
# Database Tasks

## db:backup

OVERVIEW:

```
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

```
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

```
------------------------------------------------------------
cap logging:tail_log
------------------------------------------------------------
Tail log.
```

USAGE:

`cap production logging:tail_log`

LIFECYCLE: 

This task does not run before or after other tasks.