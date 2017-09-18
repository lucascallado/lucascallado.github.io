---
layout: post
title: 'Installing Node.js, Bower, Polymer, and Google Analytics Web Components &#8212; A step-by-step guide'
author: Lucas Callado
categories:
  - Web Development
---
# Installing Node.js, Bower, Polymer, and Google Analytics Web Components &#8212; A step-by-step guide

Run as root Linux:

<pre class="lang:default decode:true ">curl --silent --location https://rpm.nodesource.com/setup | bash -</pre>

Then install, as root:

<pre class="lang:default decode:true ">yum -y install nodejs</pre>

Upgrade npm to the latest version:

<pre class="lang:default decode:true ">npm –g install npm@latest</pre>

Install Bower:

<pre class="lang:default decode:true ">npm –g install bower</pre>

Install Git

<pre class="lang:default decode:true ">yum install git</pre>

&nbsp;

Change Bower settings to execute with superuser permissions

<pre class="lang:default decode:true ">bower --allow-root init</pre>

The previous command will generate a basic bower.json file. Answer all necessary questions with information about your application.

Install Polymer

<pre class="lang:default decode:true ">bower --allow-root install --save Polymer/polymer#^1.2.0</pre>

&nbsp;

Bower adds a bower_components/ folder in the root of your project and fills it with Polymer and its dependencies.

Install Google Analytics &#8212;- Web Components

<pre class="lang:default decode:true ">bower --allow-root install --save GoogleWebComponents/google-analytics</pre>

&nbsp;

After everything is install your folder should look like this:

<a href="http://lucascallado.com/wp-content/uploads/2016/01/ga.png"  rel="lightbox[89] attachment wp-att-90"><img class="alignnone size-medium wp-image-90" src="http://lucascallado.com/wp-content/uploads/2016/01/ga-300x167.png" alt="ga" width="300" height="167" srcset="http://lucascallado.com/wp-content/uploads/2016/01/ga-300x167.png 300w, http://lucascallado.com/wp-content/uploads/2016/01/ga.png 544w" sizes="(max-width: 300px) 100vw, 300px" /></a>

Here is a sample code for a Google Analytics data:

<pre class="lang:default decode:true ">&lt;google-signin client-id="YOUR_CLIENT_ID_HERE"&gt;&lt;/google-signin&gt;
&lt;google-analytics-dashboard&gt;
  &lt;google-analytics-chart type="pie" ids="ga:YOUR_ID" metrics="ga:sessions" dimensions="ga:deviceCategory" sort="-ga:sessions" start-date="yesterday" max-results="7"&gt;
  &lt;/google-analytics-chart&gt;
&lt;/google-analytics-dashboard&gt;</pre>

&nbsp;

&nbsp;
