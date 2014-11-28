I highly recommend doing a fresh OS X install before completing the following steps. And of course remember to backup any important data to an external drive or TimeMachine if available. If you choose to continue without a clean OS X install there is no guarantee that these instructions will function correctly.

#### Step 1: Installing Command Line Tools..

**Note:** If you are running OS X 10.9 Mavericks or above, then you can install the Xcode Command Line Tools directly in your Terminal, If not, you will have to go to http://developer.apple.com/downloads, and sign in with your Apple ID and follow the onscreen instructions.

For those running OS X 10.9 Mavericks or above, Open a new Terminal window and run the following command

$ `xcode-select --install`

* Select Install
* Select Agree

When the install has completed, close the Terminal window.

#### Step 2: Installing and setting up node and npm..

**Note:** At the time of writing, this was the Current Version: v0.10.33 

Go to: https://nodejs.org/

* Select Install
* Choose to open the node.pkg by clicking Save File

When the download has completed, follow the on screen node installer and enter your password when requested.

**Note:** The package will install node and npm into `/usr/local/bin`

When the install has completed, close the Terminal window.

Now open a new Terminal window and run the following commands

$ `which node`

The output should read `/usr/local/bin/node`

$ `node --version`

The output should read `v0.10.33`

$ `which npm`

The output should read `/usr/local/bin/npm`

$ `npm -v`

The output should read `1.4.28`

$ `sudo chown -R $USER /usr/local`

**Note:** Ignore the warning and just enter your password

Now close the current Terminal window.

In a new Terminal window run the following commands

$ `npm install -g bower`

$ `npm update -g bower`

$ `bower install gumby`

* Type `y` when prompted

$ `bower update gumby`

$ `npm install -g claymate`

$ `npm update -g claymate`

Close the Terminal window.	

#### Step 3: Installing Homebrew..

**Note:** Homebrew will assist in this installation and will also be of use to you for any future developement installs.

For more information on Homebrew go to: http://brew.sh/

In a new Terminal window run the following command

$ `ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

* Hit Return
* Enter your password

When the install has completed, run the following commands

$ `brew doctor`

$ `brew update`

Close the Terminal window.

#### Step 4: Installing rvm *(ruby version manager)* and setting up the required gems for claymate..

**Note:** At the time of writing, this was the Current rvm Stable Version: 1.26.3

Need more information on rvm? then go to: https://rvm.io/

We want to install rvm stable with ruby so open a new Terminal window and run the following command

$ `\curl -sSL https://get.rvm.io | bash -s stable --ruby`

**Note:** We need to create the alias default for ruby-2.1.5 so you will most likely get these following warnings.
Dont stress, just enter your password when prompted.

**WARNINGS:**

> mkdir: /etc/openssl: Permission denied

> mkdir -p "/etc/openssl" failed, retrying with sudo

> your_username password required for 'mkdir -p /etc/openssl':

When the install has completed, Close the Terminal window.

In a new Terminal window, run the following command

$ `nano .bash_profile`

**Note:** The following 2 lines should have been automatically added to your .bash_profile The first is the rvm PATH line and the second is the rvm loading line.

`[[ -s "$HOME/.profile" ]] && source "$HOME/.profile" # Load the default .profile`

`[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*`

* Hit `control` + `x` to exit

In the same Terminal window run the following commands

$ `rvm -v`

The output should read 

`rvm 1.26.3 (latest) by Wayne E. Seguin <wayneeseguin@gmail.com>, Michal Papis <mpapis@gmail.com> [https://rvm.io/]`

Next,  

$ `rvm list`

The output should read

    rvm rubies

    =* ruby-2.1.5 [ x86_64 ]

		# => - current
		# =* - current && default
		#  * - default

Then type,

$ ```which gem```

This should output the following

`/Users/your_username/.rvm/rubies/ruby-2.1.5/bin/gem`

Now lets check the gem version

$ `gem -v`
	
The output should read `2.4.3`

Next is to install the required gems for Claymate, so run the following commands in the *exact* order as shown below

**Note:** It appears that the Claymate install command is dependant on specific gem versions. The versions below have been tested and work.

$ `gem install modular-scale -v 1.0.6`

$ `gem uninstall sass`

* Type `y` when prompted
* Then Type `y` again when prompted

$ `gem install sass -v 3.2.19`

$ `gem uninstall compass`

* Type `y` when prompted
* Then Type `y` again when prompted

$ `gem install compass -v 0.12.6`

When the required gem installs have completed, Close the Terminal window.

#### Step 5: Testing out the Claymate install command..

Run the following commands in a new terminal window

$ `mkdir gumbyclaymatetest`

Next run,

$ `cd gumbyclaymatetest`

Then finally run,

$ `claymate install`

### VOILA !!

*Congratulations*, You now have Claymate setup with the Gumby Framework.

I might suggest checking out Cory Simmons YouTube Chanel for tutorials on The Gumby Framework and in particular Claymate [Here](https://www.youtube.com/watch?v=VgE7Ztc05sQ). He will get you up to speed and demonstrate the facets to get your build started.






	


