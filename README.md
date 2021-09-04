# DoorAccess308
备注，308目前的灯管是PHILIPS Essential TL5 28W/865 YZ28RR16/G飞利浦高效率日光灯，一共8个



庭梁自己写的308的门禁，STM32+PN532+数字小键盘+指纹



## 物料清单

芯片准备用ST家的G4x4系列

[STM32G474RE](https://www.st.com/en/microcontrollers-microprocessors/stm32g474re.html)

评估板使用官方开发板

[NUCLEO-G474RE](https://www.st.com/zh/evaluation-tools/nucleo-g474re.html)



继电器

https://detail.tmall.com/item.htm?id=15909056050

普普通通的5V继电器模块带光耦隔离



PN532红板

PN532 NFC RFID module V3 kits

http://www.elechouse.com/elechouse/index.php?main_page=product_info&cPath=90_93&products_id=2242

Arduino库

https://github.com/Seeed-Studio/PN532



小键盘

普通4x4阵列薄膜键盘

https://detail.tmall.com/item.htm?id=543889432634

Pin1-4为列，5-8为行



指纹模块

指纹识别模块ATK-301

http://www.openedv.com/docs/modules/other/ATK-301.html



## 参考链接

[STM32CubeMX系列教程1:GPIO](https://www.waveshare.net/study/article-630-1.html)

https://www.st.com/zh/evaluation-tools/nucleo-g474re.html



## 硬件连接

普普通通继电器的输出端NC和COM连接插座里面的线

输入端三根线：DC+接5V，DC-接0V，IN接GPIO，选择High跳线，高电平触发

GPIO用D5即PB4，方便使用3根公对公的杜邦线



普普通通4x4阵列薄膜键盘1-8引脚分别连接D6-D13对应的引脚

PB10 PA8 PA9 PC7 PB6 PA7 PA6 PA5

Pin1-4为列，5-8为行



PN532连接在USART1上，即PC4 PC5

拨码开关选择00，HSU mode，波特率设置为115200

供电使用5V，GND



ATK-301

供电一定要用3.3V

连接UART5，PD2为RX，PC12为TX

V_TOUCH 触摸唤醒电路 VCC 一直供电3.3V

VCC 模块供电3.3V

TOUCH_OUT省电设计，空着



## 代码



