新浪微博发布输入框，用getBoundingClientRect()来获取'@'的位置

之前的版本使用nobr标签来计算'@'的位置，具体方法是用换行符把字符串分割成数组，计算每个数组的宽高，再加上所有换行符，可得高度 top；宽度是用分割后的数组最后一个元素的字符串的宽度对textarea宽度取模得出 left。加上一些基本的字符串操作和恰当的CSS定位就可以实现。不过后来发现有个问题，比如说在中文字母数字都输入的时候，一连串的数字或字母会自动换行，这样就造成了'@'定位不准确。

昨天无意中发现了getBoundingClientRect()这个API，它提供了元素的位置信息，具体的自行了解去吧。有了这个API方便多了，想想之前的版本是把问题想复杂了。