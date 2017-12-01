require 'html-proofer'

desc 'Test build, links on generated site'
task :test do
  sh "bundle exec jekyll build"
  HTMLProofer.check_directory("./_site", {
    :allow_hash_href => true,
    :check_html => true,
    :only-4xx => true,
    :validation => { :report_script_embeds => true }
    }).run
end

task :default => [:test]
