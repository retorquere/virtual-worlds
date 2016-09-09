require 'shellwords'

task :default => 'Virtual Worlds.pdf'

def compile(target)
  bib = File.basename(target, File.extname(target)) + '.bib'
  md = File.basename(target, File.extname(target)) + '.md'
  sh "pandoc -s --smart --bibliography #{bib.shellescape} --csl=apa.csl -f markdown -o #{target.shellescape} #{md.shellescape}"
end

rule '.pdf' => '.md' do |task|
  compile(task.name)
end

rule '.html' => '.md' do |task|
  compile(task.name)
end

rule '.docx' => '.md' do |task|
  compile(task.name)
end
