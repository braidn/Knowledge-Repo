* cache blocks are snippets of code in a layout that are always under cache. They start with:
* these caching blocks are called fragment caches. You can check and see if they exist with the method `fragment_exist?(action: 'nameOFAction')`
* also the below works only if there is one cache fragment per page. solved with: `<% cache(:action => 'controllername', :part => 'nameofsection) do %>`
* {{ExpiringCachedFragments}}

      <% cache do %>
        <!-- Content -->
      <%end%>