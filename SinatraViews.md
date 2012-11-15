Haml will work just fine with ERB, HAML, or Erubis. [Way more][1] too.

###Inline Templates

Just like they sound, they are included in the rb file where all the Sinatra logic lives.

* {{SinatraInlineTemplateExample}}
* Name of template must be a symbol that corresponds with the class variable for each view

###External Templates

* By default they should all be stored in the 'views' folder
* {{SinatraExternalTemplateExample}}

[1]: http://www.sinatrarb.com/intro#Available%20Template%20Languages