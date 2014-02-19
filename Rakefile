require 'rake'
require 'rake/testtask'
require 'rubocop/rake_task'

task :default => 'test:minitest'

namespace :test do

  Rubocop::RakeTask.new

  Rake::TestTask.new do |t|
    t.name = :minitest
    t.libs = %w(libraries)
    t.test_files = Dir.glob('test/spec/**/*_spec.rb')
  end

  desc 'Run all of the quick tests.'
  task :all do
    Rake::Task['test:minitest'].invoke
    Rake::Task['test:rubocop'].invoke
  end

end