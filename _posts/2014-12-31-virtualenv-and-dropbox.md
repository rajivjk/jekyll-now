---
layout: post
title: VirtualEnv and Dropbox	
---

I am usually wary of undertaking any coding project that is housed exclusively on my laptop hard disk. Up until a few months ago, I would house my repos in a dropbox folder. But then the folks at work introduced dropbox for *work*, which resulted in two folders:
	1. Dropbox (Personal)
	2. Dropbox (Work)

The inclusion of a space broke nearly every coding project that was in the "Dropbox" folder. Each attempt to create a virtualenv or activate it, would lead to tremendous frustation.

So I went back to the basics:
	1. Now I do all development on the laptop hard disk. Virtual Env does not break.
	2. Added a line in my .bash_profile to quickly backup everything into my Dropbox folder (which is a symlink to the Dropbox (Personal) folder)
			rsync -av /Users/rajivjk/programming/ /Users/rajivjk/Dropbox/programming	

#### tags: python, dropbox