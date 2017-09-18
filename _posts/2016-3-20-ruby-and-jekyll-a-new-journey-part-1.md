---
layout: post
title: 'Ruby and Jekyll &#8212; A new journey part 1'
author: Lucas Callado
categories:
  - Web Development
---

# Ruby and Jekyll &#8212; A new journey part 1

## Lately I&#8217;ve been learning a lot about a new stack &#8212; Ruby, Node.js, Python, and Jekyll&#8230; and I wanted to share a few tips on how I got my system ready for development. For this specific environment I&#8217;m using OS X. Here is my installation log &#8212; step-by-step:

1. Homebrew (OS X) &#8212; http://brew.sh/

<pre class="lang:default decode:true">/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"</pre>

To verify version, check installation status, or update &#8212; respectively:

<pre class="lang:default decode:true">$ brew --version

$ brew doctor

$ brew update</pre>

Run:

<pre class="lang:default decode:true">brew install wget
</pre>

Homebrew command library (package): [BrewFormulas.org](http://brewformulas.org/)

2. Ruby &#8212; https://www.ruby-lang.org/en/

<pre class="lang:default decode:true">brew install ruby</pre>

Install RubyGems

Download the gem file at:

https://rubygems.org/rubygems/rubygems-update-2.5.2.gem

<pre class="lang:default decode:true">gem install rubygems-update-2.5.2.gem
</pre>

Install Imagemagick

<pre class="lang:default decode:true">brew install imagemagick</pre>

3. Node.js &#8212; https://nodejs.org/en/

<pre class="lang:default decode:true">brew install node</pre>

Display node version, and display npm version &#8212; respectively:

<pre class="lang:default decode:true">node -v

npm -v</pre>

4. Python &#8212; https://www.python.org/

<pre class="lang:default decode:true">brew install python</pre>

5. Jekyll &#8212; https://jekyllrb.com/

<pre class="lang:default decode:true">gem install jekyll</pre>

&nbsp;

Build and Serve website:

<pre class="lang:default decode:true">jekyll build

jekyll serve
</pre>

Navigate to <http://127.0.0.1:4000/>

&nbsp;

Good reference article: <a href="https://scotch.io/tutorials/getting-started-with-jekyll-plus-a-free-bootstrap-3-starter-theme" target="_blank">Click Here.</a>

On Part 2 I will talk about how to build a simple website/application/blog using Ruby and Jekyll. Cheers!

&nbsp;
