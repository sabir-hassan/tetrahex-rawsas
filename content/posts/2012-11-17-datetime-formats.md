---
title: 'datetime formats'
date: '2012-11-17 15:04:00'
path: '/datetime-formats/'
previewImg: ''
tags:
  - SQL
---

My favourites:<br />

<div style="margin-bottom: 0.0001pt;"><span style="background: white; color: blue; font-family: &quot;Courier New&quot;; font-size: 10.0pt;">%put</span><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;"></span><span style="background: white; color: blue; font-family: &quot;Courier New&quot;; font-size: 10.0pt;">%sysfunc</span><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">(datetime(),B8601DT19);</span></div>
<div style="margin-bottom: 0.0001pt;"><span style="background-color: white; color: blue; font-family: 'Courier New'; font-size: 13px;">%put</span><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">&nbsp;</span><span style="background: white; color: blue; font-family: &quot;Courier New&quot;; font-size: 10.0pt;">%sysfunc</span><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">(datetime(),is8601dt.);</span></div>
<div style="margin-bottom: 0.0001pt;"><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;"><br /></span></div>
<div style="margin-bottom: 0.0001pt;"><span style="background-color: white; background-position: initial initial; background-repeat: initial initial; font-family: 'Courier New'; font-size: 10pt;">Which give:</span></div>
<div style="margin-bottom: 0.0001pt;"><span style="background-color: white;"></span></div>
<div style="margin-bottom: 0.0001pt;"><span style="font-family: Courier New; font-size: x-small;">20121117T150358&nbsp;</span></div>
<div style="margin-bottom: 0.0001pt;"><span style="font-family: Courier New; font-size: x-small;">2012-11-17T15:03:58</span></div>
<br />
Full list: &nbsp;http://support.sas.com/documentation/cdl/en/lrdict/64316/HTML/default/viewer.htm#a001263753.htm
