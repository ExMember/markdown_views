require "bundler/gem_tasks"
require "rake/testtask"

task :generate_stylesheet do
  %w( base16.light base16.dark base16.solarized.light base16.solarized.dark
      base16.monokai.light base16.monokai.dark colorful github
      gruvbox.light gruvbox.dark igorpro molokai monokai monokai.sublime
      pastie thankful_eyes tulip
  ).each do |theme|
    `rougify style #{theme} --scope .rouge-highlight > app/assets/stylesheets/rouge.#{theme}.css`
  end
end


Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList["test/**/*_test.rb"]
end

task :default => :test
