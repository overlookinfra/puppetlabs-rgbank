#This file is generated by ModuleSync, do not edit.

source ENV['GEM_SOURCE'] || "https://rubygems.org"

def location_from_env(env, default_location = [])
  if location = ENV[env]
    if location =~ /^((?:git|https?)[:@][^#]*)#(.*)/
      [{ :git => $1, :branch => $2, :require => false }]
    elsif location =~ /^file:\/\/(.*)/
      ['>= 0', { :path => File.expand_path($1), :require => false }]
    else
      [location, { :require => false }]
    end
  else
    default_location
  end
end
group :development, :unit_tests do
  gem 'metadata-json-lint'
  gem 'puppet_facts'
  gem 'puppet-blacksmith', '>= 3.4.0'
  gem 'puppetlabs_spec_helper', '>= 1.2.1'
  gem 'simplecov'
  gem 'simplecov-console'
  gem 'rspec-puppet', '>= 2.4.0', :git => 'https://github.com/rodjek/rspec-puppet.git',
                                  :ref => 'd1a7233eec08a2c605b623ced2b863c5ea4b37df'
  gem 'rspec-puppet-facts'
  gem 'parallel_tests'
  gem 'rubocop', '0.41.2' if RUBY_VERSION < '2.0.0'
  gem 'rubocop' if RUBY_VERSION >= '2.0.0'
  gem 'rubocop-rspec', '~> 1.6' if RUBY_VERSION >= '2.3.0'
  gem 'json_pure', '<= 2.0.1' if RUBY_VERSION < '2.0.0'
end
group :system_tests do
  gem 'beaker',       :git => 'https://github.com/ipcrm/beaker.git',
                      :ref => 'a60391e0dc257b87ff372bbffd424d1c46e4b55d'
  gem 'beaker-rspec', :git => 'https://github.com/hunner/beaker-rspec.git',
                      :ref => '755b3bfc6f8d661ab8c11838997890acd7875ab1'
  gem 'serverspec'
  gem 'beaker-puppet_install_helper'
  gem 'master_manipulator'
  gem 'beaker-hostgenerator', *location_from_env('BEAKER_HOSTGENERATOR_VERSION', [])
end

gem 'facter', *location_from_env('FACTER_GEM_VERSION')
gem 'puppet', *location_from_env('PUPPET_GEM_VERSION')

if File.exists? "#{__FILE__}.local"
  eval(File.read("#{__FILE__}.local"), binding)
end
