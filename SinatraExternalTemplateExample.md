Will grab the index.html file from the 'views' directory    
    get '/index' do
      erb :index 
    end

Will grab the profile.html and help.html from the 'view/user' folder
    get '/:user/profile' do
      erb '/user/profile'.to_sym
    end

    get '/:user/help' do 
      erb :'/user/help'
    end