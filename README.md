# DD ScrollSpy Menu #

*Description:* For long pages with lots of content, keeping the user oriented and knowing where within the page he/she is at all times can be challenging. DD ScrollSpy Menu solves this problem, by letting you create a menu whose menu items are automatically highlighted based on the portion of the page the user is currently viewing. As the user scrolls the page, the menu item that points to that section is highlighted (via the injection of a desired CSS class to style it). The script also works on scrollable DIVs within the page to spy on their scroll positions instead. Starting in v1.2, you can now also enable a progress bar to be shown inside each spymenu's menu item to show a progress of how much the user has scrolled within the currently viewed section. DD ScrollSpy "spies" on the visitor's position on the page, but for their benefit (and in turn yours)!

## Directions ##

*Step 1:* This script uses the following external files:

+ jQuery 1.7 or above (served via Google CDN)
+ ddscrollspy.js
+ ddscrollspydemo.css

*Step 2:* Add the below code to the HEAD section of your page:

	<link rel="stylesheet" href="ddscrollspydemo.css" />
	
	<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.8/jquery.min.js"></script>
	
	<script src="ddscrollspy.js">
	
	/*
	* DD ScrollSpy Menu Script (c) Dynamic Drive (www.dynamicdrive.com)
	* Last updated: Aug 1st, 14'
	* Visit http://www.dynamicdrive.com/ for this script and 100s more.
	*/
	
	</script>
	
	<script>
	
	jQuery(function($){ // on document load
		$('#horizontalmenu').ddscrollSpy({ // initialize first demo
			scrolltopoffset: -50
		})
	
		$('#verticalspymenu').ddscrollSpy({ // initialize 2nd demo
			spytarget: document.getElementById('contentcontainer'),
			enableprogress: 'progress',
			scrollduration: 300,
      		onHighlight: function (element) {
        		// Called when item is highlighted
      		} // <-- no comma after last option!
		})
	})
	
	function dynamicadditem(){ // function that dynamically adds a new menu item to first demo, spying on #para6
		$('#verticalspymenu').append('<li><a href="#para5">Paragraph 5</a></li>')
		$('#verticalspymenu').trigger('updatespy')
	}
	
	</script>


*Step 3:* Then, add the below sample markup to your page:

	<!-- Scroll Spy Menu 1 -->
	
	<ul id="horizontalmenu" class="underlinemenu">
	<li><a href="#section1">Section 1</a></li>
	<li><a href="#section2">Section 2</a></li>
	<li><a href="#section3">Section 3</a></li>
	<li><a href="#section4">Section 4</a></li>
	<li><a href="#section5">Section 5</a></li>
	</ul>
	
	<!-- Scroll Spy Menu 2 -->
	
	<div style="float:left; margin-right:15px; width:150px; margin-top: 120px">
		<ul  id="verticalspymenu" class="shadowblockmenu-v">
		<li><a href="#para1">Paragraph 1</a></li>
		<li><a href="#para2">Paragraph 2</a></li>
		<li><a href="#para3">Paragraph 3</a></li>
		<li><a href="#para4">Paragraph 4</a></li>
		</ul>
	
	<br />
	<a href="javascript:dynamicadditem()" style="font-weight:bold">Click to dynamically add another menu item</a>
	
	</div>
	
	<!-- Contents that Scroll Spy Menu 2 is spying on -->
	
	<div id="contentcontainer" style="width:500px; height:200px; overflow-y:scroll; border:1px solid gray; font:bold 18px Arial; float:left; background:yellow; position:relative; margin-top: 120px">
		<p id="para1" style="height:400px; background:#d5e9b2">Paragraph 1</p>
		<p id="para2" style="height:600px; background:#f7de90">Paragraph 2</p>
		<p id="para3" style="height:700px; background:#9af5ed">Paragraph 3</p>
		<p id="para4" style="height:500px; background:#fbd0e3">Paragraph 4</p>
		<p id="para5" style="height:300px; background:#cbffe1">Paragraph 5</p>
	</div>
	
	<br style="clear:left" />
	
	<!-- Contents that Scroll Spy Menu 1 is spying on -->
	
	<div id="section1" style="height:300px;">
	<h2>This is section 1</h2>
	</div>
	
	<div id="section2" style="height:400px;">
	<h2>This is section 2</h2>
	</div>
	
	<div id="section3" style="height:700px;">
	<h2>This is section 3</h2>
	</div>
	
	<div id="section4" style="height:600px;">
	<h2>This is section 4</h2>
	</div>
	
	<div id="section5" style="height:1000px;">
	<h2>This is section 5</h2>
	</div>

## DD ScrollSpy Menu set up ##

See script project page for additional details on setup and documentation: <http://www.dynamicdrive.com/dynamicindex1/ddscrollspymenu.htm>
