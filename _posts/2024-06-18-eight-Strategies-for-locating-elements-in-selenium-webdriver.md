---
title: "Selenium 自動化瀏覽器定位元素的8種策略"
---

[Selenium](https://selenium.dev.org.tw/) 是一個範圍廣泛的工具和函式庫的總稱專案，用於啟用和支援網頁瀏覽器的自動化。Selenium WebDriver 提供了 C#、JavaScript、Java、Python、Ruby 等多種語言的 API，可以用於編寫自動化測試軟體。

在定位元素時，WebDriver 提供對這 8 種傳統定位策略的支援。

## 1. 類別名稱

HTML 頁面網頁元素可以有類別屬性。我們可以使用 Selenium 中提供的類別名稱定位器來識別這些元素。

```python
driver = webdriver.Chrome()
driver.find_element(By.CLASS_NAME, "information")
```

## 2. CSS 選擇器

CSS 是用來設定 HTML 頁面樣式的語言。我們可以使用 CSS 選擇器定位策略來辨識頁面上的元素。如果元素有 id，我們可以將定位器建立為 css = #id。否則，我們遵循的格式為 css =[屬性=值]。我們將使用 CSS 為「fname」文字方塊建立定位器。

```python
driver = webdriver.Chrome()
driver.find_element(By.CSS_SELECTOR, "#fname")
```

## 3. ID 屬性

我們可以使用網頁中元素的 ID 屬性來定位它。一般來說，網頁上每個元素的 ID 屬性都應該是唯一的。我們將使用它來辨識「姓氏」欄位。

```python
driver = webdriver.Chrome()
driver.find_element(By.ID, "lname")
```

## 4. 名稱屬性

我們可以使用網頁中元素的 NAME 屬性來定位它。一般來說，網頁上每個元素的 NAME 屬性都應該是唯一的。我們將使用它來辨識「電子報」核取方塊。

```python
driver = webdriver.Chrome()
driver.find_element(By.NAME, "newsletter")
```

## 5. 連結文字

如果我們要定位的元素是連結，我們可以使用連結文字定位器來辨識網頁上的連結。連結文字是連結顯示的文字。在共用的 HTML 片段中，我們有一個可用的連結，讓我們看看我們要如何定位它。

```python
driver = webdriver.Chrome()
driver.find_element(By.LINK_TEXT, "Selenium Official Page")
```

## 6. 部分連結文字

如果我們要定位的元素是連結，我們可以使用部分連結文字定位器來辨識網頁上的連結。連結文字是連結顯示的文字。我們可以傳遞部分文字作為值。在共用的 HTML 片段中，我們有一個可用的連結，讓我們看看我們要如何定位它。

```python
driver = webdriver.Chrome()
driver.find_element(By.PARTIAL_LINK_TEXT, "Official Page")
```

## 7. 標籤名稱

我們可以使用 HTML 標籤本身作為定位器，來辨識網頁上的網頁元素。從上面共用的 HTML 片段中，讓我們使用其 HTML 標籤「a」來辨識連結。

```python
driver = webdriver.Chrome()
driver.find_element(By.TAG_NAME, "a")
```

## 8. XPath 表達式

HTML 文件可以視為 XML 文件，然後我們可以使用 XPath，這將是遍歷以到達感興趣的元素的途徑，來定位元素。XPath 可以是絕對 XPath，它是由文件的根目錄建立的。例如 `/html/form/input[1]`。這將傳回男性選項按鈕。或者 XPath 可以是相對的。例如 `//input[@name='fname']`。這將傳回名字文字方塊。讓我們使用 XPath 為女性選項按鈕建立定位器。

```python
driver = webdriver.Chrome()
driver.find_element(By.XPATH, "//input[@value='f']")
```
