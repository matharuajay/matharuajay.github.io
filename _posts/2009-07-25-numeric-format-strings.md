---
id: 1276
title: Numeric Format Strings
date: 2009-07-25T12:03:29+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1276
permalink: /numeric-format-strings/
dsq_thread_id:
  - 465389612
categories:
  - .Net
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - 'C#.Net'
  - format specifier
  - format string
  - numeric Format
  - numeric format strings
  - numeric types
  - Objects
  - vs.net
---
Standard numeric format strings are used to return string equivalents of numeric types in predefined patterns. When used with ToString, a standard numeric format string parameter takes the form.

<pre class="c-sharp">object.ToString ( "Fn" );</pre>

where F is a single alphabetic character called the format specifier, and n can be one or more digits called the precision specifier.

The following table describes the standard numeric format strings. Note that the patterns produced by these format specifiers are influenced by the settings in the Regional Options control panel. Computers using different cultures or different currency settings will display different patterns.

<table class="data" border="0" cellspacing="1" width="95%" align="center">
  <col width="20%"></col> <col width="25%"></col> <col width="55%"></col> <tr>
    <th>
      Format specifier
    </th>
    
    <th>
      Name
    </th>
    
    <th>
      Description
    </th>
  </tr>
  
  <tr>
    <td>
      C or c
    </td>
    
    <td>
      Currency
    </td>
    
    <td>
      The number is converted to a string that represents a currency amount. The conversion is controlled by the currency format information of the <a href="/aspxtreme/sys/Globalization/NumberFormatInfoClass.aspx">NumberFormatInfo</a> object used to format the number. The precision specifier indicates the desired number of decimal places. If the precision specifier is omitted, the default currency precision given by the <strong>NumberFormatInfo</strong> is used.
    </td>
  </tr>
  
  <tr>
    <td>
      D or d
    </td>
    
    <td>
      Decimal
    </td>
    
    <td>
      This format is supported for integral types only. The number is converted to a string of decimal digits ( 0-9 ), prefixed by a minus sign if the number is negative. The precision specifier indicates the minimum number of digits desired in the resulting string. If required, the number is padded with zeros to its left to produce the number of digits given by the precision specifier.
    </td>
  </tr>
  
  <tr>
    <td>
      E or e
    </td>
    
    <td>
      Scientific ( exponential )
    </td>
    
    <td>
      The number is converted to a string of the form &#8220;-d.ddd�E+ddd&#8221; or &#8220;-d.ddd�e+ddd&#8221;, where each &#8216;d&#8217; indicates a digit ( 0-9 ). The string starts with a minus sign if the number is negative. One digit always precedes the decimal point. The precision specifier indicates the desired number of digits after the decimal point. If the precision specifier is omitted, a default of six digits after the decimal point is used. The case of the format specifier indicates whether to prefix the exponent with an &#8216;E&#8217; or an &#8216;e&#8217;. The exponent always consists of a plus or minus sign and a minimum of three digits. The exponent is padded with zeros to meet this minimum, if required.
    </td>
  </tr>
  
  <tr>
    <td>
      F or f
    </td>
    
    <td>
      Fixed-point
    </td>
    
    <td>
      The number is converted to a string of the form &#8220;-ddd.ddd�&#8221; where each &#8216;d&#8217; indicates a digit ( 0-9 ). The string starts with a minus sign if the number is negative. The precision specifier indicates the desired number of decimal places. If the precision specifier is omitted, the default numeric precision given by the <strong>NumberFormatInfo</strong> is used.
    </td>
  </tr>
  
  <tr>
    <td>
      G or g
    </td>
    
    <td>
      General
    </td>
    
    <td>
      The number is converted to the most compact decimal form, using fixed or scientific notation. The precision specifier determines the number of significant digits in the resulting string. If the precision specifier is omitted, the number of significant digits is determined by the type of number being converted:</p> 
      
      <ul>
        <li>
          <strong>Int16</strong> or <strong>UInt16</strong>: 5 digits
        </li>
        <li>
          <strong>Int32</strong> or <strong>UInt32</strong>: 10 digits
        </li>
        <li>
          <strong>Int64</strong> or <strong>UInt64</strong>: 19 digits
        </li>
        <li>
          <strong>Single</strong>: 7 digits
        </li>
        <li>
          <strong>Double</strong>: 15 digits
        </li>
        <li>
          <strong>Decimal</strong>: 29 digits
        </li>
      </ul>
      
      <p>
        Trailing zeros after the decimal point are removed, and the resulting string contains a decimal point only if required.
      </p>
      
      <p>
        The resulting string uses fixed-point format if the exponent of the number ( as produced by the &#8216;E&#8217; format ) is less than the number of significant digits, and greater than or equal to –4. Otherwise, the resulting string uses scientific format, and the case of the format specifier controls whether the format is prefixed with an &#8216;E&#8217; or an &#8216;e&#8217;.</td> </tr> 
        
        <tr>
          <td>
            N or n
          </td>
          
          <td>
            Number
          </td>
          
          <td>
            The number is converted to a string of the form &#8220;-d,ddd,ddd.ddd�&#8221;, where each &#8216;d&#8217; indicates a digit ( 0-9 ). The string starts with a minus sign if the number is negative. Thousand separators are inserted between each group of three digits to the left of the decimal point. The precision specifier indicates the desired number of decimal places. If the precision specifier is omitted, the default numeric precision given by the <strong>NumberFormatInfo</strong> is used.
          </td>
        </tr>
        
        <tr>
          <td>
            P or p
          </td>
          
          <td>
            Percent
          </td>
          
          <td>
            The number is converted to a string that represents a percent as defined by the <a href="/aspxtreme/sys/Globalization/NumberFormatInfoClassPercentNegativePattern.aspx">NumberFormatInfo.PercentNegativePattern</a> property or the <a href="/aspxtreme/sys/Globalization/NumberFormatInfoClassPercentPositivePattern.aspx">NumberFormatInfo.PercentPositivePattern</a> property. If the number is negative, the string produced is defined by the <strong>PercentNegativePattern</strong> and starts with a minus sign. The converted number is multiplied by 100 in order to be presented as a percentage. The precision specifier indicates the desired number of decimal places. If the precision specifier is omitted, the default numeric precision given by <strong>NumberFormatInfo</strong> is used.
          </td>
        </tr>
        
        <tr>
          <td>
            R or r
          </td>
          
          <td>
            Round-trip
          </td>
          
          <td>
            The round-trip specifier guarantees that a numeric value converted to a string will be parsed back into the same numeric value. When a numeric value is formatted using this specifier, it is first tested using the general format, with 15 spaces of precision for a <strong>Double</strong> and 7 spaces of precision for a <strong>Single</strong>. If the value is successfully parsed back to the same numeric value, then it is formatted using the general format specifer. However, if the value is not successfully parsed back to the same numeric value, then the value is formatted using 17 digits of precision for a <strong>Double</strong> and 9 digits of precision for a <strong>Single</strong>. Although a precision specifier can be appended to the round-trip format specifier, it is ignored. Round trips are given precedence over precision when using this specifier. This format is supported by floating-point types only.
          </td>
        </tr>
        
        <tr>
          <td>
            X or x
          </td>
          
          <td>
            Hexadecimal
          </td>
          
          <td>
            The number is converted to a string of hexadecimal digits. The case of the format specifier indicates whether to use uppercase or lowercase characters for the hexadecimal digits greater than 9. For example, use &#8216;X&#8217; to produce &#8216;ABCDEF&#8217;, and &#8216;x&#8217; to produce &#8216;abcdef&#8217;. The precision specifier indicates the minimum number of digits desired in the resulting string. If required, the number is padded with zeros to its left to produce the number of digits given by the precision specifier. This format is supported for integral types only.
          </td>
        </tr></tbody> </table>