* break the resources command in routes with a do -> end block

      resources :products do  
        get :who_bought, on :member  
      end

* fairly straightforward, build a route called "who_bought", use a get method in it, and it applies to each member of products
  * Instead of :member, :collection would place the who_bought on the entirety of products (doesn't make sense)