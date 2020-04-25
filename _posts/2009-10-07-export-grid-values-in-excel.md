---
toc: false
id: 1179
title: Export grid values in excel
date: 2009-10-07T13:19:02+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=1179
permalink: /export-grid-values-in-excel/
aktt_notify_twitter:
  - no
robotsmeta:
  - index,follow
dsq_thread_id:
  - 465386938
categories:
  - .Net
  - ASP.Net
  - Development
  - Visual Studio
tags:
  - 'C#'
  - 'C#.Net'
  - Code
  - Datatable
  - Export
  - export records to excel
  - gridview
  - gridview to excel
  - Visual Studio
---
Following code helps you to import grid values to excel,

<pre class="c-sharp" name="code">//Import System.IO in your application for StreamWriter Object

//note: excel_file represents the complete physical address of excel file eg  C:/myexcel.xls
public  void export_datagridview_to_excel(DataGridView dgv, string excel_file)
{
int cols;
//open file
StreamWriter wr = new StreamWriter(excel_file);

//determine the number of columns and write columns to file
cols = dgv.Columns.Count;
for (int i = 0; i &lt; cols; i++)
{
wr.Write(dgv.Columns[i].Name.ToString().ToUpper() + “\t”);
}

wr.WriteLine();

//write rows to excel file
for (int i = 0; i &lt; (dgv.Rows.Count - 1); i++)
{
for (int j = 0; j &lt; cols; j++)
{
if (dgv.RowsIdea.Cells[j].Value != null)
wr.Write(dgv.Rows[i].Cells[j].Value + “\t”);
else
{
wr.Write(”\t”);
}
}

wr.WriteLine();
}

//close file
wr.Close();
}</pre>
