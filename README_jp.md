# 感情の類似性と関連性によるネットーワークデータ
## 1. 概要
認知実験を行い，人が感じる感情同士の類似性，関連性のデータを収集し，それらを元にしたネットワークデータを作成した．  
本実験は日本語を母語とする被験者に対して日本語で行われた．  

## 2. 実験
類似性と関連性の実験は独立に実施した．  
実験の参加者はCrowdWorksというクラウドソーシングサイトで募集し，実験は自作Web上で実施した．

### 2.1. 感情語
R. Plutchikが提案した48個の感情語を使用した．  
各感情語は日本語に翻訳した．  

|　実験に使用した48個の感情語 | |
| :--- | :--- |
| primary emotions | joy trust fear surprise <br> sadness disgust anger <br> anticipation |
| strong derived emotions | ecstasy admiration terror <br> amazement grief loathing <br> rage vigilance |
| weak derived emotions | serenity acceptance apprehension <br> distraction pensiveness boredom <br> annoyance interest |
| secondary emotions | optimism hope anxiety love guilt <br> delight submission curiosity <br> sentimentality awe despair shame <br> disappointment unbelief outrage <br> remorse envy pessimism <br> contempt cynicism morbidness <br> aggressiveness pride dominance |

### 2.2. 類似性の実験
実験参加者に対し，ある感情語AとBについて「AにBはどれくらい似ていますか?」という質問を出題し，「0:全く似ていない ~ 7:とても似ている」の8段階からドラッグして選択してもらった．
一人当たり96問出題した．

### 2.3. 関連性の実験
実験参加者に対し，ある感情語AとBについて「AからBはどれくらい連想しますか?」という質問を出題し，「0:全く連想しない ~ 7:とても連想する」の8段階からドラッグして選択してもらった．
一人当たり96問出題した．

### 2.4. フィルタリング
不備のあるデータを削除した上で，catch trialsとdouble-passという2種類のフィルタリング処理を施した．
- catch trials
    - 質問の途中に，「nという数値を選択してください」(n = 1, ..., 7) という項目を2つ挿入し，どちらか一方でも正しく選択できていなかったデータは削除した．
- double-pass
    - 全ての質問の最後に，出題した質問の中からランダムに20問選び再度出題し，その20問同士の相関係数が0.4を下回るデータは削除した．

このフィルタリング処理はkawakitaらの論文から引用した (kawakita et al., 2023) ．

## 3. ディレクトリ構造
```bash
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

## 参考文献
1. Kawakita, G., Zeleznikow-Johnston, A., Tsuchiya, N., & Oizumi, M. (2023). Is my “red” your “red”?: Unsupervised alignment of qualia structures via optimal transport. PsyArXiv. https://doi.org/10.31234/osf.io/h3pqm
