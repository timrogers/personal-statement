task :generate do
  
  # Run me - I take the readme template in Markdown 
  # (README.md.tmpl), add the text of the current
  # personal statement and make it into a nice full
  # README.md to be displayed in the GitHub repo.
  #
  # $ rake generate
  #
  
  ps = File.read("Personal statement.txt")
  template = File.read("README.md.tmpl")
  
  words = `cat 'Personal Statement.txt' | wc -w`.strip
  characters = `cat 'Personal Statement.txt' | wc -m`.strip
  stats = "\n__Words:__ " + words + "\n\n__Characters:__ " + characters
  output = template + ps + stats
  
  if File.exists?("README.md")
    File.delete("README.md")
  end
  
  File.open("README.md", 'w') {|f| f.write(output) }
end