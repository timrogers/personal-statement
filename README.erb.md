# Tim's Personal Statement

This is my personal statement, in progress, for applying to universities in the UK in academic year 2012/13.

## Personal statement *(preview)*

<% @parts.each do |part| %>
<%= part %>
<% end %>

__Words:__ <%= @words %>
__Characters:__ <%= @characters %><%= " *(too long)*" if @characters.to_i > 4000 %>