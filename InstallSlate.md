For installing on Mac, please perform the following steps:
For instructions on downloading homebrew, ruby, and rails are on https://gorails.com/setup/osx/10.10-yosemite 
*All instructions are gotten from https://gorails.com/setup/osx/10.10-yosemite

1- Download homebrew
	Execute the following command on terminal:
	$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	
2- Download Ruby (version 1.9.3 or higher)
	brew install rbenv ruby-build

	# Add rbenv to bash so that it loads every time you open a terminal
	echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile
	source ~/.bash_profile

	# Install Ruby
	rbenv install 2.2.2
	rbenv global 2.2.2
	ruby -v

3- Install rails
	$ gem install rails -v 4.2.1
	$ rbenv rehash
	$ rails -v 		//check for version

	(if you get the error: "While executing gem ... (Gem::FilePermissionError) You don't have write permissions into the....", then do $ sudo gem install rails -v 4.2.1)

4- Download Bundler
	$ gem install bundler (if you get the error: "While executing gem ... (Gem::FilePermissionError) You don't have write permissions into the....", then do $ sudo gem install bundler)

5- Clone the repository from bitbucket into the folder you would like the repostiory to be in.
	$ git clone https://mariam16@bitbucket.org/chashuHotPot/sensorthingsapidocs.git

6- Go into your slate project
	$ cd slate

7- Execute the following commands:
	$ bundle install
	$ bundle exec middleman server

	(If you get the error: "cannot find resource i18n-0.7.0", then try "$ gem install i18n -v 0.7.0", if that does not work then try deleting the package and reinstalling it)

8- To build files:
	$ rake build

------Done installing------------
