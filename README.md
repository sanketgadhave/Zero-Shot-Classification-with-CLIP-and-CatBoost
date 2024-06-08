# Zero-Shot-Classification-with-CLIP-and-CatBoost
Explored enhancing zero-shot classification by integrating OpenAI's CLIP model with CatBoost. While CLIP alone achieved a 90% F1 score on flower species, training CatBoost on CLIP's embeddings improved the F1 score to 95.9%. This approach leverages CLIP's embeddings to handle more specific classification tasks effectively.


## Summary

In this project I checked how model from OpenAI performs on zero-shot classification of flowers task. 

Still flower species are quite widespread datasets, probably, they were present in the training data of the CLIP model. What if we need to train a classifier for more specific task, where CLIP model couldn't generalize well, as it cannot handle new classes or images beyond the domain they have been trained with. So in this notebook I wanted to check an idea to train a simple gradient boosting algorithm CatBoost on embedding vectors from CLIP model and see whether it will improve metrics.

### Results of validation
- CLIP zero-shot classification - $F_1 = 90\%$
- CatBoostClassifier trained on vector embeddings from CLIP model - $F_1 = 95.9\%$

### What is CLIP

CLIP (Contrastive Language-Image Pre-Training) is a neural network trained on a variety of (image, text) pairs. It can be instructed in natural language to predict the most relevant text snippet, given an image, without directly optimizing for the task, similarly to the zero-shot capabilities of GPT-2 and 3. We found CLIP matches the performance of the original ResNet50 on ImageNet “zero-shot” without using any of the original 1.28M labeled examples, overcoming several major challenges in computer vision.
