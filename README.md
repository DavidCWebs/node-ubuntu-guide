Node, NVM & NPM on Ubuntu 14.04
=================

Guidelines on installing Node.js and
npm using Node Version Manager(NVM) in Ubuntu 14.04.

This method will avoid EACCES errors when trying to install npm or npm packages. It will allow the use of ```npm install``` without sudo privileges on project directories.

##What is Node.js?
Node.js provides a way of running Javascript on the server-side.

##What is NPM?
The package manager for Node.

* An online repository for the publishing of open-source Node.js
projects
* A command-line utility for interacting with this repository that aids in package installation, version management,
and dependency management.

Using npm, node packages can be installed from the repository
using a single line of command. e.g.

```npm install async```

Another use for npm is dependency management. When you have a node project with a package.json file, you can run ```npm install``` from the
project root and npm will install all the dependencies listed in the package.json.

##Version Management: Installing NVM:

Before following the steps below to install node/npm, you should first make sure that there are no versions of node/npm already installed on your system. This can be done with the following lines of code:

~~~
which node
which npm
~~~

If there is no output after either of the above, then that respective package is not present on your system.

Once this is complete, enter:

~~~
sudo apt-get update
sudo apt-get install build-essential libssl-dev
~~~

Once these prerequisite packages are installed you can install NVM with
with the command:

```curl https://raw.githubusercontent.com/creationix/nvm/v0.16.1/install.sh | sh```

You may now have to restart your terminal. Once you've done this, run the following command:

```source ~/.profile```

This allows the current BASH profile to be reloaded, without logging out and back in again.

##Installing Node:
You can then view which versions of Node.js are available for installation with the command:

~~~bash
nvm ls-remote

#You can install the relevant version by entering:

nvm install 0.11.14

~~~

NPM should be installed by default along with Node.js. You should now
be able to install packages without being forced to use the sudo command.

You can set a default version of Node to be used by the setting the alias
"default". This is important, otherwise node isn't recognised in a new shell:

```nvm alias default 0.11.14```

This allows you to revert to a different version of Node if the current
version is incompatible with an particular application. Each version of
Node will keep track of its own packages. You can also install a package
globally, which will make it available to all projects using the same
version of Node, by adding the -g tag. e.g.

```npm install -g grunt```

Installing globally will let you run the commands from the command line,
but you'll have to link the package into your local sphere to require
it from within a program. eg.

```npm link grunt```

##Resources
* [NPM](https://www.npmjs.com/)
* [NPM Packages](https://www.npmjs.com/package/npm)
* [NVM](https://github.com/creationix/nvm)
* [Ubuntu Specific Issues, NVM](https://github.com/creationix/nvm/issues/394)
* [Step by step guide on installing Node.js by means of NVM](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server)
* [Why consider permissions during node installation?](http://stackoverflow.com/questions/16151018/npm-throws-error-without-sudo)
* [Node/Ubuntu issue](https://github.com/joyent/node/issues/3911)
