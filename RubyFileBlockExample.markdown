    File.open("testfile", "r") do |file|
      ...process the file
    end << here is where the file is automatically closed. 