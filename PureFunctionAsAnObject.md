# Pure Function As An Object.

## Notes.

Ruby specific pattern that compromises:

1. creates an object of its own class,
1. passing its argument into the initializer,
1. and calls a single method on the object, to generate the return value.

Most of the functions will have 0 side affects (how we can sorta call it pure)
EX:

```ruby
class JSON2XML
  def self.convert(input_json)
    new(input_json).send(:xml)
  end

  private
    attr_reader :input_json

    def initialize(input_json)
      @input_json = input_json
    end

    def xml
      Ox.dump(document, with_xml: true)
    end
end
```
