source 'https://rubygems.org'
gemspec

# Stick with older racc until
# https://github.com/tenderlove/racc/issues/22
# is solved.
gem 'racc', '< 1.4.10' if RUBY_ENGINE == 'jruby'
gem 'json', '< 1.8.1'  if RUBY_VERSION.to_f == 2.1 and RUBY_ENGINE == 'ruby'
gem 'rubysl', :platform => :rbx
gem 'thin', platform: :mri

group :repl do
  gem 'therubyracer', :platform => :mri, :require => 'v8'
  gem 'therubyrhino', :platform => :jruby
end

tilt_version = ENV['TILT_VERSION']
gem 'tilt', tilt_version if tilt_version

unless ENV['CI']
  gem 'rb-fsevent'
  gem 'guard', require: false
  gem 'terminal-notifier-guard'
end

gem 'mspec', github: 'ruby/mspec', ref: '7cb4c8310677e41e48a78bc0b0029faf7a74c3c8'
