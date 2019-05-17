Name: Long Nguyen (ltn170130)
Class: CS3345
Section: 004 
Semester: Spring 2019
Project: 5
IDE used: NetBeans
Files: QuickSorter.java, Project5.java(Main Class)

Run the program on: NetBeans IDE 8.2

1. Create a project on NetBeans, then put the two files QuickSorter.java and Project4.java in the default package of the project

2. On the top left of NetBeans window, choose File -> Project Properties(project_name)

3. A new window pop up, choose Run Categories, then fillout Arguments and Working Directory:

	- Fillout Arguments with 4 arguments: 
		+ First argument: length of the arraylist you want to create
		+ Second argument: report.txt (name of the report file)
		+ Third argument: unsorted.txt (name of the output file containing the unsorted arraylist generated randomly by the program)
		+ Fourth argument: sorted.txt (name of the output file containing the sorted arraylist)
	- Fillout Working Directory with current directory of the project

5. The program will create corresponding files with names as passed from the arguments, and results are contained in these files.
(if the file already exist in the working directory (e.g. run the program twice with different content of input file), output file content will be re-wrote)

The program runs perfectly, with all the Exception are caught(including unable to open/read files, not just invalid key arguments)

Sample output 1:

report.txt:
Array Size = 10
FIRST_ELEMENT : PT0.000036978S
RANDOM_ELEMENT : PT0.000030151S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.000030151S
MEDIAN_OF_THREE_ELEMENTS : PT0.000043235S

unsorted.txt:
[590573495, 1847423995, -184005419, -1313009474, 1633522717, 183975707, 988365479, -719943276, 2009093955, 693388471]

sorted.txt:
[-1313009474, -719943276, -184005419, 183975707, 590573495, 693388471, 988365479, 1633522717, 1847423995, 2009093955]

Sample output 2:

report.txt:
Array Size = 20
FIRST_ELEMENT : PT0.000086471S
RANDOM_ELEMENT : PT0.000122311S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.000139946S
MEDIAN_OF_THREE_ELEMENTS : PT0.000051769S

unsorted.txt:
[-645392757, 140352161, 396813671, 1674304936, -261799696, 610564907, 806904114, 302509078, 1891964887, 1857066511, 
-1794900011, 1417274082, -235817815, 574543520, -2017866229, 976159563, 78195525, -1812526583, 859582864, 315993390]

sorted.txt:
[-2017866229, -1812526583, -1794900011, -645392757, -261799696, -235817815, 78195525, 140352161, 302509078, 315993390, 
396813671, 574543520, 610564907, 806904114, 859582864, 976159563, 1417274082, 1674304936, 1857066511, 1891964887]

Sample output 3 (report.txt file only):

Array Size = 100000
FIRST_ELEMENT : PT0.033407375S
RANDOM_ELEMENT : PT0.02242613S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.025000917S
MEDIAN_OF_THREE_ELEMENTS : PT0.015452987S

Below are sample outputs and observation of special instances with modified MainClass, in which the four pivot strategies are used on a sorted arraylist or an almost sorted arraylist.

Instances of sorted arraylist:

Array Size = 100
FIRST_ELEMENT : PT0.000511999S
RANDOM_ELEMENT : PT0.000240924S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.000287858S
MEDIAN_OF_THREE_ELEMENTS : PT0.000068551S

Array Size = 100
FIRST_ELEMENT : PT0.000444586S
RANDOM_ELEMENT : PT0.000193137S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.000233244S
MEDIAN_OF_THREE_ELEMENTS : PT0.000066845S

Array Size = 500
FIRST_ELEMENT : PT0.004995405S
RANDOM_ELEMENT : PT0.002846431S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.000858452S
MEDIAN_OF_THREE_ELEMENTS : PT0.000263111S

Array Size = 500
FIRST_ELEMENT : PT0.003699194S
RANDOM_ELEMENT : PT0.003180937S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.000769705S
MEDIAN_OF_THREE_ELEMENTS : PT0.000253724S

Array Size = 1000
FIRST_ELEMENT : PT0.010731217S
RANDOM_ELEMENT : PT0.003241239S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.001420798S
MEDIAN_OF_THREE_ELEMENTS : PT0.000999252S

Array Size = 1000
FIRST_ELEMENT : PT0.008434616S
RANDOM_ELEMENT : PT0.003109257S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.001025705S
MEDIAN_OF_THREE_ELEMENTS : PT0.000422399S

For the case of sorted arraylist, the strategy using median of three elements as pivot has the fastest running time, followed by the strategy using median of three random elements, 
then using random elements as pivot, and using first element as pivot is the longest strategy.

Instance of almost sorted arraylist (15% randomly swapped):

Array Size = 20
FIRST_ELEMENT : PT0.000095573S
RANDOM_ELEMENT : PT0.000282738S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.000106382S
MEDIAN_OF_THREE_ELEMENTS : PT0.000065707S

Array Size = 20
FIRST_ELEMENT : PT0.000086471S
RANDOM_ELEMENT : PT0.000256284S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.00006656S
MEDIAN_OF_THREE_ELEMENTS : PT0.000029298S

Array Size = 20
FIRST_ELEMENT : PT0.000057742S
RANDOM_ELEMENT : PT0.000253724S
MEDIAN_OF_THREE_RANDOM _ELEMENTS : PT0.000095288S
MEDIAN_OF_THREE_ELEMENTS : PT0.000027591S

For the case of almost sorted arraylist, the order of how fast these four pivot strategies changed: the fastest strategy is still median of three elements, but followed by the first-element pivot strategy 
(only 1 case showed that median of three random element is faster than first element, but it is not enough), then using median of three random element, and the longest strategy is picking random element as pivot.




