require "bundler/gem_tasks"
require "rake/testtask"
require 'find'
require 'pry'


desc 'say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

# using sh to manually run tests is not ideal

# desc 'Run tests'
# task :test do
#   sh 'ruby ./test/todolist_project_test.rb'
# end

desc 'Run Tests'
task :default => :test

# code in the block tells rake/testtask where tests and source code resides
# also, tells it that all of the test files reside in the test directory
# rake/testtask will load and run all *_test.rb files it can find in the test directory o any of its subdirectories, which are tested automatically
Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

# create a task that lists every file in your project except for hidden files (start with '.'), or which reside in hidden directories(start with '.')

desc 'List Files'
task :list_files do
  Find.find(".") do |file|
    if File.file?(file)
      puts file unless file.start_with?('./.')
    end
  end
end
