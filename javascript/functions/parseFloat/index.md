---
title: Meta:javascript/functions/parseFloat
---
<p><br />
</p><p><br />
</p>
<div class="editors-only">
<p><b>Merge Candidate</b>:  This page is a candidate for merge with the following pages: [<a rel="nofollow" class="external autonumber" href="http://docs.webplatform.org/wiki/javascript/parseFloat">[1]</a>] 
</p>
</div>
<p><br />
</p><p>The <code>parseFloat()</code> function returns the first number that it finds in the <code>String</code> argument. If the first character cannot be converted to a number, it returns <code>NaN</code>.
</p>
<pre>parseFloat("42"); // parses as 42
parseFloat("12.34 56.78"); // parses as 12.34
parseFloat("314e-2"); // parses as 3.14
parseFloat("99bottles"); // parses as 99
parseFloat("Bottles99"); // parses as NaN
</pre>
<p>You can use <code><a href="/w/index.php?title=javascript/functions/isNaN&amp;action=edit&amp;redlink=1" class="new" title="javascript/functions/isNaN (page does not exist)">isNaN()</a></code> to test for the returned value of <code>NaN</code>.
</p>
<!-- Saved in parser cache with key wpwiki:pcache:idhash:5598-0!*!0!*!*!*!*!esi=1 and timestamp 20150731181715 and revision id 45439
 -->
