---
id: 1269
title: Using ParseQueryString to get querystring values
date: 2009-06-08T00:53:30+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1269
permalink: /using-parsequerystring-to-get-querystring-values/
ljID:
  - 250
dsq_thread_id:
  - 465392450
categories:
  - .Net
  - ASP.Net
  - Visual Studio
---
Its been long I haven&#8217;t posted anything technical so just thought of sharing this with you guys, 

Following is the sample code you can use to parse your querystring and return NameCollectionValue

<pre name="code" class="c-sharp">protected void Page_Load(object sender, EventArgs e)
  {
    String currurl = HttpContext.Current.Request.RawUrl;
    String querystring = null ;

    // Check to make sure some query string variables
    // exist and if not add some and redirect.
    int iqs = currurl.IndexOf('?');
    if (iqs == -1)
    {
      String redirecturl = currurl + "?var1=1&var2=2+2%2f3&var1=3";
      Response.Redirect(redirecturl, true); 
    }
    // If query string variables exist, put them in
    // a string.
    else if (iqs >= 0)
    {
      querystring = (iqs &lt; currurl.Length - 1) ? currurl.Substring(iqs + 1) : String.Empty;
    }

    // Parse the query string variables into a NameValueCollection.
    NameValueCollection qscoll = HttpUtility.ParseQueryString(querystring);

    // Iterate through the collection.
    StringBuilder sb = new StringBuilder("<br />");
    foreach (String s in qscoll.AllKeys)
    {
      sb.Append(s + " - " + qscoll[s] + "<br />");
    }

    // Write the result to a label.
    ParseOutput.Text = sb.ToString();

  }

</pre>

This is the front end code ,

<pre name="code" class="html"></pre>

Hope this helps <img src="http://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />