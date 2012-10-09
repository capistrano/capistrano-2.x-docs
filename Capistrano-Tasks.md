# Task Listing

To get a list of the Capistrano tasks in a project, use `cap -T`. If you would like to see all the tasks (e.g. ones without descriptions or internal tasks), you can use `cap -vT`. To see more detail on an individual task, you can use `cap -e taskname`.

The following tasks should be valid as of Capistrano v2.8.0.

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

## deploy:cleanup

OVERVIEW:
```
------------------------------------------------------------
cap deploy:cleanup
------------------------------------------------------------
Clean up old releases. By default, the last 5 releases are kept on each server
(though you can change this with the keep_releases variable). All other deployed
revisions are removed from the servers. By default, this will use sudo to clean
up the old releases, but if sudo is not available for your environment, set the
:use_sudo variable to false instead.
```

USAGE:

LIFECYCLE:

## deploy:cold

OVERVIEW:
```
------------------------------------------------------------
cap deploy:cold
------------------------------------------------------------
Deploys and starts a 'cold' application. This is useful if you have not deployed
your application before, or if your application is (for some other reason) not
currently running. It will deploy the code, run any pending migrations, and then
instead of invoking 'deploy:restart', it will invoke 'deploy:start' to fire up
the application servers.
```

USAGE:

LIFECYCLE:

## deploy:finalize_update

OVERVIEW:
```
------------------------------------------------------------
cap deploy:finalize_update
------------------------------------------------------------
[internal] Touches up the released code. This is called by update_code after the
basic deploy finishes. It assumes a Rails project was deployed, so if you are
deploying something else, you may want to override this task with your own
environment's requirements.

This task will make the release group-writable (if the :group_writable variable
is set to true, which is the default). It will then set up symlinks to the
shared directory for the log, system, and tmp/pids directories, and will lastly
touch all assets in public/images, public/stylesheets, and public/javascripts so
that the times are consistent (so that asset timestamping works).  This touch
process is only carried out if the :normalize_asset_timestamps variable is set
to true, which is the default The asset directories can be overridden using the
:public_children variable.
```

USAGE:

LIFECYCLE:

## deploy:graceful_stop

OVERVIEW:
```
------------------------------------------------------------
cap deploy:graceful_stop
------------------------------------------------------------
There is no description for this task.
```

USAGE:

LIFECYCLE:

## deploy:migrate

OVERVIEW:
```
------------------------------------------------------------
cap deploy:migrate
------------------------------------------------------------
Run the migrate rake task. By default, it runs this in most recently deployed
version of the app. However, you can specify a different release via the
migrate_target variable, which must be one of :latest (for the default
behavior), or :current (for the release indicated by the `current' symlink).
Strings will work for those values instead of symbols, too. You can also specify
additional environment variables to pass to rake via the migrate_env variable.
Finally, you can specify the full path to the rake executable by setting the
rake variable. The defaults are:

  set :rake,           "rake"
  set :rails_env,      "production"
  set :migrate_env,    ""
  set :migrate_target, :latest
```

USAGE:

LIFECYCLE:

## deploy:migrations

OVERVIEW:
```
------------------------------------------------------------
cap deploy:migrations
------------------------------------------------------------
Deploy and run pending migrations. This will work similarly to the `deploy'
task, but will also run any pending migrations (via the `deploy:migrate' task)
prior to updating the symlink. Note that the update in this case it is not
atomic, and transactions are not used, because migrations are not guaranteed to
be reversible.
```

USAGE:

LIFECYCLE:

## deploy:pending

OVERVIEW:
```
------------------------------------------------------------
cap deploy:pending
------------------------------------------------------------
Displays the commits since your last deploy. This is good for a summary of the
changes that have occurred since the last deploy. Note that this might not be
supported on all SCM's.
```

USAGE:

LIFECYCLE:

## deploy:pending:diff

OVERVIEW:
```
------------------------------------------------------------
cap deploy:pending:diff
------------------------------------------------------------
Displays the `diff' since your last deploy. This is useful if you want to
examine what changes are about to be deployed. Note that this might not be
supported on all SCM's.
```

USAGE:

LIFECYCLE:

## deploy:precompile_assets

OVERVIEW:
```
------------------------------------------------------------
cap deploy:precompile_assets
------------------------------------------------------------
Compile all assets
```

USAGE:

LIFECYCLE:

## deploy:reload

OVERVIEW:
```
------------------------------------------------------------
cap deploy:reload
------------------------------------------------------------
There is no description for this task.
```

USAGE:

LIFECYCLE:

## deploy:restart

OVERVIEW:
```
------------------------------------------------------------
cap deploy:restart
------------------------------------------------------------
There is no description for this task.
```

USAGE:

LIFECYCLE:

## deploy:rollback

OVERVIEW:
```
------------------------------------------------------------
cap deploy:rollback
------------------------------------------------------------
Rolls back to a previous version and restarts. This is handy if you ever
discover that you've deployed a lemon; `cap rollback' and you're right back
where you were, on the previously deployed version.
```

USAGE:

LIFECYCLE:

## deploy:rollback:cleanup

OVERVIEW:
```
------------------------------------------------------------
cap deploy:rollback:cleanup
------------------------------------------------------------
[internal] Removes the most recently deployed release.
This is called by the rollback sequence, and should rarely
(if ever) need to be called directly.
```

USAGE:

LIFECYCLE:

## deploy:rollback:code

OVERVIEW:
```
------------------------------------------------------------
cap deploy:rollback:code
------------------------------------------------------------
Rolls back to the previously deployed version. The `current' symlink will be
updated to point at the previously deployed version, and then the current
release will be removed from the servers. You'll generally want to call
`rollback' instead, as it performs a `restart' as well.
```

USAGE:

LIFECYCLE:

## deploy:rollback:revision

OVERVIEW:
```
------------------------------------------------------------
cap deploy:rollback:revision
------------------------------------------------------------
[internal] Points the current symlink at the previous revision.
This is called by the rollback sequence, and should rarely (if
ever) need to be called directly.
```

USAGE:

LIFECYCLE:

## deploy:setup

OVERVIEW:

```
------------------------------------------------------------
cap deploy:setup
------------------------------------------------------------
Prepares one or more servers for deployment. Before you can use any of the
Capistrano deployment tasks with your project, you will need to make sure all of
your servers have been prepared with `cap deploy:setup'. When you add a new
server to your cluster, you can easily run the setup task on just that server by
specifying the HOSTS environment variable:

  $ cap HOSTS=new.server.com deploy:setup

It is safe to run this task on servers that have already been set up; it will
not destroy any deployed revisions or data.
```

USAGE:

LIFECYCLE:

## deploy:start

OVERVIEW:
```
------------------------------------------------------------
cap deploy:start
------------------------------------------------------------
There is no description for this task.
```

USAGE:

LIFECYCLE:

## deploy:stop

OVERVIEW:
```
------------------------------------------------------------
cap deploy:stop
------------------------------------------------------------
There is no description for this task.
```

USAGE:

LIFECYCLE:

## deploy:create_symlink

OVERVIEW:
```
------------------------------------------------------------
cap deploy:create_symlink
------------------------------------------------------------
Note: This used to be deploy:symlink. It was renamed in version 2.10.0 to 
deploy:create_symlink because of bad namespacing between rake 0.9.x and 
capistrano.
Updates the symlink to the most recently deployed version. Capistrano works by
putting each new release of your application in its own directory. When you
deploy a new version, this task's job is to update the `current' symlink to
point at the new version. You will rarely need to call this task directly;
instead, use the `deploy' task (which performs a complete deploy, including
`restart') or the 'update' task (which does everything except `restart').
```

USAGE:

LIFECYCLE:

## deploy:update

OVERVIEW:
```
------------------------------------------------------------
cap deploy:update
------------------------------------------------------------
Copies your project and updates the symlink. It does this in a transaction, so
that if either `update_code' or `symlink' fail, all changes made to the remote
servers will be rolled back, leaving your system in the same state it was in
before `update' was invoked. Usually, you will want to call `deploy' instead of
`update', but `update' can be handy if you want to deploy, but not immediately
restart your application.
```

USAGE:

LIFECYCLE:

## deploy:update_code

OVERVIEW:
```
------------------------------------------------------------
cap deploy:update_code
------------------------------------------------------------
Copies your project to the remote servers. This is the first stage of any
deployment; moving your updated code and assets to the deployment servers. You
will rarely call this task directly, however; instead, you should call the
`deploy' task (to do a complete deploy) or the `update' task (if you want to
perform the `restart' task separately).

You will need to make sure you set the :scm variable to the source control
software you are using (it defaults to :subversion), and the :deploy_via
variable to the strategy you want to use to deploy (it defaults to :checkout).
```

USAGE:

LIFECYCLE:

## deploy:upload

OVERVIEW:
```
------------------------------------------------------------
cap deploy:upload
------------------------------------------------------------
Copy files to the currently deployed version. This is useful for updating files
piecemeal, such as when you need to quickly deploy only a single file. Some
files, such as updated templates, images, or stylesheets, might not require a
full deploy, and especially in emergency situations it can be handy to just push
the updates to production, quickly.

To use this task, specify the files and directories you want to copy as a
comma-delimited list in the FILES environment variable. All directories will be
processed recursively, with all files being pushed to the deployment servers.

  $ cap deploy:upload FILES=templates,controller.rb

Dir globs are also supported:

  $ cap deploy:upload FILES='config/apache/*.conf'
```

USAGE:

LIFECYCLE:

## deploy:web:disable

OVERVIEW:
```
------------------------------------------------------------
cap deploy:web:disable
------------------------------------------------------------
Present a maintenance page to visitors. Disables your application's web
interface by writing a "maintenance.html" file to each web server. The servers
must be configured to detect the presence of this file, and if it is present,
always display it instead of performing the request.

By default, the maintenance page will just say the site is down for
"maintenance", and will be back "shortly", but you can customize the page by
specifying the REASON and UNTIL environment variables:

  $ cap deploy:web:disable \
        REASON="hardware upgrade" \
        UNTIL="12pm Central Time"

Further customization will require that you write your own task.
```

USAGE:

LIFECYCLE:

## deploy:web:enable

OVERVIEW:
```
------------------------------------------------------------
cap deploy:web:enable
------------------------------------------------------------
Makes the application web-accessible again. Removes the "maintenance.html" page
generated by deploy:web:disable, which (if your web servers are configured
correctly) will make your application web-accessible again.
```

USAGE:

LIFECYCLE:
 
# Database Tasks (note: these tasks may not be present; check with `cap -T`)

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

# Utility Tasks

## invoke

OVERVIEW:
```
------------------------------------------------------------
cap invoke
------------------------------------------------------------
Invoke a single command on the remote servers. This is useful for performing
one-off commands that may not require a full task to be written for them. Simply
specify the command to execute via the COMMAND environment variable. To execute
the command only on certain roles, specify the ROLES environment variable as a
comma-delimited list of role names. Alternatively, you can specify the HOSTS
environment variable as a comma-delimited list of hostnames to execute the task
on those hosts, explicitly. Lastly, if you want to execute the command via sudo,
specify a non-empty value for the SUDO environment variable.

Sample usage:

  $ cap COMMAND=uptime HOSTS=foo.capistano.test invoke
  $ cap ROLES=app,web SUDO=1 COMMAND="tail -f /var/log/messages" invoke
```

USAGE:

LIFECYCLE:

## shell

OVERVIEW:
```
------------------------------------------------------------
cap shell
------------------------------------------------------------
Begin an interactive Capistrano session. This gives you an interactive terminal
from which to execute tasks and commands on all of your servers. (This is still
an experimental feature, and is subject to change without notice!)

Sample usage:

  $ cap shell
```

USAGE:

LIFECYCLE:
