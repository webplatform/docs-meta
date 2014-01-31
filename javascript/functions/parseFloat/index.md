{{Editorial/Merge_Candidate|Other=http://docs.webplatform.org/wiki/javascript/parseFloat}}

The <code>parseFloat()</code> function returns the first number that it finds in the <code>String</code> argument. If the first character cannot be converted to a number, it returns <code>NaN</code>.

 parseFloat("42"); // parses as 42
 parseFloat("12.34 56.78"); // parses as 12.34
 parseFloat("314e-2"); // parses as 3.14
 parseFloat("99bottles"); // parses as 99
 parseFloat("Bottles99"); // parses as NaN

You can use <code>[[javascript/functions/isNaN|isNaN()]]</code> to test for the returned value of <code>NaN</code>.

[[Category:JavaScript]]