# ML-test-perovskite-database

This project is orginally from 2022.

This is just a quick first attempt of appling a ML routine on the perovskite solar cells public database: https://www.perovskitedatabase.com/

The database contains extracted results and experimental info regarding published data on perovskite solar cells. The project itself was not very succefull because of the following reasons: 1) poor data quality, 2) biased data and 3) inconsistencies in the research field. Let me elaborate:

1) This database has been manually compiled by a large number of scientists. Due to (probably) a lack of guidance regarding how to input data, each scientist used their own nomenclature when inputting chemical names, experimental procedure or numerical data as a free text field. This resulted in extremely poor data quality for doing any exploratory or ML tasks, even after an extensive data cleaning step. More could have been done but was byond the scope of this little project. 

2. This point concerns the quality of data that gets published in the literature. To put it very simply: bad results do not get published. As a consequence, data taken from the literature is extremely biased towards positive results. For example, the information on when a certain experimental variation is actually bad for the solar cell is largely missing. Moreover, additional “cherry picking” of experimental results to make the publication look better can often affect the statistics and omit important pieces of information. 

	Therefore, anything learned from a model trained on such data is not relevant when using it as a predictive tool, e.g., for our cell efficiency from some lab experimental variations. 

3. The lack of agreement between research groups on how to report data (e.g. measurement conditions, type of tests reported, statistics, etc.) eliminated the validity of several potentially important input features for our model. As such, a lot of features had to be omitted either because of their absence in a lot of publications or because reported inconsistently (e.g. measurement condition of stability data). 

For all these reasons, unfortunately, this project did not really continue or reach any interesting results. Sorry! But still, the model used (HistGradBoost) gave a MAE = 2.54, MSE = 10.85 and RMSE = 3.29 for predicting the PCE from the experimental data which is not terrible, but also not acceptable. I put here some messy Jupyter notebooks if anyone is interested. 

