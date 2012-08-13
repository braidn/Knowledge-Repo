Find a really good place where you want all your factories to live then include them into the `cucumber/support/factories.rb` file with the below:

~~~
Dir[Rails.root + 'factoryLocationFolderName/*rb'].each do |file|
  require file
end
~~~~~