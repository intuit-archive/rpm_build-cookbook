require 'emeril/rake_tasks'
require 'foodcritic'

Emeril::RakeTasks.new do |t|
  t.config[:logger]               = Logger.new(STDOUT)
  t.config[:publish_to_community] = false
  t.config[:tag_prefix]           = false
end

FoodCritic::Rake::LintTask.new do |t|
  t.options = { :fail_tags => ['any'] }
end

begin
  require 'kitchen/rake_tasks'
  Kitchen::RakeTasks.new
rescue
  puts ">>>>> Kitchen gem not loaded, omitting tasks" unless ENV['CI']
end

task :default => [:foodcritic]
