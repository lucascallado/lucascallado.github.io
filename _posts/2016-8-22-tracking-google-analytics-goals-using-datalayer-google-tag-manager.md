---
layout: post
title: 'Tracking Google Analytics Goals using dataLayer on Google Tag Manager'
author: Lucas Callado
categories:
  - JavaScript
  - Web Development
---
# Tracking Google Analytics Goals using dataLayer on Google Tag Manager

## The goal of this article is to provide an alternative to the click action with JavaScript such as _`ga('send', 'event', 'category', 'action', 'label')`_ that is not available/defined through Google Tag Manager when creating a Google Analytics tag.

Creating a _ga_ call on your code (webpage) to send data back to Google Analytics will generate an error like: _ga is not defined_.

The alternative to this problem is to create a dataLayer structure and push that data through the existing structure that Google Tag Manager provides.

[Google Tag Manager](https://www.google.com/analytics/tag-manager/) (GTM) has a built-in structure called [**dataLayer**](https://developers.google.com/tag-manager/devguide). It can be used to push data into [Google Analytics](https://analytics.google.com/) Goals.

The script tag for Google Tag Manager looks like the following &#8212; except that you need to use your GTM ID &#8212;  and the **dataLayer** variable can be found in the code.

<pre class="lang:xhtml decode:true ">&lt;!-- Google Tag Manager --&gt;
&lt;noscript&gt;&lt;iframe src="//www.googletagmanager.com/ns.html?id=GTM-YOUR_ID"
height="0" width="0" style="display:none;visibility:hidden"&gt;&lt;/iframe&gt;&lt;/noscript&gt;
&lt;script&gt;(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'//www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-YOUR_ID');&lt;/script&gt;
&lt;!-- End Google Tag Manager --&gt;</pre>

The next step is to create a default Google Analytics Tag in GTM. The Track Type should be **Event**. In addition to that, you will need to create specific variables to be used as parameters to configure the tag &#8212; Parameters are &#8220;Category&#8221;, &#8220;Action&#8221;, and &#8220;Label&#8221;.

<a href="/images/GTM-01.png" rel="lightbox[148]"><img class="size-medium wp-image-158 aligncenter" src="/images/GTM-01-300x224.png" alt="GTM-01" width="300" height="224" srcset="/images/GTM-01-300x224.png 300w, /images/GTM-01-768x573.png 768w, /images/GTM-01-1024x764.png 1024w, /images/GTM-01.png 1228w" sizes="(max-width: 300px) 100vw, 300px" /></a>

These **Data Layer Variables** can be created as follows &#8212; one for each parameter (**category**, **action**, **label** &#8212; all lower case):

<a href="/images/GTM-09.png" rel="lightbox[148]"><img class="size-medium wp-image-159 aligncenter" src="/images/GTM-09-300x173.png" alt="GTM-09" width="300" height="173" srcset="/images/GTM-09-300x173.png 300w, /images/GTM-09-768x442.png 768w, /images/GTM-09.png 958w" sizes="(max-width: 300px) 100vw, 300px" /></a>

The next step is to create a **Trigger** for the Event

<a href="/images/GTM-02.png" rel="lightbox[148]"><img class="size-medium wp-image-160 aligncenter" src="/images/GTM-02-300x163.png" alt="GTM-02" width="300" height="163" srcset="/images/GTM-02-300x163.png 300w, /images/GTM-02-768x418.png 768w, /images/GTM-02.png 1022w" sizes="(max-width: 300px) 100vw, 300px" /></a>

Choose &#8220;**Custom Event**&#8220;. I recommend using the same **Title** for **Trigger Name** and **Event Name**. In my case, **Event-NAME-Here**

<a href="/images/GTM-03.png" rel="lightbox[148]"><img class="size-medium wp-image-154 aligncenter" src="/images/GTM-03-300x158.png" alt="GTM-03" width="300" height="158" srcset="/images/GTM-03-300x158.png 300w, /images/GTM-03-768x404.png 768w, /images/GTM-03-1024x539.png 1024w, /images/GTM-03.png 1028w" sizes="(max-width: 300px) 100vw, 300px" /></a>

Now, you will see your new Trigger associated to your new Google Analytics Tag. Go ahead and **Save** your tag.

You have completed all the steps on Google Tag Manager. Let&#8217;s jump to Google Analytics to associate this tag to a new **Google Analytics Goal**.

Go to Google Analytics Admin &#8212; on a View that you want to setup this Goal.

<a href="/images/GTM-04.png" rel="lightbox[148]"><img class="size-full wp-image-153 aligncenter" src="/images/GTM-04.png" alt="GTM-04" width="246" height="132" /></a>

Hit +New Goal

<a href="/images/GTM-05.png" rel="lightbox[148]"><img class="size-medium wp-image-152 aligncenter" src="/images/GTM-05-267x300.png" alt="GTM-05" width="267" height="300" srcset="/images/GTM-05-267x300.png 267w, /images/GTM-05.png 685w" sizes="(max-width: 267px) 100vw, 267px" /></a>

Select &#8220;**Custom**&#8221;

<a href="/images/GTM-06.png" rel="lightbox[148]"><img class="size-medium wp-image-151 aligncenter" src="/images/GTM-06-300x207.png" alt="GTM-06" width="300" height="207" srcset="/images/GTM-06-300x207.png 300w, /images/GTM-06-230x160.png 230w, /images/GTM-06.png 687w" sizes="(max-width: 300px) 100vw, 300px" /></a>

Enter the **Goal Name** and Selec Type &#8220;**Event**&#8221;

<a href="/images/GTM-07.png" rel="lightbox[148]"><img class="size-medium wp-image-150 aligncenter" src="/images/GTM-07-300x284.png" alt="GTM-07" width="300" height="284" srcset="/images/GTM-07-300x284.png 300w, /images/GTM-07.png 701w" sizes="(max-width: 300px) 100vw, 300px" /></a>

Now you will have to define the &#8220;**Category Name**&#8220;, &#8220;**Action Name**&#8220;, and &#8220;**Label Name**&#8220;. This will be used on the **dataLayer** structure that is built through the JavaScript on the **Conversion Page**.

Following is the **dataLayer** code that needs to be added to a Landing Page with a conversion Form of any kind. Examples of marketing conversions forms are Free Trial and Premium Content like White Papers, Webinars, Brochures, Technical Videos, and so on.

<pre class="lang:js decode:true">&lt;script&gt;
 dataLayer.push({
                'event':'Event-NAME-Here',
                'category':'Category-NAME-Here',
                'action': 'Action-NAME-Here',
                'label': 'Label-NAME-Here'
 });
&lt;/script&gt;</pre>

Conversion Pages are capturing personal information. From a business standpoint, sales and marketing cycles are initiated through this online activity that captures name, email, company, location, and any other relevant information that leads into a future contact or prospect.

In my specific case, [Marketo](https://www.marketo.com/) is the [marketing automation tool](https://en.wikipedia.org/wiki/Marketing_automation) of choice. You can also build your own set of conversion forms and custom functions to validate fields and submit forms to your back-end.

For that, it is recommended to add a validation to make sure that you are pushing the **dataLayer** structure after the visitor submits a specific form.

<pre class="lang:js decode:true">&lt;script&gt;
MktoForms2.whenReady(function (form) {
  form.onSuccess(function(values, followUpUrl) {
    window.alert('Hello World');
    dataLayer.push({
                'event':'Event-NAME-Here',
                'category':'Category-NAME-Here',
                'action': 'Action-NAME-Here',
                'label': 'Label-NAME-Here'
 });
});
&lt;/script&gt;</pre>

The &#8216;Hello World&#8217; is just a flag to indicate the form has been submitted on success and the **dataLayer** is now ready to push this event back to Google Analytics.

Note: If everything is working as expected your Goal will show up on Google Analytics. You will see the new **Event** coming through your Google Analytics **Real Time -> Events **data.

**Event Category** and **Event Action** will match with the information submitted by the **dataLayer.push** after the form gets submitted.

<a href="/images/GTM-10.png" rel="lightbox[148]"><img class="size-medium wp-image-161 aligncenter" src="/images/GTM-10-300x89.png" alt="GTM-10" width="300" height="89" srcset="/images/GTM-10-300x89.png 300w, /images/GTM-10-768x228.png 768w, /images/GTM-10.png 832w" sizes="(max-width: 300px) 100vw, 300px" /></a>

&nbsp;
