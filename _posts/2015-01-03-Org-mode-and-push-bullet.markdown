---
layout: post
title: Integrating org-mode and PushBullet for automated reminders
published: true
---

For a while now, I have been using Emacs' [org-mode](http://orgmode.org/) as my fully customizable, open-source, plain-text to-do list manager.
In order to help me not escape my agenda items though, I wanted some way to receive push notifications, and for that I am using [PushBullet](http://www.pushbullet.com).
With a little bit of python code, this can easily be accomplished.

Note: This guide uses these services on OS X with [Homebrew](http://brew.sh/) installed. It should be easily generalizable to other systems.

## Set up your machine

Make sure you have the most recent version of emacs. Using Homebrew:

	brew install emacs

We are going to interface everything with python, and for that we need to install [`pushbullet.py`](https://github.com/randomchars/pushbullet.py) with

	pip install pushbullet.py

This requires python-magic (which should be automatically installed), but which requires [dependencies](https://github.com/ahupp/python-magic#dependencies) which we quote here

> On Windows, install Cygwin (http://cygwin.com/install.html).  To find
> the libraries, either add <your-cygwin-install>/bin to the $PATH or
> copy cygwin1.dll, cygz.dll, and cygmagic-1.dll to C:\Windows\System32
> 
> On OSX:
> 
> - When using Homebrew: `brew install libmagic`
> - When using macports: `port install file`

Now, I assume you have org-mode set up with a list of agenda files hanging around somewhere on your machine (usually identified in your `.emacs` file or your `customizations.el` file for Aquamacs).

## The Python code

I cobbled together some python code with help from the org-mode site explaining how to [extract agenda information](http://orgmode.org/manual/Extracting-agenda-information.html) as well as the python implementation I found on [this blog](http://demonastery.org/2009/05/automatic-agenda-notification/) in his `agenda.py`.

<script src="https://gist.github.com/jhwilson/09b3f43451d5f855fb5a.js"></script>

It's important to note that the `loadfile` must define `org-agenda-files`. Additionally, I had problems if the `loadfile` tried to do too much upon initialization. If your `init` file does too much, you may need to make this `loadfile` something else, something simpler.

The push notifications you receive from running this code are specifically tailored to how I wanted them output. One can easily mess around with the section I labeled "PROCESSING Agenda information into notes to send". Additionally, there are more ways than just `pb.push_note` to send information (see the documentation [here](https://github.com/randomchars/pushbullet.py)).

## Set up Automator

There are numerous tools to automate tasks on different systems.
On OS X, we'll use Automator. 

1. Create a new application.
2. Find the "Run Shell Script" action and drag it to the box on the right.
3. Select shell `/bin/bash` and insert the following code

>	export PATH=/usr/local/bin:$PATH
>	python /path/to/org-mode-agenda-push-bullet.py

This is the simplest since the shell `/usr/bin/python` doesn't necessarily use the python that we want (located in `/usr/local/bin` in this case).

From here, we open the Calendar application, create a new event, and insert when we want it to run (frequency, etc.), then under the "alert:" option, we click "Custom...", then in the first drop down menu "Open file", in the new drop down menu that appears we click "Other...", and navigate to where we saved the automator application created above. The rest should be self-explanatory.

If all is well and good, at the specified times, you should get a push bullet reminder at that time (if your computer is on and connected to the internet).