---
title: 'DIRECT_EXE warning'
date: '2015-10-13 13:22:00'
path: '/direct_exe-warning/'
previewImg: ''
tags:
  - SQL
---

This one had me puzzled for a bit (SAS 9.2, Windows 2008,&nbsp;SQLNCLI10.1, OLEDB):<br /><br /><div style="margin-bottom: 0.0001pt;"><span style="background: white; color: teal; font-family: &quot;Courier New&quot;;">WARNING: The current setting of the DIRECT_EXE libname option will not allow this SQL statement to be passed directly to the DBMS for processing.</span></div><br />Explicitly setting the DIRECT_EXE option to DELETE had no effect. &nbsp;Assigning the library in a new session, and performing the update also worked fine. &nbsp;Thankfully the SYSCC variable was not affected, so jobs / processes continued to run, but still...<br /><br />Anyways, it turned out this was actually caused by the SASTRACE option! &nbsp;Turning this OFF removed the warning.
