::::::TERMS OF USE::::::
The code in this package is open for any academic and non-comercial use.

If you use or modify the code provided here, we ask that you cite the original paper, as detailed below.

All code is produced and maintained by Travis Moore.  


::::::CITATION::::::
Moore, Travis, and Weng-Keen Wong. 
"An Efficient Quantile Spatial Scan Statistic for Finding Unusual Regions in Continuous Spatial Data with Covariates."
UAI, 2018.



::::::REPRODUCTION OF PAPER EXPERIMENTS::::::
Download QSSS v2.zip for latest version of codebase.  This version corresponds to the codebase used for the paper submission
to the Journal of Computational and Graphical Statistics.
Version 1 of the codebase is no longer supported.

:::Timing comparison for incremental and non-incremental Rank Test:::
script.m contains the code used for the timing comparison.  This uses simulated (junk) data points, and times the inner update loop
for both algorithms.  The wall-clock time is returned for each algorithm in a vector.  The size of the data in terms of number of
points (n) and number of features (p) can be specified when running the script.

:::Comparison for different hypothesis tests:::
batch_sim.m will run a suite of spatial scan algorithms using different hypothesis tests on simulated data.
It also computes a Gumbel correction term, and fits an initial quantile regression to the data, which is used by several of the methods.

The simulated data used in the paper can be downloaded from the various zip files.  Each csv file contains a batch of 30 datasets generated under 
the same set of parameters.  batch_sim.m will automatically read each dataset in the csv file and run each algorithm in turn.

simulation.m contains code for the simulator, which will inject a circular region that differs within a specified range of 
the data distribution.

PlotAUCResults.m 



:::Use of QSSS on real world datasets:::
RankTest.m contains the code to run our QSSS on a given dataset.
The datasets used in the paper (eBird, eButterfly, and US Unemployment) are all publically available.  See the original paper for
citations and weblinks to each dataset.
The subsets of this data used for the paper results are provided in the different csv files.
	eBird files, separated by BCR: ebird_BCR30.csv (not used in paper), ebird_BCR31.csv, ebird_BCR37.csv
	eButterfly: ebutterfly.csv
	U.S. education and unemployment: unemployment.csv (used for two-sided experiment), edu_unemployment2.csv (used for one-sided test)
The names of the locations have been replaced by latitude and longitude coordinates.
Each data file should be loaded as a separate response vector (Y), feature matrix (X), and location matrix (L).
These Y,X,L values can then be passed to RankTest.m, or any other spatial scan algorithm, to location unusual regions in the data.




::::::QUESTIONS/CONTACT::::::
If you have questions about using the code, or reproducing results from the paper, you can contact Travis at moortrav@oregonstate.edu
