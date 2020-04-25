---
tags: 
  - misc
toc:  false
id: 2906
title: Parameter is not valid for new Bitmap in .net
date: 2014-11-20T18:38:57+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=2906
permalink: /parameter-is-not-valid-for-new-bitmap-in-net/
dsq_thread_id:
  - 3244785571
categories:
  - .Net
  - ASP.Net
---
Recently from nowhere we bumped into the error Parameter is not valid for new Bitmap in .net

You get this error when you try to create a new bitmap from a image object. After comparing all the parameters for normal image and error image we identified that the error image was having the pixelformat as 8207 whereas the normal image had pixelformat as Format24bppRgb.

<div id="attachment_2907" style="width: 885px" class="wp-caption aligncenter">
  <a href="https://www.ajaymatharu.com/wp-content/uploads/2014/11/PixelFormat8207.png"><img class="wp-image-2907 size-full" src="https://www.ajaymatharu.com/wp-content/uploads/2014/11/PixelFormat8207.png" alt="parameter is not valid in new bitmap having PixelFormat 8207" width="875" height="320" /></a>
  
  <p class="wp-caption-text">
    PixelFormat 8207
  </p>
</div>

After reading about this we identified this happens with <a title="Indexed Color Images" href="https://en.wikipedia.org/wiki/Indexed_color" target="_blank">Indexed Color Images.</a> Color information is not directly carried by image pixel data.

## The possible solution for parameter is not valid for new bitmap

we could find was to create a bitmap from image filestream and then clone that bitmap with pixelformat.

So from

<pre name="code" class="c-sharp">Image fileImg = Image.FromStream(fileStream);
</pre>

We changed it to

<pre  name="code" class="c-sharp">Bitmap bm = new Bitmap(fileStream);
Bitmap cloneImg = null;
if (bm.PixelFormat.ToString() == "8207")
{
RectangleF cloneRect = new RectangleF(0, 0, bm.Width, bm.Height);
System.Drawing.Imaging.PixelFormat format = bm.PixelFormat.ToString() == "8207" ? PixelFormat.Format24bppRgb : bm.PixelFormat;
cloneImg = bm.Clone(cloneRect, format);
}
Image fileImg = bm.PixelFormat.ToString() == "8207" ? cloneImg : bm;

</pre>

After cloning the bitmap object from above code we set the pixelformat for new image to Format24bppRgb which the new Bitmap understand and allows to create an object. We then use this  fileImg object to create a new bitmap object without any parameter is not valid for new bitmap error.

<div id="attachment_2915" style="width: 685px" class="wp-caption aligncenter">
  <a href="https://www.ajaymatharu.com/wp-content/uploads/2014/11/bitmapfromfilestream.png"><img class="size-full wp-image-2915" src="https://www.ajaymatharu.com/wp-content/uploads/2014/11/bitmapfromfilestream.png" alt="Parameter is not valid for new bitmap before cloning the bitmap" width="675" height="329" srcset="https://www.ajaymatharu.com/wp-content/uploads/2014/11/bitmapfromfilestream-300x146.png 300w, https://www.ajaymatharu.com/wp-content/uploads/2014/11/bitmapfromfilestream.png 675w" sizes="(max-width: 675px) 100vw, 675px" /></a>
  
  <p class="wp-caption-text">
    Pixel format before cloning the bitmap
  </p>
</div>

&nbsp;

<div id="attachment_2916" style="width: 708px" class="wp-caption aligncenter">
  <a href="https://www.ajaymatharu.com/wp-content/uploads/2014/11/Pixelformatafterclone.png"><img class="size-full wp-image-2916" src="https://www.ajaymatharu.com/wp-content/uploads/2014/11/Pixelformatafterclone.png" alt="Parameter is not valid for new bitmap solved after cloning the bitmap" width="698" height="418" /></a>
  
  <p class="wp-caption-text">
    Pixel format for new image after cloning
  </p>
</div>

If you have any better solution do let me know.
