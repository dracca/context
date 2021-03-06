# Context

This repository contains an extended collection of experimental results from the paper ["On the Effectiveness of Contextualisation Techniques for Spoken Query Spoken Content Retrieval"](http://dl.acm.org/citation.cfm?doid=2911451.2914730) to be presented at the SIGIR'16 conference in Pisa, Italy.

The tables below show the retrieval effectiveness in terms of mean average precision (MAP) of four retrieval methods when tested over the queries of the SpokenQuery&Doc-1 collection. Each row shows results for a specific combination of query and document transcripts. As described in the paper, the transcript IDs stand for:
  * M: manual (perfect) transcripts.
  * A0: Kaldi ASR transcripts with matched AM and LM.
  * A1: Julius ASR transcripts with matched AM and LM.
  * A2: Julius ASR transcripts with matched AM and unmatched LM.
  * A3: Julius ASR transcripts with unmatch AM and LM.

The results presented here were obtained by optimising model parameters on the SAME set of queries, i.e. the results report retrieval performance on the training set. We hope this will allow reproducibility of results and analysis of the (near) optimal parameters learnt on each training condition. For results over the test set queries, plese refer to our paper.

The parameters shown in each column stand for:
  * b: BM25 'b' parameter for length normalisation.
  * k1: BM25 'k1' parameter to control within-document TF saturation and scale.
  * k3: BM25 'k3' parameter to control within-query TF saturation and scale.
  * d: exponent for the RSJ weight that allows for 're-shaping' of the IDF function (see paper for more information).
  * &#963; width of the Gaussian kernel in PM methods.
  * &#411;: weight assigned to document scores in DIS methods.

In tables 'DIS' and 'DIS-PM', the first columns for b, k1, k3, and d correspond to the BM25 parameters used for document ranking. The second set of columns for b, k1, k3, and d correspond to the parameters used for passage ranking instead.


### BM25

|Query|Docs|MAP|b|k1|k3|d|
|---|---|---|---|---|---|---|
|M|M|0.2912|0.43|0.97|350.36|2.04|
|M|A0|0.2410|0.41|2.25|74.77|1.92|
|M|A1|0.2166|0.40|2.12|34.30|1.61|
|A1|A1|0.2104|0.50|1.00|51.45|1.95|
|M|A2|0.1048|0.05|2.35|0.00|2.36|
|A1|A2|0.0956|0.35|1.75|600.63|1.30|
|A2|A2|0.1148|0.48|2.45|257.16|1.85|
|M|A3|0.1536|0.34|0.48|17.15|1.72|
|A1|A3|0.1191|0.68|2.29|35.28|3.10|
|A2|A3|0.0980|0.03|4.93|568.60|1.66|
|A3|A3|0.1114|0.44|2.28|491.96|1.87|


### PM

|Query|Docs|MAP|&#963;|b|k1|k3|d|
|---|---|---|---|---|---|---|---|
|M|M|0.3134|225.47|0.00|3.75|12.00|1.15|
|M|A0|0.3148|143.70|0.00|3.81|50.00|1.54|
|M|A1|0.2790|187.00|0.00|3.96|116.77|1.14|
|A1|A1|0.2755|185.96|0.05|4.91|136.43|1.54|
|M|A2|0.1806|524.90|0.00|4.50|14.34|1.70|
|A1|A2|0.1594|175.60|0.10|4.14|391.95|1.49|
|A2|A2|0.1326|81.80|0.00|4.14|14.34|3.55|
|M|A3|0.2730|325.30|0.03|2.12|397.10|1.66|
|A1|A3|0.2428|316.61|0.06|3.41|5.14|2.23|
|A2|A3|0.1778|265.33|0.08|4.78|526.66|1.80|
|A3|A3|0.1732|283.61|0.02|3.87|93.50|1.48|

### DIS

|Query|Docs|MAP|b|k1|k3|d|b|k1|k3|d|&#411;|
|---|---|---|---|---|---|---|---|---|---|---|---|
|M|M|0.3392|0.22|3.83|79.32|1.30|0.40|0.98|683.92|2.05|0.59|
|M|A0|0.2406|0.03|0.15|0.10|2.20|0.40|2.27|197.64|1.93|0.03|
|M|A1|0.2436|0.48|1.71|42.00|1.00|0.35|2.19|772.48|1.33|0.58|
|A1|A1|0.2947|0.25|4.00|1000.00|1.00|0.30|1.75|100.00|1.35|0.66|
|M|A2|0.1617|0.75|3.00|12.00|1.00|0.29|2.29|168.20|1.00|0.66|
|A1|A2|0.1461|0.32|5.00|50.00|1.00|0.45|1.25|592.36|1.45|0.70|
|A2|A2|0.1601|0.59|3.99|0.58|2.99|0.29|3.54|136.88|2.80|0.55|
|M|A3|0.1901|0.00|2.75|16.80|1.22|0.21|3.50|200.00|1.45|0.62|
|A1|A3|0.1863|0.07|3.26|0.00|1.10|0.92|3.00|104.12|2.04|0.70|
|A2|A3|0.1411|0.65|5.00|182.50|1.00|0.22|4.91|217.50|1.15|0.51|
|A3|A3|0.1541|0.00|5.00|249.95|1.00|0.54|4.25|50.00|2.05|0.97|

### DIS-PM

|Query|Docs|MAP|b|k1|k3|d|&#963;|b|k1|k3|d|&#411;|
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|M|M|0.3494|0.50|1.13|89.97|1.74|125.80|0.00|4.72|100.00|1.10|0.43|
|M|A0|0.3195|0.05|0.11|38.30|1.45|140.71|0.03|3.61|96.91|1.45|0.06|
|M|A1|0.2811|0.02|0.00|30.39|1.04|175.63|0.00|4.24|336.40|1.26|0.05|
|A1|A1|0.3001|0.73|4.32|7.15|1.00|144.61|0.11|5.00|211.89|1.00|0.30|
|M|A2|0.1879|0.00|1.70|0.00|1.00|338.10|0.06|3.90|8.51|1.10|0.36|
|A1|A2|0.1593|0.48|3.83|0.00|2.43|291.90|0.05|3.00|99.18|1.00|0.25|
|A2|A2|0.1610|0.90|1.24|8.40|1.60|466.50|0.00|4.25|99.75|1.59|0.50|
|M|A3|0.2612|0.46|2.75|54.09|1.17|282.44|0.04|4.14|7.71|1.47|0.00|
|A1|A3|0.2470|0.00|3.43|149.80|2.35|303.02|0.06|4.04|6.45|1.39|0.47|
|A2|A3|0.1846|0.06|4.08|60.04|1.16|250.50|0.07|4.87|142.41|1.04|0.50|
|A3|A3|0.1963|0.06|4.97|0.00|1.00|151.21|0.08|4.85|142.50|1.89|0.45|

The above tables only show the results for the best performing parameter configuration. Full results for many other parameter configurations can be found [here](https://drive.google.com/folderview?id=0B2PA0zyoxr0rTFlSRUwwdzgyUWc&usp=sharing).


