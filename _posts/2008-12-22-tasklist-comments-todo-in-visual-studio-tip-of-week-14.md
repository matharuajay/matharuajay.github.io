---
toc: false
id: 658
title: 'Tasklist Comments / TODO in Visual Studio &#8211; Tip Of Week #14'
date: 2008-12-22T01:00:05+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=658
permalink: /tasklist-comments-todo-in-visual-studio-tip-of-week-14/
ljID:
  - 132
dsq_thread_id:
  - 465385083
categories:
  - .Net
  - Development
  - Tip of Week
  - Visual Studio
tags:
  - .Net
  - Development
  - Microsoft
  - Technology
  - Tip of Week
  - Visual Studio
  - Visual Studio Tip Of Week
  - Visual Studio tips
  - vs.net
---
Task list comments are a great way to remind you or others of something that still needs to be done or something that may need to be revisited for enhancement.

The <a name="visualstudiohks-CHP-3-ITERM-2596"></a><a name="visualstudiohks-CHP-3-ITERM-2597"></a><a name="visualstudiohks-CHP-3-ITERM-2598"></a>task list (<a name="visualstudiohks-CHP-3-ITERM-2599"></a>Ctrl-Alt-K/View.TaskList) is a handy tool that is most often used to view errors or warnings from the compilation of your code.

<p class="docText">
  The task list also has another use; it can be used to leave reminders for yourself or other members of your team in comment form.
</p>

<p class="docText">
  You can use this comment anywhere throughout your code, and they will show up in the task list when the file with the comment is open.
</p>

<p class="docText">
  <p class="docText">
    //
  </p>
  
  <p class="docText">
    // TODO: Add addition logic here
  </p>
  
  <p class="docText">
    //
  </p>
  
  <p class="docText">
    <p class="docText">
      To list this in your task list first make sure that the task list is configured to show comments, and then you will see in the task list that this comment has been added as an item.
    </p>
    
    <p class="docText">
      You will see a drop-down list at the top of the task list that lets you choose what should be displayed in the task list.
    </p>
    
    <p class="docText">
      You can then click on this comment and be taken to the place where you need to add code.
    </p>
    
    <p class="docText">
      You can use shortcuts to step back and forth between tasks as well. The View.NextTask (<a name="visualstudiohks-CHP-3-ITERM-2607"></a> <a name="visualstudiohks-CHP-3-ITERM-2608"></a>Ctrl-Shift-F12) and View.PreviousTask<a name="visualstudiohks-CHP-3-ITERM-2609"></a> (no default shortcut) commands can be used to step through the tasks listed in the task list.
    </p>
    
    <p class="docText">
      You can also click in the area at the top of the task list with the <a name="visualstudiohks-CHP-3-ITERM-2610"></a><a name="visualstudiohks-CHP-3-ITERM-2611"></a>text &#8220;Click here to add a new task,&#8221; or  you can click the Create User Task button. This creates a user task for you and acts much like the tasks portion of Outlook. You can also tag any line in your project as a task by using the Edit.ToggleTaskListShortcut (Ctrl-K, Ctrl-H)<a name="visualstudiohks-CHP-3-ITERM-2612"></a> <a name="visualstudiohks-CHP-3-ITERM-2613"></a>command. Whenever you call this command, it will add a shortcut to the task list pointing to this line of code. You can then add text that says what should be done to the line of code. It is a quick and easy way to add something to the task list to tackle later on. These tasks will appear only on your system and not on the systems of your team members.
    </p>
    
    <p class="docText">
      <p class="docText">
