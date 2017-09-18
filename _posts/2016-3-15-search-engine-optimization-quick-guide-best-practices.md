---
layout: post
title: 'Search Engine Optimization &#8211; Quick guide &#038; Best practices'
author: Lucas Callado
categories:
  - Web-Development
---
# Search Engine Optimization &#8211; Quick guide &#038; Best practices

I’ve been collecting some info on SEO. I just wanted to share all what I think is a very valuable info and references:

Optimal Format

<a href="http://www.example.com/category-keyword/subcategory-keyword/primary-keyword.html" target="_blank">http://www.foo.io/category-keyword/subcategory-keyword/primary-keyword.html</a>

&nbsp;

A well-crafted <a href="https://moz.com/learn/seo/url" target="_blank">URL</a> should semantically make sense.

URLs with duplicate content should have canonical URLs specified for them; there should be no confusing redirects on the site (two maximum redirects).

The word “canonical” simply means “preferred” in this case. Picking a preferred (canonical) URL becomes necessary when search engines see duplicate pages on your site.

Add the following code to the <head> section of the page. Use absolute paths rather than relative &#8212; http://foo.io/*

<pre class="lang:default decode:true">&lt;link rel="canonical" href="#" /&gt;</pre>

Google @ “<a href="https://support.google.com/webmasters/answer/139066?hl=en&rd=1" target="_blank">Use Canonical URLs</a>”

&nbsp;

When search engines arrive on a page with a canonical tag, they attribute the page to the canonical URL, regardless of the URL they used to reach the page.

So, for example, if a bot reached the above page using the URL http://foo.io/index.html, the search engine would not index the additional, non-canonical URL.

Typically, it seems that inbound link-juice is also passed through the canonical tag.

&nbsp;

Underscores, while legal, are problematic for SEO. It’s an issue search engines have always dealt with but never solved.

Search engines see underscores as connectors. Ex: blue\_doll = blue\_doll, and blue-doll = blue doll

To separate words, use dashes.

Not recommended characters on URLs:

<table>
  <tr>
    <td width="151">
      Space
    </td>

    <td width="151">
      %20
    </td>
  </tr>

  <tr>
    <td width="151">
      Quotation marks
    </td>

    <td width="151">
      %22
    </td>
  </tr>

  <tr>
    <td width="151">
      <
    </td>

    <td width="151">
      %3C
    </td>
  </tr>

  <tr>
    <td width="151">
      >
    </td>

    <td width="151">
      %3E
    </td>
  </tr>

  <tr>
    <td width="151">
      #
    </td>

    <td width="151">
      %23
    </td>
  </tr>

  <tr>
    <td width="151">
      Percentage
    </td>

    <td width="151">
      %25
    </td>
  </tr>
</table>

&nbsp;

For the discussion on case sensitive URLs and SEO the rule of thumb is to keep everything lowercase, unless there is intent for the capitalization.

For the discussion on sub-folders the rule of thumb is to keep things clean, try to have the least possible number of sub-folders. But keep in mind that a well-structured website three won’t make a bad impact on rankings.

&nbsp;

Create an XML Sitemap

This helps search engines find your site’s pages more easily; Use Google Developers Console (former Google Webmaster Tools), and Bing Webmaster Tools.

Search engines can use the Sitemap as a reference when choosing canonical URLs on your site. Create a Sitemap structure for each language on the site (e.g. sitemap-FR.xml, sitemap-DE.xml, sitemap-ES.xml, and so on) and reference those files from a main sitemap file (sitemap.xml).

**sitemap.xml**

<pre class="lang:default decode:true">&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;sitemapindex xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"&gt;
&lt;sitemap&gt;&lt;loc&gt;http://foo.io/sitemap-EN.xml&lt;/loc&gt;&lt;lastmod&gt;2014-10-28&lt;/lastmod&gt;&lt;/sitemap&gt;
&lt;sitemap&gt;&lt;loc&gt;http://foo.io/sitemap-FR.xml&lt;/loc&gt;&lt;lastmod&gt;2014-10-28&lt;/lastmod&gt;&lt;/sitemap&gt;
&lt;sitemap&gt;&lt;loc&gt;http://foo.io/sitemap-DE.xml&lt;/loc&gt;&lt;lastmod&gt;2014-10-28&lt;/lastmod&gt;&lt;/sitemap&gt;
&lt;sitemap&gt;&lt;loc&gt;http://foo.io/sitemap-IT.xml&lt;/loc&gt;&lt;lastmod&gt;2014-10-28&lt;/lastmod&gt;&lt;/sitemap&gt;
&lt;sitemap&gt;&lt;loc&gt;http://foo.io/sitemap-ES.xml&lt;/loc&gt;&lt;lastmod&gt;2014-10-28&lt;/lastmod&gt;&lt;/sitemap&gt;
&lt;/sitemapindex&gt;
</pre>

**sitemap-EN.xml**

<pre class="lang:default decode:true">&lt;?xml version='1.0' encoding='UTF-8'?&gt;
&lt;urlset xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://www.sitemaps.org/schemas/sitemap/0.9 http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd"
        xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"
        xmlns:example="http://www.example.com/schemas/example_schema"&gt;
  &lt;url&gt;
    &lt;loc&gt;http://foo.io/en/index.html&lt;/loc&gt;
    &lt;lastmod&gt;2014-10-15&lt;/lastmod&gt;
    &lt;changefreq&gt;monthly&lt;/changefreq&gt;
    &lt;priority&gt;0.7&lt;/priority&gt;
  &lt;/url&gt;
  &lt;url&gt;
    &lt;loc&gt;http://foo.io/en/another-page.html&lt;/loc&gt;
    &lt;lastmod&gt;2014-09-17&lt;/lastmod&gt;
    &lt;changefreq&gt;monthly&lt;/changefreq&gt;
    &lt;priority&gt;0.7&lt;/priority&gt;
  &lt;/url&gt;
&lt;/urlset&gt;
</pre>

Regardless of how smart you are to trick search engines with strategies like <a href="https://support.google.com/webmasters/answer/66358?hl=en" target="_blank">keyword stuffing</a> it all comes down to content. Make relevant content very measurable.

It&#8217;s all about developing relevant and comprehensive content for users dealing with more than just one aspect of a certain topic.

The conclusion for the basics of SEO is also understanding that a low quality blog post once a week is far less valuable than collecting details on a single subject for a month and putting something outstanding out for readers to consume.

I keep an excellent article for my own reference:

**Why Quality Content Focuses on Topics, not Keywords** @ <a href="https://moz.com/blog/searchmetrics-ranking-factors-2014" target="_blank">https://moz.com/blog/searchmetrics-ranking-factors-2014</a>

Here is his conclusion that I agree 100%.

“Don&#8217;t build landing pages for single keywords. And don&#8217;t build landing pages for search engines, either. Focus on topics related to your website/content/niche/product and try to write the best content for these topics and subtopics. Create landing pages dealing with several, interdependent aspects of main topics and write comprehensive texts **using semantically closely related terms**. This is how you can optimize the user experience as well as your rankings…”

&nbsp;
