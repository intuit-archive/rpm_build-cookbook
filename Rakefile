require 'foodcritic'

FoodCritic::Rake::LintTask.new do |t|
  t.options = { :fail_tags => ['any'] }
end

task :default => [:foodcritic]

begin
  require 'kitchen/rake_tasks'
  Kitchen::RakeTasks.new
rescue
  puts ">>>>> Kitchen gem not loaded, omitting tasks" unless ENV['CI']
end
