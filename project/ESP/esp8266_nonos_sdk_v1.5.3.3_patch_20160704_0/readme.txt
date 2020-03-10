ESP8266_NONOS_SDK_V1.5.3.3_patch 发布说明
本patch基于ESP8266_NONOS_SDK_V1.5.3，已包含1.5.3.1、1.5.3.2的改动，使用时将压缩包中.a文件覆盖SDK/lib目录下对应文件。
对比1.5.3，有如下更新：
1. 修正 system_adc_read 返回值异常的问题。（1.5.3.1中解决）
2. 修正 light sleep 模式下电流较高的问题。（1.5.3.1中解决）
3. 修正 igmp 中一处由于连接特殊路由器可能导致的系统重启问题。（1.5.3.1中解决）
4. 修正部分情况下，RF_Init_data 系统参数区可能被破坏的问题。新增 user_rf_cal_sector_set，用户程序必须实现此接口，详细参见文档 “2C-ESP8266__SDK__API Guide”。 (1.5.3.2中解决）
5. 修正外部复位后，小概率存在 rf 不工作的问题。（1.5.3.3中解决）
6. 修改esp_init_data_default.bin的112字节，0x03->0x00，默认关闭频偏自动校正。

注意：基于更新4的示例代码可参考压缩包中的user_main.c。
_____________________________________________________________________________________

ESP8266_NONOS_SDK_V1.5.3.3_patch release notes
This patch is based on the ESP8266_NONOS_SDK_V1.5.3 and contains all changes updated within ESP8266_NONOS_SDK_V1.5.3.1 and ESP8266_NONOS_SDK_V1.5.3.2. When this patch is used, .a files in this patch shall replace corresponding files under the SDK/lib Folder.

Optimisation:
1. Resolved the issue that API system_adc_read may return wrong value. (Resolved in 1.5.3.1)

2. Resolved the issue that the current in light sleep mode is too high. (Resolved in 1.5.3.1)

3. Optimised igmp to resolve the issue that ESP8266 maybe reset if connected to a special router. (Resolved in 1.5.3.1)

4. Resolved an issue that RF_Init_data sector may be broken in stress test. Provided a function “user_rf_cal_sector_set” which has to be added in application by software developer. More details about user_rf_cal_sector_set refer to documentation “2C-ESP8266__SDK__API Guide”.(Resolved in ESP8266_NONOS_SDK_V1.5.3.2) 

5. Fix a potential risk that will cause rf not work after external reset.(Resolved in ESP8266_NONOS_SDK_V1.5.3.3)

6. Modify 112 byte of esp_init_data_default.bin, 0x03->0x00, turn off auto freq correction.

Attention: Please refer to “user_main.c” in the zip for “user_rf_cal_sector_set” sample code.