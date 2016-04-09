---
id: 1109
title: Sharepoint on Windows Vista
date: 2009-03-29T22:53:38+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1109
permalink: /sharepoint-on-windows-vista/
aktt_notify_twitter:
  - no
ljID:
  - 211
dsq_thread_id:
  - 465390938
categories:
  - Development
  - Featured Articles
  - Microsoft
  - Sharepoint
  - Technical
  - Technology
tags:
  - IIS
  - MOSS
  - Sharepoint
  - Tools
  - Vista
  - Web
  - Windows
  - WSS
---
Many people have this question &#8220;Does Sharepoint gets installed on Vista?&#8221;. The answer is yes. I installed MOSS on my Vista machine yesterday successfully.

All you need to install Sharepoint, WSS or MOSS, on Vista is

  * <div class="MsoNormal" style="margin: 0in 0in 10pt; line-height: normal;">
      You must select the Advanced option during install.
    </div>

  * <div class="MsoNormal" style="margin: 0in 0in 10pt; line-height: normal;">
      If you want to run on SQLExpress, manually install it first.  <a class="null" title="SQL Server 2005 Express download" href="http://msdn.microsoft.com/en-us/express/bb410792.aspx" target="_blank">Get it here</a>.
    </div>

  * <div class="MsoNormal" style="margin: 0in 0in 10pt; line-height: normal;">
      You have to manually enable IIS7 with the proper options. <span style="font-family: 'Century Gothic','sans-serif';"><strong>Web Management Tools</strong> and <strong>World Wide Web Services</strong>. Enable at least the following options in IIS. </span>
    </div>

Download Vista Helper file from <a title="VistaSharepoint" href="http://www.box.net/shared/z0gl37bakh" target="_blank"><strong>here</strong></a>, and run the setup file <span style="font-family: 'Century Gothic','sans-serif';"><strong>WssVista.msi</strong></span>.

<p style="text-align: center;">
  <div style="width: 535px" class="wp-caption aligncenter">
    <img title="Sharepoint on Vista" src="http://ajaymatharu.files.wordpress.com/2009/03/wssvista02.jpg" alt="Vista on Sharepoint" width="525" height="426" />
    
    <p class="wp-caption-text">
      Sharepoint on Vista
    </p>
  </div>
  
  <p>
    <span style="font-family: 'Century Gothic','sans-serif';">You will see an <a class="null" href="http://en.wikipedia.org/wiki/User_Account_Control" target="_blank">UAC prompt</a> select Continue to proceed with the installation. </span>
  </p>
  
  <p class="MsoNormal" style="margin: 0in 0in 10pt;">
    <span style="font-family: 'Century Gothic','sans-serif';">Once the install has completed you will find the SetupLauncher.exe in the install location you selected. If you didn’t change the default option you will see it under the directory ..\</span><span style="font-family: consolas;"><strong>Program Files\WssOnVista\</strong></span>
  </p>
  
  <p class="MsoNormal" style="margin: 0in 0in 10pt;">
    <span style="font-family: consolas;"><strong></strong></span>
  </p>
  
  <div style="width: 562px" class="wp-caption aligncenter">
    <strong><strong><img title="Sharepoint on Vista" src="http://ajaymatharu.files.wordpress.com/2009/03/wsslocation.jpg" alt="Sharepoint on Vista" width="552" height="434" /></strong></strong>
    
    <p class="wp-caption-text">
      Sharepoint on Vista
    </p>
  </div>
  
  <p>
    <strong></strong>
  </p>
  
  <p class="MsoNormal" style="margin: 0in 0in 10pt;">
    Before starting the setup make sure you have enabled IIS with the following options, <span style="font-family: 'Century Gothic','sans-serif';"><strong>Web Management Tools</strong> and <strong>World Wide Web Services</strong>. Enable at least the following options and choose OK. </span>
  </p>
  
  <p class="MsoNormal" style="margin: 0in 0in 10pt;">
    <span style="font-family: 'Century Gothic','sans-serif';">To set this </span><span style="font-family: 'Century Gothic','sans-serif';">Go to Control Panel and click <strong>Programs</strong>. </span><span style="font-family: 'Century Gothic','sans-serif';">Under Program and Features click <strong>Turn Windows features on or off</strong>.</span>
  </p>
  
  <p class="MsoNormal" style="margin: 0in 0in 10pt;">
    <div style="width: 479px" class="wp-caption aligncenter">
      <img title="Sharepoint on Vista" src="http://ajaymatharu.files.wordpress.com/2009/03/wssiisfeatures.jpg" alt="Sharepoint on Vista" width="469" height="692" />
      
      <p class="wp-caption-text">
        Sharepoint on Vista
      </p>
    </div>
    
    <p class="MsoNormal" style="margin: 0in 0in 10pt;">
      <span style="font-family: 'Century Gothic','sans-serif';">After completing the above steps it’s time for the interesting part. Locate <strong>SetupLauncher.exe</strong> and start it. You will once again see an UAC prompt, select <strong>Continue</strong>.</span>
    </p>
    
    <p class="MsoNormal" style="margin: 0in 0in 10pt;">
      <div style="width: 535px" class="wp-caption aligncenter">
        <img title="Sharepoint on Vista" src="http://ajaymatharu.files.wordpress.com/2009/03/wssvistalauncher1.png" alt="Sharepoint on Vista" width="525" height="396" />
        
        <p class="wp-caption-text">
          Sharepoint on Vista
        </p>
      </div>
      
      <p class="MsoNormal" style="margin: 0in 0in 10pt;">
        <span style="font-family: 'Century Gothic','sans-serif';">After the SetupLauncher run, select the WSS installation file <strong>Sharepoint.exe, </strong>or the MOSS installation file, and click OK.  First, the package will be extracted.</span>
      </p>
      
      <p class="MsoNormal" style="margin: 0in 0in 10pt;">
        <div style="width: 567px" class="wp-caption aligncenter">
          <img title="Sharepoint on Vista" src="http://ajaymatharu.files.wordpress.com/2009/03/wssextract.jpg" alt="Sharepoint on Vista" width="557" height="488" />
          
          <p class="wp-caption-text">
            Sharepoint on Vista
          </p>
        </div>
        
        <p class="MsoNormal" style="margin: 0in 0in 10pt;">
          <span style="font-family: 'Century Gothic','sans-serif';">After the files have been extracted the WSS setup program will be started. </span>
        </p>
        
        <p class="MsoNormal" style="margin: 0in 0in 10pt;">
          <div style="width: 513px" class="wp-caption aligncenter">
            <img title="Sharepoint on Vista" src="http://ajaymatharu.files.wordpress.com/2009/03/wssadvanced.jpg" alt="Sharepoint on Vista" width="503" height="268" />
            
            <p class="wp-caption-text">
              Sharepoint on Vista
            </p>
          </div>
          
          <p class="MsoNormal" style="margin: 0in 0in 10pt;">
            <span style="font-family: 'Century Gothic','sans-serif';">The current version only supports the <strong>advanced installation</strong> option so select that one.</span>
          </p>
          
          <p class="MsoNormal" style="margin: 0in 0in 10pt;">
            <span style="font-family: 'Century Gothic','sans-serif';">Sit back and relax while SharePoint is being installed, you are running Vista remember 😉</span>
          </p>
          
          <p class="MsoNormal" style="margin: 0in 0in 10pt;">
            <span style="font-family: 'Century Gothic','sans-serif';">Once installed you can configure your Sharepoint setup.</span>
          </p>
          
          <p class="MsoNormal" style="margin: 0in 0in 10pt;">
            <div style="width: 494px" class="wp-caption aligncenter">
              <img title="Sharepoint on Vista" src="http://ajaymatharu.files.wordpress.com/2009/03/wssconfig.png" alt="Sharepoint on Vista" width="484" height="414" />
              
              <p class="wp-caption-text">
                Sharepoint on Vista
              </p>
            </div>
            
            <p>
              <span style="font-family: 'Century Gothic','sans-serif';">Let the Configuration Wizard do it&#8217;s work.</span>
            </p>
            
            <p class="MsoNormal" style="margin: 0in 0in 10pt;">
              <div style="width: 500px" class="wp-caption aligncenter">
                <img title="Sharepoint on Vista" src="http://ajaymatharu.files.wordpress.com/2009/03/wssconfig1.png" alt="Sharepoint on Vista" width="490" height="423" />
                
                <p class="wp-caption-text">
                  Sharepoint on Vista
                </p>
              </div>
              
              <p class="MsoNormal" style="margin: 0in 0in 10pt;">
                <span style="font-family: 'Century Gothic','sans-serif';">The final result is WSS running on Vista, Enjoy!</span>
              </p>
              
              <p class="MsoNormal" style="margin: 0in 0in 10pt;">
                <div style="width: 604px" class="wp-caption aligncenter">
                  <img title="Sharepoint on Vista" src="http://ajaymatharu.files.wordpress.com/2009/03/sharepointonvista.png" alt="Sharepoint on Vista" width="594" height="449" />
                  
                  <p class="wp-caption-text">
                    Sharepoint on Vista
                  </p>
                </div>
                
                <p class="MsoNormal" style="margin: 0in 0in 10pt;">
                  <p class="MsoNormal" style="margin: 0in 0in 10pt;">
                    Resource:
                  </p>
                  
                  <p class="MsoNormal" style="margin: 0in 0in 10pt;">
                    <a href="http://community.bamboosolutions.com/blogs/bambooteamblog/archive/2008/05/21/how-to-install-windows-sharepoint-services-3-0-sp1-on-vista-x64-x86.aspx" target="_blank">Bamboo Solutions</a>
                  </p>
                  
                  <p>
                    <span style="font-family: 'Century Gothic','sans-serif';">You can find more on their forums. Enjoy!!!<br /> </span>
                  </p>