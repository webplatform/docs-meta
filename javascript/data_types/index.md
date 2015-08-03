---
title: Meta:javascript/data types
---
<h1><span class="mw-headline" id="JavaScript_data_types">JavaScript data types</span></h1>
<h2><span class="mw-headline" id="Summary">Summary</span></h2>
<p>Index page for JavaScript data types
</p><p><br />
</p><p><br />
</p>
<div class="editors-only">
<p><b>Merge Candidate</b>:  This page is a candidate for merge with the following pages:  
</p>
</div>
<p><br />
</p><p><br />
</p>
<h2><span class="mw-headline" id="Introduction">Introduction</span></h2>
<p>Unlike other programming languages every thing in JavaScript is a object, this includes arrays(lists), functions, strings, and numbers. There are 6 types defined by ECMAScript: <code>Undefined</code>, <code>Null</code>, <code>Boolean</code>, <code>String</code>, <code>Number</code> and <code>Object</code>.
</p><p>As functions are objects in JavaScript they can be passed as normal data, which means this would work:
</p><p><code>SomeFunction(1, function(error) { console.log(error);});</code>
</p><p>in JavaScript and wouldn't in most other languages.
</p><p>Also in JavaScript there are two ways to create Variables:
</p><p>1. The Object way:
</p>
<div dir="ltr" class="mw-geshi mw-code mw-content-ltr"><div class="javascript source-javascript"><pre class="de1"><span class="co1">//A string</span>
<span class="kw1">var</span> string <span class="sy0">=</span> <span class="kw1">new</span> <span class="kw4">String</span><span class="br0">&#40;</span><span class="st0">&quot;Hello World!&quot;</span><span class="br0">&#41;</span><span class="sy0">;</span>
<span class="co1">//An array</span>
<span class="kw1">var</span> array <span class="sy0">=</span> <span class="kw1">new</span> <span class="kw4">Array</span><span class="br0">&#40;</span><span class="st0">&quot;H&quot;</span><span class="sy0">,</span> <span class="st0">&quot;e&quot;</span><span class="sy0">,</span> <span class="st0">&quot;l&quot;</span><span class="sy0">,</span> <span class="st0">&quot;l&quot;</span><span class="sy0">,</span> <span class="st0">&quot;o&quot;</span><span class="sy0">,</span> <span class="st0">&quot; &quot;</span><span class="sy0">,</span> <span class="st0">&quot;W&quot;</span><span class="sy0">,</span> <span class="st0">&quot;o&quot;</span><span class="sy0">,</span> <span class="st0">&quot;r&quot;</span><span class="sy0">,</span> <span class="st0">&quot;l&quot;</span><span class="sy0">,</span> <span class="st0">&quot;d&quot;</span><span class="sy0">,</span> <span class="st0">&quot;!&quot;</span><span class="br0">&#41;</span><span class="sy0">;</span>
<span class="co1">//A number</span>
<span class="kw1">var</span> number <span class="sy0">=</span> <span class="kw1">new</span> <span class="kw4">Number</span><span class="br0">&#40;</span><span class="nu0">435560967531</span><span class="br0">&#41;</span><span class="sy0">;</span>
<span class="co1">// or </span>
<span class="kw1">var</span> number <span class="sy0">=</span> <span class="kw1">new</span> <span class="kw4">Number</span><span class="br0">&#40;</span><span class="st0">&quot;435560967531&quot;</span><span class="br0">&#41;</span><span class="sy0">;</span></pre></div></div>
<p>2.The way used in most other languages:
</p>
<div dir="ltr" class="mw-geshi mw-code mw-content-ltr"><div class="javascript source-javascript"><pre class="de1"><span class="co1">//A string</span>
<span class="kw1">var</span> string <span class="sy0">=</span> <span class="st0">&quot;Hello World!&quot;</span><span class="sy0">;</span>
<span class="co1">//An array</span>
<span class="kw1">var</span> array <span class="sy0">=</span> <span class="br0">&#91;</span><span class="st0">&quot;H&quot;</span><span class="sy0">,</span> <span class="st0">&quot;e&quot;</span><span class="sy0">,</span> <span class="st0">&quot;l&quot;</span><span class="sy0">,</span> <span class="st0">&quot;l&quot;</span><span class="sy0">,</span> <span class="st0">&quot;o&quot;</span><span class="sy0">,</span> <span class="st0">&quot; &quot;</span><span class="sy0">,</span> <span class="st0">&quot;W&quot;</span><span class="sy0">,</span> <span class="st0">&quot;o&quot;</span><span class="sy0">,</span> <span class="st0">&quot;r&quot;</span><span class="sy0">,</span> <span class="st0">&quot;l&quot;</span><span class="sy0">,</span> <span class="st0">&quot;d&quot;</span><span class="sy0">,</span> <span class="st0">&quot;!&quot;</span><span class="br0">&#93;</span><span class="sy0">;</span>
<span class="co1">//A number</span>
<span class="kw1">var</span> number <span class="sy0">=</span> <span class="nu0">435560967531</span><span class="sy0">;</span></pre></div></div>
<div class="attribution">
<p><br />
</p><p><br />
</p>
</div>
