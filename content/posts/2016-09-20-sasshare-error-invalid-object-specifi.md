---
title: 'SAS/Share ERROR: Invalid object specifi...'
date: '2016-09-20 15:12:00'
path: '/sasshare-error-invalid-object-specifi/'
previewImg: '../images/frontmatter21.png'
tags:
  - 'ERROR: Invalid object specifi...'
  - 'Invalid object specifi...'
---

Had an interesting error message today (SAS 9.3, Windows 2012R2), which appeared to be truncated:

<div><span style="color: red;">ERROR: Attempt to connect to server "dev01.domain.com".__8551 rejected by server.</span></div>
<div><span style="color: red;">ERROR: Invalid object specifi...</span></div>
<div><span style="color: red;">ERROR: Error in the LIBNAME statement.</span></div>
The issue occurred when trying to connect to a SAS/Share library using the following syntax:
<div><span style="background: white; color: blue; font-family: 'courier new';">LIBNAME</span><span style="background: white; font-family: 'courier new';"> MYLIBREF REMOTE  </span><span style="background: white; color: blue; font-family: 'courier new';">HOSTNAME</span><span style="background: white; font-family: 'courier new';">=</span><span style="background: white; color: purple; font-family: 'courier new';">"dev01.domain.com"</span><span style="background: white; font-family: 'courier new';">  </span><span style="background: white; color: blue; font-family: 'courier new';">Server</span><span style="background: white; font-family: 'courier new';">=__8551 </span><span style="background: white; color: blue; font-family: 'courier new';">slibref</span><span style="background: white; font-family: 'courier new';">=MYLIBREF;</span></div>
The fix was simple - simply log into the application server, open Services, and restart the "SAS Share Server" service.
<div style="clear: both; text-align: center;"></div>
<img class="size-medium wp-image-102 aligncenter" src="../images/Capture1.png" alt="" width="300" height="111" />

This left the customer happy, but I'm still curious about what caused the elipsis (...)

Any ideas<span style="background-color: white; color: #444444; font-family: 'arial' , 'tahoma' , 'helvetica' , 'freesans' , sans-serif; font-size: 13px; line-height: 18.2px;">‽</span>
