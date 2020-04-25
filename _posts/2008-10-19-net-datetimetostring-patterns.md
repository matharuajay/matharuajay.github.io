---
toc: false
id: 213
title: .Net DateTime.ToString() Patterns
date: 2008-10-19T11:25:10+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=213
permalink: /net-datetimetostring-patterns/
ljID:
  - 42
dsq_thread_id:
  - 465391366
categories:
  - .Net
  - ASP.Net
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - asp.net datetime
  - Datetime
  - Datetime patterns
---
## All the patterns:

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy
    </td>
    
    <td class="TableCell">
      08/22/2006
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      1
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy
    </td>
    
    <td class="TableCell">
      Tuesday, 22 August 2006
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      2
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy
    </td>
    
    <td class="TableCell">
      HH:mm Tuesday, 22 August 2006 06:30
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      3
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy
    </td>
    
    <td class="TableCell">
      hh:mm tt Tuesday, 22 August 2006 06:30 AM
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      4
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy
    </td>
    
    <td class="TableCell">
      H:mm Tuesday, 22 August 2006 6:30
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      5
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy
    </td>
    
    <td class="TableCell">
      h:mm tt Tuesday, 22 August 2006 6:30 AM
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      6
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy HH:mm:ss
    </td>
    
    <td class="TableCell">
      Tuesday, 22 August 2006 06:30:07
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      7
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy HH:mm
    </td>
    
    <td class="TableCell">
      08/22/2006 06:30
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      8
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy hh:mm tt
    </td>
    
    <td class="TableCell">
      08/22/2006 06:30 AM
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      9
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy H:mm
    </td>
    
    <td class="TableCell">
      08/22/2006 6:30
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      10
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy h:mm tt
    </td>
    
    <td class="TableCell">
      08/22/2006 6:30 AM
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      10
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy h:mm tt
    </td>
    
    <td class="TableCell">
      08/22/2006 6:30 AM
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      10
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy h:mm tt
    </td>
    
    <td class="TableCell">
      08/22/2006 6:30 AM
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      11
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy HH:mm:ss
    </td>
    
    <td class="TableCell">
      08/22/2006 06:30:07
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      12
    </td>
    
    <td class="TableCell">
      MMMM dd
    </td>
    
    <td class="TableCell">
      August 22
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      13
    </td>
    
    <td class="TableCell">
      MMMM dd
    </td>
    
    <td class="TableCell">
      August 22
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      14
    </td>
    
    <td class="TableCell">
      yyyy&#8217;-&#8216;MM&#8217;-&#8216;dd&#8217;T&#8217;HH&#8217;:&#8217;mm&#8217;:&#8217;ss.fffffffK
    </td>
    
    <td class="TableCell">
      2006-08-22T06:30:07.7199222-04:00
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      15
    </td>
    
    <td class="TableCell">
      yyyy&#8217;-&#8216;MM&#8217;-&#8216;dd&#8217;T&#8217;HH&#8217;:&#8217;mm&#8217;:&#8217;ss.fffffffK
    </td>
    
    <td class="TableCell">
      2006-08-22T06:30:07.7199222-04:00
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      16
    </td>
    
    <td class="TableCell">
      ddd, dd MMM yyyy HH&#8217;:&#8217;mm&#8217;:&#8217;ss &#8216;GMT&#8217;
    </td>
    
    <td class="TableCell">
      Tue, 22 Aug 2006 06:30:07 GMT
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      17
    </td>
    
    <td class="TableCell">
      ddd, dd MMM yyyy HH&#8217;:&#8217;mm&#8217;:&#8217;ss &#8216;GMT&#8217;
    </td>
    
    <td class="TableCell">
      Tue, 22 Aug 2006 06:30:07 GMT
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      18
    </td>
    
    <td class="TableCell">
      yyyy&#8217;-&#8216;MM&#8217;-&#8216;dd&#8217;T&#8217;HH&#8217;:&#8217;mm&#8217;:&#8217;ss
    </td>
    
    <td class="TableCell">
      2006-08-22T06:30:07
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      19
    </td>
    
    <td class="TableCell">
      HH:mm
    </td>
    
    <td class="TableCell">
      06:30
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      20
    </td>
    
    <td class="TableCell">
      hh:mm tt
    </td>
    
    <td class="TableCell">
      06:30 AM
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      21
    </td>
    
    <td class="TableCell">
      H:mm
    </td>
    
    <td class="TableCell">
      6:30
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      22
    </td>
    
    <td class="TableCell">
      h:mm tt
    </td>
    
    <td class="TableCell">
      6:30 AM
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      23
    </td>
    
    <td class="TableCell">
      HH:mm:ss
    </td>
    
    <td class="TableCell">
      06:30:07
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      24
    </td>
    
    <td class="TableCell">
      yyyy&#8217;-&#8216;MM&#8217;-&#8216;dd HH&#8217;:&#8217;mm&#8217;:&#8217;ss&#8217;Z&#8217;
    </td>
    
    <td class="TableCell">
      2006-08-22 06:30:07Z
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      25
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy HH:mm:ss
    </td>
    
    <td class="TableCell">
      Tuesday, 22 August 2006 06:30:07
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      26
    </td>
    
    <td class="TableCell">
      yyyy MMMM
    </td>
    
    <td class="TableCell">
      2006 August
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      27
    </td>
    
    <td class="TableCell">
      yyyy MMMM
    </td>
    
    <td class="TableCell">
      2006 August
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;d&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy
    </td>
    
    <td class="TableCell">
      08/22/2006
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;D&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy
    </td>
    
    <td class="TableCell">
      Tuesday, 22 August 2006
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;f&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy HH:mm
    </td>
    
    <td class="TableCell">
      Tuesday, 22 August 2006 06:30
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      1
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy hh:mm
    </td>
    
    <td class="TableCell">
      tt Tuesday, 22 August 2006 06:30 AM
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      2
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy H:mm
    </td>
    
    <td class="TableCell">
      Tuesday, 22 August 2006 6:30
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      3
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy h:mm
    </td>
    
    <td class="TableCell">
      tt Tuesday, 22 August 2006 6:30 AM
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;F&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy HH:mm:ss
    </td>
    
    <td class="TableCell">
      Tuesday, 22 August 2006 06:30:07
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;g&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy HH:mm
    </td>
    
    <td class="TableCell">
      08/22/2006 06:30
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      1
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy hh:mm
    </td>
    
    <td class="TableCell">
      tt 08/22/2006 06:30 AM
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      2
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy H:mm
    </td>
    
    <td class="TableCell">
      08/22/2006 6:30
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      3
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy h:mm tt
    </td>
    
    <td class="TableCell">
      08/22/2006 6:30 AM
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;G&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      MM/dd/yyyy HH:mm:ss
    </td>
    
    <td class="TableCell">
      08/22/2006 06:30:07
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;m&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      MMMM dd
    </td>
    
    <td class="TableCell">
      August 22
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;r&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      ddd, dd MMM yyyy HH&#8217;:&#8217;mm&#8217;:&#8217;ss &#8216;GMT&#8217;
    </td>
    
    <td class="TableCell">
      Tue, 22 Aug 2006 06:30:07 GMT
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;s&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      yyyy&#8217;-&#8216;MM&#8217;-&#8216;dd&#8217;T&#8217;HH&#8217;:&#8217;mm&#8217;:&#8217;ss
    </td>
    
    <td class="TableCell">
      2006-08-22T06:30:07
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;u&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      yyyy&#8217;-&#8216;MM&#8217;-&#8216;dd HH&#8217;:&#8217;mm&#8217;:&#8217;ss&#8217;Z&#8217;
    </td>
    
    <td class="TableCell">
      2006-08-22 06:30:07Z
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;U&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      dddd, dd MMMM yyyy HH:mm:ss
    </td>
    
    <td class="TableCell">
      Tuesday, 22 August 2006 06:30:07
    </td>
  </tr>
</table>

## The patterns for DateTime.ToString ( &#8216;y&#8217; ) :

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
    </td>
    
    <td class="TableCell">
      yyyy MMMM 2006 August
    </td>
  </tr>
</table>

## Building a custom DateTime.ToString Patterns

The following details the meaning of each pattern character. Not the **K** and **z** character.

<table class="TableClass" border="0" cellspacing="1" cellpadding="2">
  <tr>
    <td class="TableCell">
      <strong>d</strong>
    </td>
    
    <td class="TableCell">
      Represents the day of the month as a number from 1 through 31. A single-digit day is formatted without a leading zero
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>dd</strong>
    </td>
    
    <td class="TableCell">
      Represents the day of the month as a number from 01 through 31. A single-digit day is formatted with a leading zero
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>ddd</strong>
    </td>
    
    <td class="TableCell">
      Represents the abbreviated name of the day of the week (Mon, Tues, Wed etc)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>dddd</strong>
    </td>
    
    <td class="TableCell">
      Represents the full name of the day of the week (Monday, Tuesday etc)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>h</strong>
    </td>
    
    <td class="TableCell">
      12-hour clock hour (e.g. 7)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>hh</strong>
    </td>
    
    <td class="TableCell">
      12-hour clock, with a leading 0 (e.g. 07)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>H</strong>
    </td>
    
    <td class="TableCell">
      24-hour clock hour (e.g. 19)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>HH</strong>
    </td>
    
    <td class="TableCell">
      24-hour clock hour, with a leading 0 (e.g. 19)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>m</strong>
    </td>
    
    <td class="TableCell">
      Minutes
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>mm</strong>
    </td>
    
    <td class="TableCell">
      Minutes with a leading zero
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>M</strong>
    </td>
    
    <td class="TableCell">
      Month number
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>MM</strong>
    </td>
    
    <td class="TableCell">
      Month number with leading zero
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>MMM</strong>
    </td>
    
    <td class="TableCell">
      Abbreviated Month Name (e.g. Dec)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>MMMM</strong>
    </td>
    
    <td class="TableCell">
      Full month name (e.g. December)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>s</strong>
    </td>
    
    <td class="TableCell">
      Seconds
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>ss</strong>
    </td>
    
    <td class="TableCell">
      Seconds with leading zero
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>t</strong>
    </td>
    
    <td class="TableCell">
      Abbreviated AM / PM (e.g. A or P)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>tt</strong>
    </td>
    
    <td class="TableCell">
      AM / PM (e.g. AM or PM
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>y</strong>
    </td>
    
    <td class="TableCell">
      Year, no leading zero (e.g. 2001 would be 1)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>yy</strong>
    </td>
    
    <td class="TableCell">
      Year, leadin zero (e.g. 2001 would be 01)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>yyy</strong>
    </td>
    
    <td class="TableCell">
      Year, (e.g. 2001 would be 2001)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>yyyy</strong>
    </td>
    
    <td class="TableCell">
      Year, (e.g. 2001 would be 2001)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>K</strong>
    </td>
    
    <td class="TableCell">
      Represents the time zone information of a date and time value (e.g. +05:00)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>z</strong>
    </td>
    
    <td class="TableCell">
      With <a href="https://www.geekzilla.co.uk/View00FF7904-B510-468C-A2C8-F859AA20581F.htm">DateTime</a> values, represents the signed offset of the local operating system&#8217;s time zone from Coordinated Universal Time (UTC), measured in hours. (e.g. +6)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>zz</strong>
    </td>
    
    <td class="TableCell">
      As z but with leadin zero (e.g. +06)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>zzz</strong>
    </td>
    
    <td class="TableCell">
      With <a href="https://www.geekzilla.co.uk/View00FF7904-B510-468C-A2C8-F859AA20581F.htm">DateTime</a> values, represents the signed offset of the local operating system&#8217;s time zone from UTC, measured in hours and minutes. (e.g. +06:00)
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>f</strong>
    </td>
    
    <td class="TableCell">
      Represents the most significant digit of the seconds fraction; that is, it represents the tenths of a second in a date and time value.
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>ff</strong>
    </td>
    
    <td class="TableCell">
      Represents the two most significant digits of the seconds fraction; that is, it represents the hundredths of a second in a date and time value.
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>fff</strong>
    </td>
    
    <td class="TableCell">
      Represents the three most significant digits of the seconds fraction; that is, it represents the milliseconds in a date and time value.
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>ffff</strong>
    </td>
    
    <td class="TableCell">
      Represents the four most significant digits of the seconds fraction; that is, it represents the ten thousandths of a second in a date and time value. While it is possible to display the ten thousandths of a second component of a time value, that value may not be meaningful. The precision of date and time values depends on the resolution of the system clock. On Windows NT 3.5 and later, and Windows Vista operating systems, the clock&#8217;s resolution is approximately 10-15 milliseconds.
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>fffff</strong>
    </td>
    
    <td class="TableCell">
      Represents the five most significant digits of the seconds fraction; that is, it represents the hundred thousandths of a second in a date and time value. While it is possible to display the hundred thousandths of a second component of a time value, that value may not be meaningful. The precision of date and time values depends on the resolution of the system clock. On Windows NT 3.5 and later, and Windows Vista operating systems, the clock&#8217;s resolution is approximately 10-15 milliseconds.
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>ffffff</strong>
    </td>
    
    <td class="TableCell">
      Represents the six most significant digits of the seconds fraction; that is, it represents the millionths of a second in a date and time value. While it is possible to display the millionths of a second component of a time value, that value may not be meaningful. The precision of date and time values depends on the resolution of the system clock. On Windows NT 3.5 and later, and Windows Vista operating systems, the clock&#8217;s resolution is approximately 10-15 milliseconds.
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>fffffff</strong>
    </td>
    
    <td class="TableCell">
      Represents the seven most significant digits of the seconds fraction; that is, it represents the ten millionths of a second in a date and time value. While it is possible to display the ten millionths of a second component of a time value, that value may not be meaningful. The precision of date and time values depends on the resolution of the system clock. On Windows NT 3.5 and later, and Windows Vista operating systems, the clock&#8217;s resolution is approximately 10-15 milliseconds.
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>F</strong>
    </td>
    
    <td class="TableCell">
      Represents the most significant digit of the seconds fraction; that is, it represents the tenths of a second in a date and time value. Nothing is displayed if the digit is zero.
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>:</strong>
    </td>
    
    <td class="TableCell">
      Represents the time separator defined in the current DateTimeFormatInfo..::.TimeSeparator property. This separator is used to differentiate hours, minutes, and seconds.
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>/</strong>
    </td>
    
    <td class="TableCell">
      Represents the date separator defined in the current DateTimeFormatInfo..::.DateSeparator property. This separator is used to differentiate years, months, and days.
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>&#8220;</strong>
    </td>
    
    <td class="TableCell">
      Represents a quoted string (quotation mark). Displays the literal value of any string between two quotation marks (&#8220;). Your application should precede each quotation mark with an escape character (\).
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong></strong>&#8216;
    </td>
    
    <td class="TableCell">
      Represents a quoted string (apostrophe). Displays the literal value of any string between two apostrophe (&#8216;) characters.
    </td>
  </tr>
  
  <tr>
    <td class="TableCell">
      <strong>%c</strong>
    </td>
    
    <td class="TableCell">
      Represents the result associated with a c custom format specifier, when the custom date and time format string consists solely of that custom format specifier. That is, to use the d, f, F, h, m, s, t, y, z, H, or M custom format specifier by itself, the application should specify %d, %f, %F, %h, %m, %s, %t, %y, %z, %H, or %M. For more information about using a single format specifier, see Using Single Custom Format Specifiers.
    </td>
  </tr>
</table>
