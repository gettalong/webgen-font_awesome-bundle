require 'rubygems/package_task'
require 'rake/clean'
require 'yaml'
require 'fileutils'

NAME='font_awesome'
INFOS = YAML::load(File.read("lib/webgen/bundle/#{NAME}/info.yaml"))

CLOBBER << "VERSION"
file 'VERSION' do
  puts "Generating VERSION file for #{INFOS['version']}"
  File.open('VERSION', 'w+') {|file| file.write(INFOS['version'] + "\n")}
end

spec = Gem::Specification.new do |s|
  s.name = "webgen-#{NAME}-bundle"
  s.version = INFOS['version']
  s.summary = INFOS['summary']
  s.description = INFOS['description']
  s.license = INFOS['license']
  s.files = FileList.new(['lib/**/*', 'README.md', 'ChangeLog', 'LICENSE', 'VERSION'])
  s.add_dependency('sass')
  s.require_path = 'lib'
  s.has_rdoc = false

  author_info = INFOS['author'].scan(/(?:^|,)\s*(.*?)\s*<(.*?)>/)
  s.authors = author_info.map(&:first)
  s.email = author_info.map(&:last)
  s.homepage = INFOS['homepage']
end

Gem::PackageTask.new(spec).define

task :gem => ['VERSION']

task :release => [:gem] do
  sh "gem push pkg/webgen-#{NAME}-bundle-#{INFOS['version']}.gem"
end
