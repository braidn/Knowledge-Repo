~~~
FactoryGirl.define do 
  sequence :name do |n|
      "Project_#{n}"
   end 
end
~~~~