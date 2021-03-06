---
title: 'The Performance of Dosubl vs Call Execute'
date: '2017-11-16 01:21:59'
path: '/dosubl-vs-call-execute/'
previewImg: ''
tags:
  - Programming
  - sas
---

Both <code>dosubl</code> and <code>call execute</code> accept raw SAS code as input.  The difference between them is that <code>call execute</code> will take your code and add it to the stack (so, after your data step completes) whilst <code>dosubl</code> will execute your code <em>immediately</em>.

Dosubl is a fantastic function, which I use frequently, but after recently <a href="https://www.linkedin.com/feed/update/urn:li:activity:6334095623373099008?commentUrn=urn%3Ali%3Acomment%3A%28activity%3A6334034113179242496%2C6334095608772726784%29">lamenting it's performance</a> I was asked - just how slow is it compared to call execute?

Well of course the way to find out is to run some tests, which I did as per below.  I created a minimal data step, and switched off logging, and ran the exact same code twice:

<pre>options nonotes;
/* dosubl */
data _null_;
 call symputx('start',datetime());
run;
data _null_;
  do x=1 to 500;
  rc=dosubl('data;do stuff=1;end;run;');
  end;
run;
data _null_;
  dur=datetime()-&amp;start;
  call symputx('dosubl',dur);
run;

/* call execute */
data _null_;
  call symputx('start',datetime());
run;
data _null_;
  do x=1 to 500;
  call execute('data;do stuff=1;end;run;');
  end;
run;
data _null_;
  dur=datetime()-&amp;start;
  call symputx('execute',dur);
run;
%put &amp;=dosubl;
%put &amp;=execute;
</pre>

And the results?  Drum roll please...

<img class="alignnone size-medium wp-image-263" src="../images/Screen-Shot-2017-11-16-at-01.12.39-300x94.png" alt="" width="300" height="94" />

As per the log, dosubl finished in 47.6 seconds vs 3.7 seconds for call execute.  Lesson learned?  As useful and incredibly convenient as it is, <code>dosubl</code> is a function that should be used sparingly!
