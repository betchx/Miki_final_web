

task :default => :zip


HTMLS = %w(index.html application.html lecture.html)
PDFS = Dir['*.pdf'].to_a

(HTMLS + PDFS).each do |f|
  file "final/#{f}" => ["final", f] do |t|
    sh "cp #{f} final/"
  end
end

directory "final"

SOURCES = (HTMLS+PDFS).map{|x| "final/#{x}"}

task :zip => SOURCES do |t|
  sh "zip -u final.zip #{t.prerequisites.join(' ')}"
end

