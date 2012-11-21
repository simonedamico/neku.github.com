---
layout: post
title: "Bootstrapping chef server in Vagrant"
date: 2012-11-21 17:48
comments: true
categories: [chef, devops, vagrant]
---
Installing a [chef](http://opscode.com) server for learning  porpoise could be quite an annoying task.  
Dear devops fellows, fear no more, in our rescue come [Vagrant](http://vagrantup.com) a very nice tool that let us spawn and manage virtual machines through Virtual box.   
Cherry on the cake? It integrates easily with chef: you can either specify a cookbook path and a runlist or a proper chef server.  

On my [github repo](https://github.com/Neku/vagrant-chef-server-bootstrap) you can find a vagrant project to bootstrap a chef server though chef solo (inception :P) with the latest cookbooks available at opscode.  
A simple ```vagrant up``` and you have a chef-server ready to play with.  

Enjoy.
