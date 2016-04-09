---
id: 1421
title: Integrating BlogEngine
date: 2009-07-07T10:30:51+00:00
author: Ajay Matharu
layout: page
guid: http://www.ajaymatharu.com/?p=1421
aktt_notify_twitter:
  - no
dsq_thread_id:
  - 465390985
buffer-my-post-log:
  - Invalid access token
---
Lots of people have this query on how to integrating BlogEngine to an existing site. Here is the solution that explains how to integrate blogengine.net into existing site.

&#8211; Copy BlogEngine code to a subfolder of your existing site, say it Blogs.

&#8211; Make the following changes from you BlogEngine web.config file into your application web.config file,

1 &#8211; Find and copy the following code from your BlogEngine web.config file and paste it in your Web Application web.config file under &#8220;configSections&#8221; tag,

<pre name="code" class="xml">&lt;sectionGroup name="BlogEngine"&gt;
 &lt;section name="blogProvider" requirePermission="false" type="BlogEngine.Core.Providers.BlogProviderSection, BlogEngine.Core" allowDefinition="MachineToApplication" restartOnExternalChanges="true" /&gt;
&lt;/sectionGroup&gt;</pre>

2 &#8211; Find and copy the following code from your BlogEngine web.config file and paste it in your web application web.config file just after &#8220;configSections&#8221; tag,

<pre name="code" class="xml">&lt;BlogEngine&gt;
 &lt;blogProvider defaultProvider="DbBlogProvider"&gt;
 &lt;providers&gt;
 &lt;add name="XmlBlogProvider" type="BlogEngine.Core.Providers.XmlBlogProvider, BlogEngine.Core"/&gt;
 &lt;add name="DbBlogProvider" type="BlogEngine.Core.Providers.DbBlogProvider, BlogEngine.Core" connectionStringName="BlogEngine"/&gt;
 &lt;/providers&gt;
 &lt;/blogProvider&gt;
&lt;/BlogEngine&gt;</pre>

3 &#8211; Add the connection string if you have not already have one.

4 &#8211; If you don&#8217;t already have connection string in your existing web application web.config file, find and copy the following code in your BlogEngine web.config file, and paste it after the &#8220;BlogEngine&#8221; tag from the above step,

<pre name="code" class="xml">&lt;connectionStrings&gt;
 &lt;clear/&gt;
 &lt;add name="LocalSqlServer" connectionString="dummy"/&gt;
 &lt;!-- Mono complains if LocalSqlServer isn't specified --&gt;
 &lt;add name="BlogEngine" connectionString="Data Source=192.168.0.59;User ID=sa;Password=magnet;persist security info=False;initial catalog=new_BlogEngine;" providerName="System.Data.SqlClient"/&gt;
&lt;/connectionStrings&gt;</pre>

5 &#8211; Find and copy everything within &#8220;appSettings&#8221; tag from BlogEngine web.config, and paste it within &#8220;appSettings&#8221; tag in your web application web.config file,

<pre name="code" class="xml">&lt;appSettings&gt;
 &lt;add key="BlogEngine.FileExtension" value=".aspx"/&gt;
 &lt;!-- You can e.g. use "~/blog/" if BlogEngine.NET is not located in the root of the application --&gt;
 &lt;add key="BlogEngine.VirtualPath" value="~/blogs/"/&gt;
 &lt;!-- The regex used to identify mobile devices so a different theme can be shown --&gt;
 &lt;add key="BlogEngine.MobileDevices" value="(nokia|sonyericsson|blackberry|samsung|sec\-|windows ce|motorola|mot\-|up.b|midp\-)"/&gt;
 &lt;!-- The name of the role with administrator permissions --&gt;
 &lt;add key="BlogEngine.AdminRole" value="Administrators"/&gt;
 &lt;!--This value is to provide an alterantive location for storing data.--&gt;
 &lt;add key="StorageLocation" value="~/Blogs/App_Data/"/&gt;
 &lt;!--A comma separated list of script names to hard minify. It's case-sensitive. --&gt;
 &lt;add key="BlogEngine.HardMinify" value="blog.js,widget.js,WebResource.axd"/&gt;
&lt;/appSettings&gt;</pre>

**NOTE:** I have copy pasted &#8220;appSettings&#8221; tag for your reference, you should not include &#8220;appSettings&#8221; tag and copy everything within it.

**NOTE:** I have changed the value of &#8220;BlogEngine.VirtualPath&#8221; to refer to our sub directory rather than the top level directory.

6 &#8211; Find and copy everything within &#8220;assemblies&#8221; tag from your BlogEngine web.config file, and paste it within &#8220;assemblies&#8221; tag of your web application web.config file.

**NOTE:** Paste only those tags within &#8220;assemblies&#8221; tag which do not already exists.

<pre name="code" class="xml">&lt;compilation&gt;
&lt;assemblies&gt;
 &lt;add assembly="System.Management, Version=2.0.0.0, Culture=neutral, PublicKeyToken=B03F5F7F11D50A3A"/&gt;
 &lt;add assembly="System.Configuration, Version=2.0.0.0, Culture=neutral, PublicKeyToken=B03F5F7F11D50A3A"/&gt;
 &lt;add assembly="System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/&gt;
 &lt;add assembly="System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/&gt;
 &lt;add assembly="System.Drawing, Version=2.0.0.0, Culture=neutral, PublicKeyToken=B03F5F7F11D50A3A"/&gt;
 &lt;add assembly="System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=B03F5F7F11D50A3A"/&gt;
 &lt;add assembly="System.Xml, Version=2.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/&gt;
&lt;/assemblies&gt;
&lt;/compilation&gt;</pre>

**NOTE:** I have copy pasted &#8220;assemblies&#8221; tag for your reference, you should not include &#8220;assemblies&#8221; tag and copy everything within it.

7 &#8211; Find and copy the following line from BlogEngine web.config, and paste it in your web application web.config file just under &#8220;compilation&#8221; tag from above point,

**NOTE:** Paste this code in your web application web.config file only if already does not exists.

<pre name="code" class="xml">&lt;globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="auto" uiCulture="auto"/&gt;</pre>

8 &#8211; Find and copy the following line from BlogEngine web.config, and paste it in your web application web.config file just under &#8220;globalization&#8221; tag from above point,

**NOTE:** Paste this code in your web application web.config file only if already does not exists.

<pre name="code" class="xml">&lt;httpRuntime enableVersionHeader="false" useFullyQualifiedRedirectUrl="true" maxRequestLength="16384" executionTimeout="3600" requestLengthDiskThreshold="16384"/&gt;</pre>

9 &#8211; Find and copy the following line from BlogEngine web.config, and paste it in your web application web.config file just under &#8220;httpRuntime&#8221; tag from above point,

**NOTE:** Paste this code in your web application web.config file only if already does not exists.

<pre name="code" class="xml">&lt;machineKey validationKey="D9F7287EFDE8DF4CAFF79011D5308643D8F62AE10CDF30DAB640B7399BF6C57B0269D60A23FBCCC736FC2487ED695512BA95044DE4C58DC02C2BA0C4A266454C" decryptionKey="BDAAF7E00B69BA47B37EEAC328929A06A6647D4C89FED3A7D5C52B12B23680F4" validation="SHA1" decryption="AES"/&gt;</pre>

10 &#8211; Change the authentication mode in your web application web.config file to &#8220;Forms&#8221; and find and copy the following line from BlogEngine web.config, and paste it in your web application web.config within &#8220;authentication&#8221; tag,

**NOTE:** if you want to use your own form for authentication then change the value of the &#8220;loginUrl&#8221; attribute of the &#8220;form&#8221; tag to the login page from your site.

<pre name="code" class="xml">&lt;authentication mode="Forms"&gt;
 &lt;forms timeout="129600" name=".AUXBLOGENGINE" protection="All" slidingExpiration="true" loginUrl="~/login.aspx" cookieless="UseCookies"/&gt;
 &lt;/authentication&gt;</pre>

**NOTE:** I have copy pasted &#8220;authentication&#8221; tag for your reference, this tag will already be there in your web application web.config file, so just check the &#8220;mode&#8221; of authentication and the &#8220;loginUrl&#8221; value of the form tag.

11 &#8211; Find and copy the following line from BlogEngine web.config, and paste it in your web application web.config file

<pre name="code" class="xml">&lt;pages enableSessionState="false" enableViewStateMac="true" enableEventValidation="true"&gt;
 &lt;controls&gt;
 &lt;add namespace="Controls" tagPrefix="blog"/&gt;
 &lt;/controls&gt;
&lt;/pages&gt;</pre>

**NOTE:** Paste this code in your web application web.config file only if already does not exists. If it already exists just copy everything within &#8220;controls&#8221; tag from you BlogEngine web.config file and paste in within &#8220;controls&#8221; tag of your web application web.config file.

**NOTE:** I have copy pasted &#8220;pages&#8221; and &#8220;controls&#8221; tags for your reference, you should not include &#8220;pages&#8221; and &#8220;controls&#8221; tag if they already exists and copy everything within it. If they don&#8217;t exists then copy the entire &#8220;page&#8221; tag.

12 &#8211; Change the custom error mode in your web application web.config file if you want to redirect user to &#8220;error page&#8221;.

**NOTE:** if you want to use your own error page change the value of the &#8220;mode&#8221; attribute of the &#8220;customErrors&#8221; tag and the value of &#8220;redirect&#8221; attribute of the &#8220;error&#8221; tag within it, as per your requirements,

<pre name="code" class="xml">&lt;customErrors mode="RemoteOnly" defaultRedirect="~/error404.aspx"&gt;
 &lt;error statusCode="404" redirect="~/error404.aspx"/&gt;
&lt;/customErrors&gt;</pre>

13 &#8211; Find and copy the following line from BlogEngine web.config, and paste it in your web application web.config file just after &#8220;customErrors&#8221; tag from above point,

**NOTE:** Paste this code in your web application web.config file only if already does not exists.

<pre name="code" class="xml">&lt;membership defaultProvider="DbMembershipProvider"&gt;
 &lt;providers&gt;
 &lt;clear/&gt;
 &lt;add name="XmlMembershipProvider" type="BlogEngine.Core.Providers.XmlMembershipProvider, BlogEngine.Core" description="XML membership provider" passwordFormat="Hashed"/&gt;
 &lt;add name="SqlMembershipProvider" type="System.Web.Security.SqlMembershipProvider" connectionStringName="BlogEngine" applicationName="BlogEngine"/&gt;
 &lt;add name="DbMembershipProvider" type="BlogEngine.Core.Providers.DbMembershipProvider, BlogEngine.Core" passwordFormat="Hashed" connectionStringName="BlogEngine"/&gt;
 &lt;/providers&gt;
&lt;/membership&gt;
&lt;roleManager defaultProvider="DbRoleProvider" enabled="true" cacheRolesInCookie="true" cookieName=".BLOGENGINEROLES"&gt;
 &lt;providers&gt;
 &lt;clear/&gt;
 &lt;add name="XmlRoleProvider" type="BlogEngine.Core.Providers.XmlRoleProvider, BlogEngine.Core" description="XML role provider"/&gt;
 &lt;add name="SqlRoleProvider" type="System.Web.Security.SqlRoleProvider" connectionStringName="BlogEngine" applicationName="BlogEngine"/&gt;
 &lt;add name="DbRoleProvider" type="BlogEngine.Core.Providers.DbRoleProvider, BlogEngine.Core" connectionStringName="BlogEngine"/&gt;
 &lt;/providers&gt;
&lt;/roleManager&gt;</pre>

**NOTE:** if these tags already exists just copy paste the content within &#8220;providers&#8221; tag and paste it within respective tag.

14 &#8211; Find and copy the following line from BlogEngine web.config, and paste it in your web application web.config file just after &#8220;roleManager&#8221; tag from above point,

**NOTE:** Paste this code in your web application web.config file only if it does not exists.

<pre name="code" class="xml">&lt;siteMap defaultProvider="PageSiteMap" enabled="true"&gt;
 &lt;providers&gt;
 &lt;add name="PageSiteMap" description="The site map provider that reads in the .sitemap XML files." type="BlogEngine.Core.Web.Controls.PageSiteMap, BlogEngine.Core"/&gt;
 &lt;add name="SecuritySiteMap" description="Used for authenticated users." type="System.Web.XmlSiteMapProvider, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" securityTrimmingEnabled="true" siteMapFile="Web.sitemap"/&gt;
 &lt;/providers&gt;
&lt;/siteMap&gt;</pre>

**NOTE:** if these &#8220;siteMap&#8221; tag already exists just copy paste the content within &#8220;providers&#8221; tag and paste it within your web application &#8220;provider&#8221; tag within &#8220;siteMap&#8221; tag.

15 &#8211; Find the &#8220;httpModules&#8221; tag within &#8220;system.web&#8221; tag in BlogEngine web.config and copy the content within &#8220;httpModules&#8221; tag, and paste it in &#8220;httpModules&#8221; tag within &#8220;system.web&#8221; tag within your Web Application web.config

<pre name="code" class="xml">&lt;httpModules&gt;
 &lt;add name="WwwSubDomainModule" type="BlogEngine.Core.Web.HttpModules.WwwSubDomainModule, BlogEngine.Core"/&gt;
 &lt;add name="UrlRewrite" type="BlogEngine.Core.Web.HttpModules.UrlRewrite, BlogEngine.Core"/&gt;
 &lt;add name="CompressionModule" type="BlogEngine.Core.Web.HttpModules.CompressionModule, BlogEngine.Core"/&gt;
 &lt;add name="ReferrerModule" type="BlogEngine.Core.Web.HttpModules.ReferrerModule, BlogEngine.Core"/&gt;
 &lt;!--Remove the default ASP.NET modules we don't need--&gt;
 &lt;remove name="PassportAuthentication"/&gt;
 &lt;remove name="Profile"/&gt;
 &lt;remove name="AnonymousIdentification"/&gt;
&lt;/httpModules&gt;</pre>

**NOTE:** If any of the &#8220;add&#8221; tag already exists in &#8220;httpModules&#8221; tag in your Web Application web.config, do not copy it again. Make sure you only have one copy of each &#8220;add&#8221; tag within &#8220;httpModules&#8221;.

16 &#8211; Find the &#8220;httpHandlers&#8221; tag within &#8220;system.web&#8221; tag in BlogEngine web.config and copy the content within &#8220;httpHandlers&#8221; tag, and paste it in &#8220;httpHandlers&#8221; tag within &#8220;system.web&#8221; tag within your Web Application web.config

<pre name="code" class="xml">&lt;httpHandlers&gt;
 &lt;add verb="*" path="file.axd" type="BlogEngine.Core.Web.HttpHandlers.FileHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="image.axd" type="BlogEngine.Core.Web.HttpHandlers.ImageHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="syndication.axd" type="BlogEngine.Core.Web.HttpHandlers.SyndicationHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="sitemap.axd" type="BlogEngine.Core.Web.HttpHandlers.SiteMap, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="trackback.axd" type="BlogEngine.Core.Web.HttpHandlers.TrackbackHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="pingback.axd" type="BlogEngine.Core.Web.HttpHandlers.PingbackHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="opensearch.axd" type="BlogEngine.Core.Web.HttpHandlers.OpenSearchHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="metaweblog.axd" type="BlogEngine.Core.API.MetaWeblog.MetaWeblogHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="rsd.axd" type="BlogEngine.Core.Web.HttpHandlers.RsdHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="css.axd" type="BlogEngine.Core.Web.HttpHandlers.CssHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="js.axd" type="BlogEngine.Core.Web.HttpHandlers.JavaScriptHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="rating.axd" type="BlogEngine.Core.Web.HttpHandlers.RatingHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="opml.axd" type="BlogEngine.Core.Web.HttpHandlers.OpmlHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="blogml.axd" type="BlogEngine.Core.Web.HttpHandlers.BlogMLExportHandler, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="sioc.axd" type="BlogEngine.Core.Web.HttpHandlers.Sioc, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="apml.axd" type="BlogEngine.Core.Web.HttpHandlers.Apml, BlogEngine.Core" validate="false"/&gt;
 &lt;add verb="*" path="foaf*.axd" type="BlogEngine.Core.Web.HttpHandlers.Foaf, BlogEngine.Core" validate="false"/&gt;
&lt;/httpHandlers&gt;</pre>

**NOTE:** If any of the &#8220;add&#8221; tag already exists in &#8220;httpHandlers&#8221; tag in your Web Application web.config, do not copy it again. Make sure you only have one copy of each &#8220;add&#8221; tag within &#8220;httpHandlers&#8221;.

17 &#8211; Find the &#8220;modules&#8221; tag within &#8220;system.webServer&#8221; tag in BlogEngine web.config and copy the content within &#8220;modules&#8221; tag, and paste it in &#8220;modules&#8221; tag within &#8220;system.webServer&#8221; tag within your Web Application web.config

<pre name="code" class="xml">&lt;modules&gt;
 &lt;add name="WwwSubDomainModule" type="BlogEngine.Core.Web.HttpModules.WwwSubDomainModule, BlogEngine.Core"/&gt;
 &lt;add name="UrlRewrite" type="BlogEngine.Core.Web.HttpModules.UrlRewrite, BlogEngine.Core"/&gt;
 &lt;add name="CompressionModule" type="BlogEngine.Core.Web.HttpModules.CompressionModule, BlogEngine.Core"/&gt;
 &lt;add name="ReferrerModule" type="BlogEngine.Core.Web.HttpModules.ReferrerModule, BlogEngine.Core"/&gt;
&lt;/modules&gt;</pre>

**NOTE:** If any of the &#8220;add&#8221; tag already exists in &#8220;modules&#8221; tag in your Web Application web.config, do not copy it again. Make sure you only have one copy of each &#8220;add&#8221; tag within &#8220;modules&#8221;.

18 &#8211; Find the &#8220;handlers&#8221; tag within &#8220;system.webServer&#8221; tag in BlogEngine web.config and copy the content within &#8220;handlers&#8221; tag, and paste it in &#8220;handlers&#8221; tag within &#8220;system.webServer&#8221; tag within your Web Application web.config

<pre name="code" class="xml">&lt;handlers accessPolicy="Read, Write, Script, Execute"&gt;
 &lt;add name="FileHandler" verb="*" path="file.axd" type="BlogEngine.Core.Web.HttpHandlers.FileHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="ImageHandler" verb="*" path="image.axd" type="BlogEngine.Core.Web.HttpHandlers.ImageHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="Syndication" verb="*" path="syndication.axd" type="BlogEngine.Core.Web.HttpHandlers.SyndicationHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="Sitemap" verb="*" path="sitemap.axd" type="BlogEngine.Core.Web.HttpHandlers.SiteMap, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="Trackback" verb="*" path="trackback.axd" type="BlogEngine.Core.Web.HttpHandlers.TrackbackHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="Pingback" verb="*" path="pingback.axd" type="BlogEngine.Core.Web.HttpHandlers.PingbackHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="OpenSearch" verb="*" path="opensearch.axd" type="BlogEngine.Core.Web.HttpHandlers.OpenSearchHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="MetaWeblog" verb="*" path="metaweblog.axd" type="BlogEngine.Core.API.MetaWeblog.MetaWeblogHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="RSD" verb="*" path="rsd.axd" type="BlogEngine.Core.Web.HttpHandlers.RsdHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="CssHandler" verb="*" path="css.axd" type="BlogEngine.Core.Web.HttpHandlers.CssHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="Javascript" path="js.axd" verb="*" type="BlogEngine.Core.Web.HttpHandlers.JavaScriptHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="Rating" verb="*" path="rating.axd" type="BlogEngine.Core.Web.HttpHandlers.RatingHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="Opml" verb="*" path="opml.axd" type="BlogEngine.Core.Web.HttpHandlers.OpmlHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="BlogML" verb="*" path="blogml.axd" type="BlogEngine.Core.Web.HttpHandlers.BlogMLExportHandler, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="SIOC" verb="*" path="sioc.axd" type="BlogEngine.Core.Web.HttpHandlers.Sioc, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="Apml" verb="*" path="apml.axd" type="BlogEngine.Core.Web.HttpHandlers.Apml, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
 &lt;add name="Foaf" verb="*" path="foaf*.axd" type="BlogEngine.Core.Web.HttpHandlers.Foaf, BlogEngine.Core" resourceType="Unspecified" requireAccess="Script" preCondition="integratedMode"/&gt;
&lt;/handlers&gt;</pre>

**NOTE:** If any of the &#8220;add&#8221; tag already exists in &#8220;handlers&#8221; tag in your Web Application web.config, do not copy it again. Make sure you only have one copy of each &#8220;add&#8221; tag within &#8220;handlers&#8221;.

19 &#8211; Move directories from BlogEngine.Web/App\_Code under your Web Application/App\_code

20 &#8211; Move directories from BlogEngine.Web/App\_GlobalResources under your Web Application/App\_GlobalResources.

21 &#8211; Add reference to BlogEngine.Core.Dll in your application.

Please drop me a comment if you have any doubts or you liked this post.

Hope this helps <img src="http://www.ajaymatharu.com/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />