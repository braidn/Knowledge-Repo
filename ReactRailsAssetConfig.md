# Config For React Dev Server + Rails

```ruby
 config.action_controller.asset_host = Proc.new { |source|
    if source =~ /wp_bundle\.js$/i
    "http://localhost:8080"
    end
  }
```