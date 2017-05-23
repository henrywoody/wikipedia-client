$LOAD_PATH.push File.expand_path('../lib', __FILE__)
require 'rake'
require 'rubocop/rake_task'
require 'rspec/core/rake_task'

task default: [:spec, :rubocop]

desc 'Test the wikipedia plugin.'
RSpec::Core::RakeTask.new(:spec)

desc 'Run rubocop'
RuboCop::RakeTask.new(:rubocop)

desc 'Run spec with coverage'
task :coverage do
  ENV['COVERAGE'] = 'true'
  Rake::Task['spec'].execute
end

require 'rdoc/task'
require 'wikipedia/version'
Rake::RDocTask.new do |rdoc|
  version = Wikipedia::VERSION

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "wikipedia-client #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
