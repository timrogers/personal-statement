require 'erb'

namespace :ps do
  task :generate do
  
    # Run me - I take the readme template in ERB
    # with Markdown (README.erb.md), store the
    # paragraphs from parts/ in an array and save
    # the word and character counts too.
    #
    # $ rake ps:generate
    #
  
    # Read all the parts of the personal statement
    # into an array
    @parts = []
  
    part_filenames = Dir.entries("parts")
    part_filenames.keep_if {|filename| filename.include?(".txt") or filename.include?(".md") } # Remove the meta-directories
    part_filenames.sort!
    part_filenames.each do |filename|
      @parts.push(File.read("parts/#{filename}"))
    end
  
    # Generate a pure personal statement text file
    # from the parts, then save it.
    ps = @parts.join("\n\n")
    if File.exists?("Personal Statement.txt")
      File.delete("Personal Statement.txt")
    end
    File.open("Personal Statement.txt", 'w') {|f| f.write(ps) }
  
    # Perform a word and character count to be displayed
    @words = `cat 'Personal Statement.txt' | wc -w`.strip
    @characters = `cat 'Personal Statement.txt' | wc -m`.strip
  
    # Display the counts in the console for quick reference
    puts "Words: #{@words}"
    puts "Characters: #{@characters}"
  
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
end