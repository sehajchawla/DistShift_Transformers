# Investigating Distribution Shifts in Review Classification

## Abstract

This work quantifies the extent to which accuracy degrades on review classification when state-of-the-art Transformer models are subjected to distribution shifts, and offers a solution to significantly decrease this degradation. We find differences in the extent of degradation depending on the independent variable across which the shift is created. Specifically, in our experiments time and sentiment shifts show upto 10% drops in accuracy; whereas shifts between industry and product sectors show 20-40% drops in accuracy. We provide ablation experiments with different Transformer architectures, such as BERT, T5 and Jurassic-I, and study their relationship with this degradation. The suggested solution reuses the base of the model trained on one distribution, in addition to fine-tuning the final dense layer in the model to support the new distribution that is seen once the model is deployed. This uses just 100-300 samples compared to the previous 10,000 samples from the unseen distribution, while decreasing the accuracy drops in half.

## Code Structure

The code structure for our project is as follows:
The `code` directory contains the notebooks that we worked on, and is structured as per the "steps" section in our report. i.e. it contains the following subdirectories:
* `1_preprocess`: parses and preprocesses our data sets to make them compliant with our pretrained transformer models (3 instances of BERT and 1 of T5).
* `2_baseline`: creates and evaluates baseline models that train and test on the same distribution (but test on OOD), in order to establish baselines that we can compare our distribution shift results with.
* `3_distribution_shift`: contains 4 types of distribution shifts (`1_industry`, `2_time`, `3_product`, and `4_sentiment`) and the results for our analysis in each. 
* `4_finetune_shift`: contains 4 types of distribution shifts (`1_industry`, `2_time`, `3_product`, and `4_sentiment`) and the results for our analysis in each, where we retrain the final layer of a model trained on one distribution with 20% samples from the other distribution. 

Most of the work seen in the "results" section of our report will be found in the directories `3_distribution_shift` and `4_finetune_shift`.

## Data

The data that is being referred to on the notebooks is all in the following Google Drive folder that should be accessible with any `mit.edu` email: `https://drive.google.com/drive/folders/1RA5QyeQpAJhWrYIxoYFBdTq_RQXsk7TZ?usp=sharing`.

## Contact

For any questions, email any of the following:
* Sehaj Chawla (Harvard University): sehajchawla@g.harvard.edu
* Iddo Drori (MIT): nsingh1@mit.edu
* Nikhil Singh (MIT): idrori@mit.edu
