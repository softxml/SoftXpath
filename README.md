SoftXpath
===================

**SoftXPath** is small cross browser JavaScript library for parsing complex XML documents on client side using powerful **Xpath** expressions. Focus on building effective Xpath expressions instead of wasting time on browser compatibility issues.

----------


Browsers supported:
-------------
![supported web browsers](http://www.softxml.com/images/supported-browsers.png)


SoftXPath Tutorials & Examples
-------------------
**Include SoftXPath library in your file**:

    <script language="javascript"  src="js/SoftXPath.js"></script>

**Create new instance of SoftXpath**

    var myXpathObj = new SoftXpath();





|Method|Description|Example|Result
|:----|:----|:----|:----
|**load**|expects valid path to <b>xml file</b> as parameter and loads given file|`myXpathObj.load("flash_vs_page.xml")`|`true/false`
|**loadXML**|expects valid <b>xml string</b> as parameter and loads given string|`myXpathObj.loadXML("<root><item color='blue'>demo1</item><item color='red'>demo2</item><item color='blue'>demo3</item></root>")`|`true/false`
|**selectNodes**|expects valid <b>xpath expression</b> and returns array of objects|`var results = myXpathObj.selectNodes("//item[@color='blue']")`|var results = myXpathObj.<b>selectNodes</b>("//item[@color='blue']");<br>
<b>Check array length to see if there are matched nodes:</b><br>
<pre>if(results.length==0){
	alert("No records found");
}
else
{
 //<b>loop over matched nodes</b><br>
 for(var i=0;i&lt;results.length;i++)
  {
	//<b>Print current node's text</b>
	alert(results[i].<b>text</b>);
	
	//<b>Print current node's parent element name</b>
	//<b>me</b> points to current node itself
	alert(re[i].<b>me</b>.parentNode.nodeName);
											
	//<b>Print current node's name</b>
	alert(re[i].<b>me</b>.nodeName);

  }
}
</pre>

Online Demo
-------------

[SoftXpath Online Demo](http://www.softxml.com/SoftXPathDemo.htm)
