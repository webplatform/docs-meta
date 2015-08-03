---
title: Meta:javascript/functions/parseInt
---
<p><br />
</p><p><br />
</p>
<div class="editors-only">
<p><b>Merge Candidate</b>:  This page is a candidate for merge with the following pages: [<a rel="nofollow" class="external autonumber" href="http://docs.webplatform.org/wiki/javascript/parseInt">[1]</a>] 
</p>
</div>
<p><br />
</p><p>When a <code>String</code> variable containing numbers is passed as an argument of the <code>parseInt()</code> function, it returns the equivalent <code>Integer</code> variable, so it can be manipulated as a number to do calculations or logic tests.
</p>
<pre>var foo = "42";
var bar = parseInt(foo, 10) + 1; // bar = 43
</pre>
<p>The second parameter of the <code>parseInt()</code> function is the radix which specifies the number system used by the function. Explicitly define your radix with each function call to avoid unexpected behaviour.
</p>
<pre>parseInt('0016'); // parses as 14. The beginning 0 in the string means the browser assumes the octal number system.
parseInt('0016', 10); // parses as 16. We explicitly set the function to use decimal number system.
</pre>
<!-- Saved in parser cache with key wpwiki:pcache:idhash:5207-0!*!*!*!*!*!*!esi=1 and timestamp 20150731181704 and revision id 45440
 -->
