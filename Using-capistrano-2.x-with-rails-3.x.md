Example of deploy.rb (source: git://gist.github.com/289464.git)

# This is only a subset of a regular deploy.rb


# You would set this to vendor/bundled_gems or wherever else for rails 2.3
set :gems_path, "vendor/gems"
set :ruby_engine, "ruby"
set :ruby_version, "1.8"
set :shared_gems, File.join(shared_path, gems_path)
set(:rails_env) { "production"}

# Needed for Webistrano for some reason
set :mod_rails_restart_file, "#{deploy_to}/current/tmp/restart.txt"

namespace :deploy do
  task :start do ; end
  task :stop do ; end
  task :restart, :roles => :app, :except => { :no_release => true } do
    run "touch #{File.join(current_path,'tmp','restart.txt')}"
  end
  
  task :setup, :roles => :app, :except => {:no_release => true } do
    dirs = [deploy_to, releases_path, shared_path]
    dirs += shared_children.map { |d| File.join(shared_path, d) }
    run "#{try_sudo} mkdir -p #{dirs.join(' ')} && #{try_sudo} chmod g+w #{dirs.join(' ')}"
    deploy.update_initial_code
    bundler.setup_bundle_cache
  end
  
  task :update_initial_code, :roles => :app, :except => {:no_release => :true} do
    on_rollback { run "rm -rf #{release_path}; true" }
    strategy.deploy!
    finalize_update
  end
end

namespace :bundler do
  task :install , :roles => :app, :except => { :no_release => true }  do
    run("gem install bundler --source=http://gemcutter.org")
  end

  task :symlink_vendor , :roles => :app, :except => { :no_release => true }  do
    release_gems = "#{release_path}/#{gems_path}/#{ruby_engine}/#{ruby_version}/" 
    %w(gems specifications dirs).each do |sub_dir|
      shared_sub_dir = File.join(shared_gems, sub_dir)
      run("mkdir -p #{shared_sub_dir} && mkdir -p #{release_gems} && ln -s #{shared_sub_dir} #{release_gems}/#{sub_dir}")
    end
  end

  task :setup_bundle_cache , :roles => :app, :except => { :no_release => true }  do
    bundler.symlink_vendor
    run("cd #{release_path} && gem bundle --only #{rails_env}")
  end
  
  task :bundle_new_release , :roles => :app, :except => { :no_release => true }  do
    bundler.symlink_vendor
    run("cd #{release_path} && gem bundle --only #{rails_env} --cached")
  end
end

after 'deploy:update_code', 'bundler:bundle_new_release'