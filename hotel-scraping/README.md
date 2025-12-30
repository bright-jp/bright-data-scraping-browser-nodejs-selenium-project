# Bright Data Hotel Search Scraper with Selenium WebDriver

このプロジェクトでは、Bright Data の Scraping Browser を Selenium WebDriver とともに使用して Booking.com でホテルを検索する方法を示します。自動化されたブラウザ制御による Webスクレイピング の実用的な例を提供します。

<a href="https://codesandbox.io/p/devbox/github/luminati-io/bright-data-scraping-browser-selenium-webdriver-project?file=%2Fbooking-hotel-scraping.js" target="_blank" rel="noopener">Open in CodeSandbox</a> を開き、GitHub アカウントでサインインしてから、リポジトリをフォークして変更を開始してください。

### Getting Started

1. `booking-hotel-scraping.js` 内の `YOUR_BRIGHT_DATA_SCRAPING_BROWSER_ENDPOINT` の値を、実際の Bright Data scraping browser endpoint に置き換えてください
2. `node booking-hotel-scraping.js` を実行してスクレイピングを開始してください


## 💻 Usage

1. `booking-hotel-scraping.js` の検索パラメータを変更してください:
   ```javascript
   const SEARCH_LOCATION = "New York";  // Change to your desired location
   const CHECK_IN_DAYS_FROM_NOW = 1;    // Adjust check-in date
   const CHECK_OUT_DAYS_FROM_NOW = 2;   // Adjust check-out date
   ```

2. スクリプトを実行してください:
   ```bash
   node booking-hotel-scraping.js
   ```

## 🔍 How It Works

このスクリプトは Selenium WebDriver を使用して次を行います:
1. Bright Data の Scraping Browser に接続する
2. Booking.com に移動する
3. 表示されるポップアップを処理する
4. ロケーションと日付を使用して検索フォームに入力する
5. 検索を送信し、結果を待機する
6. ホテル情報（名前、価格、評価）を抽出する
7. 結果をテーブル形式で表示する

```javascript
// Initialize the WebDriver using Bright Data's Scraping Browser
driver = await new Builder()
    .forBrowser(Browser.CHROME)
    .usingServer(SCRAPING_BROWSER)
    .build();
```

## 📊 Example Output

```
📊 Search Results:
==================
┌─────────┬─────┬────────────────────┬──────────┬─────────┐
│ (index) │  #  │     Hotel Name     │  Price   │ Rating  │
├─────────┼─────┼────────────────────┼──────────┼─────────┤
│    0    │  1  │ Hotel Name 1       │ $100     │ 8.5     │
│    1    │  2  │ Hotel Name 2       │ $150     │ 9.0     │
│    2    │  3  │ Hotel Name 3       │ $200     │ 8.8     │
└─────────┴─────┴────────────────────┴──────────┴─────────┘
```