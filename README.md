<h1>Udacity FEND P4: Website Performance Optimization</h1>

Part 1: Optimize PageSpeed Insights score for index.html

1.	Host project on GitHub pages [Score: 30]
2.	Resize/compress pizzeria.jpg from 2.25 MB to 22 KB [Score: 88]
3.	Add async attribute to google-analytics script [Score: 88]
4.	Inline style.css & print.css [Score: 89]
5.	Remove font styles without any noticeable change in website (but see 8 below) [Score: 94]
6.	Inline perfmatters.js [Score: 95]
7.	Move styles and scripts to bottom of HTML [Score: 95]

Possible further improvements:
8.	Inline font styles (see details given in index.html/13)
9.	Leverage browser caching of: profilepic.jpg (by 10 minutes), perfmatters.js (10 minutes), pizzeria.jpg (10 minutes), analytics.js (2 hours)
10.	Optimize images further
11.	Add build tools to automatically optimize CSS & JavaScript (minify) and images.
12.	 [Run on a local server]

Part 2: Optimize Frames per Second in pizza.html

Changes to pizza.html:

1.	Configure viewport to make browser render the width of the page at the width of its own screen  [line: 5]
2.	Inline style.css  [8]
3.	Average time to generate frames on scrolling < 0.3 ms or > 3333 fps
4.	Time to resize pizzas < 0.5 ms

Changes to main.js:

5.	Optimize pizza.png (to reduce size)  [363]
6.	Replace querySelectorAll by getElementsByClass to access the DOM faster  [391, 485, 526]
7.	Delete determineDx & sizeSwitcher as not required to change pizza sizes directly (see 435 below)  [411]
8.	Change sizeSwitcher to changePizzaSizes  [428]
9.	Remove document.getElementsByClassName and –.length outside for loop (constant; unnecessary to call DOM repeatedly)  [431]
10.	Changes width of each element to new width using percentages  [435]
11.	Remove document.getElementById outside for loop (constant; unnecessary to call DOM repeatedly)  [451]
12.	Remove items.length and document.body.scrollTop/1250 outside for loop (constant; unnecessary to call DOM repeatedly)  [488]
13.	Reduce number of pizzas to only that necessary to fill the screen, using screen.availHeight  [515]

Possible further improvements:
14.	Remove style.css?  Not required anymore, as it is inlined in pizza.html.
15.	 Understand that (i % 5) = {0,1,2,3,4} for all i  0, but how can this be used to speed up the page?  This computation changes with every run of the for loop (i.e. it is not constant, so can be moved out of the loop).  [493]

Other

•	Project available at rajiv-shankar.github.io/Udacity-FEND-Project-4
•	Folders: src contains readable code and dist contains minified files
•	Wrote this ReadMe document
•	All changes given in files as well in ALLCAP in block comments (usually), to distinguish them from existing comments.
