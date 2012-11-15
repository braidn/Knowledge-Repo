    <% flash.each do |key, msg| %>
      <div id="<%= key %>">
        <p style="float:right;"><%= link_to_function 'X', "Effect.Fade('#{key}')" %></p>
        <p><%= msg %></p>
        <div class="clear"></div>
      </div>
    <% end %>

[reference][1]

another simple way:

     <% if flash[:notice] %>
          <p class="notice"><%= flash[:notice] %></p>
        <% end %>
        <% if flash[:error] %>
          <p class="error"><%= flash[:error] %></p>
        <% end %>

[1]: http://travisonrails.com/2008/08/17/Working-with-the-flash-hash