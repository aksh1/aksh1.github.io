---
layout: post
title:  "How to control different version of any software in git?"
date:   2016-02-04 12:00:00
categories: git
tags: [github]
---

What is "version control" ?
 Version control is a system that records changes to a file or set of files over time so that we can recall specific versions later.
 For example the posts of this blog is version controlled by git ,if in future i want to revert the changes i made earlier can be done only because of the distributed version control system Git.

Before we start furthur i assume that you are all have an account on Github and have git installed on your local machine.
So lets start first you create a new repository(in this case my-repo) and add README.md file in it.
And Follow following steps:

 + Clone the repo to your local machine by using `git clone`  command.
{% highlight ruby %}
git clone https://github.com/aksh1/my-repo.git
{% endhighlight %}

After cloning a folder is created of name `my-repo`.Here you can code or copy your precoded code.

 + Add your  files in the repo.I here create a new python file hello.py 
	{% highlight ruby %}
	 $ sudo gedit hello.py
{% endhighlight %}

 + Check  the status of your repo by using `git status` command.
	{% highlight ruby %}
	$ git staus
{% endhighlight %}
+ Now add the changes by using `git add -A`  command.
	{% highlight ruby %}
	$ git add -A
{% endhighlight %}
+ Commit your changes 
	{% highlight ruby %}

   git commit -m "my first commit"
{% endhighlight %}
 `-m` is a delimeter used to give message.

Vola! we are now ready to set our first version of our repo , this can be done by git tagging. 

+ Tag your commit for version
	{% highlight ruby %}
    $ git tag -a v1.0 -m "version 1"
{% endhighlight %}
Now you have your first version of repository and you can check the number of versions you have by using `git tag` command.
+ Push your first version on your github account 
	{% highlight ruby %}

   $ git push origin master
{% endhighlight %}

Now develop a new version of this repo . Here i just added a new file abc.py and again follow the `add-commit-push` steps.
{% highlight ruby %}
	 $ sudo gedit abc.py
{% endhighlight %}


+ Add the changes
{% highlight ruby %}
 $ git add -A 
{% endhighlight %}
+ Check the status of your repository to confirm your addtion.
{% highlight ruby %}
 $ git status
{% endhighlight %}
+ Commit the changes you made.
{% highlight ruby %}
  $ git commit -m "abc.py added
{% endhighlight %}


 Suppose you want to declare this as your version v1.02.
+ Declare your version v1.02.
{% highlight ruby %}
 git tag -a v1.02 -m "version2"
{% endhighlight %}


+ Again push your repository on github.By default, the git push command doesn’t transfer tags to remote servers. You will have to explicitly push tags to a shared server after you have created them. This process is just like sharing remote branches – you can run `git push origin [tagname]`.
{% highlight ruby %}
   $ git push origin v1.02.
Username for 'https://github.com': aksh1
Password for 'https://aksh1@github.com': 
Counting objects: 1, done.
Writing objects: 100% (1/1), 168 bytes | 0 bytes/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To https://github.com/aksh1/my-repo.git
 * [new tag]         v1.02 -> v1.02

{% endhighlight %}


You can see the tag data along with the commit that was tagged by using the `git show` command

{% highlight ruby %}
$ git show
commit f9e2a8d915be3a45600a545bd2f5edbfd7be43b9
Author: aksh1 <srivastava.sumi3@gmail.com>
Date:   Wed Feb 3 14:30:34 2016 +0530

    abc.py added

diff --git a/abc.py b/abc.py
new file mode 100644
index 0000000..8b3a2b8
--- /dev/null
+++ b/abc.py
@@ -0,0 +1 @@
+print "this is  vwersion v1.02"
diff --git a/abc.py~ b/abc.py~
new file mode 100644
index 0000000..c9ce317
--- /dev/null
+++ b/abc.py~
@@ -0,0 +1 @@
+print "this is in new vwersion"

{% endhighlight %}

   



Now you have two version of your repository one of them is in your working directoy and one is in your .git repository(a git database you can say).

Suppose there is some bugs in your version2 and you want to put version1 of your repository in your working directory, you can create a new branch at a specific tag with `git checkout -b [branchname] [tagname]`:
{% highlight ruby %}
$ git checkout -b version2 v1.0
Switched to a new branch 'version1'
{% endhighlight %}


Of course if you do this and do a commit, your version2 branch will be slightly different than your v1.0 tag since it will move forward with your new changes, so do be careful.

I think now you understand the handling of versions by git and if you need any help or any doubt feel free to comment in comment box.






