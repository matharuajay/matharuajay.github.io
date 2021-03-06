---
toc: false
id: 229
title: Visual Studio Higher to Lower Version Converter
date: 2008-10-21T18:36:49+00:00
author: Ajay Matharu
layout: post
guid: https://ajaymatharu.wordpress.com/?p=229
permalink: /visual-studio-higher-to-lower-version-converter/
robotsmeta:
  - index,follow
aktt_notify_twitter:
  - no
ljID:
  - 45
dsq_thread_id:
  - 465358075
categories:
  - .Net
  - Featured Articles
  - Visual Studio
tags:
  - .Net
  - .Net version conversion
  - Visual Studio
  - vs.net
---
Many a times we find it diffucult to switch between various versions of Visual Studios available.

Visual <a name="visualstudiohks-CHP-1-ITERM-2208"></a><a name="visualstudiohks-CHP-1-ITERM-2209"></a>Studio <a name="visualstudiohks-CHP-1-ITERM-2210"></a>does an excellent job of converting files from older versions to newer versions. For instance, if you open a Visual Studio .NET 2002 solution in Visual Studio .NET 2003, it will first ask if you want to convert the solution. After you say yes, it will convert all of your solution and project files to the new version of Visual Studio .NET. Now what if you accidentally converted those files and didn&#8217;t have a backup? Or perhaps you are writing a solution in Visual Studio .NET 2003 and find out that your client has only Visual Studio .NET 2002?

One method would be to create a new solution in the old version, create an identical project structure, and then copy all the files over and add them to their respective projects.

Thankfully, there is a better solution. There are project converter that helps you to convert the project. <a title="C# project version converter" href="https://www.box.net/shared/2940188png" target="_blank">Here</a> is converter for C# projects and <a title="VB project version converter" href="https://www.box.net/shared/egvnjoe9y1" target="_blank">here</a> is for VB projects.  The program can be launched as a normal windows application or it can be installed in order to get a new Explorer &#8220;shell extension&#8221; that adds ProjectConverter to the &#8220;Open With&#8221; option when right-clicking on a *.sln file.

[<img class="aligncenter size-full wp-image-231" title="version" src="https://ajaymatharu.files.wordpress.com/2008/10/version.png" alt="" width="450" height="266" />](https://ajaymatharu.files.wordpress.com/2008/10/version.png)

The solution file is a text-based file that contains information about one or more projects.  The solution file contains the target version of Visual Studio. You can change this version number to change the target Visual Studio Version, from higher to lower.

Here is how the solution file looks like,

Microsoft Visual Studio Solution File, <span class="style7"><span style="background-color:#ffff00;">Format Version 10.00</span></span>
  
\# <span class="style7"><span style="background-color:#ffff00;">Visual Studio 2008</span></span>
  
Project(&#8220;{F184B08F-C81C-45F6-A57F-5ABD9991F28F}&#8221;) = &#8220;ProjectConverter&#8221;,
  
&#8220;ProjectConverter.vbproj&#8221;, &#8220;{B637ACFD-0AFC-4FBB-A8C0-602B5ABA62F0}&#8221;
  
EndProject
  
Project(&#8220;{54435603-DBB4-11D2-8724-00A0C9A8B90C}&#8221;) = &#8220;Setup&#8221;, &#8220;SetupSetup.vdproj&#8221;,
  
&#8220;{09667F41-0E35-4D40-A0A9-E71BA6740D93}&#8221;
  
EndProject
  
Global
  
  GlobalSection(SolutionConfigurationPlatforms) = preSolution
  
    Debug|Any CPU = Debug|Any CPU
  
    Release|Any CPU = Release|Any CPU
  
  EndGlobalSection
  
  GlobalSection(ProjectConfigurationPlatforms) = postSolution
  
    {B637ACFD-0AFC-4FBB-A8C0-602B5ABA62F0}.Debug|Any CPU.ActiveCfg = Debug|Any CPU
  
    {B637ACFD-0AFC-4FBB-A8C0-602B5ABA62F0}.Debug|Any CPU.Build.0 = Debug|Any CPU
  
    {B637ACFD-0AFC-4FBB-A8C0-602B5ABA62F0}.Release|Any CPU.ActiveCfg = Release|Any CPU
  
    {B637ACFD-0AFC-4FBB-A8C0-602B5ABA62F0}.Release|Any CPU.Build.0 =Release|Any CPU
  
    {09667F41-0E35-4D40-A0A9-E71BA6740D93}.Debug|Any CPU.ActiveCfg = Debug
  
    {09667F41-0E35-4D40-A0A9-E71BA6740D93}.Release|Any CPU.ActiveCfg = Release
  
  EndGlobalSection
  
  GlobalSection(SolutionProperties) = preSolution
  
    HideSolutionNode = FALSE
  
  EndGlobalSection
  
EndGlobal

 

<p class="docText">
  In Visual Studio .NET 2003 and Visual Studio 2005, project dependencies are also tracked here. These are not the <a name="visualstudiohks-CHP-1-ITERM-2162"></a>implicit dependences that are created by project <a name="visualstudiohks-CHP-1-ITERM-2163"></a>references. When Project A references Project B, there is an implicit dependency. Project B must be built before Project A since it references the other project&#8217;s output. Since this type of dependency is project-specific information, it is stored in the project file. (In this example, it would be stored in Project A&#8217;s project file since it is referencing Project B, rather than the solution file we are looking at here.) Project files and dependencies are described in the next section.
</p>

<p class="docText">
  The dependences stored in the <tt>ProjectSection</tt> tag are configured at the solution level. They define when a project must be built before another project, but they may not directly reference each other. This is stored in the <tt>ProjectSection</tt> tag of the project that is dependent on the other project. In this example, the <em>HacksWinApp</em> project is dependent on the <em>HacksLib</em> project and thus includes a reference to the GUID of the other project. This dependency is normally configured by right-clicking on the solution file, selecting Properties from the context menu, and navigating to Project Dependencies in the property page that appears.
</p>

<p class="docText">
  <a name="visualstudiohks-CHP-1-ITERM-2164"></a><a name="visualstudiohks-CHP-1-ITERM-2165"></a>Visual Studio .NET 2003 includes a <tt>ProjectSection</tt> tag even if there is no dependency (you can see this in the <tt>HacksLib</tt> project tag). Visual Studio 2005 completely omits the <tt>ProjectSection</tt> tag if there are no dependencies for the project. Visual Studio .NET 2002 stores the dependency information in a completely different section of the solution file, which we will cover next.
</p>

<p class="docText">
  The next section in the solution file is the <tt>Global</tt><a name="visualstudiohks-CHP-1-ITERM-2166"></a> <a name="visualstudiohks-CHP-1-ITERM-2167"></a>section, which begins with a <tt>Global</tt> tag and ends with an <tt>EndGlobal</tt> tag. Inside these tags are a number of <tt>GlobalSection</tt><a name="visualstudiohks-CHP-1-ITERM-2168"></a> tags that store an array of different pieces of information, including the configuration settings for various projects as well as source control information.
</p>

[](https://ajaymatharu.files.wordpress.com/2008/10/solution.png)

The difference between the product version and the file format are displayed here,

[<img class="aligncenter size-full wp-image-233" title="versiondiff" src="https://ajaymatharu.files.wordpress.com/2008/10/versiondiff.png" alt="" width="450" height="102" />](https://ajaymatharu.files.wordpress.com/2008/10/versiondiff.png)

 

Each <a name="visualstudiohks-CHP-1-ITERM-2179"></a>project creates a number of files to store information about itself. This includes a project file and a user settings file. The extension for the project file is based on the language type; for example, a <a name="visualstudiohks-CHP-1-ITERM-2180"></a><a name="visualstudiohks-CHP-1-ITERM-2181"></a>C# Project is saved with the extension _.csproj_ and a <a name="visualstudiohks-CHP-1-ITERM-2182"></a>VB.NET Project is stored with the extension _.vbproj_. Thankfully, the internal formats of these various files are based on the same <a name="visualstudiohks-CHP-1-ITERM-2183"></a><a name="visualstudiohks-CHP-1-ITERM-2184"></a>XML schema. The beginning of each project file includes some basic information about the project, including the <a name="visualstudiohks-CHP-1-ITERM-2185"></a>version of Visual Studio that it was created for as well as the <a name="visualstudiohks-CHP-1-ITERM-2186"></a>GUID for this project. the <tt>Build</tt> section, which includes build settings and configuration settings as well as references information.  The project file will usually contain at least a <tt>Debug</tt> and <tt>Release</tt> section.

The <tt>References</tt><a name="visualstudiohks-CHP-1-ITERM-2195"></a> <a name="visualstudiohks-CHP-1-ITERM-2196"></a>section contains a reference tag for each assembly referenced by the project. Starting with Visual Studio 2005, you can create a reference to either an assembly or an executable, which comes in very handy when you are trying to unit-test a Windows application, since this lets you directly reference your application. To get this same functionality in Visual Studio .NET 2003, you can actually hack the project file to create a reference to an executable—you simply need to manually enter a reference tag in the references element pointing to your executable.

Similarly projects .vbproj or .csproj is XML format file which looks like this,

<pre style="font-size:x-small;font-family:Arial, Helvetica, sans-serif;background-color:#ffffff;border:1px solid;padding:1px 4px;">&lt;?xml version="1.0" encoding="utf-8"?&gt;
&lt;Project <span class="style7"><span style="background-color:#ffff00;">ToolsVersion="3.5"</span></span> DefaultTargets="Build" xmlns="https://schemas.microsoft.com/developer/msbuild/2003"&gt;
  &lt;PropertyGroup&gt;
    &lt;Configuration Condition=" '$(Configuration)' == '' "&gt;Debug&lt;/Configuration&gt;
    &lt;Platform Condition=" '$(Platform)' == '' "&gt;AnyCPU&lt;/Platform&gt;
    &lt;ProductVersion&gt;<span class="style7"><span style="background-color:#ffff00;">9.0.21022&lt;</span></span>/ProductVersion&gt;
    &lt;SchemaVersion&gt;2.0&lt;/SchemaVersion&gt;
    &lt;ProjectGuid&gt;{B637ACFD-0AFC-4FBB-A8C0-602B5ABA62F0}&lt;/ProjectGuid&gt;
    &lt;OutputType&gt;WinExe&lt;/OutputType&gt;
    &lt;StartupObject&gt;ProjectConverter.My.MyApplication&lt;/StartupObject&gt;
    &lt;RootNamespace&gt;ProjectConverter&lt;/RootNamespace&gt;
    &lt;AssemblyName&gt;ProjectConverter&lt;/AssemblyName&gt;
    &lt;FileAlignment&gt;512&lt;/FileAlignment&gt;
    &lt;MyType&gt;WindowsForms&lt;/MyType&gt;
    &lt;TargetFrameworkVersion&gt;<span class="style7"><span style="background-color:#ffff00;">v2.0</span></span>&lt;/TargetFrameworkVersion&gt;
    &lt;OptionExplicit&gt;On&lt;/OptionExplicit&gt;
    &lt;OptionCompare&gt;Binary&lt;/OptionCompare&gt;
    &lt;OptionStrict&gt;Off&lt;/OptionStrict&gt;
    &lt;OptionInfer&gt;On&lt;/OptionInfer&gt;
    &lt;ApplicationIcon&gt;Icon1.ico&lt;/ApplicationIcon&gt;
  &lt;/PropertyGroup&gt;
  &lt;PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' "&gt;
    &lt;DebugSymbols&gt;true&lt;/DebugSymbols&gt;
    &lt;DebugType&gt;full&lt;/DebugType&gt;
    &lt;DefineDebug&gt;true&lt;/DefineDebug&gt;
    &lt;DefineTrace&gt;true&lt;/DefineTrace&gt;
    &lt;OutputPath&gt;binDebug&lt;/OutputPath&gt;
    &lt;DocumentationFile&gt;
    &lt;/DocumentationFile&gt;
    &lt;NoWarn&gt;42016,41999,42017,42018,42019,42032,42036,42020,42021,42022&lt;/NoWarn&gt;
  &lt;/PropertyGroup&gt;
  &lt;PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' "&gt;
    &lt;DebugType&gt;pdbonly&lt;/DebugType&gt;
    &lt;DefineDebug&gt;false&lt;/DefineDebug&gt;
    &lt;DefineTrace&gt;true&lt;/DefineTrace&gt;
    &lt;Optimize&gt;true&lt;/Optimize&gt;
    &lt;OutputPath&gt;binRelease&lt;/OutputPath&gt;
    &lt;DocumentationFile&gt;
    &lt;/DocumentationFile&gt;
    &lt;NoWarn&gt;42016,41999,42017,42018,42019,42032,42036,42020,42021,42022&lt;/NoWarn&gt;
  &lt;/PropertyGroup&gt;
  &lt;ItemGroup&gt;
    &lt;Reference Include="System" /&gt;
    &lt;Reference Include="System.Data" /&gt;
    &lt;Reference Include="System.Deployment" /&gt;
    &lt;Reference Include="System.Drawing" /&gt;
    &lt;Reference Include="System.Windows.Forms" /&gt;
    &lt;Reference Include="System.Xml" /&gt;
  &lt;/ItemGroup&gt;
  &lt;ItemGroup&gt;
    &lt;Import Include="Microsoft.VisualBasic" /&gt;
    &lt;Import Include="System" /&gt;
    &lt;Import Include="System.Collections" /&gt;
    &lt;Import Include="System.Collections.Generic" /&gt;
    &lt;Import Include="System.Data" /&gt;
    &lt;Import Include="System.Drawing" /&gt;
    &lt;Import Include="System.Diagnostics" /&gt;
    &lt;Import Include="System.Windows.Forms" /&gt;
  &lt;/ItemGroup&gt;
  &lt;ItemGroup&gt;
    &lt;Compile Include="fmMain.vb"&gt;
      &lt;SubType&gt;Form&lt;/SubType&gt;
    &lt;/Compile&gt;
    &lt;Compile Include="fmMain.Designer.vb"&gt;
      &lt;DependentUpon&gt;fmMain.vb&lt;/DependentUpon&gt;
      &lt;SubType&gt;Form&lt;/SubType&gt;
    &lt;/Compile&gt;
    &lt;Compile Include="My ProjectAssemblyInfo.vb" /&gt;
    &lt;Compile Include="My ProjectApplication.Designer.vb"&gt;
      &lt;AutoGen&gt;True&lt;/AutoGen&gt;
      &lt;DependentUpon&gt;Application.myapp&lt;/DependentUpon&gt;
    &lt;/Compile&gt;
    &lt;Compile Include="My ProjectResources.Designer.vb"&gt;
      &lt;AutoGen&gt;True&lt;/AutoGen&gt;
      &lt;DesignTime&gt;True&lt;/DesignTime&gt;
      &lt;DependentUpon&gt;Resources.resx&lt;/DependentUpon&gt;
    &lt;/Compile&gt;
    &lt;Compile Include="My ProjectSettings.Designer.vb"&gt;
      &lt;AutoGen&gt;True&lt;/AutoGen&gt;
      &lt;DependentUpon&gt;Settings.settings&lt;/DependentUpon&gt;
      &lt;DesignTimeSharedInput&gt;True&lt;/DesignTimeSharedInput&gt;
    &lt;/Compile&gt;
  &lt;/ItemGroup&gt;
  &lt;ItemGroup&gt;
    &lt;EmbeddedResource Include="fmMain.resx"&gt;
      &lt;DependentUpon&gt;fmMain.vb&lt;/DependentUpon&gt;
      &lt;SubType&gt;Designer&lt;/SubType&gt;
    &lt;/EmbeddedResource&gt;
    &lt;EmbeddedResource Include="My ProjectResources.resx"&gt;
      &lt;Generator&gt;VbMyResourcesResXFileCodeGenerator&lt;/Generator&gt;
      &lt;LastGenOutput&gt;Resources.Designer.vb&lt;/LastGenOutput&gt;
      &lt;CustomToolNamespace&gt;My.Resources&lt;/CustomToolNamespace&gt;
      &lt;SubType&gt;Designer&lt;/SubType&gt;
    &lt;/EmbeddedResource&gt;
  &lt;/ItemGroup&gt;
  &lt;ItemGroup&gt;
    &lt;None Include="app.config" /&gt;
    &lt;None Include="My ProjectApplication.myapp"&gt;
      &lt;Generator&gt;MyApplicationCodeGenerator&lt;/Generator&gt;
      &lt;LastGenOutput&gt;Application.Designer.vb&lt;/LastGenOutput&gt;
    &lt;/None&gt;
    &lt;None Include="My ProjectSettings.settings"&gt;
      &lt;Generator&gt;SettingsSingleFileGenerator&lt;/Generator&gt;
      &lt;CustomToolNamespace&gt;My&lt;/CustomToolNamespace&gt;
      &lt;LastGenOutput&gt;Settings.Designer.vb&lt;/LastGenOutput&gt;
    &lt;/None&gt;
  &lt;/ItemGroup&gt;
  &lt;ItemGroup&gt;
    &lt;Content Include="Icon1.ico" /&gt;
  &lt;/ItemGroup&gt;
  &lt;Import Project="<span class="style7"><span style="background-color:#ffff00;">$(MSBuildToolsPath)</span></span>Microsoft.VisualBasic.targets" /&gt;
  &lt;!-- To modify your build process, add your task inside one of the targets below and uncomment it.
       Other similar extension points exist, see Microsoft.Common.targets.
  &lt;Target Name="BeforeBuild"&gt;
  &lt;/Target&gt;
  &lt;Target Name="AfterBuild"&gt;
  &lt;/Target&gt;
  --&gt;
&lt;/Project&gt;</pre>

The diffrence in the two file formats are,

[<img class="aligncenter size-full wp-image-234" title="diff" src="https://ajaymatharu.files.wordpress.com/2008/10/diff.png" alt="" width="450" height="145" />](https://ajaymatharu.files.wordpress.com/2008/10/diff.png)

The schema of the project file is pretty straightforward in case you need to edit it directly.

<p class="docText">
  Visual Studio also creates a <a name="visualstudiohks-CHP-1-ITERM-2199"></a><a name="visualstudiohks-CHP-1-ITERM-2200"></a>user-specific project file much like the <em>.suo</em> file created for the solution file except with an extension of <<em>projectextension>.user</em>, so if you were using <a name="visualstudiohks-CHP-1-ITERM-2201"></a>VB.NET, it would be <em>vbproj.user</em>. Similarly, this user-specific file does not contain anything pertinent enough to cover here, and is also <a name="visualstudiohks-CHP-1-ITERM-2202"></a>hidden by default, so you will need configure Windows Explorer to show hidden files through Tools &#8211; Folder Options &#8211; View.
</p>

<p class="docText">
  Visual Studio 2005 has not been mentioned up until this point because the project files in Visual Studio 2005 are completely different than the project files in Visual Studio .NET 2002 and 2003. The <a name="visualstudiohks-CHP-1-ITERM-2203"></a><a name="visualstudiohks-CHP-1-ITERM-2204"></a><a name="visualstudiohks-CHP-1-ITERM-2205"></a>project files in Visual Studio 2005 are MSBuild XML files.
</p>

<p class="docText">
  So this shows you can still convert higher VS.Net projects to lower versions.
</p>
