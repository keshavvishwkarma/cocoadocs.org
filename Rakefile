require 'rubocop/rake_task'

def specs(dir)
  FileList["spec/#{dir}/*_spec.rb"].shuffle.join(' ')
end

desc 'Runs all the specs'
task :specs do
  sh "bundle exec bacon #{specs('**')}"
end

RuboCop::RakeTask.new(:rubocop) do |task|
  task.patterns = ['classes', 'spec']
end

# TODO: Put rubocop in by default
task :default => :specs

