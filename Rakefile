require 'rubygems'
require 'rake/gempackagetask'
require 'rake/testtask'

task :default => [:test]

Rake::TestTask.new do |t|
  t.verbose = true
  t.warning = true
end

PKG_VERSION = "0.5.0"
PKG_FILES = FileList[
  'LICENSE',
  'Rakefile',
  'lib/**/*.rb',
  'test/**/test_*.rb'
]

spec = Gem::Specification.new do |s|
  s.name = "hessian"
  s.version = PKG_VERSION
  s.author = "Christer Sandberg"
  s.email = "chrsan@gmail.com"
  s.homepage = "http://www.baanii.se/"
  s.platform = Gem::Platform::RUBY
  s.summary = "A Ruby Hessian client."
  s.files = PKG_FILES.to_a
  s.require_path = "lib"
end

package_task = Rake::GemPackageTask.new(spec) do |pkg|
  pkg.need_zip = true
  pkg.need_tar_gz = true
end
