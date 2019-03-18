+++
title = "Back to basics"
date = 2019-02-26T13:03:26-05:00
weight = 1
+++

We all gotta start somewhere


```bash
ssh username@cedar.computecanada.ca
```


### How to submit the SCIL_QA NextFlow

```bash
#!/bin/bash

#SBATCH --account=YOURACCOUNT
#SBATCH --time=2:00:00
#SBATCH --job-name=WTVUWANT_QA
#SBATCH --output=WTVUWANTqa-%A.out
#SBATCH --nodes=1
#SBATCH --cpus-per-task=32
#SBATCH --mem=0

nextflow -c ../singularity.conf run /PATHTOTHENEXTFLOWQA/scil_qa/qa_nf/main.nf --root /PATHOFTHERESULTSTOBEQA/ -with-singularity /PATHTOYOURQAIMG/src/scil_qa/qa.img
```
