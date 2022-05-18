# ImplicitRelations Dataset
[Download the ImplicitRelations datasets](https://github.com/katzurik/ImplicitRelations/raw/main/dataset/ImplicitRelations.gzip)

This gzip file contains dev/test/full data in json format for curated questions and annotated implicit relations from StrategyQA, CommonsenseQA 2.0, and Creak.


## Dataset Format

Each example follows the following structure:

```json
{
  "idx": "The original unique ID from the source dataset",
  "question": "The Question/claim" ,
  "implicit_relation_pairs": "Implicit relation annotations. List of annotators, each annotator list is constructed"
                            "from all the implicit relation pairs written by a that spacific annotator"
  [
      [
        ["concept_1","relation_1"] , ["concept_2","relation_2"] ... Annotator 1
      ]
    ] 
    ,
    [
      [
        ["concept_1","relation_1"] , ["concept_2","relation_2"] ... Annotator 2
      ]
    ]
    ,
    [
      [
        ["concept_1","relation_1"] , ["concept_2","relation_2"] ... Annotator 3
      ]
    ] 
 
  "answer": "binary answer",
  "source": "Source dataset name"
}
```
For StrategyQA we also provide the question decomposition and facts, for Creak we provide the explanation. These supplements are both taken from the original source dataset.



```json
{
  "idx": "87dfba946e7f6e2d7926",
  "question": "Is 1936 Summer Olympics venue too small for a Superbowl crowd?",
  "implicit_relation_pairs": [
    [
      [
        "1936 Summer Olympics",
        "spectator capacity of venue"
      ],
      [
        "Superbowl crowd",
        "average number"
      ]
    ],
    [
      [
        "1936 Summer Olympics venue",
        "Spectator capacity"
      ],
      [
        "Superbowl crowd",
        "Number of participants"
      ]
    ],
    [
      [
        "1936 Summer Olympics venue",
        "capacity"
      ],
      [
        "Superbowl",
        "average attendance"
      ]
    ]
  ],
  "fact": [
    "The 1936 Summer Olympics was held at the Olympiastadion Berlin.",
    "The Olympiastadion Berlin has a capacity of over 74,000 people.",
    "The 2020 Superbowl was attended by 62,417 fans."
  ],
  "decomposition": [
    "At which venue did the 1936 Summer Olympics take place?",
    "What is the spectator capacity of #1?",
    "How many people attended the 2020 Superbowl?",
    "Is #3 greater than #2?"
  ],
  "answer": false,
  "source": "strategyqa"
}
```
