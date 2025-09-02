Incrementator
=================

This is a fork of [IncrementSelection by yulanggong.](https://github.com/yulanggong/IncrementSelection)
yulanggong appears to be completely inactive on GitHub, but thankfully the license permits me
to publish my modified version.  I changed the project name so it wouldn't collide with the original.

My version simply changes the inserted text so it's a uniform width.  If you insert the numbers
1-20, in the original version the numbers 1-9 would be one character wide, and the numbers
10-20 would be two characters wide.  So if you were overwriting a 2x20 selection, the first nine
edits would remove a column.  My edit changes it so every insertion is the same width; shorter
numbers are padded with spaces as needed.

The original documentation is below.

Increment Selection
==================

Add a number to each selection in Sublime Text, incremented once per selection.
You may also insert the number of line containing the selection by using the '#' symbol.

This plugin is based on [Riccardo Marotti's answer](http://stackoverflow.com/a/14578077) on StackOverflow.  The default hotkey is <kbd>ctrl</kbd> <kbd>alt</kbd> <kbd>i</kbd> or <kbd>cmd</kbd> <kbd>ctrl</kbd> <kbd>i</kbd>.

Usage
-------

Place the cursors where you need:

![step 1](http://i.stack.imgur.com/rBPkj.png)

Insert the number the counter should start from (in this case 1):

![step 2](http://i.stack.imgur.com/hODtW.png)

Select the number you typed (<kbd>shift</kbd> <kbd><&mdash;</kbd>):

![step 3](http://i.stack.imgur.com/EJLco.png)

Type the shortcut:

![step 4](http://i.stack.imgur.com/w7wpJ.png)


Examples
----------

Tips:  `[]` stands for a selection, `|` stands for a caret.

	[1] text [1] text [1] -> 1| text 2| text 3|

	[a] text [a] text [a] -> a| text b| text c|

	[A] text [A] text [A] -> A| text B| text C|

	[01] text [01] text [01] -> 01| text 02| text 03|

	[05,2] text [05,2] text [05,2] -> 05| text 07| text 09|

	[5,-1] text [5,-1] text [5,-1] -> 5| text 4| text 3|

	[a,3] text [a,3] text [a,3] -> a| text d| text g|

Increment follows the difference between the first and second element:
                                   
	[10] text [9] text [1] -> 10| text 9| text 8|   

	[a] text [c] text [a] -> a| text c| text e|

Generate line numbers:    

	[#] line -> 1| line
	[#] line -> 2| line
	[#] line -> 3| line
	[#] line -> 4| line
	[#] line -> 5| line
