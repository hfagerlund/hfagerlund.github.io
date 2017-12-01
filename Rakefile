require 'html-proofer'

desc 'Remove generated site directory'
task :clean do
  FileUtils.rm_r("./_site")
  Rake::Task["test"].invoke
end

desc 'Test build, links on generated site'
task :test do
  sh "bundle exec jekyll build"
  HTMLProofer.check_directory("./_site", {
    :allow_hash_href => true,
    :check_html => true
    }).run
end

task :default => [:clean]
