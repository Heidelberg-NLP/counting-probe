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
Please acknowledge our [paper](https://arxiv.org/pdf/2012.12352.pdf) at MMSR at IWCS and the original Visual7W paper if you are using this dataset.

```
@inproceedings{parcalabescuetal:2021b,
  author = {Letitia Parcalabescu and Albert Gatt and Anette Frank and Iacer Calixto},
  title = {{Seeing Past Words: Testing the Cross-Modal Capabilities of Pretrained V{\&}L Models}},
  year = {2021},
  booktitle = {Proceedings of the First Workshop on Multimodal Semantic Representations (MMSR)},
  address = {Groningen},
  note = {to appear}
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
