task :generate do
  ps = File.read("Personal statement.txt")
  template = File.read("README.md.tmpl")
  output = template + ps
  
  if File.exists?("README.md")
    File.delete("README.md")
  end
  
  File.open("README.md", 'w') {|f| f.write(output) }
end