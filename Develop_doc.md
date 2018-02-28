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

**regions.js**

A simplified example of `regions.js` is as follows:

``` javascript
var region_list = [
	// Some codes
	[null, 1928, 1934,
		[ 1928, 1931,"cn/sov","中國工農紅軍","Chinese Red Army","@","(共産党)","(Communists)","@",2960,625,1],
		[ 1931, 1934,"cn/sov","中華ソヴィエト共和国","Soviet Republic of China","中華蘇維埃共和国","(共産党)","(Communists)","@"],
		["主席","Leader","@"],
		[ 1931, 1934,"cn/mao-young","毛澤東","Mao Ze-dong","@"],
	],
	// Some codes
]
```

There're a master array `region_list`.

Within `region_list`, there're several sub-arraies. Each sub-array means a countries. The first item is now deprecated, its value is unified as `null`. The following two items is the beginning and ending year of the country. If the contry did not perish,set the item of ending year as 9999.

Starting from the fourth, each item is an array. Within it, country names and flags should be defined first. As the example, the front two item is the beginning and ending year of the item. The third item defines the nathonal flag or symble (image path relative to `./sym/` and without `.png`). The fourth to sixth items define the country name in Japanese, English and Chinese. `@` and `$` means to be the same with the Japanese part and English part. 

(To be supplemented...)

**territory.js**

(To be supplemented...)
