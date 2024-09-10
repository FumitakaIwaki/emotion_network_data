# The network data of emotions in similarity and association
## 1. 概要
認知実験を行い，人が感じる感情同士の類似性，関連性のデータを収集し，ネットワークデータに変換した．  
本実験は日本語を母語とする被験者に対して日本語で行われた．

## 2. 実験内容
類似性と関連性の実験は独立に実施した．  
実験の参加者はCrowdWorksというクラウドソーシングサイトで募集し，実験は自作Web上で実施した．

### 2.1. 感情データ
R. Plutchikが提案した48個の感情語を使用した．  
各感情語は日本語に翻訳した．

### 2.2. 類似性の実験
実験参加者に対し，ある感情語AとBについて「AにBはどれくらい似ていますか?」という質問を出題し，「0:全く似ていない ~ 7:とても似ている」の8段階からドラッグして選択してもらった．

### 2.3. 関連性の実験
実験参加者に対し，ある感情語AとBについて「AからBはどれくらい連想しますか?」という質問を出題し，「0:全く連想しない ~ 7:とても連想する」の8段階からドラッグして選択してもらった．

### 2.4. フィルタリング
不備のあるデータを削除した上で，catch trialsとdouble-passという2種類のフィルタリング処理を施した．

## 3. ディレクトリ構造
```bash
├── LICENSE
├── README.md
├── network_data
│   ├── association_edgelist_eng.csv # 関連性の辺リスト (英語)
│   ├── association_edgelist_jp.csv # 関連性の辺リスト (日本語)
│   ├── similarity_edgelist_eng.csv # 類似性の辺リスト (英語)
│   ├── similarity_edgelist_jp.csv # 類似性の辺リスト (日本語)
│   ├── words_eng.csv # 感情語のリスト (英語)
│   └── words_jp.csv # 感情語のリスト (日本語)
├── notebooks
│   └── view.ipynb # データを表示した簡易的なnotebook
├── poetry.lock
└── pyproject.toml
```