---
title: 'Debugging Stored Processes'
date: '2013-11-08 11:49:00'
path: '/debugging-stored-processes/'
tags:
  - Movable Type
---

<h2>Debugging Stored Processes</h2><div>One challenge that developers have when working with stored processes, is access to the work library. &nbsp;Whilst sessions can be configured to persist, this does not help if you want to view a snapshot of your datasets at a particular point in the process. &nbsp; The following snippet may help in this regard:</div><div><br /></div><div><div style="font-family: 'Courier New'; font-size: 10px;"><span style="color: #0433ff;">libname</span> twork <span style="color: #942193;">"&amp;tloc"</span>;</div><div style="color: #011993; font-family: 'Courier New'; font-size: 10px;"><b>proc</b><span style="color: black;"> </span><b>datasets</b><span style="color: black;"> </span><span style="color: #0433ff;">lib</span><span style="color: black;">=twork </span><span style="color: #0433ff;">kill</span><span style="color: black;">;&nbsp;</span></div><div style="font-family: 'Courier New'; font-size: 10px;"><span style="color: #011993;"><b>proc</b></span> <span style="color: #011993;"><b>copy</b></span> inlib=work <span style="color: #0433ff;">outlib</span>=twork;</div><div style="color: #0433ff; font-family: 'Courier New'; font-size: 10px;"><span style="color: #011993;"><b>data</b></span><span style="color: black;"> </span>_Null_<span style="color: black;">;</span></div><div style="color: #942193; font-family: 'Courier New'; font-size: 10px;"><span style="color: #0433ff;">file</span><span style="color: black;"> </span>"&amp;tloc/macros.txt"<span style="color: black;">;</span></div><div style="font-family: 'Courier New'; font-size: 10px;"><span style="color: #0433ff;">set</span> sashelp.vmacro;</div><div style="font-family: 'Courier New'; font-size: 10px;"><span style="color: #0433ff;">put</span> name <span style="color: #942193;">'='</span> value;</div><br /><div style="color: #0433ff; font-family: 'Courier New'; font-size: 10px;">run<span style="color: black;">;</span></div><div style="font-family: 'Courier New'; font-size: 10px;"><span style="color: #0433ff;">libname</span><span style="color: black;">&nbsp;twork clear</span><span style="color: black;">;</span></div></div>