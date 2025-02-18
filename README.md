# AutoCaptions: Metadata Tagging for St. Jude Children's Hospital

St Jude's Staff: Marie Steele, 
T4SG Leads: Sunny Liu, Davin Jeong
T4SG Software Engineers: Denny Cao, Caleb Capoccia, Sam Huang, Isabel Kim, Sophia Liu

## Project Overview
AutoCaptions is a project in collaboration with St. Jude's Children Research Hospital to automatically generate high-quality metadata for a vast archive of photographic assets. By leveraging AI-driven automation, this project aims to save years of manual effort and over $340,000 in costs while improving metadata quality and accessibility.

St. Jude has a vast collection of historical and contemporary images, many of which lack meaningful metadata. Existing metadata is often incorrect, generic, or incomplete. Manually cleaning and tagging these images is infeasible due to the sheer scale of the dataset. **The goal of this project is to develop an AI model capable of accurately tagging and categorizing images according to St. Jude’s documentation standards.**

## Key Features

For reference, a full summary of our key features and methods can be found in our [Midpoint](https://docs.google.com/presentation/d/1AP4NmQQlVEgihZhwihh5qDjf50fEecxssAKANuMRVBA/edit?usp=sharing) and [Final](https://docs.google.com/presentation/d/1r0JZJco-kXUPgAh32-N4EHrFfciWJEMUbeBc9vetMWg/edit?usp=sharing) presentations. 

### Preprocessing
- Ensured completeness and correctness of metadata
- Created a sample dataset of well-documented images for training and evaluation

### Generation
Of eleven types, we attempted to generate the following two forms of metadata for the sample datasets. Other fields followed similar formats, and our methods can be generalized to them as needed:
- Descriptions (a collection of words, typically 10-15 long, describing the content of the image)
- Captions (structured keywords from a predetermined hierarchy, used for the organization of image files)

We used the following models, along with various fine-tuning, hyperparameter-tuning, and transfer-learning methods, towards these tasks:
- [Paligemma: Google's Open Vision Language Model](https://ai.google.dev/gemma/docs/paligemma)
- [BLIP: Bootstrapped Large Image Pre-training](https://arxiv.org/abs/2104.01109)
- [Llava: Large Language Assistant](https://arxiv.org/abs/2301.12542)

### Evaluation
The sample assets contained human-generated metadata, which we used to evaluate our models. We implemented semantic similarity scoring using the following models:
- [CLIP: Contextual Language-Image Pre-training](https://openai.com/blog/clip/)
- [Sbert: Sentence-BERT](https://arxiv.org/abs/1908.00897)
- [USE: Universal Sentence Encoder](https://ai.google/research/google-research/2020/10/using-unsupervised-similarity-to-improve-ai-models.html)

## Example Usage

0. Download Images
Please coordinate with the team at St. Jude's for access to sampled assets. For future steps, we will assume that you have already downloaded images to a folder named "Labelled Assets".

1. Setup Environment
```
conda create -n acaptions python=3.10
conda activate acaptions

python -m pip install jupyter

jupyter notebook
```

2. Download Datasets

3. Run Generation Script (preprocessing will occur as a side effect)

## Next Steps
1. Optimize performance for deployment
2. Begin batch processing of image metadata
4. Develop search functionality for metadata retrieval

For any questions or contributions, please refer to the Github repository or contact the project leads. 

