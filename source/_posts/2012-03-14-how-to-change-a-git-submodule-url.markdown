---
layout: post
title: "How to change a git submodule URL"
date: 2012-03-14 18:50
comments: true
categories: git
---
Let me save you some headache today: if you're like me, you really *do* like keeping your git repo neat and clean using submodules for third party libraries. (Especially if the language you're using doesn't have something like CPAN or rubygem)  

Everything runs perfect untill you have to change one submodule URL.  
For istance: your submodule is a github repo and you can't wait for your pull request to been accepted, so you press the fork button and commit the patch in your private repo. Now what?  

Let 'yourproject' be your git working directory, 'supercoolib' the submodule and 'yourusername' your github username. Open with an editor of your choice (in my case emacs) the .gitmodules file (usually is located at the root of the repo):

{% codeblock %}
$ cd yourproject
$ emacs .gitmodule
{% endcodeblock %}

You should see something like this:
{% blockquote %}
[submodule "supercoolib"]
           path = lib/supercoolib
           url = https://github.com/anotherusername/supercoolib.git
{% endblockquote %}

Change the url of the repo like that:
{% blockquote %}
[submodule "supercoolib"]
           path = lib/supercoolib
           url = https://github.com/yourusername/supercoolib.git
{% endblockquote %}

Now tell git to update his internal reference:
```
$ git submodule sync
```

And then init(if you didn't already) and update the submodules:
```
$ git submodule init
$ git submodule update
```

Don't forget to checkout the branch inside the submodule (remember? submodules have a detached HEAD):
```
$ cd lib/supercoolib
$ git checkout master
```
Check if everything is working and finally commit your changes ;)
