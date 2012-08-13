syntax: `content_for`

A good example would be if you had side bar items. Call:  
    <% content_for (:sidebar) do %>
    all of your lists (<li>)
    <% end %>

you could then call `<%= yield :sidebar %>` in your view and be awesome!
