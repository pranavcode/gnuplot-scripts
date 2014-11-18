gnuplot-scripts
===============

My experiments with gnuplot.

My Setup
---------

* Ubuntu 14.04 (Trusty Tahr)
* GNU Plot 4.6

Understanding the script
------------------------

* Title for the graph/chart. Replace "Some Title" with suitable text (quotes required).

```
set title "Some Title"
```

* Set the label for X and Y axis. Replace the text 'x' with X-Axis label and 'y' with Y-Axis label.
```
set xlabel '{/Helvetica-Oblique x}'
set ylabel '{/Helvetica-Oblique y}'
```

* Set the input and output files (relative paths can be used). **input** is declared as variables and will be used further in the script. **output** is the keyword.
```
input = "input_data_file"
set output "output_data_file.jpeg"
```
You can create the data from multiple files. In that case, you may wish to create more such input variables, to make this script easy to understand and change in longer run.


* To set the legend text for the data you are plotting change "Some data" to desired data/column name. You can use multiple such for multi-line plots.
```
data_title = "Some Data"
```

* Settings for plot. Use Resources below to change this according to your needs.
```
set term jpeg size 1024,768 enhanced font 'Helvetica,10'
set key inside right top vertical Right noreverse enhanced autotitles box linetype -1 linewidth 1.000
set grid
set border linewidth 2
```

* Actual command to plot the graph. Currently the graph is hardcoded to be single file, linepoints graph. Also linestyle (color) and linewidth can be changed according to the need. See Resources below for more information.
```
plot input title data_title with linespoints linestyle 1 linewidth 1
```

How to use
----------

If the desired values are properly mentioned in the script - **gplotscript** as explained above. Then **gplotscript** can be consumed by gnuplot as given below (type this on your terminal):

```
gnuplot gplotscript
```

Resources
---------

* GNU Plot tutorial [here (in PDF)](http://www.gnuplot.info/docs/tutorial.pdf).
* Demo scripts for gnuplot [(Gnuplot Sourceforge page)](http://gnuplot.sourceforge.net/demo/).
* A collection of Gnuplot [examples](http://alvinalexander.com/technology/gnuplot-charts-graphs-examples).
* Gnuplot [tricks](http://gnuplot-tricks.blogspot.in/).
* (Yet another) Gnuplot [tutorial](http://people.duke.edu/~hpgavin/gnuplot.html).
* [Not-So-FAQs](http://www.helsinki.fi/~jalaaman/gnuplot/index.html) on Gnuplot.
