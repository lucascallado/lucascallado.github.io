---
layout: post
title: 'Google Web Components a Polymer approach — A step-by-step guide Part 2'
author: Lucas Callado
categories:
  - Web Development
---
# Google Web Components a Polymer approach — A step-by-step guide Part 2

## This post is to explain how to obtain a Google API &#8212; Client ID &#8212; to run the Google Web Components utilizing the Polymer code.

This is the continuation of my previous blog post [HERE](http://lucascallado.com/2016/01/26/installing-node-js-bower-polymer-and-google-analytics-web-components-a-step-by-step-guide/).

<pre class="lang:default decode:true">&lt;google-signin client-id="YOUR_CLIENT_ID_HERE"&gt;&lt;/google-signin&gt;
&lt;google-analytics-dashboard&gt;
  &lt;google-analytics-chart type="pie" ids="ga:YOUR_ID" metrics="ga:sessions" dimensions="ga:deviceCategory" sort="-ga:sessions" start-date="yesterday" max-results="7"&gt;
  &lt;/google-analytics-chart&gt;
&lt;/google-analytics-dashboard&gt;</pre>

First go to:

**<a href="https://console.developers.google.com/" target="_blank">Google Cloud Platform</a>**

_https://console.developers.**google**.com/_

After you login, you will see the following screen. Click on &#8220;**Use Google APIs**&#8220;.

<a href="http://lucascallado.com/wp-content/uploads/2016/03/GDC_01.png"  rel="lightbox[120] attachment wp-att-121"><img class="alignnone size-medium wp-image-121" src="http://lucascallado.com/wp-content/uploads/2016/03/GDC_01-300x196.png" alt="Google Developers Console" width="300" height="196" srcset="http://lucascallado.com/wp-content/uploads/2016/03/GDC_01-300x196.png 300w, http://lucascallado.com/wp-content/uploads/2016/03/GDC_01.png 606w" sizes="(max-width: 300px) 100vw, 300px" /></a>

Now, click on &#8220;**Enable**&#8221; to start the API Project.

<a href="http://lucascallado.com/wp-content/uploads/2016/03/GDC_02.png"  rel="lightbox[120] attachment wp-att-122"><img class="alignnone size-medium wp-image-122" src="http://lucascallado.com/wp-content/uploads/2016/03/GDC_02-300x283.png" alt="GDC_02" width="300" height="283" srcset="http://lucascallado.com/wp-content/uploads/2016/03/GDC_02-300x283.png 300w, http://lucascallado.com/wp-content/uploads/2016/03/GDC_02.png 450w" sizes="(max-width: 300px) 100vw, 300px" /></a>

A few seconds later, you will be able to create a new credential for your &#8212; Client ID &#8212; variable.

<a href="http://lucascallado.com/wp-content/uploads/2016/03/GDC_03.png"  rel="lightbox[120] attachment wp-att-123"><img class="alignnone size-medium wp-image-123" src="http://lucascallado.com/wp-content/uploads/2016/03/GDC_03-300x23.png" alt="GDC_03" width="300" height="23" srcset="http://lucascallado.com/wp-content/uploads/2016/03/GDC_03-300x23.png 300w, http://lucascallado.com/wp-content/uploads/2016/03/GDC_03-768x58.png 768w, http://lucascallado.com/wp-content/uploads/2016/03/GDC_03.png 917w" sizes="(max-width: 300px) 100vw, 300px" /></a>

Follow the step-by-step process filling all the necessary field. Click on &#8220;**What credentials do I need?**&#8221; to continue.

<a href="http://lucascallado.com/wp-content/uploads/2016/03/GDC_04.png"  rel="lightbox[120] attachment wp-att-124"><img class="alignnone size-medium wp-image-124" src="http://lucascallado.com/wp-content/uploads/2016/03/GDC_04-271x300.png" alt="GDC_04" width="271" height="300" srcset="http://lucascallado.com/wp-content/uploads/2016/03/GDC_04-271x300.png 271w, http://lucascallado.com/wp-content/uploads/2016/03/GDC_04.png 507w" sizes="(max-width: 271px) 100vw, 271px" /></a>

Here you will create an **OAuth 2.0 client ID**. Give it a name. If you are still running the project locally in your machine, you still can use http://localhost and any specific web server ports &#8212; in my case port 4000.

<a href="http://lucascallado.com/wp-content/uploads/2016/03/GDC_05.png"  rel="lightbox[120] attachment wp-att-125"><img class="alignnone size-medium wp-image-125" src="http://lucascallado.com/wp-content/uploads/2016/03/GDC_05-208x300.png" alt="GDC_05" width="208" height="300" srcset="http://lucascallado.com/wp-content/uploads/2016/03/GDC_05-208x300.png 208w, http://lucascallado.com/wp-content/uploads/2016/03/GDC_05.png 501w" sizes="(max-width: 208px) 100vw, 208px" /></a>

Continue with steps 3 and 4, and download the JSON file for your records. You are done!

Your client ID is the **Client\_ID\_Hashtag**._apps.googleusercontent.com_

Keep in mind that you can always manage your Google API Credentials through the dashboard.

<a href="http://lucascallado.com/wp-content/uploads/2016/03/GDC_06.png"  rel="lightbox[120] attachment wp-att-126"><img class="alignnone size-medium wp-image-126" src="http://lucascallado.com/wp-content/uploads/2016/03/GDC_06-300x74.png" alt="GDC_06" width="300" height="74" srcset="http://lucascallado.com/wp-content/uploads/2016/03/GDC_06-300x74.png 300w, http://lucascallado.com/wp-content/uploads/2016/03/GDC_06-768x188.png 768w, http://lucascallado.com/wp-content/uploads/2016/03/GDC_06-1024x251.png 1024w, http://lucascallado.com/wp-content/uploads/2016/03/GDC_06.png 1194w" sizes="(max-width: 300px) 100vw, 300px" /></a>

The best part of all is here:

<a href="https://ga-dev-tools.appspot.com/query-explorer/" target="_blank">https://ga-dev-tools.appspot.com/query-explorer/</a>

Allow the Query Explorer to access your GA data and you will be able to fill the remaining variable on the <google-analytics-dashboard> block of code.

<pre class="lang:default decode:true">&lt;google-analytics-chart type="pie" ids="ga:YOUR_ID" metrics="ga:sessions" dimensions="ga:deviceCategory" sort="-ga:sessions" start-date="yesterday" max-results="7"&gt;</pre>

Now you will be able to get &#8220;YOUR_ID&#8221;, and create your data tile based on metrics that you want to display.

Here is another piece of metric that you can add in another block of <google-analytics-dashboard>.

<pre class="lang:default decode:true ">&lt;google-analytics-chart
  type="area"
  metrics="ga:sessions"
  dimensions="ga:date"
  startDate="30daysAgo"
  endDate="yesterday"&gt;
&lt;/google-analytics-chart&gt;</pre>

A full Polymer Elements Demo can be found <a href="https://elements.polymer-project.org/elements/google-analytics?view=demo:demo/index.html" target="_blank">HERE</a>.
