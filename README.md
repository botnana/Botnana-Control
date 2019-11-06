# Botnana-Control Release History

Botnana Control 更新步驟請參考：

[https://botnana.github.io/botnana-book/update-software.html](https://botnana.github.io/botnana-book/update-software.html)

Botnana Control 更新檔下載網址：

[https://drive.google.com/drive/u/0/folders/1_8j0_r2Hxsl5TJnn83XF2cGb4gC0BmFK](https://drive.google.com/drive/u/0/folders/1_8j0_r2Hxsl5TJnn83XF2cGb4gC0BmFK)

## Version 1.15.3

日期 : 2019/11/06

修改要點：

1. Botnana HMI about 現在需要先輸入驗證碼才可以繼續動作。
2. rtforth : BASIC support. 增加 0labels, label, goto, call 指令。
3. rtforth : 修正了 +loop 只執行一次的 bug。
4. 增加 Encoder : +ec-enc-latch, -ec-enc-latch, ec-enc-latch!, ec-enc-latch?, ec-enc-latch@, ec-enc-overflow?, ec-enc-underflow? 指令
5. 支援 BECKHOFF EL5101 Encoder Module

## Version 1.15.2

日期 : 2019/09/30

修改要點：

1. Server 改為使用 Xenomai Task 處理與 VM 間的 Input/Output，並且限制每個周期最多的命令封包數與總命令長度
2. 統計 Input/Output 的最大使用量。增加命令設定每個周期最多的命令封包數與總命令長度
3. 增加設定驅動器 Touch Probe Function 的 SDO
4. debug:修正軟硬體版本字串後面帶有 NULL 字元的問題

## Version 1.15.1

日期 : 2019/09/23

修改要點：

1. 改用 rtforth 新增的 include 指令引用 forth scripts
2. 增加開機時讀回從站軟硬體版本
3. 軸組允許長度為零之路徑

## Version 1.13.21

日期 : 2019/09/06

修改要點：

1. 增加 `drive-psl@` 與 `drive-nsl@` 指令。


## Version 1.13.20

日期 : 2019/08/15

修改要點：

1. 整合 BECKHOFF EL9410 模組。
2. 整合 TECO JSDG2S 伺服驅動器。
3. 整合 FUJI ALPHA7 伺服驅動器。
4. 修改 `.timer` 回應訊息中的 `timer_expored` 的資料型態。

## Version 1.13.19

日期 : 2019/07/27

修改要點：

1. 增加 `ec-gatway?` 指令。
2. rtforth 增加 `defer`, `defer@`，`defer!`, `>body`, `on` 與 `off` 命令
3. rtforth 增加  `r/o`, `w/o` 與 `r/w` 常數。

參考 [https://mapacode.github.io/rtforth/dictionary.html](https://mapacode.github.io/rtforth/dictionary.html) 中「字典」一章中的「向量執行」一節。
這一節中的程式可以用 defer 和 defer! 改寫如下：

```
    : hello   ." Hello!" ;
    : ciao    ." Ciao!" ;
    defer greet
    : english   ['] hello ['] greet defer! ;
    : italian   ['] ciao ['] greet defer! ;
    english greet
    > Hello!
    italian greet
    > Ciao!

```

## Version 1.13.18

日期 : 2019/07/24

修改要點：

1. rtForth 修正 `move` 命令的錯誤（當移動區間重疊時，資料順序移動錯誤）。 


## Version 1.13.17

日期 : 2019/07/22

修改要點：

1. 支援 IAI RCON-GW-EC 從站 。
2. 增加 `#groups` 與 `#axes` 指令。
3. `encoder_length_unit` 增加 UserDefine 設定。
4. rtForth 增加 `_postpone`,`postpone`,`literal`, `fliteral`, `2literal` 指令。 

## Version 1.13.16

日期 : 2019/07/15

修改要點：

1. rtForth 增加 `tuck`, `/string`, `append`, `word`, `move`, `_skip`, `!token`, `.memory` 指令 。
2. 增加 `.ec-wdt-proc-data` 指令，顯示 EtherCAT Slave Watchdog 設定。
3. encoder。

## Version 1.13.15

日期 : 2019/07/14

修改要點：

1. 直接讀取 FOXNUM 驅動器 Supported Drive Mode 暫存器來判斷可支援的模式。
2. 新增軸組運動 ignorable distance 設定參數，修正軸組運動在 pulse 單位下，因為浮點運算的累計誤差導致無法走到路徑終點的問題，

## Version 1.13.14

日期 : 2019/07/12

修改要點：

1. 新增 `.coordinator` 指令，回傳 `coordinator_enabled` 狀態。

## Version 1.13.13

日期 : 2019/07/11

修改要點：

1. 修改 Websocket Client 連線數超過 2 的時的訊息。
2. 新增 Disable EtherCAT Slave Watchdog 的功能。  

## Version 1.13.12

除錯版。

## Version 1.13.11

日期 : 2019/07/06

修改要點：

1. 增加 `ec_ready` 旗標到 `.ec-links` 指令的回應訊息。
2. 整合 BECKHOFF EL1889 DIN 模組
3. 整合 BECKHOFF EL2889 DOUT 模組
4. 整合 BECKHOFF EL3064 AIN 模組
5. 整合 BECKHOFF EL4004 AOUT 模組

## Version 1.13.10

日期 : 2019/06/22

修改要點：

1. 修正 Omron NX EC203 模組識別條件。
2. 整合 BECKHOFF EL5152 2-Channel Incremental Encoder Interface 模組。

## Version 1.13.9

日期 : 2019/06/22

修改要點：

1. 整合 ADLINK EPS-600, EPS-1032, EPS-2132, EPS-3032, EPS-4008 模組。
2. 增加 `ext_encoder_ppu` 與 `ext_encoder_direction` 狀態到 `.axiscfg` 指令的輸出訊息。
3. 修正網頁上 `encoder_length_unit` 的錯字。
4. 增加起迄點旗標到 `.group` 與 `.axis` 指令的回應訊息。

