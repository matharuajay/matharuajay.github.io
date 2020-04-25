---
toc: false
id: 2218
title: Adding URL shortner to Tweet Old Post wordpress plugin
date: 2010-03-25T10:51:03+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=2218
permalink: /adding-url-shortner-to-tweet-old-post-wordpress-plugin/
aktt_notify_twitter:
  - no
dsq_thread_id:
  - 465383699
categories:
  - PHP
  - Plugins
  - wordpress
tags:
  - adding URL shortener to Tweet Old Post
  - adding URL shortner to Tweet Old Post
  - Tweet Old Post
  - URL Shortener
---
This is small tutorial showing you how to integrate new URL shortner to [Tweet Old Post wordpress plugin](http://www.ajaymatharu.com/wordpress-plugin-tweet-old-posts/)

Make the following changes in top-admin.php file

1 &#8211; Look for the URL shortner drop down list, find the code that looks like below

<pre class="php" name="code"><label for="top_opt_url_shortener">'.__('URL Shortener Service', 'TweetOldPost').':</label>
<select id="top_opt_url_shortener" style="width: 100px;" name="top_opt_url_shortener">
		&lt;option value="is.gd">'.__('is.gd', 'TweetOldPost').'&lt;/option>
		&lt;option value="su.pr">'.__('su.pr', 'TweetOldPost').'&lt;/option>
		 &lt;option value="bit.ly">'.__('bit.ly', 'TweetOldPost').'&lt;/option>
		 &lt;option value="tr.im">'.__('tr.im', 'TweetOldPost').'&lt;/option>
		 &lt;option value="3.ly">'.__('3.ly', 'TweetOldPost').'&lt;/option>
		 &lt;option value="u.nu">'.__('u.nu', 'TweetOldPost').'&lt;/option>
		 &lt;option value="tinyurl">'.__('tinyurl', 'TweetOldPost').'&lt;/option>
	 </select>
</pre>

2 &#8211; Once you get there, add another option tag to the list like below,

<pre class="html" name="code">&lt;option value="urlshortner">'.__('urlshortner', 'TweetOldPost').'&lt;/option>
</pre>

**Note &#8211;** In the above option replace &#8216;urlshortner&#8217; with new shortner name.

Make the below changes in top-core.php file,

1 &#8211; find the function shorten_url(), and add an elseif block of new shortner api like below code,

<pre class="php" name="code">elseif ($shortener=="urlshortner") {
		$url = "http://u.nu/unu-api-simple?url={$the_url}";
		$response = send_request($url, 'GET');
	}
</pre>

**Note &#8211;** replace urlshortner with new shortner name, it should be same as in point 2 of top-admin.php changes. In the URL section change the API URL with your shortner API URL and pass the required parameters the above just have the URL parameter.

2 -Some API may require additional parameters like API key. So it will look somewhat like this,

<pre class="php" name="code">elseif ($shortener=="urlshortner") {
		$url = "http://yourshortnerapiurl/api?url={$the_url}&api=xxxxxx";
		$response = send_request($url, 'GET');
	}
</pre>

**Note &#8211;** replace urlshortner with new shortner name, it should be same as in point 2 of top-admin.php changes. In the URL section change the API URL with your shortner API URL and pass the required parameters. The above have the URL parameter and API key replace xxxxxx with your API Key value.

That&#8217;s it and you are ready to go. In case you find it difficult to implement the above code feel free to drop by a comment I&#8217;ll add it for everyone  <img src="http://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":-)" class="wp-smiley" style="height: 1em; max-height: 1em;" />and you can always drop me a mail.
