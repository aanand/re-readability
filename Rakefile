readability_css  = "src/readability.css"
readability_sass = "src/readability.sass"
source_file      = "src/re-readability.sass"
build_file       = "build/re-readability.css"

task :default => build_file

file build_file => [source_file, readability_sass] do
  sh "sass #{source_file} #{build_file}"
end

file readability_sass => [readability_css] do
  sh "sass-convert #{readability_css} > #{readability_sass}"
end

desc "Download readability.css from arc90.com"
task :update_readability_css do
  sh "curl http://lab.arc90.com/experiments/readability/css/readability.css > #{readability_css}"
end

def sh(cmd)
  puts(cmd)
  system(cmd)
end  
