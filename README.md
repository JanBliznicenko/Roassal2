
This fork changes the timeline functionality to allow visualizing arrays of dates. Here's an example:

```Smalltalk
	| data b s |
	data := Array with: 
        (Array with:'abc' with:(Date fromString:'1 March 2019') with:(Date fromString: '5 April 2019')) with:
        (Array with:'efg' with:(Date fromString:'1 April 2019') with:(Date fromString: '7 April 2019')).

	b := RTTimeline new.
	
	s := RTTimelineSet new.
	s objects: data.
	s lineIdentifier: #first.
	s start: #second.
	s end: #third.
	b add: s.
	
	b axisX 
		numberOfLabels: 5;
		labelRotation: -45;
		labelConversion: [ :v | v ]. 
	
	b build.
	^ b view
```

# Roassal2

Roassal2 is a visualization engine for the Pharo and VisualWorks programming language and environment.
Extensive documentation is available on http://AgileVisualization.com

---
## VisualWorks

The distribution of Roassal for VisualWorks is in the Cincom public store. Simply look for `roassal2-full` on the public store. Note that your need to have the Cairo libraries installed along with the VisualWorks installation.

---
## Pharo 7
The source code of Roassal2 is contained in this GitHub repository.

Execute the following code snippet to load Roassal2 in a fresh Pharo 7 image:
```Smalltalk
Metacello new
    baseline: 'Roassal2';
    repository: 'github://ObjectProfile/Roassal2/src';
    load.
```

You can also load Roassal2 from the Pharo Catalog browser.

If you have a local copy of Roassal, you can do the following:

```Smalltalk
Metacello new
  baseline: 'Roassal2';
  repository: 'gitlocal:///Users/alexandrebergel/Dropbox/GitRepos/Roassal2' ;
  lock;
  load.
```

---
## Pharo 6.1

You can load Roassal in Pharo 6.1 using the following script:

```Smalltalk
Gofer it
    smalltalkhubUser: 'ObjectProfile' project: 'Roassal2';
    configurationOf: 'Roassal2';
    loadVersion: '1.59'
```
