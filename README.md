# Dataset Card for OASum Dataset

## Table of Contents
- [Dataset Description](#dataset-description)
- [Dataset Usage](#dataset-usage)
- [Dataset Structure](#dataset-structure)
  - [Data Instances](#data-instances)
  - [Data Fields](#data-fields)
  - [Data Splits](#data-splits)
- [Additional Information](#additional-information)
  - [Licensing Information](#licensing-information)
  - [Citation Information](#citation-information)
 
## Dataset Description
- **Paper:** [OASum: Large-Scale Open Domain Aspect-based Summarization](https://arxiv.org/pdf/2212.09233.pdf), [Get To The Point: Summarization with Pointer-Generator Networks](https://www.aclweb.org/anthology/K16-1028.pdf)

The OASum Dataset is an English-language dataset containing over 3.6M document, aspect, and summary triplets.

## Dataset Usage
You can directly download it with huggingface datasets.
``` python
from datasets import load_dataset

dataset = load_dataset("cnn_dailymail")
```

## Dataset Structure
### Data Instances
For each instance, there is a list of strings for the document, a list of strings for the summary, a string for the document title, a string for the aspect and a list of indices for the sentences in the corresponding section. 

```json
{
"title": "Ker's WingHouse Bar & Grill",
"document":[
  "After Clearwater, Florida chicken wing pioneering restaurant chain Hooters began rapidly expanding, Florida based, Canadian-born restaurant entrepreneur Ed Burnett saw the opportunity.",
  "Burnett secured the rights to a closed restaurant (\"Knockers\") and opened \"The WingHouse\" restaurant at 7369 Ulmerton Road, Largo, Florida, a high traffic corridor.",
  "He strategically selected the restaurant in between where people work (commercial real estate) and live (residential real estate), to appeal to the local lunch crowd and family dining crowd.",
  "This flagship location proved to be a success soon after launching and is the model that the chain expanded on.",
  "Burnett, looking to expand to additional locations, accepted a financing partner (Crawford Ker) during this time frame, to open additional locations and beyond.",
  "Burnett's goal was to open 20 to 50 locations, and then sell the chain to a larger restaurant chain or investors.",
  "Burnett would ultimately regret his choice of investor.","In 1992, Ker retired from the NFL and took a job selling cars at a local dealer.",
  "In 1994, he invested half interest in a Largo, Florida wing restaurant called, \"Wing House\" that imitated Hooters.",
  "The restaurant was always The Wing House, and the atmosphere was always toned down to make it more family friendly.",
  "The restaurant did well and two additional locations were opened in the Tampa Bay area in the following three years.",
  "Ker won a $1.2-million jury award from Hooters in late 2004, which had sued him for trademark violations for allegedly using their uniforms and decor.",
  "After a three-week trial in which lawyers discussed hula hoops, surfboards, scrunchy socks, pantyhose, and something called \"vicarious sexual recreation\", the jury ruled that no trademark infringement existed and Hooters was penalized for their frivolous lawsuit.",
  "Hooters appealed the decision, but in June, 2006, the 11th U.S. Circuit Court of Appeals in Atlanta upheld the verdict.",
  "As of 2007, the company had 1,700 employees at 22 locations with revenue of nearly $60 million.",
  "Ker attended, and the company participated in, the 2007 National Buffalo Wing Festival and placed first in the \"traditional x-hot sauce\" category and gained some national recognition.",
  "On June 4, 2008 the company announced the launch of its national franchise program.",
  "In mid-2008 the chain operated 19 locations in Florida and Texas and expected to add six franchises by the end of 2008, and 48 by 2011.",
  "The initial focus was for franchises in the Southeastern US.",
  "WingHouses feature several amenities that differ from other wing restaurants, including Hooters.",
  "There is a full liquor bar in every store, sports memorabilia line the walls instead of NASCAR and most locations include a game room.",
  "Super Bowl XLIII in Tampa, Florida attracted the rich and famous; WingHouse hosted three events to raise money for charity."
],
"aspect": "Opening",
"aspect_sents": [0,1,2,3,4,5,6,7,8,9,10],
"summary":[
  "WingHouse Bar & Grill (formerly Ker\u2019s WingHouse Bar & Grill) is a restaurant chain based in Florida, created and founded by Ed Burnett, a Canadian restaurant entrepreneur.",
  "After opening his first WingHouse location, Burnett sought out investors to open additional WingHouse locations.",
  "Burnett accepted investor Crawford Ker (a former National Football League player) to assist financing the expansion."
]
}
```

The average token count for the articles and the highlights are provided below:

| Feature    | Mean Token Count |
| ---------- | ---------------- |
| Document   | 1,612            |
| Summary    | 40               |

### Data Fields
- `title`: a string, containing the original Wikipedia title.
- `document`: a list of sentences, containing the original content in the Wikipedia sections except the first abstract section.
- `aspect`: a string, containing the section name and its parent section names.
- `aspect_sents`: a list of indices, representing the sentences in the `aspect` section.
- `summary`: a list of sentences, the corresponding aspect-based summary for the document.

### Data Splits
The OASum dataset has 3 splits: _train_, _valid_, and _test_. Below are the statistics for the Version 1.0.0 of the dataset.

| Dataset Split | Number of Instances in Split                |
| ------------- | ------------------------------------------- |
| Train         | 3,523,986                                   |
| Validation    | 111,578                                     |
| Test          | 112,005                                     |


## Additional Information

### Licensing Information
The OASum Dataset version 1.0.0 is released under the [CC-BY-SA-3.0 License](https://en.wikipedia.org/wiki/Wikipedia:Text_of_the_Creative_Commons_Attribution-ShareAlike_3.0_Unported_License)

### Citation Information
```
@article{yang2022oasum,
  title={Oasum: Large-scale open domain aspect-based summarization},
  author={Yang, Xianjun and Song, Kaiqiang and Cho, Sangwoo and Wang, Xiaoyang and Pan, Xiaoman and Petzold, Linda and Yu, Dong},
  journal={arXiv preprint arXiv:2212.09233},
  year={2022}
}
```
