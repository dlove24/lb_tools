task :default => :build
task :test => :build

task :build do |t|
  sh "bundle exec jekyll build"
end

task :serve do |t|
  sh "bundle exec jekyll serve --baseurl ''"
end