---
id: 243
title: 'Pasting into Visual Studio &#8211; Tip of week #8'
date: 2008-10-25T07:27:46+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=243
permalink: /pasting-into-visual-studio-tip-of-week-6/
ljID:
  - 47
dsq_thread_id:
  - 465387809
categories:
  - Tip of Week
  - Visual Studio
tags:
  - Tip of Week
  - Visual Studio tips
---
<p class="docText">
  <span class="docEmphBold">Don&#8217;t be limited to plain text. You can paste strings into Visual Studio as comments, string, StringBuilders, and more</span>.
</p>

<a name="visualstudiohks-CHP-2-ITERM-2260"></a>

<p class="docText">
  SmartPaster is a plug-in for Visual Studio .NET 2008 that allows text on the clipboard to be pasted in a format compatible with C# and Visual Basic code. <a name="visualstudiohks-CHP-2-ITERM-2261"></a>SmartPaster can be downloaded from <a href="http://www.box.net/shared/qn4g3ehvv4" target="_blank">here</a>.
</p>

To install it, un-zip above to:
  
Vista/2008: C:\Users\<user-name>\Documents\Visual Studio 2008\Addins
  
Earlier Windows: C:\Documents and Settings\All Users\Shared Documents\Visual Studio 2008\Addins

Then restart Visual Studio 2008 and update settings for the Add-In in the Tools menu / Add-In Manager. After downloading and installing SmartPaster, you will see a new item on the right-click (context) menu, which is shown in [Figure 2-4](http://ajaymatharu.wordpress.com/wp-admin/#visualstudiohks-CHP-2-FIG-4){.docLink}.

<p class="docText">
  <a href="http://ajaymatharu.files.wordpress.com/2008/10/paster.png"><img class="aligncenter size-full wp-image-244" title="paster" src="http://ajaymatharu.files.wordpress.com/2008/10/paster.png" alt="" width="379" height="248" /></a>
</p>

<p class="docText">
  <strong>Paste as String/StringBuilder</strong>
</p>

<p class="docText">
  Many developers like to build a <a name="visualstudiohks-CHP-2-ITERM-2266"></a><a name="visualstudiohks-CHP-2-ITERM-2267"></a>SQL statement using a tool such as Query Analyzer, for easy testing and debugging, or Microsoft Access, for quick, visual development. As simple as it is to build queries externally, putting them into code can often be a challenge, especially when the queries span multiple lines. SmartPaster eases the task of bringing external queries to code: simply copy your query to the clipboard and paste as a string or StringBuilder. For example, if you copied the following SQL to your clipboard:
</p>

<pre>SET ROWCOUNT 10

SELECT ProductName

FROM Products

ORDER BY Products.UnitPrice DESC</pre>

<p class="docText">
  then paste the code into Visual Studio using Paste As &#8211; String, you would see the following code:
</p>

<pre>@"SET ROWCOUNT 10" + Environment.NewLine +

@"SELECT ProductName" + Environment.NewLine +

@"FROM Products" + Environment.NewLine +

@"ORDER BY Products.UnitPrice DESC" + Environment.NewLine +

@""</pre>

<p class="docText">
  You could also paste this code using Paste As &#8211; StringBuilder and specify a StringBuilder name of &#8220;sqlBuilder,&#8221; and this would result in the following code:
</p>

<pre>StringBuilder sqlBuilder = new StringBuilder(141);

sqlBuilder.AppendFormat(@"SET ROWCOUNT 10{0}", Environment.NewLine);

sqlBuilder.AppendFormat(@"SELECT ProductName{0}", Environment.NewLine);

sqlBuilder.AppendFormat(@"FROM Products{0}", Environment.NewLine);

sqlBuilder.AppendFormat(@"ORDER BY Products.UnitPrice DESC");</pre>

<p class="docText">
  Like SQL statements, text displayed to the user is often developed externally, either by a copywriter, business analyst, or coder (such as myself), and requires the spellchecker within Microsoft Word. Usually, pasting such code would require going character by character, escaping quotes, and manually adding in line breaks. With SmartPaster, a quick right-click, paste-as, and your external copy is now internal without any of the normal hassle.
</p>

<p class="docText">
  In an ideal world, all messages and dialogs would be stored in an external resource file and all SQL statements would be in views and stored procedures. But in a world of deadlines and disposable microapplications, doing it the right way is often trumped by &#8220;make sure it works.&#8221;
</p>

<p class="docText">
  As we&#8217;ve seen, SmartPaster offers the option of pasting your text as a string or a StringBuilder. While the difference may seem cosmetic, there are actually appropriate times to use one over the other. The reasoning behind this is that<a name="visualstudiohks-CHP-2-ITERM-2268"></a> string literals (i.e., strings explicitly declared in your code, as opposed to those input by the user) are immutable. This means that every operation on a string, such as a concatenation or replacement, involves creating an in-memory buffer, performing the operation, creating a new string, and finally passing the old one to garbage collection.
</p>

<p class="docText">
  Knowing that, it&#8217;s fairly easy to decide whether to use a string or a StringBuilder. If the text will always be static, such as a tool tip, there will be no advantage to using a StringBuilder (even if string literals are concatenated across lines, the compiler joins them in memory). However, if the text will vary on conditions, such as a runtime error message, then there will definitely be a performance hit using a string as opposed to a StringBuilder.
</p>

<p class="docText">
  <p class="docText">
    <strong>Paste as Comment</strong>
  </p>
  
  <p class="docText">
    <a name="visualstudiohks-CHP-2-ITERM-2269"></a><a name="visualstudiohks-CHP-2-ITERM-2270"></a><a name="visualstudiohks-CHP-2-ITERM-2271"></a>Just as with strings, any text on the clipboard may be pasted as a block of comments. I&#8217;ve found this very helpful in many cases. Having instant blocks of comments makes development much easier because of the following reasons:
  </p>
  
  <ul>
    <li>
      <p class="docList">
        Business rule requirements may be pasted directly into the code for easier translation and to explain what is being done.
      </p>
    </li>
    
    <li>
      <p class="docList">
        Documentation from MSDN or other sources may be pasted in, avoiding the need to switch between the code and a browser window.
      </p>
    </li>
    
    <li>
      <p class="docList">
        When upgrading code from another platform, the legacy code can be pasted as a comment, making it easier to ensure the logic is the same.
      </p>
    </li>
  </ul>
  
  <p class="docText">
    To paste text as a comment, you simply need to copy text to your clipboard and then choose Paste As &#8211; Comment. For example, if you copied the following piece of text to your clipboard:
  </p>
  
  <pre>Call the test method to walk through this scenario and test every part.</pre>
  
  <p class="docText">
    and then pasted it into your document using Paste As &#8211; Comment, you would see the following comment added:
  </p>
  
  <pre>//Call the test method to walk through this scenario and test every part.</pre>
  
  <p class="docText">
    <p class="docText">
      <strong>Paste as Region</strong>
    </p>
    
    <p class="docText">
      When <a name="visualstudiohks-CHP-2-ITERM-2272"></a><a name="visualstudiohks-CHP-2-ITERM-2273"></a>pasting as a region, the clipboard text will simply appear between <tt>#region</tt> and <tt>#endregion</tt> tags with a region name of your choice. This feature is often helpful when organizing code within your application or pasting regions of code developed by someone else.
    </p>
    
    <p class="docText">
      First, copy a piece of code like this one to your clipboard:
    </p>
    
    <pre>private void DoSomething( )

{

    //Write Code Here

}</pre>
    
    <p class="docText">
      Then select Paste As &#8211; Region, and you will see the dialog shown in <a class="docLink" href="http://ajaymatharu.wordpress.com/wp-admin/#visualstudiohks-CHP-2-FIG-5">Figure 2-5</a>.
    </p>
    
    <p class="docText">
      <a href="http://ajaymatharu.files.wordpress.com/2008/10/region.png"><img class="aligncenter size-full wp-image-245" title="region" src="http://ajaymatharu.files.wordpress.com/2008/10/region.png" alt="" width="397" height="191" /></a>
    </p>
    
    <p class="docText">
      From this dialog, you specify the name of the region that you want to use; after you click OK, this code will be pasted into your document:
    </p>
    
    <pre>#region DoSomething Method

private void DoSomething( )

{

    //Write Code Here

}

#endregion</pre>
    
    <p class="docText">
      <p class="docText">
        <strong>Configuration</strong>
      </p>
      
      <p class="docText">
        SmartPaster offers a number of configuration options to make the add-in work best for you. The SmartPaster configuration dialog is shown in <a class="docLink" href="http://ajaymatharu.wordpress.com/wp-admin/#visualstudiohks-CHP-2-FIG-6">Figure 2-6</a> and can be accessed through Paste As &#8211; Configure.
      </p>
      
      <p>
        <a href="http://ajaymatharu.files.wordpress.com/2008/10/configuration.png"><img class="aligncenter size-full wp-image-246" title="configuration" src="http://ajaymatharu.files.wordpress.com/2008/10/configuration.png" alt="" width="450" height="261" /></a>
      </p>