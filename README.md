# Context

This repository contains an extended collection of experimental results from the paper "On the Effectiveness of Contextualisation Techniques for Spoken Query Spoken Content Retrieval".

### bm25

|MAP|Query|Docs|b|k1|k3|d|
|---|---|---|---|---|---|---|
|man|man|0.2912|0.43|0.97|350.36|2.04|
|man|kaldi|0.2410|0.41|2.25|74.77|1.92|
|man|match|0.2166|0.40|2.12|34.30|1.61|
|match|match|0.2104|0.50|1.00|51.45|1.95|
|man|unmatchLM|0.1048|0.05|2.35|0.00|2.36|
|match|unmatchLM|0.0956|0.35|1.75|600.63|1.30|
|unmatchLM|unmatchLM|0.1148|0.48|2.45|257.16|1.85|
|man|unmatchAMLM|0.1536|0.34|0.48|17.15|1.72|
|match|unmatchAMLM|0.1191|0.68|2.29|35.28|3.10|
|unmatchLM|unmatchAMLM|0.0980|0.03|4.93|568.60|1.66|
|unmatchAMLM|unmatchAMLM|0.1114|0.44|2.28|491.96|1.87|
