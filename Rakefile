require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "petfinder"
    gem.summary = %Q{Ruby gem wrapper for the Petfinder API}
    gem.description = %Q{Ruby gem wrapper for the Petfinder API}
    gem.email = "ehutzelman@gmail.com"
    gem.homepage = "http://github.com/ehutzelman/petfinder"
    gem.authors = ["Eric Hutzelman"]

    gem.add_dependency('happymapper', '>= 0.3.2')
    gem.add_dependency('httparty', '>= 0.5.0')
    
    gem.add_development_dependency "rspec", ">= 1.3.0"
    gem.add_development_dependency 'fakeweb', '>= 1.2.5'
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :spec => :check_dependencies

task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "petfinder #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
