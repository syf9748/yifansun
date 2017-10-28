# Final Project

## database
Check the [database]() in this folder. 
## gnuplot
Here are the lists of code used to create the three graphs in gnuplot:
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

## r
