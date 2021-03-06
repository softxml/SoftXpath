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
|**load**|expects valid path to <b>xml file</b> as parameter and loads given file|<pre>myXpathObj.<b>load</b>("flash_vs_page.xml")</pre>|`true/false`
|**loadXML**|expects valid <b>xml string</b> as parameter and loads given string|<pre>myXpathObj.<b>loadXML</b>("&lt;root&gt;&lt;item color='blue'&gt;demo1&lt;/item&gt;&lt;item color='red'&gt;demo2&lt;/item&gt;&lt;item color='blue'&gt;demo3&lt;/item&gt;&lt;/root&gt;")</pre>|`true/false`
|**registerNamespace**|expects <b>prefix</b>/<b>URI</b> pair and sets user defined namespaces<br>default is none - myXpathObj.<b>registerNamespace</b>("","")|<pre>myXpathObj.<b>registerNamespace</b>("<b>xsl</b>","<b>http://www.softxml.com</b>");<br/>myXpathObj.<b>loadXML</b>("&lt;xsl:root xmlns:xsl='http://www.softxml.com'&gt; &lt;xsl:item color='blue'&gt;demo1&lt;/xsl:item&gt;&lt;xsl:item color='red'&gt;demo2&lt;/xsl:item&gt;&lt;xsl:item color='blue'&gt;demo3&lt;/xsl:item&gt;&lt;/xsl:root&gt;");<br/>//<b>After defining namespace you don't need to change your xpath expression</b><br/>var results = myXpathObj.<b>selectNodes</b>("//item[@color='blue']");</pre>|
|**selectNodes**|expects valid <b>xpath expression</b> and returns array of objects|<pre>var results = myXpathObj.<b>selectNodes</b>("//item[@color='blue']")</pre>|Array of Objects<br>
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

Examples
-------------
SoftXpath **load** method
Our XML file called "flash_vs_page.xml" and it's structure shown below:
-------------
<pre>
	&lt;?xml version="1.0"?&gt;
		&lt;xsl:categories xmlns:xsl="http://www.softxml.com"&gt;
			&lt;xsl:category name="CLeasing"&gt;
				&lt;xsl:language name="en"&gt;
					&lt;xsl:page name="aboutSixt.asp" value="video_41.swf"/&gt;
					&lt;xsl:page name="aboutUs.asp" value="video_42.swf"/&gt;
					&lt;xsl:page name="advantage.asp" value="video_43.swf"/&gt;
					&lt;xsl:page name="club.asp" value="video_44.swf"/&gt;
					&lt;xsl:page name="Cservice.asp" value="video_45.swf"/&gt;
					&lt;xsl:page name="infoSafety.asp" value="video_46.swf"/&gt;
					&lt;xsl:page name="LetterFinal.asp" value="video_47.swf"/&gt;
					&lt;xsl:page name="orderInfo.asp" value="video_48.swf"/&gt;
					&lt;xsl:page name="pressRelease.asp" value="video_49.swf"/&gt;
					&lt;xsl:page name="Resultview.asp" value="video_50.swf"/&gt;
					&lt;xsl:page name="roadTests.asp" value="video_51.swf"/&gt;
					&lt;xsl:page name="SearchAdvanceB.asp" value="video_52.swf"/&gt;
					&lt;xsl:page name="SearchQuickB.asp" value="video_53.swf"/&gt;
					&lt;xsl:page name="SearchResultB.asp" value="video_54.swf"/&gt;
					&lt;xsl:page name="service.asp" value="video_55.swf"/&gt;
					&lt;xsl:page name="SI_jobs.asp" value="video_56.swf"/&gt;
					&lt;xsl:page name="SI_orderFix.asp" value="video_57.swf"/&gt;
					&lt;xsl:page name="SI_writeus.asp" value="video_58.swf"/&gt;
					&lt;xsl:page name="SupplementsB.asp" value="video_59.swf"/&gt;
					&lt;xsl:page name="ResultView.asp" value="video_60.swf"/&gt;
					&lt;xsl:page name="branches.asp" value="video_61.swf"/&gt;
					&lt;xsl:page name="login.asp" value="video_62.swf"/&gt;
					&lt;xsl:page name="makelogin.asp" value="video_63.swf"/&gt;
					&lt;xsl:page name="personal.asp" value="video_64.swf"/&gt;
				&lt;/xsl:language&gt;
				&lt;xsl:language name="he"&gt;
					&lt;xsl:page name="aboutSixt.asp" value="new_kopel_key_120x150.swf"/&gt;
					&lt;xsl:page name="aboutUs.asp" value="new_kopel_key_120x151.swf"/&gt;
					&lt;xsl:page name="advantage.asp" value="new_kopel_key_120x152.swf"/&gt;
					&lt;xsl:page name="club.asp" value="new_kopel_key_120x153.swf"/&gt;
					&lt;xsl:page name="Cservice.asp" value="new_kopel_key_120x154.swf"/&gt;
					&lt;xsl:page name="infoSafety.asp" value="new_kopel_key_120x155.swf"/&gt;
					&lt;xsl:page name="LetterFinal.asp" value="new_kopel_key_120x156.swf"/&gt;
					&lt;xsl:page name="orderInfo.asp" value="new_kopel_key_120x157.swf"/&gt;
					&lt;xsl:page name="pressRelease.asp" value="new_kopel_key_120x158.swf"/&gt;
					&lt;xsl:page name="accident.asp" value="new_kopel_key_120x159.swf"/&gt;
					&lt;xsl:page name="Resultview.asp" value="new_kopel_key_120x160.swf"/&gt;
					&lt;xsl:page name="roadTests.asp" value="new_kopel_key_120x161.swf"/&gt;
					&lt;xsl:page name="SearchAdvanceB.asp" value="new_kopel_key_120x162.swf"/&gt;
					&lt;xsl:page name="SearchQuickB.asp" value="new_kopel_key_120x163.swf"/&gt;
					&lt;xsl:page name="SearchQuickBNew.asp" value="new_kopel_key_120x164.swf"/&gt;
					&lt;xsl:page name="icar.asp" value="new_kopel_key_120x165.swf"/&gt;
					&lt;xsl:page name="SearchResultB.asp" value="new_kopel_key_120x166.swf"/&gt;
					&lt;xsl:page name="service.asp" value="new_kopel_key_120x167.swf"/&gt;
					&lt;xsl:page name="SI_jobs.asp" value="new_kopel_key_120x168.swf"/&gt;
					&lt;xsl:page name="SI_orderFix.asp" value="new_kopel_key_120x169.swf"/&gt;
					&lt;xsl:page name="SI_writeus.asp" value="new_kopel_key_120x170.swf"/&gt;
					&lt;xsl:page name="SupplementsB.asp" value="new_kopel_key_120x171.swf"/&gt;
					&lt;xsl:page name="branches.asp" value="new_kopel_key_120x172.swf"/&gt;
					&lt;xsl:page name="login.asp" value="new_kopel_key_120x173.swf"/&gt;
					&lt;xsl:page name="makelogin.asp" value="new_kopel_key_120x174.swf"/&gt;
					&lt;xsl:page name="personal.asp" value="new_kopel_key_120x175.swf"/&gt;
				&lt;/xsl:language&gt;
			&lt;/xsl:category&gt;
		&lt;/xsl:categories&gt;
</pre>

JavaScript Code
-------------
<pre>
	var myXpathObj = new SoftXpath();
	myXpathObj.registerNamespace("xsl","http://www.softxml.com");
	if(myXpathObj.load("flash_vs_page.xml")){
		var results = myXpathObj.selectNodes("//page[./parent::language[@name='he'] and ./@name='aboutSixt.asp']/@value");
		if(results.length==0){
			alert("No records found!");
		}
		else{
			for(var i=0;i&lt;results.length;i++){
				alert(results[i].text);
			}
		}	
	}
	else{
		alert("Loading xml file failed!");
	}
</pre>


SoftXpath **loadXML** method
Our XML string shown below:
-------------
<pre>
	&lt;?xml version="1.0"?&gt;
	&lt;catalog&gt;
	   &lt;product description="Cardigan Sweater" product_image="cardigan.jpg"&gt;
	      &lt;catalog_item gender="Men's"&gt;
	         &lt;item_number&gt;QWZ5671&lt;/item_number&gt;
	         &lt;price&gt;39.95&lt;/price&gt;
	         &lt;size description="Medium"&gt;
	            &lt;color_swatch image="red_cardigan.jpg"&gt;Red&lt;/color_swatch&gt;
	            &lt;color_swatch image="burgundy_cardigan.jpg"&gt;Burgundy&lt;/color_swatch&gt;
	         &lt;/size&gt;
	         &lt;size description="Large"&gt;
	            &lt;color_swatch image="red_cardigan.jpg"&gt;Red&lt;/color_swatch&gt;
	            &lt;color_swatch image="burgundy_cardigan.jpg"&gt;Burgundy&lt;/color_swatch&gt;
	         &lt;/size&gt;
	      &lt;/catalog_item&gt;
	      &lt;catalog_item gender="Women's"&gt;
	         &lt;item_number&gt;RRX9856&lt;/item_number&gt;
	         &lt;price&gt;42.50&lt;/price&gt;
	         &lt;size description="Small"&gt;
	            &lt;color_swatch image="red_cardigan.jpg"&gt;Red&lt;/color_swatch&gt;
	            &lt;color_swatch image="navy_cardigan.jpg"&gt;Navy&lt;/color_swatch&gt;
	            &lt;color_swatch image="burgundy_cardigan.jpg"&gt;Burgundy&lt;/color_swatch&gt;
	         &lt;/size&gt;
	         &lt;size description="Medium"&gt;
	            &lt;color_swatch image="red_cardigan.jpg"&gt;Red&lt;/color_swatch&gt;
	            &lt;color_swatch image="navy_cardigan.jpg"&gt;Navy&lt;/color_swatch&gt;
	            &lt;color_swatch image="burgundy_cardigan.jpg"&gt;Burgundy&lt;/color_swatch&gt;
	            &lt;color_swatch image="black_cardigan.jpg"&gt;Black&lt;/color_swatch&gt;
	         &lt;/size&gt;
	         &lt;size description="Large"&gt;
	            &lt;color_swatch image="navy_cardigan.jpg"&gt;Navy&lt;/color_swatch&gt;
	            &lt;color_swatch image="black_cardigan.jpg"&gt;Black&lt;/color_swatch&gt;
	         &lt;/size&gt;
	         &lt;size description="Extra Large"&gt;
	            &lt;color_swatch image="burgundy_cardigan.jpg"&gt;Burgundy&lt;/color_swatch&gt;
	            &lt;color_swatch image="black_cardigan.jpg"&gt;Black&lt;/color_swatch&gt;
	         &lt;/size&gt;
	      &lt;/catalog_item&gt;
	   &lt;/product&gt;
	&lt;/catalog&gt;
</pre>

JavaScript Code
-------------
<pre>
	var myXpathObj = new SoftXpath();
	myXpathObj.registerNamespace('','');
	if(myXpathObj.loadXML(xmlstring)){
		var results = myXpathObj.selectNodes("//color_swatch[./ancestor::catalog_item/child::item_number[text()='QWZ5671'] and ./parent::size[@description='Medium']]");
		if(results.length==0){
			alert("No records found!");
		}
		else{
			for(var i=0;i&lt;results.length;i++){
				alert(results[i].text);
			}
		}
	}
	else{
		alert("Loading xml string failed!");
	}
</pre>



Online Demo
-------------

[SoftXpath Online Demo](http://www.softxml.com/SoftXPathDemo.htm)
