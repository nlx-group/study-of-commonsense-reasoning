# A Study of Commonsense Reasoning with Language Models

<p align="center"><img src="NLX_and_FCUL.png" alt="NLX and FCUL Logo" /></p>

This repository contains the code and some data (certain datasets cannot be shared due to licensing issues) for the [dissertation]():

```
A Study of Commonsense Reasoning with Language Models
Ruben Branco
Supervised by Prof. Dr. António Branco
```

This dissertation was produced to obtain a Masters Degree in Data Science.

## Abstract

> Artificial Intelligence (AI) has gone through an increasing growth in the past decades, which in the present day translates to its usage in almost every sector of society. From its inception, AI pursues the reproduction of human intelligence. Currently, AI-equipped devices are capable of solving particular problems within specific domains with varying degrees of success. The goal and hope is that the combination of these systems will eventually approximate human intelligence. This dissertation addresses a problem in Natural Language Processing (NLP), a central subfield of AI that aims to produce devices capable of handling human language for problems such as translation, parsing, commonsense reasoning, and others.
>
> Deep learning has fueled state-of-the-art NLP research. The current most prominent methodology leverages large scale neural networks and large amounts of data to achieve outstanding performances. Recent research has started to uncover how these neural networks obtain state-of-the-art results. In some cases the models appear to latch on to so called data artifacts, whether they sustain valid generalizations or not, which happen to minimize loss w.r.t. the training dataset distribution. Although this is generally the rationale behind a machine learning approach, it can be error inducing, as models can fail miserably when the distribution of the input data differs from the training data.
>
> Our work reported in this dissertation investigates whether models learn to perform commonsense reasoning, a cognitively demanding task inherent to the human experience, by resorting to such shortcuts. Five state-of-the-art models of different major types are trained to perform four most prominent commonsense reasoning tasks. Models undergo stress testing with five additional tasks devised to provide hints of possible shortcut learning and of memorization.
>
> The results indicate that the models seem to be resorting to shortcut learning in three of the four commonsense reasoning tasks%, which are flagged as problematic; they seem to be learning a different task from the one the data is meant to convey by relying on spurious patterns present in the dataset. For example, the trained models can pick the answer from a set of options without even being supplied with the question they are meant to answer. Further experimentation confirmed that this behavior could not be attributed to memorization. This behavior is worrisome, as the field measures progress by the capabilities of these models to perform these tasks, and show that their cognitive abilities are disappointingly still low, susceptible to simple deceptions in spite of the overwhelming good scores obtained under mainstream performance metrics.
>
> Parts of this work have passed peer review and were accepted for publication.

## Code

The dissertation comprises six experiments in the pursuit of identifying Shortcut Learning when applying state-of-the-art Transformer models to Commonsense Reasoning tasks, and what that means for the grand scheme of NLP methodology.

It follows a list of the experiments and the file associated with them:

- **Tasks baselines**: each models folder (`RoBERTa/`, `GPT-2/`, `T5/` and `BART_AND_COMET/`) contains a scripts folder, which provides an example of how to run the models for each task.

- **Partial Inputs**: To perform partial input training, modify the `data.py` file in each model folders by commenting the section of inputs to not be supplied. Afterwards, run the task training script again.

- **Adversarial Attack**: Adversarial attacks can be performed using the `create_adversarial.py` file in the `RoBERTa/` and `BART_AND_COMET/` folder. An example of how to run an adversarial attack is given in `RoBERTa/scripts/run_adversarial.sh`. This experiment required modifying the [TextAttack library](https://github.com/QData/TextAttack). The modified library can be found in `TextAttack/`. It is recommended to install this version of the library for reproduction purposes.

- **Data Contamination**: The code and requirements for the experiment is provided in the `Data_Contamination/` folder. The code and results for the experiment are found in a jupyter-notebook: `Data_Contamination/Contamination.ipynb`. The code in the notebook was adapted to create a data contamination library, [Overlapy](https://github.com/nlx-group/overlapy). The jupyter-notebook includes URLs to download the data that was not supplied in `data/`. Only one dataset cannot be obtained easily due to licensing issues, which is CC-News. The script `Data_Contamination/crawl_ccnews.py` can be used to retrieve the dataset, however, **it takes a LONG time**. You may contact rmbranco[at]fc[dot]ul[dot]pt for more details on how to obtain this dataset.

- **Cross Tasks**: The code for the cross tasks experiment is implemented in `BART_AND_COMET/cross_eval.py` and `RoBERTa/cross_eval.py`. A script to run this code is provided in `BART_AND_COMET/scripts/cross.sh` and `RoBERTa/scripts/cross.sh`.

- **Shortcut Exploration**: The Shortcut Exploration experiments, described in detail in the appendix, are implemented in the end of the data contamination jupyter-notebook (`Data_Contamination/Contamination.ipynb`).

## Citation

Parts of this dissertation were published in the form of two articles.

---

```
Shortcutted Commonsense: Data Spuriousness in Deep Learning of Commonsense Reasoning
Ruben Branco, António Branco, João Silva and João Rodrigues
to appear at EMNLP 2021
```

```
@inproceedings{branco-etal-2021-shortcutted-commonsense,
    title = "Shortcutted Commonsense: Data Spuriousness in Deep Learning of Commonsense Reasoning",
    author = "Branco, Ruben  and
        Branco, Ant{\'o}nio  and
        Silva, João and
        Rodrigues, João",
    booktitle = "Proceedings of the 2021 Conference on Empirical Methods in Natural Language Processing (EMNLP)",
    month = nov,
    year = "2021",
    publisher = "Association for Computational Linguistics",
}
```

---

```
Commonsense Reasoning: how do Neuro-Symbolic and Neuro-only approaches compare?
Ruben Branco, António Branco, João Silva and João Rodrigues
to appear at KINN 2021
```

```
@article{branco2021commonsense,
  title={Commonsense Reasoning: how do Neuro-Symbolic and Neuro-only approaches compare?},
  author={Branco, Ruben and Branco, Ant{\'o}nio and Silva, Jo{\~a}o and Rodrigues, Jo{\~a}o},
  year={2021}
}
```

---

```
A Study of Commonsense Reasoning with Language Models
Ruben Branco, supervised by António Branco
Masters in Data Science Dissertation 2020/2021
```

```
@mastersthesis{branco2021study,
  title={A Study of Commonsense Reasoning with Language Models},
  author={Branco, Ruben},
  year={2021}
}
```
