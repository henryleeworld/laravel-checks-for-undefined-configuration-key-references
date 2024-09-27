# Laravel 11 檢查未定義設定鍵參用

引入 chrisdicarlo 的 laravel-config-checker 套件來擴增檢查未定義設定鍵參用，新增了一個 Artisan 指令來檢查程式碼和 Blade 視圖中的無效設定檔參用。

## 使用方式
- 把整個專案複製一份到你的電腦裡，這裡指的「內容」不是只有檔案，而是指所有整個專案的歷史紀錄、分支、標籤等內容都會複製一份下來。
```sh
$ git clone
```
- 將 __.env.example__ 檔案重新命名成 __.env__，如果應用程式金鑰沒有被設定的話，你的使用者 sessions 和其他加密的資料都是不安全的！
- 當你的專案中已經有 composer.lock，可以直接執行指令以讓 Composer 安裝 composer.lock 中指定的套件及版本。
```sh
$ composer install
```
- 產生 Laravel 要使用的一組 32 字元長度的隨機字串 APP_KEY 並存在 .env 內。
```sh
$ php artisan key:generate
```
- 執行 __Artisan__ 指令的 `config:check` 指令來掃描 app 目錄下的程式碼和 resources/views 目錄下的 Blade 視圖。
```sh
$ php artisan config:check
```

----

## 畫面截圖
![](https://i.imgur.com/khgu1SI.png)
> 任何錯誤都會顯示在表格中，包含檔案位置和遺漏參用的資訊
