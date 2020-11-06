---
title: 'Submitting OS commands from SAS'
date: '2012-11-12 22:27:00'
path: '/submitting-os-commands-from-sas/'
tags:
  - Movable Type
---

When dealing with a Pooled Workspace Server, a generic 'host account' is normally used. &nbsp;So you tend not to have individual host accounts to log in with. &nbsp;Therefore, sometimes the only way to navigate the server is to use EG! &nbsp;Hence this piece of code (used to grep files but can be easily modified for other commands)..<br /><div><br /></div><div><br /><div style="margin-bottom: 0.0001pt;"><b><span style="background: white; color: navy; font-family: &quot;Courier New&quot;; font-size: 10.0pt;">%macro</span></b><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">grep(loc,string); <o:p></o:p></span></div><div style="margin-bottom: 0.0001pt;"><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">filename x pipe </span><span style="background: white; color: purple; font-family: &quot;Courier New&quot;; font-size: 10.0pt;">"cd &amp;loc; grep -irl &amp;string ."</span><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">; <o:p></o:p></span></div><div style="margin-bottom: 0.0001pt;"><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">data _null_; <o:p></o:p></span></div><div style="margin-bottom: 0.0001pt;"><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">infile x; <o:p></o:p></span></div><div style="margin-bottom: 0.0001pt;"><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">input; <o:p></o:p></span></div><div style="margin-bottom: 0.0001pt;"><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">put _infile_; <o:p></o:p></span></div><div style="margin-bottom: 0.0001pt;"><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">run; <o:p></o:p></span></div><div style="margin-bottom: 0.0001pt;"><b><span style="background: white; color: navy; font-family: &quot;Courier New&quot;; font-size: 10.0pt;">%mend</span></b><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">; <o:p></o:p></span></div><div style="margin-bottom: 0.0001pt;"><span style="background: white; color: green; font-family: &quot;Courier New&quot;; font-size: 10.0pt;">/* check logs */</span><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;"><o:p></o:p></span></div><div style="margin-bottom: 0.0001pt;"><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">%<b><i>grep</i></b>(C:myDirLoc,searchString)&nbsp;<o:p></o:p></span></div></div>