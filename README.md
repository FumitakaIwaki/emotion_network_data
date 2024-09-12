# The network data of emotions in similarity and association
[README in Japanese](README_jp.md)

## 1. Overview
We conducted cognitive experiments to collect similarity and association between emotions that human feel and made the network data based on the results of the experiments.  

## 2. Experiments
We have conducted the similarity experiment and the association experiment are independently.  
We have hired the participants on the crowdsourcing platform named [CrowdWorks](https://crowdworks.jp/) and they have joined the experiments on the web.

### 2.1. The data of emotions
We used 48 emotion words proposed by R. Plutchik on out experiments.  
We translated each emotion words to Japanese.

|　48 emotion words for the experiments | |
| :--- | :--- |
| primary emotions | joy trust fear surprise <br> sadness disgust anger <br> anticipation |
| strong derived emotions | ecstasy admiration terror <br> amazement grief loathing <br> rage vigilance |
| weak derived emotions | serenity acceptance apprehension <br> distraction pensiveness boredom <br> annoyance interest |
| secondary emotions | optimism hope anxiety love guilt <br> delight submission curiosity <br> sentimentality awe despair shame <br> disappointment unbelief outrage <br> remorse envy pessimism <br> contempt cynicism morbidness <br> aggressiveness pride dominance |

### 2.2. The experiment of similarity
We presented participants with the questions “How similar is A to B?” for all two emotions A and B, and they then dragged a slider to choose an evaluation score from 0 (not at all) to 7 (very similar) .  
We assigned 96 question to each participant.

### 2.3. The experiment of association
We presented questions “How associated is
A with B?” and participants chose an answer from the
same evaluation scores.  
We assigned 96 question to each participant.

### 2.4. Filterings
After removing defective data, to remove poor quality answers from the obtained data, we applied two kinds of filtering, catch trials and a double-pass procedure.
- catch trials
    - We inserted the request “Please choose n” twice during each experiment (n was a value from 0 to 7) . 
    - We removed the responses of the participants who have not properly chosen the indicated value at least once of the catch trials.
- double-pass
    - We again subjected to the participants 20 questions from within the questions that have already been submitted at the end of the experiments. 
    - We deleted the data of which the correlation coefficient of the 20 pairs of answers was less than 0.4.  

These filterings were cited from the research by kawakita et al. (kawakita et al. 2023) .

## 3. The directory composition
```shell
├── LICENSE
├── README.md
├── network_data
│   ├── association_edgelist_eng.csv
│   ├── association_edgelist_jp.csv
│   ├── similarity_edgelist_eng.csv
│   ├── similarity_edgelist_jp.csv
│   ├── words_eng.csv
│   └── words_jp.csv
├── notebooks
│   └── view.ipynb
├── poetry.lock
└── pyproject.toml
```

## References
1. Kawakita, G., Zeleznikow-Johnston, A., Tsuchiya, N., & Oizumi, M. (2023). Is my “red” your “red”?: Unsupervised alignment of qualia structures via optimal transport. PsyArXiv. https://doi.org/10.31234/osf.io/h3pqm
