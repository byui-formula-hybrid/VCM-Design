# BYU-I Formula Hybrid VCM Design

This Repository holds all appropriate pcb files for the BYU-I Formula Hybrid teams Vehicle Control Module pcb board design.

The Microcontroller being built around is the STM32-F767ZI


## STM32 pins to be exposed by the pcb
```
PD0      ------> CAN1_RX
PD1      ------> CAN1_TX
PB12     ------> CAN2_RX
PB6      ------> CAN2_TX
PD8      ------> USART3_TX
PD9      ------> USART3_RX
PA8      ------> USB_OTG_FS_SOF
PA9      ------> USB_OTG_FS_VBUS
PA10     ------> USB_OTG_FS_ID
PA11     ------> USB_OTG_FS_DM
PA12     ------> USB_OTG_FS_DP
PA5      ------> SPI1_SCK
PA6      ------> SPI1_MISO
PD7      ------> SPI1_MOSI
PA4      ------> SPI1_CS
```

* CAN1 - Primary CAN Bus
* CAN2 - Backup CAN Bus
* USART3 - External Communication
* USB_OTG - For flashing updates
* SPI - External Communication
