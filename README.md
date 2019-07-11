# Botnana-Control Release History

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

