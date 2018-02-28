# Develop Doc

This document shows the structure of the system.

### Program Files
---
The core program files of the system are as follows:

``` javascript
./js/LangButton.js // Language switching
./js/Map.js // Map drawing
./js/Region.js // Regions and annotations
./js/twha.js // Master script
./js/YearBar.js // Year bar
./js/YearText.js // Year text(Chinese/Japanese era name or centuries)
./js/ZoomBar.js // Zoom bar
```

(To be supplemented...)

### Data Files
---
The data files of the system are as follows:

``` javascript
./f/0.png // Image of who has no face image
./f/*/*.png // Faces images of leaders
./img/*.png // Images of controls and background
./js/era.js // Chinese/Japanese era name texts
./js/regions.js // Data of countries and leaders 
./js/territory.js // The territory changes of each region
./sf/*.png // Images of lands and oceans, the file names stand for the region id
./sym/(*/)*.png // Images of countries' flags and symbols
./t/*/*.png // Images of territories, the folder names stand for the region id and the file names stand for the years
```

**era.js**

A simplified example of `era.js` is as follows:

``` javascript
var era_jp = [
	[
		[ 645,"大化"],
		[ 650,"白雉"],
		[ 655,null],
		// Some codes
		[1338,"[北]暦應"]
		// Some codes
	],
	[
		[1331,"[南]元弘"],
		[1334,null]
		// Some codes
	]
]
var era_cn = [
	// Some codes
]
```

There're two arraies `era_jp` and `era_cn` in it, `jp` and `cn` is the language code.

Within them, each sub-array is a series, that means the last era name will be end when a next one starts. And the first numeric field of 2nd-level sub-array is the beginning year of the era name.

For example, AD 645 is the first year of 大化, and AD 650 is the first year of 白雉, so AD 449 is the last year of 大化.

Especially, `null` means there're no era name since this year.

If there're two or more era names at the same time, we need more sub-arraies. In this way, it can shows as like `[北]暦應1年 / [南]元弘8年` when AD 1338.
