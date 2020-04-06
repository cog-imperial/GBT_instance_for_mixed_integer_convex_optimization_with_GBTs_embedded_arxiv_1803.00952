# Gradient-Boosted Trees Model used for Concrete Mixture Design Instance in ArXiv:1803.00952
##### Miten Mistry, Dimitrios Letsios, Gerhard Krennrich, Robert M. Lee and Ruth Misener
###### Imperial College London, UK
###### BASF SE, Germany
---
### Overview
This repository contains the concrete mixture design gradient-boosted tree instance used in the numerical tests of:

- [Mistry M, Letsios D, Krennrich G, Lee RM, and Misener R. 2018. Mixed-integer convex nonlinear optimization with gradient-boosted trees embedded. ArXiv eprints; 1803.00952](https://arxiv.org/abs/1803.00952). 

### Files
- `trained_instance.RData`: the trained instance using the parameters listed under Training Description below
- `trained_instance.tree`: the trained instance printed using `pretty.gbm.tree`.

### Training Description
- Data source: [concrete compressive strength data set](https://archive.ics.uci.edu/ml/datasets/concrete+compressive+strength) on UCI machine learning repository (Yeh, 1998; Dheeru and Karra Taniskidou, 2017).
- Gradient-boosted tree instance trained using:
	- R version 3.4.0
	- gbm version 2.1.3
	- caret version 6.0
	- caret trainControl parameters:
		- method: cv
		- number: 6
	- caret tuneGrid parameters:
		- n.trees: `seq(1000, 8000, 100)`
		- interaction.depth: `c(2,4,6,8)`
		- shrinkage: `c(0.1, 0.05, 0.01)`
		- n.minobsinnode: `c(10)`
	- caret metric parameter: RMSE
	- caret distribution: gaussian


### References
- Dheeru D, Karra Taniskidou E. 2017. UCI machine learning repository. URL: [http://archive.ics.uci.edu/ml/index.php](http://archive.ics.uci.edu/ml/index.php).
- Yeh IC. 1998. Modeling of strength of high-performance concrete using artificial neural networks. Cement Concrete Research. 28(12):1797--1808.
