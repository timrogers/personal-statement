require 'erb'

task :generate do
  
  # Run me - I take the readme template in ERB
  # with Markdown (README.erb.md), add the text
  # of the current personal statement and make it
  # into a nice full README.md to be displayed in
  # the GitHub repo.
  #
  # $ rake generate
  #
  
  # Set the variables for populating the template
  @ps = File.read("Personal statement.txt")
  @words = `cat 'Personal Statement.txt' | wc -w`.strip
  @characters = `cat 'Personal Statement.txt' | wc -m`.strip
  
  # Build the template into an output file
  template = File.read("README.erb.md")
  erb = ERB::new(template)
  
  # Check if there's already an output file, and
  # remove it if so.
  if File.exists?("README.md")
    File.delete("README.md")
  end
  
  # Write the newly produced file
  File.open("README.md", 'w') {|f| f.write(erb.result) }
end