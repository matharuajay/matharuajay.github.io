---
toc: false
id: 117
title: Access Active Directory from Sharepoint
date: 2008-09-14T08:06:46+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=117
permalink: /access-active-directory-from-sharepoint/
ljID:
  - 22
dsq_thread_id:
  - 465386215
categories:
  - Sharepoint
tags:
  - Sharepoint
---
Here is the sample code thar you can use to access Active Directory details from a sharepoint site,

DirectoryEntry oDE;
  
oDE = new DirectoryEntry(&#8220;LDAP://<ldapserver>,&#8221;ADusername&#8221;,&#8221;ADpassword&#8221;,AuthenticationTypes.Secure);

DirectoryEntry de = oDE;

DirectorySearcher deSearch = new DirectorySearcher();

deSearch.Filter = &#8220;(&(objectClass=user)(SAMAccountName=&#8221; + SPContext.Current.Web.CurrentUser.LoginName + &#8220;))&#8221;;

deSearch.SearchScope = SearchScope.Subtree;

SearchResult results = deSearch.FindOne();

if (!(results == null))
  
{
  
de = new DirectoryEntry(results.Path,&#8221;AD username&#8221;,&#8221;AD password&#8221;,AuthenticationTypes.Secure);

//if you know the propertyname you want to get value from you can use this
  
de.Properties[&#8220;propertyname&#8221;].ToString();

//this code will loop thru all the properties in active directory
  
ResultPropertyCollection propertiesCollection;

propertiesCollection = results.Properties;

//loop thru all the properties in AD
  
foreach (string currentProperty in propertiesCollection.PropertyNames)
  
{

Response.Write(&#8220;Property Name: &#8221; + currentProperty);

//loop thru all the sub properties
  
foreach (Object thisCollection in propertiesCollection[currentProperty])
  
{

Response.Write(thisCollection.ToString() + &#8220;<br/>&#8221;);
  
}
  
}
  
}

The above code reads and writes the values of the properties from the Active directory for the current user.
  
But to be able to run the above code you need to make sure that you import System.DirectoryServices,
  
<%@ Import Namespace=&#8221;System.DirectoryServices&#8221; %>
  
Also you need to make sure Web.config has an entry for the System.DirectoryServices in its Assemblies Section,

<assemblies>
  
<add assembly=&#8221;System.DirectoryServices, Version=2.0.0.0,
  
Culture=neutral, PublicKeyToken=b77a5c561934e089&#8243; />
  
</assemblies>
