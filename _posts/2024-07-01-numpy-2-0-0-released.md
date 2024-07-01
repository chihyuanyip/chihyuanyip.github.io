---
title: "科學運算函式庫 NumPy 2.0.0 發布"
---

NumPy 是 Python 語言的一個擴充程式庫，支援高階大規模的多維陣列與矩陣運算的數學函式函式庫。

NumPy 2.0.0 是自 2006 年以來的第一個主要發行版本，此重要版本標誌著 NumPy 發展歷程中的一項重要里程碑，為使用者提供了豐富的增強功能和改進，並為未來的功能開發奠定了基礎。

## 更新要點

* 新功能

  * 新的變長字串資料類型 StringDType，以及新的 numpy.strings 命名空間，其中包含用於字串運算的高效能 ufunc，

  * 在所有 numpy.fft 函數中支援 float32 和 longdouble，

  * 在主要 numpy 命名空間中支援陣列 API 標準。

* 效能改善

  * 排序函數（sort、argsort、partition、argpartition）已透過使用 Intel x86-simd-sort 和 Google Highway 函式庫加速，並可能大幅提升速度（特定於硬體），

  * 支援 macOS 加速和 macOS >=14 的二進制輪，大幅提升 macOS 上線性代數運算的效能，且輪的體積縮小約 3 倍，

  * numpy.char 定長字串操作已透過實作 ufunc 加速，ufunc 除了支援定長字串資料型態外，也支援 StringDType。

  * 新的追蹤和內省 API，opt_func_info，用於判斷有哪些硬體特定核心可用，以及將派送至何處。

* Python API 改進

  * 公開 API 和私人 API 之間的明確區分，採用新的 模組結構，每個公開函式現在都可以在單一位置取得。

  * 移除許多不建議使用的函式和別名。這應讓學習和使用 NumPy 變得更容易。主命名空間中的物件數量減少約 10%，numpy.lib 中減少約 80%。

  * 正規資料型態名稱 和新的 isdtype 內省函式。

* C API 改進

  * 新的 用於建立自訂資料型態的公開 C API。

  * 移除許多過時的函式和巨集，並隱藏私人內部結構，以簡化未來的可擴充性。

  * 新的、更容易使用的初始化函式：PyArray_ImportNumPyAPI 和 PyUFunc_ImportUFuncAPI。

* 行為改善

  * 透過採用 NEP 50，改善類型提升行為。這修正了許多使用者的驚訝，這些驚訝以前經常取決於輸入陣列的資料值，而不僅取決於它們的資料型態。請參閱 NEP 和 NumPy 2.0 遷移指南，以了解詳細資訊，因為此變更可能會導致輸出資料型態變更，以及混合資料型態操作的精度降低。

  * Windows 上的預設整數類型現在是 int64，而非 int32，這與其他平台上的行為相符。

  * 陣列維度的最大數量已從 32 變更為 64

* 文件

  * 參考指南導覽已大幅改善，現在有 NumPy 模組結構 的文件。

  * 從原始碼建置 文件已完全改寫。

此外，NumPy 內部有許多變更，包括持續將程式碼從 C 遷移至 C++，這將讓 NumPy 在未來更容易改善和維護。

「沒有免費的午餐」定理規定，所有這些 API 和行為改善以及更好的未來可擴充性都需要付出代價。這個代價是

1. 向後相容性。Python 和 C API 有許多重大變更。在大部分情況下，會有明確的錯誤訊息，告知使用者如何調整他們的程式碼。然而，也有行為變更無法提供此類錯誤訊息 - 這些情況都包含在下列的「不建議使用」和「相容性」區段，以及 NumPy 2.0 遷移指南 中。
  請注意，有一個ruff模式可以自動修正 Python 程式碼中的許多問題。

2. NumPy ABI 的重大變更。因此，使用 NumPy C API 並針對 NumPy 1.xx 版本建置的套件二進位檔將無法與 NumPy 2.0 搭配使用。匯入時，此類套件會看到ImportError，並附有關於二進位檔不相容性的訊息。
  可以針對 NumPy 2.0 建置二進位檔，這些二進位檔可以在執行時與 NumPy 2.0 和 1.x 搭配使用。請參閱NumPy 2.0 專屬建議以取得更多詳細資訊。
  建議所有依賴 NumPy ABI 的下游套件針對 NumPy 2.0 進行新的版本建置，並驗證該版本可以與 2.0 和 1.26 搭配使用，理想情況是在 2.0.0rc1（ABI 將保持穩定）和最終的 2.0.0 版本之間，以避免使用者的問題。

此版本支援的 Python 版本為 3.9-3.12。

## NumPy 2.0 文件

* 英文 [https://numpy.org/doc/stable/](https://numpy.org/doc/stable/)
* 繁中 [https://numpy.dev.org.tw/doc/stable/](https://numpy.dev.org.tw/doc/stable/)
* 簡中 [https://numpy.com.cn/doc/stable/](https://numpy.com.cn/doc/stable/)
