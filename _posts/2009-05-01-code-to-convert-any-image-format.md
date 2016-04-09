---
id: 1161
title: Code to convert any image format
date: 2009-05-01T23:34:59+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=1161
permalink: /code-to-convert-any-image-format/
aktt_notify_twitter:
  - no
ljID:
  - 226
dsq_thread_id:
  - 465387783
categories:
  - .Net
  - ASP.Net
  - Visual Studio
tags:
  - .Net
  - ASP.Net
  - C-Sharp
  - 'C#.Net'
  - Image Conversion
  - Visual Studio
---
The following code converts any image format,

<pre name="code" class="c-sharp">public void ConvertImage2Jpeg(string input, string output)
{
try
{
ImageCodecInfo myimagecodeinfo;
string inputpath;
string outputpath = output;
string format;
inputpath = input;
format = inputpath.Substring(inputpath.LastIndexOf(".") + 1);

if (format == "tif")
{
myimagecodeinfo = GetEncoderInfo("image/tiff");

}
else
{
myimagecodeinfo = GetEncoderInfo("image/" + format);

}
EncoderParameters eparam = new EncoderParameters(1);
EncoderParameter encparam;
System.Drawing.Imaging.Encoder enc;
enc = System.Drawing.Imaging.Encoder.Transformation;
encparam = new EncoderParameter(enc, (long)EncoderValue.TransformRotate90);
eparam.Param[0] = new EncoderParameter(System.Drawing.Imaging.Encoder.Quality, 10L);
string jpg;
Image img;
img = Image.FromFile(inputpath);
jpg = outputpath.Substring(0, outputpath.LastIndexOf("\\") + 1) + Path.GetFileNameWithoutExtension(inputpath) + ".JPG";
img.Save(jpg, myimagecodeinfo, eparam);

}
catch (Exception exp)
{

}

}

private static ImageCodecInfo GetEncoderInfo(String mimeType)
{
int j;
ImageCodecInfo[] encoders;
encoders = ImageCodecInfo.GetImageEncoders();
for (j = 0; j &lt; encoders.Length; ++j)
{
if (encoders[j].MimeType == mimeType)
return encoders[j];
}
return null;
}</pre>