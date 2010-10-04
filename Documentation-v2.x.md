## General Resources & Beginner Guides

If you are new to Capistrano 2.x please read [[Getting Started|2.x Getting Started]], once you are familiar with the basics you may want to read [[From the beginning|2.x-From-The-Beginning]] which is a much more detailed tutorial.

You may also want to read, and or contribute to the [[Capistrano handbook|http://github.com/leehambley/capistrano-handbook/blob/master/index.markdown]] - an immature document that holds some really useful tips, but needs a lot more work!

 * [[Github Guide to Deploying with Capistrano|http://github.com/guides/deploying-with-capistrano]]

## Frameworks & Tools

* [[Using Capistrano 2.x with Rails 2.x]]
* [[Using Capistrano 2.x with Rails 3.x]]

* [[Using Capistrano 2.x with Bundler|http://github.com/carlhuda/bundler/blob/master/lib/bundler/capistrano.rb]]
* [[Using Capistrano 2.x with RVM|http://rvm.beginrescueend.com/integration/capistrano/]]

## Intermediate Resources

* [[Default Deployment Behaviour|2.x-Default-Deployment-Behaviour]]
* [[Managing `database.yml` Securely|http://www.simonecarletti.com/blog/2009/06/capistrano-and-database-yml/]]
* [[Packaging Recipes|http://matthewtodd.org/2008/04/24/rails-tip-4-writing-capistrano-recipes-to-be-loaded-from-gems.html/]]

## Reference Resources

* [[API Documentation|http://rubydoc.info/github/capistrano/capistrano/master/frames]]
* DSL Documentation
  * [[Action Module|2.x-DSL-Documentation-Action-Module]] (`put()`, `get()`, `run()`, `stream()`, `capture()`, etc)
  * [[Configuration Module|2.x-DSL-Documentation-Configuration-Module]] (`namespace()`, `task()`, `set()`, `fetch()`, etc)
* [[Configuration Variables|2.x-Significant-Configuration-Variables]]

## Useful Background Knowledge (3rd Party Articles)

• Unix Shell
  * [[Unix shell skills|http://codex.wordpress.org/UNIX_Shell_Skills]] (Wordpress guide, but very readable for beginners)

* Bash 
  * [[Shell scripting for beginners|http://wiki.bash-hackers.org/scripting/basics]]

* SSH
  * [[Getting Started with SSH|http://kimmo.suominen.com/docs/ssh/]]
  * [[How to use SSH Keys|http://www.sshkeychain.org/mirrors/SSH-with-Keys-HOWTO/]]
  * [[What is an SSH Agent|http://en.wikipedia.org/wiki/Ssh-agent]]
  * [[How SSH Agent Forwarding Works|http://unixwiz.net/techtips/ssh-agent-forwarding.html]]
  * [[What are deploy keys?|http://help.github.com/deploy-keys/]]

## Semi-Official Extensions

  * [[Capistrano Multistage, Deploying to Multiple Environments|2.x Multistage Extension]]
  * [[Rails-less Deploy|http://github.com/leehambley/railsless-deploy/]]

## 3rd Party Extensions

  * [[capistrano-offroad|http://rubygems.org/gems/capistrano-offroad]] (For deploying non-rails apps, specially Django)
  * [[capistrano_winrm|http://github.com/zenchild/capistrano_winrm]] Run commands against MS Windows servers with WinRM

## 3rd Party Tutorials

* Testing
  * [[Testing Capistrano with Cucumber|http://pivotallabs.com/users/jdean/blog/articles/763-testing-capistrano-recipes-with-cucumber]]
* Other Software Packages
  * [[Drupal|http://tempe.st/2008/07/deploying-drupal-with-capistrano/]] 
  * Wordpress
    * [[http://github.com/jestro/wordpress-capistrano/tree/master]]
    * [[http://whomwah.com/2006/05/21/deploying-wordpress-using-capistrano/]]
    * [[http://devblog.imedo.de/2008/6/23/wordpress-deployment-with-capistrano-2-and-git]]
* Other Languages / Frameworks
  * PHP
    * [[http://mathew-davies.co.uk/2009/10/28/php-deployment.html]]
    * [[http://hivelogic.com/articles/view/deploying-expressionengine-github-capistrano]]
  * [[Any Non-Rails Project|http://github.com/leehambley/railsless-deploy/]]

## Seeking Assistance

Help first and foremost via the [[Capistrano Google Group|http://groups.google.com/group/capistrano]]. Community support is also also often available in [[#Capistrano on freenode||irc://irc.freenode.org/capistrano]].

There are extensive archives of questions and answers also at [[stackoverflow.com, tagged #capistrano|http://stackoverflow.com/questions/tagged/capistrano]].

For bugs and problems please open an issue in the [[lighthouse project tracker|http://capistrano.lighthouseapp.com/]] - preferably with a patch, test-case, or steps-to-reproduce. Pull requests on Github will be ignored without a corresponding ticket, as there is no history of changes or forum for discussion without submitting a ticket.