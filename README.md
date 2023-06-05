# score-claim-extraction

This repository contains the training script to train a SciBERT model for the task of claim-extraction. The trained model can be accessed on huggingface at [https://huggingface.co/biodatlab/score-claim-identification](https://huggingface.co/biodatlab/score-claim-identification). A gradio demo app is available at the space [https://huggingface.co/spaces/biodatlab/score-claim-identification-demo](https://huggingface.co/spaces/biodatlab/score-claim-identification-demo).

Use the Claim_Extraction_Training.ipynb notebook to train a [SCIBert](https://huggingface.co/allenai/scibert_scivocab_uncased) model with your own labelled claim data. Follow the commented instructions to upload and process your files correctly.

Use the Claim_Extraction_Gradio.ipynb notebook to deploy the model as a web-app for extracting claims from an abstract using Gradio.

Our model trained on a SCORE dataset achieves the following results on the test set - 
-  Accuracy: 0.931597
-  Precision: 0.764563
-  Recall: 0.722477
-  F1: 0.742925

## Model Usage
See the [model card](https://huggingface.co/biodatlab/score-claim-identification) at huggingface.

## Examples

Here are some examples - 

|                                                         Statement                                            |    Label   | 
|:------------------------------------------------------------------------------------------------------------:|:----------:|
|We consistently found that participants selectively chose to learn that bad (good) things happened to <br>bad (good) people (Studies 1 to 7) that is, they selectively exposed themselves to deserved outcomes.| 1 (Claim) |
|Members of higher status groups generalize characteristics of their ingroup to superordinate categories<br> that serve as a frame of reference for comparisons with outgroups (ingroup projection).| 0 (Null)  |
|Motivational Interviewing helped the goal progress of those participants who, at pre-screening, reported<br> engaging in many individual pro-environmental behaviors, but the more directive approach <br> worked better for those participants who were less ready to change.| 1 (Claim) |

## Training Procedure

### Framework versions
- transformers 4.28.0
- sentence-transformers 2.2.2
- accelerate 0.19.0
- datasets 2.12.0
- spacy 3.5.3

### Training Hyperparameters

The following hyperparameters were used during training:

- learning_rate: 3e-05
- train_batch_size: 32
- eval_batch_size: 32
- n_epochs: 6
