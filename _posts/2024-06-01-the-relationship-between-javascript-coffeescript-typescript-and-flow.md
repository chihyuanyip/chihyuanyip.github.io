---
title: "JavaScript 與 CoffeeScript、TypeScript 和 Flow 的關係"
---

JavaScript (簡稱 JS) 是具有一級函數的輕量級、直譯式或即時編譯的程式語言。它因為用作網頁的腳本語言而大為知名，但也用於許多非瀏覽器的環境，像是 [Node.js](https://node.dev.org.tw/) 等。由於 JavaScript 語法上的一些缺點，軟體工程師們又設計出了 CoffeeScript、TypeScript 和 Flow 等語言，它們最終也可以在 JavaScript 環境中執行。

## [CoffeeScript](https://coffeescript.dev.org.tw/)

CoffeeScript 是一種編譯成 JavaScript 的小型語言。在笨拙的 Java 風格外表下，JavaScript 一直擁有華麗的心。CoffeeScript 嘗試以簡單的方式揭露 JavaScript 的優點。

CoffeeScript 的黃金法則為：「它只是 JavaScript。」程式碼會一對一編譯成等效的 JS，且執行時沒有解釋。您可以從 CoffeeScript 無縫使用任何現有的 JavaScript 函式庫（反之亦然）。編譯的輸出可讀、美化，而且執行速度往往與手寫的等效 JavaScript 一樣快，甚至更快。

## [TypeScript](https://typescript.dev.org.tw/)

TypeScript 是 [Microsoft](https://www.microsoft.com) 的一種語言，建構在 JavaScript 之上，是 JavaScript 的嚴格語法超集，它包含所有 JavaScript 的全部，然後再增加了可選的靜態型別檢查。TypeScript 在執行前會檢查程式是否有錯誤，並根據值類型進行檢查，使其成為靜態類型檢查器。

TypeScript 起源於 JavaScript 在微軟以及客戶中開發大型應用中遇到的缺點。處理複雜 JavaScript 代碼帶來的挑戰使他們需要自訂工具來簡化組件開發流程。

## [Flow](https://flow.dev.org.tw/)

Flow 是 [Facebook](https://www.facebook.com/) 釋出的一個 JavaScript 開源靜態類型檢查器。Flow 為 JavaScript 新增了靜態型別，以提升開發人員的生產力和程式碼品質。特別的是，靜態型別提供以下優點，例如提早在檢查錯誤，這有助於您避免某些類型的執行時間失敗，以及程式碼情報，這有助於程式碼維護、導覽、轉換和最佳化。
