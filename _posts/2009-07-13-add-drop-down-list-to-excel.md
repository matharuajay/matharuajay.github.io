---
toc: false
id: 719
title: Add drop down list to Excel
date: 2009-07-13T21:27:38+00:00
author: Ajay Matharu
layout: post
guid: http://ajaymatharu.wordpress.com/?p=719
permalink: /add-drop-down-list-to-excel/
ljID:
  - 283
dsq_thread_id:
  - 465389692
categories:
  - Microsoft
  - Technology
tags:
  - data entry
  - drop down list
  - excel sheet
  - highlight
  - Microsoft
  - Microsoft Excel
  - Microsoft Office
  - office applications
  - Technology
---
<div class="entry">
  <p>
    In Access, you can limit user entries by forcing users to choose a value from a list control. Office applications use the same functionality in built-in drop-down lists. For instance, the Highlight and Font Color controls on most Formatting toolbars use this flexible tool. Simply click the small triangle to the right of the icon to display a list of choices.
  </p>
  
  <p>
    You can create the same type of control for your users in an Excel sheet, but the process isn’t intuitive. The option is in the Data Validation feature. Fortunately, once you know the feature exists, it’s easy to implement. You need only two things: a list and a data entry cell. The following sheet shows a simple drop-down list in an Excel sheet.
  </p>
  
  <p>
    <img class="aligncenter size-full wp-image-720" title="excel" src="http://ajaymatharu.files.wordpress.com/2008/12/excel.jpg" alt="excel" width="320" height="115" />
  </p>
  
  <p>
    Users click the drop-down arrow to display a list of items from A1:A4. If a user tries to enter something that isn’t in the list, Excel rejects the entry. To add this drop-down list to a sheet, do the following:
  </p>
  
  <ol>
    <li>
      Create the list in cells A1:A4. Similarly, you can enter the items in a single row, such as A1:D4.
    </li>
    <li>
      Select cell E3. (You can position the drop-down list in most any cell or even multiple cells.)
    </li>
    <li>
      Choose Validation from the Data menu.
    </li>
    <li>
      Choose List from the Allow option’s drop-down list. (See, they’re everywhere.)
    </li>
    <li>
      Click the Source control and drag to highlight the cells A1:A4. Alternately, simply enter the reference (=$A$1:$A$4).
    </li>
    <li>
      Make sure the In-Cell Dropdown option is checked. If you uncheck this option, Excel still forces users to enter only list values (A1:A4), but it won’t present a drop-down list.
    </li>
    <li>
      Click OK.
    </li>
  </ol>
  
  <p>
    You can add the drop-down list to multiple cells. Select the range of data input cells (step 2) instead of a single cell. It even works for noncontiguous cells. Hold down the Shift key while you click the appropriate cells.
  </p>
  
  <p>
    It’s worth noting that the drop-down arrow is visible only when the cell is active.
  </p>
</div>

<!-- /entry -->
