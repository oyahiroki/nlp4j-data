# nlp4j-data

Open Data Collection for Natural Language Processing and Analytics

## Overview

This repository contains curated open datasets from various Japanese government agencies and public sources, formatted for data analysis and natural language processing applications. The data is provided in multiple formats including CSV, JSON, JSONL, and Excel files.

## Dataset Categories

### 1. MLIT (Ministry of Land, Infrastructure, Transport and Tourism) - Automobile Data
**Directory:** `data-mlit/`

**Description:** Information on automobile recalls and defects from the Japanese Ministry of Land, Infrastructure, Transport and Tourism.

**Data Sources:**
- Current: https://renrakuda.mlit.go.jp/renrakuda/top.html
- Legacy: http://carinf.mlit.go.jp/jidosha/carinf/opn/index.html

**Contents:**
- Vehicle defect information from July 2007 to December 2025
- Monthly and yearly aggregated data (2019-2025)
- Data formats: CSV, JSONL, Excel (XLSX)
- Compressed archives (.gz) for large datasets
- Vector embeddings (1024-dimensional) for NLP applications

**Key Files:**
- `不具合情報一覧_200701-202512.jsonl` - Complete defect information in JSONL format
- `mlit_carinfo-YYYYMM_utf8.csv` - Monthly data in UTF-8 CSV format
- `mlit_carinfo-YYYY_all_utf8_vector1024.jsonl` - Yearly data with vector embeddings

**Data Fields Include:**
- Date, location, manufacturer, vehicle type
- Registration date, odometer reading, engine type
- Malfunction device category
- Detailed incident descriptions

### 2. CAA (Consumer Affairs Agency) - Product Recall Data
**Directory:** `data-caa-recall/`

**Description:** Product recall information from the Consumer Affairs Agency of Japan.

**Contents:**
- Over 20,000 product recall records
- Data split into manageable chunks (0-9999, 10000-19999, 20000+)
- Example data and category classifications
- Vector embeddings for semantic search

**Key Files:**
- `caa_recall_all.json` - Complete recall database
- `caa_recall_example.json` - Sample records
- `nlp4j-caa-recall-category8-top660-20241109_json.txt` - Categorized top recalls
- `nlp4j-caa-recall-category8-top660-20241109_vector_json.txt` - Vector embeddings

**Data Fields Include:**
- Product title and description
- Product category
- Contact information
- Response method (repair, exchange, refund)
- Response start date
- URL and unique identifiers

### 3. JADA (Japan Automobile Dealers Association) - Sales Data
**Directory:** `data-jada/`

**Description:** Automobile sales statistics by manufacturer from the Japan Automobile Dealers Association.

**Note:** Data for analysis purposes only.

**Data Source:** http://www.jada.or.jp/data/month/m-r-hanbai/m-r-maker/

**Contents:**
- Yearly sales data from 2017 to 2022
- Individual year files and multi-year compilations
- Data formats: CSV, Excel (XLSX)
- Graphical analysis files

**Key Files:**
- `maker2017-2022.xlsx` - Comprehensive multi-year data
- `makerYYYY.csv` - Individual year CSV files
- `maker2017-2018-2019-2020-2021-2022-graph.xlsx` - Visualization data

### 4. Wikipedia Data
**Directory:** `data-wiki/`

**Description:** Processed Japanese Wikipedia article data for NLP applications.

**Contents:**
- Wikipedia article dumps from various dates (2024-2026)
- Redirect information
- Sample datasets of varying sizes (10, 100, 1000, 10000 articles)
- Japanese Wiktionary index data
- Compressed archives for efficient storage

**Key Files:**
- `jawiki-YYYYMMDD-pages-articles_N.jsonl` - N articles in JSONL format
- `jawiki-20241001-pages-articles-multistream_nlp4j_redirects.txt.gz` - Redirect mappings
- `jawiki-20250801-pages-articles-multistream_ja_familyname.xlsx` - Japanese family name data
- `jawiktionary-20210401-pages-articles-multistream-index.txt` - Wiktionary index

**Data Fields Include:**
- Article ID, timestamp, title
- Article text content
- Categories

## Data Formats

### JSON/JSONL
- Structured data with consistent field names
- One JSON object per line (JSONL) for streaming processing
- UTF-8 encoding

### CSV
- UTF-8 and UTF-8 BOM encoded versions
- Comma-separated values
- Header row with field names

### Excel (XLSX)
- Multi-sheet workbooks for complex datasets
- Formatted tables and graphs
- Compatible with Microsoft Excel and LibreOffice

### Compressed Archives (.gz)
- Gzip compression for large files
- Reduces storage and transfer requirements
- Maintains data integrity

## Use Cases

- **Natural Language Processing:** Text analysis, entity recognition, sentiment analysis
- **Machine Learning:** Training data for classification and prediction models
- **Data Analytics:** Statistical analysis, trend identification, visualization
- **Semantic Search:** Vector embeddings enable similarity-based search
- **Research:** Academic and commercial research on Japanese automotive industry, consumer products, and language

## Technical Notes

- All text data is encoded in UTF-8
- Vector embeddings are 1024-dimensional
- JSONL format allows for efficient streaming and processing of large datasets
- Compressed files should be decompressed before use
- Some files contain Japanese text; ensure proper encoding support

## File Naming Conventions

- `YYYY` - Four-digit year
- `YYYYMM` - Year and month
- `YYYYMMDD` - Full date
- `_utf8` - UTF-8 encoded
- `_json` or `.jsonl` - JSON Lines format
- `.gz` - Gzip compressed
- `_vector1024` - Includes 1024-dimensional vector embeddings

## License and Usage

This repository aggregates open data from Japanese government agencies and public sources. Please refer to the original data sources for specific licensing terms and conditions:

- MLIT data: Check https://renrakuda.mlit.go.jp/renrakuda/top.html
- CAA data: Check https://www.recall.caa.go.jp/
- JADA data: For analysis purposes only
- Wikipedia data: Licensed under Creative Commons Attribution-ShareAlike

## Contributing

This is a data collection project. If you have additional open datasets that would be valuable for NLP and analytics applications, please consider contributing.

## Project Structure

```
nlp4j-data/
├── README.md                 # This file
├── data-caa-recall/         # Consumer Affairs Agency recall data
├── data-jada/               # Automobile sales statistics
├── data-mlit/               # MLIT automobile defect data
│   ├── data-mlit-2019/     # 2019 data
│   ├── data-mlit-2020/     # 2020 data
│   ├── data-mlit-2021/     # 2021 data
│   ├── data-mlit-2022/     # 2022 data
│   ├── data-mlit-2023/     # 2023 data
│   ├── data-mlit-2024/     # 2024 data
│   └── data-mlit-2025/     # 2025 data
├── data-wiki/               # Wikipedia article data
└── docs/                    # Documentation
```

## Contact and Support

For questions or issues regarding this data collection, please open an issue in the repository.

---

**Last Updated:** 2026-05-06








以下、日本語訳です。 

---

# nlp4j-data

自然言語処理およびデータ分析向けオープンデータコレクション

## 概要

このリポジトリには、日本の政府機関および公開データソースから収集・整備したオープンデータセットを格納しています。
データ分析や自然言語処理（NLP）用途向けに、CSV、JSON、JSONL、Excel 形式などで提供しています。

---

# データセットカテゴリ

## 1. 国土交通省（MLIT）- 自動車不具合情報

**ディレクトリ:** `data-mlit/`

### 説明

国土交通省が公開している自動車のリコール・不具合情報です。

### データソース

* 現行:
  [https://renrakuda.mlit.go.jp/renrakuda/top.html](https://renrakuda.mlit.go.jp/renrakuda/top.html)
* 旧サイト:
  [http://carinf.mlit.go.jp/jidosha/carinf/opn/index.html](http://carinf.mlit.go.jp/jidosha/carinf/opn/index.html)

### 内容

* 2007年7月〜2025年12月の自動車不具合情報
* 月次・年次集計データ（2019〜2025年）
* CSV / JSONL / Excel（XLSX）形式
* 大容量データ向け gzip 圧縮ファイル（`.gz`）
* NLP用途向け1024次元ベクトル埋め込みデータ

### 主なファイル

* `不具合情報一覧_200701-202512.jsonl`

  * 全不具合情報（JSONL形式）
* `mlit_carinfo-YYYYMM_utf8.csv`

  * 月次CSVデータ（UTF-8）
* `mlit_carinfo-YYYY_all_utf8_vector1024.jsonl`

  * ベクトル埋め込み付き年次データ

### 主な項目

* 発生日、場所、メーカー、車種
* 登録年月日、走行距離、エンジン型式
* 不具合装置区分
* 詳細な事象説明

---

## 2. 消費者庁（CAA）- 製品リコール情報

**ディレクトリ:** `data-caa-recall/`

### 説明

日本の消費者庁が公開している製品リコール情報です。

### 内容

* 2万件以上の製品リコール情報
* 管理しやすいチャンク単位に分割

  * 0-9999
  * 10000-19999
  * 20000+
* サンプルデータおよびカテゴリ分類
* 意味検索向けベクトル埋め込み

### 主なファイル

* `caa_recall_all.json`

  * 全リコールデータ
* `caa_recall_example.json`

  * サンプルデータ
* `nlp4j-caa-recall-category8-top660-20241109_json.txt`

  * カテゴリ分類済み主要リコール情報
* `nlp4j-caa-recall-category8-top660-20241109_vector_json.txt`

  * ベクトル埋め込みデータ

### 主な項目

* 商品名・説明
* 商品カテゴリ
* 問い合わせ先
* 対応方法（修理・交換・返金）
* 対応開始日
* URLおよび一意ID

---

## 3. 日本自動車販売協会連合会（JADA）- 販売統計データ

**ディレクトリ:** `data-jada/`

### 説明

日本自動車販売協会連合会によるメーカー別自動車販売統計データです。

**注意:** 分析用途向けデータです。

### データソース

[http://www.jada.or.jp/data/month/m-r-hanbai/m-r-maker/](http://www.jada.or.jp/data/month/m-r-hanbai/m-r-maker/)

### 内容

* 2017年〜2022年の年次販売データ
* 単年データおよび複数年統合データ
* CSV / Excel（XLSX）形式
* グラフ分析用ファイル

### 主なファイル

* `maker2017-2022.xlsx`

  * 複数年統合データ
* `makerYYYY.csv`

  * 年別CSV
* `maker2017-2018-2019-2020-2021-2022-graph.xlsx`

  * 可視化データ

---

## 4. Wikipediaデータ

**ディレクトリ:** `data-wiki/`

### 説明

NLP用途向けに加工した日本語Wikipedia記事データです。

### 内容

* 2024〜2026年のWikipediaダンプ
* リダイレクト情報
* 各種サイズのサンプルデータ

  * 10件
  * 100件
  * 1000件
  * 10000件
* 日本語Wiktionaryインデックスデータ
* gzip圧縮アーカイブ

### 主なファイル

* `jawiki-YYYYMMDD-pages-articles_N.jsonl`

  * JSONL形式の記事データ
* `jawiki-20241001-pages-articles-multistream_nlp4j_redirects.txt.gz`

  * リダイレクト対応表
* `jawiki-20250801-pages-articles-multistream_ja_familyname.xlsx`

  * 日本の姓データ
* `jawiktionary-20210401-pages-articles-multistream-index.txt`

  * Wiktionaryインデックス

### 主な項目

* 記事ID
* タイムスタンプ
* タイトル
* 本文
* カテゴリ

---

# データ形式

## JSON / JSONL

* 一貫したフィールド名を持つ構造化データ
* JSONLは1行1JSON形式
* UTF-8エンコーディング

## CSV

* UTF-8 / UTF-8 BOM対応
* カンマ区切り形式
* ヘッダ行付き

## Excel（XLSX）

* 複雑なデータ向け複数シート構成
* 表やグラフを整形済み
* Microsoft Excel / LibreOffice対応

## 圧縮アーカイブ（`.gz`）

* gzip圧縮
* 保存容量および転送量を削減
* データ整合性を維持

---

# 利用用途

* **自然言語処理（NLP）**

  * テキスト分析
  * 固有表現抽出
  * 感情分析
* **機械学習**

  * 分類・予測モデルの学習データ
* **データ分析**

  * 統計分析
  * 傾向分析
  * 可視化
* **意味検索**

  * ベクトル埋め込みによる類似検索
* **研究**

  * 日本の自動車産業
  * 消費者製品
  * 日本語解析に関する研究

---

# 技術メモ

* 全テキストデータはUTF-8エンコード
* ベクトル埋め込みは1024次元
* JSONL形式により大規模データのストリーム処理が可能
* 圧縮ファイルは展開して利用してください
* 日本語テキストを含むため、適切な文字コード対応が必要です

---

# ファイル命名規則

* `YYYY`

  * 年（4桁）
* `YYYYMM`

  * 年月
* `YYYYMMDD`

  * 年月日
* `_utf8`

  * UTF-8エンコード
* `_json` / `.jsonl`

  * JSON Lines形式
* `.gz`

  * gzip圧縮
* `_vector1024`

  * 1024次元ベクトル埋め込み付き

---

# ライセンスおよび利用条件

本リポジトリは、日本の政府機関および公開ソースから取得したオープンデータを集約しています。
詳細なライセンス条件については、各元データソースを確認してください。

* MLITデータ:
  [https://renrakuda.mlit.go.jp/renrakuda/top.html](https://renrakuda.mlit.go.jp/renrakuda/top.html)
* 消費者庁データ:
  [https://www.recall.caa.go.jp/](https://www.recall.caa.go.jp/)
* JADAデータ:
  分析用途向け
* Wikipediaデータ:
  Creative Commons Attribution-ShareAlike ライセンス

---

# コントリビューション

このプロジェクトはデータ収集プロジェクトです。
NLPやデータ分析に有用なオープンデータをお持ちの場合は、ぜひコントリビューションをご検討ください。

---

# プロジェクト構成

```text
nlp4j-data/
├── README.md                 # このファイル
├── data-caa-recall/         # 消費者庁リコールデータ
├── data-jada/               # 自動車販売統計
├── data-mlit/               # 国交省自動車不具合データ
│   ├── data-mlit-2019/     # 2019年データ
│   ├── data-mlit-2020/     # 2020年データ
│   ├── data-mlit-2021/     # 2021年データ
│   ├── data-mlit-2022/     # 2022年データ
│   ├── data-mlit-2023/     # 2023年データ
│   ├── data-mlit-2024/     # 2024年データ
│   └── data-mlit-2025/     # 2025年データ
├── data-wiki/               # Wikipedia記事データ
└── docs/                    # ドキュメント
```

---

# 問い合わせ・サポート

データ収集に関する質問や問題がある場合は、GitHubリポジトリのIssueをご利用ください。

---

**最終更新日:** 2026-05-06
