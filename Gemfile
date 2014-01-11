source 'https://rubygems.org'

gemspec

%w[rspec rspec-core rspec-expectations rspec-mocks rspec-support].each do |lib|
  library_path = File.expand_path("../../#{lib}", __FILE__)
  if File.exist?(library_path)
    gem lib, :path => library_path
  else
    gem lib, :git => "git://github.com/rspec/#{lib}.git", :branch => ENV.fetch('BRANCH',"2-99-maintenance") unless lib == 'rspec-support'
  end
end

gem "cucumber", "~> 1.1.9"
gem "aruba",    "~> 0.5"
gem "rake",     "~> 10.0.0"

eval File.read('Gemfile-custom') if File.exist?('Gemfile-custom')
