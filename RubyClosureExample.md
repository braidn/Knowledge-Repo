    def multiple_gen(m)
      lambda do |n|
        n * m
      end
    end

    triple = multiple_gen(3)
    quad = multiple_gen(4)

    puts quad(5) # 20
    puts triple(5) # 15