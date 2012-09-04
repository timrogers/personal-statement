# Tim's Personal Statement

This is my personal statement, in progress, for applying to universities in the UK in academic year 2012/13.

A valid personal statement can only be 4000 characters long. The full word and character counts for the personal statement in its current form can be found at the bottom of this file.

This is mainly for me to keep track and benefit from the ability to revert and the like.

To edit the personal statement, edit the files in the parts/ directory. The files are ordered according to the preceding number. Once you've edited the parts, you can generate the final versions by running `rake ps:generate`.

Thoughts (and pull requests!) are appreciated. Do not plaigirise this - it's against the UCAS rules.

## Personal statement *(preview)*

<% @parts.each do |part| %>
<%= part %>
<% end %>

__Words:__ <%= @words %>
__Characters:__ <%= @characters %><%= " *(too long)*" if @characters.to_i > 4000 %>