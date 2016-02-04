---
layout: post
title: How to install Ruby 2.0 on Ubuntu 14.04
date:   2016-01-31 
tag: ruby
---

The `ruby`'s version `Ubuntu` provides is less than 2.0 and in most cases we require greater than 2.0 like if you want to use `jekyll` theme. So here are the three ways to install it on your Ubuntu 14.04. 

You can install it using one of the methods given below

## 1. Using rbnev 
Installing with rbenv is a simple two step process. First you install rbenv, and then ruby-build:
{% highlight ruby %}
cd
git clone git://github.com/sstephenson/rbenv.git .rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

git clone git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/sstephenson/rbenv-gem-rehash.git ~/.rbenv/plugins/rbenv-gem-rehash

rbenv install 2.2.3
rbenv global 2.2.3
ruby -v
{% endhighlight %}
Now we tell Rubygems not to install the documentation for each package locally and then install Bundler
{% highlight ruby %}
echo "gem: --no-ri --no-rdoc" > ~/.gemrc
gem install bundler


{% endhighlight %}



## 2. Using rvm

The installation for rvm is pretty simple:
{% highlight ruby %}
sudo apt-get install libgdbm-dev libncurses5-dev automake libtool bison libffi-dev
curl -L https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
rvm install 2.2.3
rvm use 2.2.3 --default
ruby -v
{% endhighlight %}
Now we tell Rubygems not to install the documentation for each package locally and then install Bundler
{% highlight ruby %}
echo "gem: --no-ri --no-rdoc" > ~/.gemrc
gem install bundler

{% endhighlight %}




## 3. From Source


Arguably the least useful Ruby setup for development is installing from source, but I thought I'd give you the steps anyways:
{% highlight ruby %}
cd
wget http://ftp.ruby-lang.org/pub/ruby/2.2/ruby-2.2.3.tar.gz
tar -xzvf ruby-2.2.3.tar.gz
cd ruby-2.2.3/
./configure
make
sudo make install
ruby -v

{% endhighlight %}
Now we tell Rubygems not to install the documentation for each package locally and then install Bundler


{% highlight ruby %}
echo "gem: --no-ri --no-rdoc" > ~/.gemrc
gem install bundler

{% endhighlight %}


I hope this post will helpful to you.

Thanks for reading.



<!--
<div id="share-buttons">
    
   
    
    
    <a href="mailto:?Subject=Simple Share Buttons&amp;Body=I%20saw%20this%20and%20thought%20of%20you!%20 https://simplesharebuttons.com">
        <img src="https://simplesharebuttons.com/images/somacro/email.png" alt="Email" />
    </a>
 
   
    <a href="http://www.facebook.com/sharer.php?u=https://{{ site.baseurl }}{{ post.url | remove_first: '/' }}" target="_blank">
        <img src="https://simplesharebuttons.com/images/somacro/facebook.png" alt="Facebook" />
    </a>
    
    
    <a href="https://plus.google.com/share?url=https://simplesharebuttons.com" target="_blank">
        <img src="https://simplesharebuttons.com/images/somacro/google.png" alt="Google" />
    </a>
    
    
    <a href="http://www.linkedin.com/shareArticle?mini=true&amp;url=https://simplesharebuttons.com" target="_blank">
        <img src="https://simplesharebuttons.com/images/somacro/linkedin.png" alt="LinkedIn" />
    </a>
    
    
    
    
    <a href="javascript:;" onclick="window.print()">
        <img src="https://simplesharebuttons.com/images/somacro/print.png" alt="Print" />
    </a>
    

     
   
    <a href="https://twitter.com/share?url=https://simplesharebuttons.com&amp;text=Simple%20Share%20Buttons&amp;hashtags=simplesharebuttons" target="_blank">
        <img src="https://simplesharebuttons.com/images/somacro/twitter.png" alt="Twitter" />
    </a>
    

</div> -->



### Comments ! 

<div id="disqus_thread"></div>
<script>
/**
* RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
* LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables
*/
/*
var disqus_config = function () {
this.page.url = PAGE_URL; // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');

s.src = '//sumitsrivastava.disqus.com/embed.js';

s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript" rel="nofollow">comments powered by Disqus.</a></noscript>




<script id="dsq-count-scr" src="//sumitsrivastava.disqus.com/count.js" async></script>
<style type="text/css">
 
#share-buttons img {
width: 35px;
padding: 5px;
border: 0;
box-shadow: 0;
display: inline;
}
 
</style>



