# PathSankey
Qlik Sense Path Sankey Extension

Developed by Xavier Le Pitre, based on D3.js
Modified by Bardess Group
Modified by Dalton Ruer

Single Dimension Entry:

There are many areas of data we work with that involve a series of events over time. In the online world it may involve clicking on web pages. In healthcare it might involve a series of surgical events or procedures. Thus for the sake of simplicity I simply chose the values "Event1" "Event2" etc. 

Assume the following in your load script:
Data:
Load * Inline [
ID, Path
1, 'Event1, Event2, Event3'
2, 'Event1, Event2, Event4'
3, 'Event1, Event3, Event4, Event5, Event6'
4, 'Event2, Event3, Event4, Event5'
5, 'Event2, Event3, Event5, Event6'
6, 'Event2, Event3, Event5, Event6'
7, 'Event2, Event4, Event5, Event4, Event5'
8, 'Event1, Event2, Event4'
9, 'Event3, Event6, Event9'
10, 'Event3, Event6, Event9, Event10'
11, 'Event3, Event6, Event9'
12, 'Event3, Event6, Event9'
13, 'Event3, Event6, Event9'
14, 'Event4, Event10, Event11'
];

Setting a single Dimension to your field "Path" and using a measure of "Count(ID)" will yield the following output:
![alt tag](https://raw.githubusercontent.com/DaltonRuer/PathSankey/master/pathsankey.png) 

There are also many areas of data where analysis of relationships is also important to understand. Pie charts are great for comparing single dimesnions. But this sankey can also be used to show relationships between dimensions so you understand how they relate to each other. 

Assume the following data in the load script:
data2:
Load * Inline [
ID2, Field1, Field2, Field3
1, Male, Blue, Zip1
2, Male, Brown, Zip2
3, Male, Green, Zip2
4, Female, Blue, Zip2
5, Female, Blue, Zip3
6, Female, Blue, Zip3
7, Female, Green, Zip1
8, Female, Brown, Zip2
9, Male, Hazel, Zip3
10, Female, Green, Zip2
11, Female, Blue, Zip3
];

Setting a single dimension to a concatentation of the fields like "=Field1 & ', ' & Field2 & ', '& Field3 & '," and using a measure of "Count(ID2) will yield the following output. Notice that like a pie chart you can tell that there are more Females than Male. More importantly you can tell that the majority of Blue eyed people are Female rather than male. While also seeing the overall comparison like a pie chart between the color of eyes. 

![alt tag](https://raw.githubusercontent.com/DaltonRuer/PathSankey/master/relationship.png) 

You can create the same effect to view the relationships between fields by simply using multiple Dimensions:
![alt tag](https://raw.githubusercontent.com/DaltonRuer/PathSankey/master/dimensions.png) 

License
Please, if you update this extension feel free to send me your pull requests to help others users to enjoy all features!
The MIT License (MIT)
Copyright (c) 2015 Xavier Le Pitre
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
