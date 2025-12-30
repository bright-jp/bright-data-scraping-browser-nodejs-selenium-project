# Bright Data Amazon Product Scraper with Selenium WebDriver

このプロジェクトでは、Bright Data の Scraping Browser を Selenium WebDriver と併用して Amazon.com で商品を検索する方法を示します。自動化されたブラウザ制御による Webスクレイピングの実用的な例を提供します。

<a href="https://codesandbox.io/p/devbox/github/bright-jp/bright-data-scraping-browser-nodejs-selenium-project?file=%2Famazon-product-scraping.js" target="_blank" rel="noopener">Open in CodeSandbox</a> を開き、GitHub アカウントでサインインしてから、リポジトリを fork して変更を開始してください。

### Getting Started

1. `amazon-product-scraping.js` の `YOUR_BRIGHT_DATA_SCRAPING_BROWSER_ENDPOINT` 値を、実際の Bright Data scraping browser endpoint に置き換えてください：
2. `node amazon-product-scraping.js` を実行してスクレイピングを開始してください


## 💻 Usage

1. `amazon-product-scraping.js` で検索パラメータを変更してください：
   ```javascript
   const SEARCH_TERM = "laptop";   // Change to your search term
   ```

2. スクリプトを実行してください：
   ```bash
   node amazon-product-scraping.js
   ```

## 🔍 How It Works

このスクリプトは Selenium WebDriver を使用して以下を行います：
1. Bright Data の Scraping Browser に接続します
2. Amazon.com に移動します
3. 指定した検索語を使用して商品を検索します
4. 商品情報（タイトル、価格、評価）を抽出します
5. 結果を整形して表示します

```javascript
// Initialize the WebDriver using Bright Data's Scraping Browser
driver = await new Builder()
    .forBrowser(Browser.CHROME)
    .usingServer(SCRAPING_BROWSER)
    .build();
```

## 📊 Example Output

```
📊 AMAZON SEARCH RESULTS for "laptop"
=======================

#1 ASUS Vivobook Go 15 L510 Thin & Light Laptop, 15.6" FHD Display, Intel Celeron N4020 Processor, 4GB RAM, 64GB Storage, Windows 11 Home in S Mode, 1 Year Microsoft 365, Star Black, L510MA-WB04
   💰 Price: $249.99
   ⭐ Rating: 4.3 out of 5 stars
   --------------------------------------------------

#2 Acer Aspire 3 A315-24P-R7VH Slim Laptop | 15.6" Full HD IPS Display | AMD Ryzen 3 7320U Quad-Core Processor | AMD Radeon Graphics | 8GB LPDDR5 | 128GB NVMe SSD | Wi-Fi 6 | Windows 11 Home in S Mode
   💰 Price: $299.99
   ⭐ Rating: 4.4 out of 5 stars
   --------------------------------------------------

#3 HP 15.6" HD Laptop, Intel Celeron N4500, 8GB RAM, 256GB SSD, Silver, Windows 11 Home in S Mode
   💰 Price: $279.00
   ⭐ Rating: 4.2 out of 5 stars
   --------------------------------------------------

#4 Lenovo IdeaPad 1 14 Laptop, 14.0" HD Display, Intel Celeron N4020, 4GB RAM, 64GB Storage, Intel UHD Graphics 600, Win 11 in S Mode, Cloud Grey
   💰 Price: $199.99
   ⭐ Rating: 4.1 out of 5 stars
   --------------------------------------------------

#5 HP 14" HD Laptop, Intel Celeron N4020, 4GB RAM, 64GB Storage, Pale Rose Gold, Windows 11 Home in S Mode
   💰 Price: $219.99
   ⭐ Rating: 4.3 out of 5 stars
   --------------------------------------------------

✅ Found 5 products for "laptop"
```