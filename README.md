# HtmlParser
PD-2 HW3

# Powerful Toolkit in Java: Using HTML Parser to Crawl Internet Data



## Homework Requirement

作業要求使用 `jsoup` 套件爬取 [指定網站](https://pd2-hw3.netdb.csie.ncku.edu.tw/) 上的股價資料，並根據以下任務要求處理這些數據。

### Task Descriptions:

- **Task 0**: 抓取網站上的股票資料並將其追加存儲到 `output.csv` 中。
- **Task 1**: 計算並輸出指定股票在指定時間段的 5 日移動平均至 `output.csv` 中。
- **Task 2**: 計算並輸出指定股票在指定時間段的標準差至 `output.csv` 中。
- **Task 3**: 計算並輸出指定時間段股價標準差最大的前 3 名股票至 `output.csv` 中。
- **Task 4**: 輸出指定股票在指定時間段的線性回歸直線公式至 `output.csv` 中。

### Input Arguments:

程序將接收以下參數作為輸入：

```bash
$ java HtmlParser {mode} {task} {stock} {start} {end}
```

- **mode**: 
  - `0` 表示爬取網站資料並將其保存至 `data.csv`；
  - `1` 表示進行數據分析並將結果輸出到 `output.csv`。
- **task**: 指定要執行的任務編號（0-4），如上所述。
- **stock**: 指定股票代號（僅在 task 1、2、4 中有效）。
- **start** 和 **end**: 指定時間段範圍。

## 使用範例

- 爬取當前網站股票資料：
  ```bash
  $ java HtmlParser 0
  ```
- 輸出搜集至今的所有股價資料：
  ```bash
  $ java HtmlParser 1 0
  ```
- 輸出AAL股票在第2天至第6天的5日移動平均：
  ```bash
  $ java HtmlParser 1 1 AAL 2 6
  ```
- 輸出AAL股票在第1天到第3天的股價標準差：
  ```bash
  $ java HtmlParser 1 2 AAL 1 3
  ```
- 輸出第1天到第15天的股價標準差Top 3：
  ```bash
  $ java HtmlParser 1 3 AAL 1 15
  ```
- 輸出AAL股票第1天到第30天的回歸直線：
  ```bash
  $ java HtmlParser 1 4 AAL 1 30
  ```

## 輸入問題

網站上的股價資料每 2 分鐘更新一次，並每小時完成一次第1到第30天的輪播，因此在指定時間段內抓取數據至關重要。

## 輸出問題

輸出文件中的數據需滿足以下要求：
- 股票代號應全大寫
- 所有數據需四捨五入到小數點後兩位

## 挑戰點

如果不使用 `java.util.stream` 和 `java.lang.math` 並自行實作所有計算方法，將可獲得作業挑戰點 1 分。

---

# README (English Version)

## Homework Requirement

The homework requires using the `jsoup` library to crawl stock price data from the [specified website](https://pd2-hw3.netdb.csie.ncku.edu.tw/) and process the data based on the following task requirements.

### Task Descriptions:

- **Task 0**: Crawl the stock price data and append it to `output.csv`.
- **Task 1**: Compute and output the 5-day moving average for a specified stock during a given time period to `output.csv`.
- **Task 2**: Compute and output the standard deviation of a specified stock during a given time period to `output.csv`.
- **Task 3**: Output the top 3 stocks with the highest standard deviation in a specified time period to `output.csv`.
- **Task 4**: Compute and output the linear regression line for a specified stock during a given time period to `output.csv`.

### Input Arguments:

The program accepts the following input arguments:

```bash
$ java HtmlParser {mode} {task} {stock} {start} {end}
```

- **mode**: 
  - `0` for crawling the stock data and saving it to `data.csv`；
  - `1` for analyzing the collected data and saving the results to `output.csv`。
- **task**: Specify the task number (0-4), as described above.
- **stock**: Specify the stock symbol (only applicable for tasks 1, 2, 4).
- **start** and **end**: Specify the time range.

## Usage Examples

- Crawl current stock data from the website:
  ```bash
  $ java HtmlParser 0
  ```
- Output all collected stock data:
  ```bash
  $ java HtmlParser 1 0
  ```
- Output 5-day moving average for AAL stock from day 2 to day 6:
  ```bash
  $ java HtmlParser 1 1 AAL 2 6
  ```
- Output standard deviation of AAL stock from day 1 to day 3:
  ```bash
  $ java HtmlParser 1 2 AAL 1 3
  ```
- Output the top 3 stocks with the highest standard deviation from day 1 to day 15:
  ```bash
  $ java HtmlParser 1 3 AAL 1 15
  ```
- Output the linear regression line for AAL stock from day 1 to day 30:
  ```bash
  $ java HtmlParser 1 4 AAL 1 30
  ```

## Input Issues

The stock price data on the website is updated every 2 minutes, and each hour it rotates through 30 days of data. Therefore, it's important to crawl the data within the specified time range.

## Output Issues

The output file should meet the following requirements:
- Stock symbols must be in uppercase.
- All numbers should be rounded to two decimal places.

## Challenge Point

If you avoid using `java.util.stream` and `java.lang.math` and manually implement all calculations, you will earn an additional challenge point.
