# Counting Probe
Counting dataset for probing cross-modal capabilities of Vision &amp; Language models. Introduced in the paper

"Seeing Past Words: Testing the Cross-Modal Capabilities of Pretrained V&amp;L Models" by Parcalabescu, L., Gatt, A., Frank, A., and Calixto, I. (2021). Proceedings of the First Workshop on Multimodal Semantic Representations (MMSR), Groningen, to appear. https://arxiv.org/abs/2012.12352

## Instructions
Please find the standard, hard and interpolated splits in their respective folders.

The dataset comes in the following `json` format containing a reference to the Visual7W images, the original question, the original answer, the foil answer and the QA pairs in a declarative format:
```python
{
    "counting_visual7w_18": {                        # id specific to our release
        "dataset": "visual7w",                       # the dataset this data sample was taken from
        "dataset_idx": "18",                         # the ID of the sample in the original dataset
        "image_file": "v7w_18.jpg",                  # associated image file in Visual7W
        "caption": "How many soda bottles are on the table?", # original question for the image as associated in Visual7W
        "answer": 1,                                 # original answer as associated in Visual7W
        "classes": [
            1
        ],
        "split": "test",                             # split of the sample in our dataset
        "original_split": "test",                    # original split of the sample in Visual7W
        "foils": [                                   # FOIL answers to the question
            2,
            5,
            6
        ],
        "classes_foil": [
            2,
            5,
            6
        ],
        "declarative_statement": "There is 1 soda bottles on the table.", # QA formulated as a declarative statement
        "declarative_statement_foils": [             # FOILS formulated as a declarative statement
            "There are 2 soda bottles on the table.",
            "There are 5 soda bottles on the table.",
            "There are 6 soda bottles on the table."
        ]
    }, ...
}
```

For the images, please follow the instructions from the [Visual7W Webpage](https://ai.stanford.edu/~yukez/visual7w/) or follow directly [this link](http://vision.stanford.edu/yukezhu/visual7w_images.zip).

## Reference
Please acknowledge our [paper](https://aclanthology.org/2021.mmsr-1.4.pdf) at MMSR at IWCS and the original Visual7W paper if you are using this dataset.

```
@inproceedings{parcalabescu-etal-2021-seeing,
    title = "Seeing past words: Testing the cross-modal capabilities of pretrained {V}{\&}{L} models on counting tasks",
    author = "Parcalabescu, Letitia  and
      Gatt, Albert  and
      Frank, Anette  and
      Calixto, Iacer",
    booktitle = "Proceedings of the 1st Workshop on Multimodal Semantic Representations (MMSR)",
    month = jun,
    year = "2021",
    address = "Groningen, Netherlands (Online)",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2021.mmsr-1.4",
    pages = "32--44",
    abstract = "We investigate the reasoning ability of pretrained vision and language (V{\&}L) models in two tasks that require multimodal integration: (1) discriminating a correct image-sentence pair from an incorrect one, and (2) counting entities in an image. We evaluate three pretrained V{\&}L models on these tasks: ViLBERT, ViLBERT 12-in-1 and LXMERT, in zero-shot and finetuned settings. Our results show that models solve task (1) very well, as expected, since all models are pretrained on task (1). However, none of the pretrained V{\&}L models is able to adequately solve task (2), our counting probe, and they cannot generalise to out-of-distribution quantities. We propose a number of explanations for these findings: LXMERT (and to some extent ViLBERT 12-in-1) show some evidence of catastrophic forgetting on task (1). Concerning our results on the counting probe, we find evidence that all models are impacted by dataset bias, and also fail to individuate entities in the visual input. While a selling point of pretrained V{\&}L models is their ability to solve complex tasks, our findings suggest that understanding their reasoning and grounding capabilities requires more targeted investigations on specific phenomena.",
}
```

Visual7W paper reference:
```
@InProceedings{zhu2016cvpr,
  title = {{Visual7W: Grounded Question Answering in Images}},
  author = {Yuke Zhu and Oliver Groth and Michael Bernstein and Li Fei-Fei},
  booktitle = {{IEEE Conference on Computer Vision and Pattern Recognition}},
  year = 2016,
}
```

### Papers with Code entry
You can find our dataset on Papers with Code here: https://paperswithcode.com/dataset/counting-probe
