``` ruby
before_save :payment_due
protected
 def payment_due
 self.payment_due ||= Time.now + 30.days
end
```

VS

``` ruby
def before_save
  self.payment_due ||= Time.now + 30.days
end
```