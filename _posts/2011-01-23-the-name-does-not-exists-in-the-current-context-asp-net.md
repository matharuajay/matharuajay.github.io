---
toc: false
id: 2548
title: The name does not exists in the current context asp.net
date: 2011-01-23T22:20:25+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=2548
permalink: /the-name-does-not-exists-in-the-current-context-asp-net/
dsq_thread_id:
  - 465385530
categories:
  - .Net
  - ASP.Net
  - Visual Studio
tags:
  - asp.net control does not exists
  - asp.net control does not exists in current context
  - asp.net control does not exists in the current context
  - asp.net control error
  - asp.net server control error
  - control does not exists in current context
  - control does not exists in the current context
  - name does not exists in current context
  - the name does not exists in the corrent context
---
Many a times while writing a code we get this error which says, &#8220;The name <control> does not exists in the current context&#8221;. This is because the code behind file is not able to find the control being added to your aspx file.

<div id="attachment_2569" style="width: 726px" class="wp-caption aligncenter">
  <a rel="attachment wp-att-2569" href="https://www.ajaymatharu.com/the-name-does-not-exists-in-the-current-context-asp-net/control_does_not_exists_in_current_context/"><img class="size-full wp-image-2569 " title="Control does not exists in current context" src="https://blog.ajaymatharu.com/wp-content/uploads/2011/01/control_does_not_exists_in_current_context.png" alt="Control does not exists in current context" width="716" height="444" srcset="https://blog.ajaymatharu.com/wp-content/uploads/2011/01/control_does_not_exists_in_current_context-300x186.png 300w, https://blog.ajaymatharu.com/wp-content/uploads/2011/01/control_does_not_exists_in_current_context.png 716w" sizes="(max-width: 716px) 100vw, 716px" /></a>
  
  <p class="wp-caption-text">
    Control does not exists in current context
  </p>
</div>

There are three possible solutions for this error,

1 &#8211; There are two classes with same name. Possibly you have renamed a page and created a new one, but you did not changed the name in the cs file. So make sure you have only one file with this name in your project. There may be two files with different name but same class name this may create problems.

2 &#8211; Multiple web.config files in your project. Make sure you have only one web.config file in your project. However you can have mulitple web.config files in your project but that has to be in particular format <a title="Working with mulitple web.config files" href="https://www.codeproject.com/KB/aspnet/multipleWebConfig.aspx" target="_blank">check here</a>.

3 &#8211; The designer file is not refreshed.

<div id="attachment_2570" style="width: 700px" class="wp-caption aligncenter">
  <a rel="attachment wp-att-2570" href="https://www.ajaymatharu.com/the-name-does-not-exists-in-the-current-context-asp-net/control_does_not_exists_in_current_context_designer/"><img class="size-full wp-image-2570" title="control does not exists in current context designer file" src="https://blog.ajaymatharu.com/wp-content/uploads/2011/01/control_does_not_exists_in_current_context_designer.png" alt="control does not exists in current context designer file" width="700" height="508" /></a>
  
  <p class="wp-caption-text">
    control does not exists in current context designer file
  </p>
</div>

<p style="text-align: center;">
  <p>
    In this case you have to delete the existing designer file
  </p>
  
  <p style="text-align: center;">
    <div id="attachment_2571" style="width: 314px" class="wp-caption aligncenter">
      <a rel="attachment wp-att-2571" href="https://www.ajaymatharu.com/the-name-does-not-exists-in-the-current-context-asp-net/control_does_not_exists_in_current_context_designer1/"><img class="size-full wp-image-2571  " title="delete web page designer file" src="https://blog.ajaymatharu.com/wp-content/uploads/2011/01/control_does_not_exists_in_current_context_designer1.png" alt="delete web page designer file" width="304" height="513" /></a>
      
      <p class="wp-caption-text">
        delete web page designer file
      </p>
    </div>
    
    <p>
      After deleting the file right click on the page, in this case default.aspx and select &#8220;Convert to web application&#8221;
    </p>
    
    <div id="attachment_2572" style="width: 549px" class="wp-caption aligncenter">
      <a rel="attachment wp-att-2572" href="https://www.ajaymatharu.com/the-name-does-not-exists-in-the-current-context-asp-net/control_does_not_exists_in_current_context_designer2/"><img class="size-full wp-image-2572 " title="regenerate designer file - convert page to web application" src="https://blog.ajaymatharu.com/wp-content/uploads/2011/01/control_does_not_exists_in_current_context_designer2.png" alt="regenerate designer file - convert page to web application" width="539" height="536" srcset="https://blog.ajaymatharu.com/wp-content/uploads/2011/01/control_does_not_exists_in_current_context_designer2-300x298.png 300w, https://blog.ajaymatharu.com/wp-content/uploads/2011/01/control_does_not_exists_in_current_context_designer2.png 539w" sizes="(max-width: 539px) 100vw, 539px" /></a>
      
      <p class="wp-caption-text">
        regenerate designer file - convert page to web application
      </p>
    </div>
    
    <p>
      Once you convert it will prompt for confirmation just select yes
    </p>
    
    <div id="attachment_2573" style="width: 541px" class="wp-caption aligncenter">
      <a rel="attachment wp-att-2573" href="https://www.ajaymatharu.com/the-name-does-not-exists-in-the-current-context-asp-net/control_does_not_exists_in_current_context_designer3/"><img class="size-full wp-image-2573 " title="web Page to web application conversion prompt" src="https://blog.ajaymatharu.com/wp-content/uploads/2011/01/control_does_not_exists_in_current_context_designer3.png" alt="web Page to web application conversion prompt" width="531" height="203" /></a>
      
      <p class="wp-caption-text">
        web Page to web application conversion prompt
      </p>
    </div>
    
    <p>
      Once converted you can see the added control declaration in the designer file.
    </p>
    
    <div id="attachment_2574" style="width: 700px" class="wp-caption aligncenter">
      <a rel="attachment wp-att-2574" href="https://www.ajaymatharu.com/the-name-does-not-exists-in-the-current-context-asp-net/control_does_not_exists_in_current_context_designer4/"><img class="size-full wp-image-2574" title="New designer file after converting page to web application" src="https://blog.ajaymatharu.com/wp-content/uploads/2011/01/control_does_not_exists_in_current_context_designer4.png" alt="New designer file after converting page to web application" width="700" height="529" /></a>
      
      <p class="wp-caption-text">
        New designer file after converting page to web application
      </p>
    </div>
    
    <p style="text-align: center;">
      <p>
        Now you can use the control in your code behind.
      </p>
      
      <p>
        Enjoy coding!!
      </p>
