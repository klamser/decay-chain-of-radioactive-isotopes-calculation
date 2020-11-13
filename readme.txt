This repository provides a tool to calculate decay chains with the Bateman equation and plot them in a LogLogPlot.
It needs Mathematica 12 or later and can be run on a raspberry pi with Mathematica installed on raspbian. On my raspberry pi 4 Mathematica 12.1.1 runs perfectly fine.
The code is write protected, but this can easy changed in the cell/cell propeties menu of Mathematica, so you can change the code if you like to.
The main procedure is
plutonium$decay$gas$mass = 
  Table[{n, list$of$tally$of$decay$modes["Pu", n, False]}, {n, 238, 
    242}];
and
PlotBateman["U238", {10^-2, 10^12}]
and this is self explaining, I think so.
Be paitent, to run the wohle Mathematica notebook takes 35 hours on my Lenovo T430.
With raspbian, you should select smaller parts of the Table expression, otherwise you get problems:
isotop$nr = 235;
Table[isotop$nr++; Print[isotop$nr]; 
  PlotBateman["Pu" <> ToString[n], {10^-3, 10^12}], {n, 238,242}] // TableForm