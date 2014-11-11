gnuplot-scripts
===============

My experiments with gnuplot.

My Setup
---------

* Ubuntu 14.04 (Trusty Tahr)
* GNU Plot 4.6

Understanding the script
------------------------

* Title for the graph/chart. Replace text "Some Title" with suitable text (quotes are mandatory).

```
set title "Some Title"
```

* Set the label for X and Y axis. Replace the text 'x' with X-Axis label and 'y' with Y-Axis label.
```
set xlabel '{/Helvetica-Oblique x}'
set ylabel '{/Helvetica-Oblique y}'
```

* Set the input file by replacing "input_data_file" and similarly for output. **input** is declared as variables and will be used further in the script. **output** is the keyword.
```
input = "input_data_file"
set output "output_data_file.jpeg"
```
You create the data from multiple files. In that case you may wish to create more such input variables.


* To set the legend text for the data you are plotting change "Some data" to desired data name. You can use multiple such on seperate lines for multi-line plots.
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

```bash
gnuplot gplotscript
```

Resources
---------

GNU Plot tutorial [here (in PDF)](http://www.gnuplot.info/docs/tutorial.pdf).