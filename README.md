Node, NVM & NPM on Ubuntu 14.04
=================

A guide - to using Node.js in Ubuntu 14.04

##To Do
*Summarise Node.js, NVM, NPM
*Outline installation procedures for the above in Ubuntu 14.04
*Outline bugfixes

The objective is to be able to run scripts and tasks must run without root permissions, so that common packages (e.g. Yeaoman) can be properly installed and used.

We've been mucking about with this for quite some time - we need a definitive guide.

##Resources##
NVM repo on GitHub:
https://github.com/creationix/nvm

Step by step guide on installing Node.js by means of NVM:
https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server

Outlines a problem with Ubuntu and NVM, along with a potential solution (adding a line manually to ~/.bashrc). See last post especially:
https://github.com/creationix/nvm/issues/394

Why this is an issue:
See the answer titled "You need to consider permissions during node installation" in this Stack Overflow answer:
http://stackoverflow.com/questions/16151018/npm-throws-error-without-sudo


This is very important:
"To set a default Node version to be used in any new shell, use the alias 'default' e.g.

```nvm alias default 0.10```

Otherwise node isn't recognised in a new shell. This is taken from the NVM readme: 

Node/Ubuntu Issue
https://github.com/joyent/node/issues/3911
