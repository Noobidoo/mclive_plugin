require 'rubygems'
require 'bundler/setup'

require 'ant'
require 'rcon'

task :clean do
  ant.delete :dir => 'build'
end

task :setup do
  ant.path :id => 'classpath' do
    fileset :dir => 'build/compile'
    fileset :dir => 'lib'
  end
end

task :jar => :setup do
  ant.mkdir :dir => 'build/classes'
  ant.javac :srcdir => 'src', :destdir => 'build/classes', :classpathref => 'classpath', :source => '1.6', :target => '1.6', :debug => 'yes', :includeantruntime => 'no'
  ant.jar :jarfile => 'build/compile/MCLive.jar', :basedir => 'build/classes', :includes => 'plugin.yml'
  ant.delete :dir => 'build/classes'
end

namespace :test do
end
