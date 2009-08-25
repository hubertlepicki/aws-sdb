require 'rubygems'
require 'spec/rake/spectask'
require 'rake/gempackagetask'

Spec::Rake::SpecTask.new

gem_spec = Gem::Specification.new do |s|
  s.name = "aws-sdb"
  s.rubyforge_project = s.name
  s.version = "0.2.0"
  s.platform = Gem::Platform::RUBY
  s.has_rdoc = true
  s.extra_rdoc_files = ["README", "LICENSE"]
  s.summary = "Amazon SDB API"
  s.description = s.summary
  s.author = "Tim Dysinger"
  s.email = "tim@dysinger.net"
  s.homepage = "http://aws-sdb.rubyforge.org"
  s.add_dependency "needle"
  s.require_path = 'lib'
  s.files = %w(LICENSE README Rakefile) + Dir.glob("{lib,spec}/**/*")
end

Rake::GemPackageTask.new(gem_spec) do |pkg|
  pkg.gem_spec = gem_spec
end

task :install => [:package] do
  sh %{sudo gem install pkg/#{gem_spec.name}-#{gem_spec.version}}
end

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gemspec|
    gemspec.name = "aws-sdb"
    gemspec.summary = "Amazon SimpleDB with Ruby"
    gemspec.description = ""
    gemspec.email = "hubert.lepicki@amberbit.com"
    gemspec.homepage = "http://github.com/hubertlepicki/aws-sdb"
    gemspec.description = ""
    gemspec.authors = ["Tim Dysinger"]
  end
rescue LoadError
  puts "Jeweler not available. Install it with: sudo gem install technicalpickles-jeweler -s http://gems.github.com"
end

