# Final Project

## database
Check the [database](https://github.com/syf9748/yifansun/blob/master/data/GlobalTemperatures.csv) in this folder. 
## gnuplot
You can find three graphs plotted by gnuplot from my database. 
The scatterplot.png shows the relationship between the global average temperature and the uncertainty within that temperature.
The the xfrequency.png and yfrequency.png shows the frequency distribution of x and y value from the scatterplot separately.
Following are the lists of code used to create the three graphs in gnuplot:
* scatterplot.png
```
set terminal png
set output 'scatterplot.png'
set title '<Average Temperature Uncertainty>'
set xlabel '<Average Temperature>'
set ylabel '<Temperature Uncertainty>'
set datafile separator ","
plot 'GlobalTemperatures.csv' using 2:3
```
* xfrequency.png
```
set terminal png
set output 'xfrequency.png'
set title '<Average Temperature Frequency>'
set xlabel '<Average Temperature>'
set ylabel '<Frequency>'
set datafile separator ","
bin_width = 1
bin_number(x) = floor(x/bin_width)
rounded(x) = bin_width * (bin_number(x) + 0.5)
plot 'GlobalTemperatures.csv' using (rounded($2)):(1) smooth frequency with boxes
```
* yfrequency.png
```
set terminal png
set output 'yfrequency.png'
set title '<Uncertainty Frequency>'
set xlabel '<Average Temperature Uncertainty>'
set ylabel '<Frequency>'
set datafile separator ","
bin_width = .1
bin_number(x) = floor(x/bin_width)
rounded(x) = bin_width * (bin_number(x) + 0.5)
plot 'GlobalTemperatures.csv' using (rounded($3)):(1) smooth frequency with boxes
```

## r
