* If each one of your products had a review: 

      resources :products do
        resources : product_reviews
      end

* Paths to reviews would be absolute and through products like /products/:product_id/reviews/:reviews_id
* Sometimes these can get unwealdy, so by passing `shallow, :true` right before the do of the block it cleans things up
