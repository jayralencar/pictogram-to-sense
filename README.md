# Pictogram to Sense: mapping pictographic symbols to WordNet synsets

Pictogram is the term used by the Augmentative and Alternative Communication (AAC) community for an image with a label that represents a place, person, action, object and animal. AAC systems like the shown below allow message construction and communication by arranging pictograms in sequence. 

![image](https://user-images.githubusercontent.com/7529265/139294919-14830639-b5a7-46a9-8267-d1a8d3754568.png)


Every day the need to use artificial intelligence in tools of this type grows. An example is [PictoBERT](https://github.com/jayralencar/pictoBERT/), an adaptation of BERT language model to perform pictogram prediction. PictoBERT use word-sense language modeling to perform pictogram prediction. This way, each pictogram must be associated with a word-sense. Besides, assosiating pictograms to word-senses allow they to be used in other natural language processing applications related to AAC (e.g., text expansion).

This project aims to provide AAC developers with a tool for facilitating the mapping between pictograms and WordNet word-senses. For this, we use [CLIP](https://openai.com/blog/clip/) (Constrative Language-Image Pre-Training), which learns visual concepts from natural language supervision, using image+text pairs for training. The procedure consists on searching for the synsets of the pictogram label in WordNet. CLIP encodes the synsets definitions and the pictogram image and calculates a cosine similarity between each encoded definition and the image. The similarity scores are then scaled by a temperature parameter τ, and normalized into a probability distribution via a softmax. The definition with the highest value after softmax is chosen for the pictogram, as well as its synset. To improve the quality of predictions made by CLIP for this task, we trained the model for a few more epochs using [ARASAAC](https://arasaac.org/) pictograms and their definitions as a dataset.

![image](https://user-images.githubusercontent.com/7529265/139293966-8d6c63b3-a53f-491e-9a1e-5f8494e73c58.png)

![image](https://user-images.githubusercontent.com/7529265/139294357-405b99c9-a982-43ea-8b9e-8798ccac4d50.png)


For evaluating our proposal, we attributed synsets to 900 of the pictograms from [Mulberry Symbols](https://mulberrysymbols.org/), and calculated how accurate is CLIP on selecting the correct pictogram. We evaluated both versions of CLIP, the original and the fine-tuned. The results demonstrate that the fine-tuned models have a better performance than the original CLIP. Besides, the accuracy score acquired (70\%) demonstrates the proposal's potential.

![image](https://user-images.githubusercontent.com/7529265/139294626-07f3aaca-a18f-49c1-abb9-e1067a1e47fa.png)

## Usage

To be provided.
