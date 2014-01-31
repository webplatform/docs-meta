{{Editorial/Merge_Candidate|Other=http://docs.webplatform.org/wiki/javascript/parseInt}}

When a <code>String</code> variable containing numbers is passed as an argument of the <code>parseInt()</code> function, it returns the equivalent <code>Integer</code> variable, so it can be manipulated as a number to do calculations or logic tests.

 var foo = "42";
 var bar = parseInt(foo, 10) + 1; // bar = 43

The second parameter of the <code>parseInt()</code> function is the radix which specifies the number system used by the function. Explicitly define your radix with each function call to avoid unexpected behaviour.

 parseInt('0016'); // parses as 14. The beginning 0 in the string means the browser assumes the octal number system.
 parseInt('0016', 10); // parses as 16. We explicitly set the function to use decimal number system.

[[Category:JavaScript]]