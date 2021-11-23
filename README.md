---
language:
- en
- de
- fr
- it
tags:
- punctuation prediction
- punctuation
datasets: wmt/europarl
license: MIT
widget:
- text: "Ho sentito che ti sei laureata il che mi fa molto piacere"
  example_title: "Italian"
- text: "Tous les matins vers quatre heures mon père ouvrait la porte de ma chambre"
  example_title: "French"
- text: "Ist das eine Frage Frau Müller"
  example_title: "German"
- text: "My name is Clara and I live in Berkeley California"
  example_title: "English"  
metrics:
- f1
---

This model predicts the punctuation of English, Italian, French and German texts. We developed it to restore the punctuation of transcribed spoken language. 

This multilanguage model was trained on the [Europarl Dataset](https://huggingface.co/datasets/wmt/europarl) provided by the [SEPP-NLG Shared Task](https://sites.google.com/view/sentence-segmentation). *Please note that this dataset consists of political speeches. Therefore the model might perform differently on texts from other domains.*

The model restores the following punctuation markers: **"." "," "?" "-" ":"**

## Results 

The performance differs for the single punctuation markers as hyphens and colons, in many cases, are optional and can be substituted by either a comma or a full stop. The model achieves the following F1 scores for the different languages:

| Label         | EN    | DE    | FR    | IT    |
| ------------- | ----- | ----- | ----- | ----- |
| 0             | 0.991 | 0.997 | 0.992 | 0.989 |
| .             | 0.948 | 0.961 | 0.945 | 0.942 |
| ?             | 0.890 | 0.893 | 0.871 | 0.832 |
| ,             | 0.819 | 0.945 | 0.831 | 0.798 |
| :             | 0.575 | 0.652 | 0.620 | 0.588 |
| -             | 0.425 | 0.435 | 0.431 | 0.421 |
| macro average | 0.775 | 0.814 | 0.782 | 0.762 |


## References
```
@article{guhr-EtAl:2021:fullstop,
  title={FullStop: Multilingual Deep Models for Punctuation Prediction},
  author    = {Guhr, Oliver  and  Schumann, Anne-Kathrin  and  Bahrmann, Frank  and  Böhme, Hans Joachim},
  booktitle      = {Proceedings of the Swiss Text Analytics Conference 2021},
  month          = {June},
  year           = {2021},
  address        = {Winterthur, Switzerland},
  publisher      = {CEUR Workshop Proceedings},  
  url       = {http://ceur-ws.org/Vol-2957/sepp_paper4.pdf}
}
```