## General Resources & Beginner Guides

If you are new to Capistrano 2.x please read [[Getting Started|2.x Getting Started]]; once you are familiar with the basics, you may want to read [[From the beginning|2.x-From-The-Beginning]] which is a much more detailed tutorial.

You may also want to read and/or contribute to the [[Capistrano handbook|http://github.com/stefanooldeman/capistrano-handbook/blob/master/README.markdown#capistrano-handbook]] - an immature document that holds some really useful tips, but needs a lot more work!

 * [[Github Guide to Deploying with Capistrano|http://help.github.com/deploy-with-capistrano/]]

## Frameworks & Tools

* [[Using Capistrano 2.x with Rails 2.x]]

* [[Using Capistrano 2.x with Bundler|http://gembundler.com/v1.3/deploying.html]]
* [[Using Capistrano 2.x with RVM|http://rvm.io/integration/capistrano/]]

## Intermediate Resources

* [[Default Deployment Behaviour|2.x-Default-Deployment-Behaviour]]
* [[Managing `database.yml` Securely|http://www.simonecarletti.com/blog/2009/06/capistrano-and-database-yml/]]
* [[Packaging Recipes|http://matthewtodd.org/2008/04/24/rails-tip-4-writing-capistrano-recipes-to-be-loaded-from-gems.html/]]
* [[Writing Extensions]]

## Reference Resources

* [[API Documentation|http://rubydoc.info/github/capistrano/capistrano/master/frames]]
* DSL Documentation
  * [[Action Module|2.x-DSL-Documentation-Action-Module]] (`put()`, `get()`, `run()`, `stream()`, `capture()`, etc)
  * [[Configuration Module|2.x-DSL-Documentation-Configuration-Module]] (`namespace()`, `task()`, `set()`, `fetch()`, etc)
* [[Configuration Variables|2.x-Significant-Configuration-Variables]]
* [[Capistrano Tasks]]
* [[Formatting Logs]]
* [[Upgrading to Rails 4]]

## Useful Background Knowledge (3rd Party Articles)

* Unix Shell
  * [[Unix shell skills|http://codex.wordpress.org/UNIX_Shell_Skills]] (Wordpress guide, but very readable for beginners)

* Bash 
  * [[Shell scripting for beginners|http://wiki.bash-hackers.org/scripting/basics]]

* SSH
  * [[Getting Started with SSH|http://kimmo.suominen.com/docs/ssh/]]
  * [[What is an SSH Agent|http://en.wikipedia.org/wiki/Ssh-agent]]
  * [[How SSH Agent Forwarding Works|http://unixwiz.net/techtips/ssh-agent-forwarding.html]]
  * [[What are deploy keys?|http://help.github.com/deploy-keys/]]

## Semi-Official Extensions

  * [[Capistrano Multistage, Deploying to Multiple Environments|2.x Multistage Extension]]
  * [[Rails-less Deploy|http://github.com/leehambley/railsless-deploy/]]

## 3rd Party Extensions

  * [[capistrano-windows-server|http://github.com/SciMed/capistrano-windows-server]] Deploy Rails apps to Windows servers
  * [[capistrano-offroad|http://rubygems.org/gems/capistrano-offroad]] For deploying non-rails apps, specially Django
  * [[capistrano_winrm|http://github.com/zenchild/capistrano_winrm]] Run commands against MS Windows servers with WinRM
  * [[capify-ec2|https://github.com/forward/capify-ec2]] A number of utilities to help with deploying to amazon ec2 instances
  * [[resque_utils|https://github.com/forward/resque_utils]] Helper tasks for remote Resque deployments (requeue & remove failed jobs)
  * [[capistrano-ash|https://github.com/augustash/capistrano-ash]] For deploying Magento, Drupal, WordPress, and Zend/Doctrine apps
  * [[play-capistrano|http://www.playframework.org/modules/capistrano]] For deploying/controlling remote Play Framework apps
  * [[capifony|http://capifony.org/]] For deploying symfony and Symfony2 apps
  * [[capcake|https://github.com/jadb/capcake]] extension of Capistrano, deploy CakePHP apps
  * [[capistrano-chef|https://github.com/cramerdev/capistrano-chef]] Integrates Capistrano with Chef search
  * [[capistrano-puppet|https://github.com/garethr/capistrano-puppet]] Integrates Capistrano with [[Puppet|http://puppetlabs.com/]] 
  * [[capistrano-deploytags|https://github.com/mydrive/capistrano-deploytags]] Track your current and all previous releases with Git tags automatically at deployment time
  * [[cap_git_tools|https://github.com/jrochkind/cap_git_tools]] Another approach to automatically git tagging at deployment, guarding against deploying with uncommitted changes, multi-stage deployment with git, and other git tasks. 
  * [[capistrano-detect-migrations|https://github.com/mydrive/capistrano-detect-migrations]] Automatically discover and warn about pending Rails migrations with Git before you deploy
  * [[capistrano-notifier|https://github.com/cramerdev/capistrano-notifier]] Notify via mail and StatsD when deploying
  * [[capistrano-remote-cache-with-project-root|https://github.com/mcollina/capistrano-remote-cache-with-project-root]] Adds a new deployment strategy to deploy your app from an internal folder (non-root).
  * [[magentify|https://github.com/alistairstead/Magentify]] Deployment recipes customised for deployment of Magento projects.

## 3rd Party Tutorials

* Testing
  * [[Testing Capistrano with Cucumber|http://pivotallabs.com/testing-capistrano-recipes/]]
* Other Software Packages
  * [[Drupal|http://tempe.st/2008/07/deploying-drupal-with-capistrano/]] 
  * Magento
    * [[http://www.designdisclosure.com/2012/04/deploy-magento-with-capistrano/]]
  * Wordpress
    * [[http://github.com/jestro/wordpress-capistrano/tree/master]]
    * [[http://whomwah.com/2006/05/21/deploying-wordpress-using-capistrano/]]
    * [[http://devblog.imedo.de/2008/6/23/wordpress-deployment-with-capistrano-2-and-git]]
    * [[http://www.tractionco.com/blog/95-deploying-wordpress-with-capistrano-and-svn]]
    * [[http://theme.fm/2011/08/tutorial-deploying-wordpress-with-capistrano-2082/]]
* Other Languages / Frameworks
  * PHP
    * [[http://mathew-davies.co.uk/2009/10/28/php-deployment.html]]
    * [[http://hivelogic.com/articles/deploying-expressionengine-github-capistrano]]
    * [[http://blog.servergrove.com/2011/09/07/deploying-symfony2-projects-on-shared-hosting-with-capifony]]
  * [[Any Non-Rails Project|http://github.com/leehambley/railsless-deploy/]]

## Seeking Assistance

Help first and foremost via the [[Capistrano Google Group|http://groups.google.com/group/capistrano]]. Community support is also also often available in [[#Capistrano on freenode|http://webchat.freenode.net/?channels=Capistrano]].

There are extensive archives of questions and answers also at [[stackoverflow.com, tagged #capistrano|http://stackoverflow.com/questions/tagged/capistrano]].

For bugs and problems please open an issue in the [[Github issues page|https://github.com/capistrano/capistrano/issues]] - preferably with a patch, test-case, or steps-to-reproduce. Pull requests on Github will be ignored without a corresponding ticket, as there is no history of changes or forum for discussion without submitting a ticket.