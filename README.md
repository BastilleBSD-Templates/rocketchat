# rocketchat
Bastille Template to create a Rocket.Chat Server Jail

 STATUS:  Testing

Create the Rocketchat user

	$ adduser
	Username: rocketchat
	Full name: User used for running rocket chat
	Uid (Leave empty for default): *press enter*
	Login group [rocketchat]: *press enter*
	Login group is rocketchat. Invite rocketchat into other groups? []: *press enter*
	Login class [default]: *press enter*
	Shell (sh csh tcsh git-shell bash rbash nologin) [sh]: bash
	Home directory [/home/rocketchat]: *press enter, or pick where you want your Rocket.chat installation to be*
	Home directory permissions (Leave empty for default): *press enter*
	Use password-based authentication? [yes]: *press enter*
	Use an empty password? (yes/no) [no]: *press enter*
	Use a random password? (yes/no) [no]: yes
	Lock out the account after creation? [no]: *press enter*
	Username   : rocketchat
	Password   : <random>
	Full Name  : User used for running Rocket chat
	Uid        : 1001
	Class      :
	Groups     : rocketchat
	Home       : /home/rocketchat
	Home Mode  :
	Shell      : /usr/local/bin/bash
	Locked     : no
	OK? (yes/no): yes
	adduser: INFO: Successfully added (rocketchat) to the user database.
	adduser: INFO: Password for (rocketchat) is: qGn&j9nXBx&j*C#u
	Add another user? (yes/no): no


Change to the newly created user

	# su -l rocketchat

	$ export MAKE_CMD=gmake
	$ export CXX=clang++
	$ export CC=clang

	$ cd $HOME
	$ git clone -b freebsd https://github.com/williambr/meteor

	$ cd meteor
	$ ./scripts/build-mongo-for-dev-bundle.sh
	$ ./scripts/build-node-for-dev-bundle.sh
	$ ./scripts/generate-dev-bundle.sh

	$ ./meteor --version

	$ export PATH=$PATH:$HOME/meteor

	$ cd $HOME
	$ git clone https://github.com/RocketChat/Rocket.Chat.git
	$ cd Rocket.Chat

	$ npm install --clang=1 bcrypt

	$ meteor




