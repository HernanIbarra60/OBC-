STM32F722xx
STM32F723xx
® ®
ARM Cortex -M7 32b MCU+FPU, 462DMIPS, up to 512KB Flash
/256+16+4KB RAM, USB OTG HS/FS, 18 TIMs, 3 ADCs, 21 com IF
Datasheet - production data
Features
• Core: ARM® 32-bit Cortex®-M7 CPU with FPU, (cid:38)(cid:34)(cid:39)(cid:33)
adaptive real-time accelerator (ART
Accelerator™) and L1-cache: 8 Kbytes of data
cache and 8 Kbytes of instruction cache, LQFP64 (10 × 10 mm) UFBGA144 (7 x 7 mm) WLCSP100
allowing 0-wait state execution from embedded LQFP100 (14 × 14 mm) (0.4 mm pitch)
UFBGA176 (10 x 10 mm)
Flash memory and external memories,
LQFP144 (20 × 20 mm)
frequency up to 216 MHz, MPU,
LQFP176 (24 x 24 mm)
462 DMIPS/2.14 DMIPS/MHz (Dhrystone 2.1)
and DSP instructions.
– V supply for RTC, 32×32 bit backup
BAT
• Memories registers + 4 Kbytes of backup SRAM
– Up to 512 Kbytes of Flash memory with • 3×12-bit, 2.4 MSPS ADC: up to 24 channels
protection mechanisms (read and write and 7.2 MSPS in triple interleaved mode
protections, proprietary code readout
• 2×12-bit D/A converters
protection (PCROP))
• Up to 18 timers: up to thirteen 16-bit (1x low-
– 528 bytes of OTP memory
power 16-bit timer available in Stop mode) and
– SRAM: 256 Kbytes (including 64 Kbytes of
two 32-bit timers, each with up to 4
data TCM RAM for critical real-time data) +
IC/OC/PWMs or pulse counter and quadrature
16 Kbytes of instruction TCM RAM (for
(incremental) encoder inputs. All 15 timers
critical real-time routines) + 4 Kbytes of
running up to 216 MHz. 2x watchdogs, SysTick
backup SRAM (available in the lowest
timer
power modes)
• General-purpose DMA: 16-stream DMA
– Flexible external memory controller with up
controller with FIFOs and burst support
to 32-bit data bus: SRAM, PSRAM,
SDRAM/LPSDR SDRAM, NOR/NAND • Debug mode
memories – SWD & JTAG interfaces
• Dual mode Quad-SPI – Cortex®-M7 Trace Macrocell™
• Clock, reset and supply management • Up to 140 I/O ports with interrupt capability
– 1.7 V to 3.6 V application supply and I/Os – Up to 136 fast I/Os up to 108 MHz
– POR, PDR, PVD and BOR – Up to 138 5 V-tolerant I/Os
– Dedicated USB power • Up to 21 communication interfaces
– 4-to-26 MHz crystal oscillator – Up to 3× I2C interfaces (SMBus/PMBus)
– Internal 16 MHz factory-trimmed RC (1% – Up to 4 USARTs/4 UARTs (27 Mbit/s,
accuracy) ISO7816 interface, LIN, IrDA, modem
– 32 kHz oscillator for RTC with calibration control)
– Internal 32 kHz RC with calibration – Up to 5 SPIs (up to 54 Mbit/s), 3 with
• Low-power muxed simplex I2Ss for audio class
accuracy via internal audio PLL or external
– Sleep, Stop and Standby modes
clock
– 2 x SAIs (serial audio interface)
June 2017 DocID029808 Rev 3 1/229
This is information on a product in full production. www.st.com

STM32F722xx STM32F723xx
– 1 x CAN (2.0B active) • True random number generator
– 2 x SDMMCs • CRC calculation unit
• Advanced connectivity • RTC: subsecond accuracy, hardware calendar
– USB 2.0 full-speed device/host/OTG • 96-bit unique ID
controller with on-chip PHY
– USB 2.0 high-speed/full-speed
device/host/OTG controller with dedicated
DMA, on-chip full-speed PHY and on-chip
Hi-speed PHY or ULPI depending on the
part number
Table 1. Device summary
Reference Part number
STM32F722IE, STM32F722ZE, STM32F722VE, STM32F722RE, STM32F722IC,
STM32F722xx
STM32F722ZC, STM32F722VC, STM32F722RC
STM32F723xx STM32F723IE, STM32F723ZE, STM32F723VE, STM32F723IC, STM32F723ZC
2/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Contents
Contents
1 Description . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 13
1.1 Full compatibility throughout the family . . . . . . . . . . . . . . . . . . . . . . . . . . 16
1.2 STM32F723xx versus STM32F722xx LQFP144/LQFP176 packages: . . 18
2 Functional overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 20
2.1 ARM® Cortex®-M7 with FPU . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 20
2.2 Memory protection unit . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 20
2.3 Embedded Flash memory . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
2.4 CRC (cyclic redundancy check) calculation unit . . . . . . . . . . . . . . . . . . . 21
2.5 Embedded SRAM . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
2.6 AXI-AHB bus matrix . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
2.7 DMA controller (DMA) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
2.8 Flexible memory controller (FMC) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 24
2.9 Quad-SPI memory interface (QUADSPI) . . . . . . . . . . . . . . . . . . . . . . . . . 24
2.10 Nested vectored interrupt controller (NVIC) . . . . . . . . . . . . . . . . . . . . . . . 25
2.11 External interrupt/event controller (EXTI) . . . . . . . . . . . . . . . . . . . . . . . . . 25
2.12 Clocks and startup . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
2.13 Boot modes . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 26
2.14 Power supply schemes . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 26
2.15 Power supply supervisor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 28
2.15.1 Internal reset ON . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 28
2.15.2 Internal reset OFF . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 28
2.16 Voltage regulator . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 30
2.16.1 Regulator ON . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 30
2.16.2 Regulator OFF . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
2.16.3 Regulator ON/OFF and internal reset ON/OFF availability . . . . . . . . . . 34
2.17 Real-time clock (RTC), backup SRAM and backup registers . . . . . . . . . . 34
2.18 Low-power modes . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
2.19 V operation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 36
BAT
2.20 Timers and watchdogs . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 36
2.20.1 Advanced-control timers (TIM1, TIM8) . . . . . . . . . . . . . . . . . . . . . . . . . 38
2.20.2 General-purpose timers (TIMx) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
DocID029808 Rev 3 3/229
6

Contents STM32F722xx STM32F723xx
2.20.3 Basic timers TIM6 and TIM7 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
2.20.4 Low-power timer (LPTIM1) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 39
2.20.5 Independent watchdog . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 39
2.20.6 Window watchdog . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 39
2.20.7 SysTick timer . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 39
2.21 Inter-integrated circuit interface (I2C) . . . . . . . . . . . . . . . . . . . . . . . . . . . . 40
2.22 Universal synchronous/asynchronous receiver transmitters (USART) . . 41
2.23 Serial peripheral interface (SPI)/inter- integrated sound interfaces (I2S) . 42
2.24 Serial audio interface (SAI) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 42
2.25 Audio PLL (PLLI2S) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 43
2.26 Audio PLL (PLLSAI) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 43
2.27 SD/SDIO/MMC card host interface (SDMMC) . . . . . . . . . . . . . . . . . . . . . 43
2.28 Controller area network (bxCAN) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 43
2.29 Universal serial bus on-the-go full-speed (OTG_FS) . . . . . . . . . . . . . . . . 44
2.30 Universal serial bus on-the-go high-speed (OTG_HS) . . . . . . . . . . . . . . . 44
2.31 Random number generator (RNG) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 45
2.32 General-purpose input/outputs (GPIOs) . . . . . . . . . . . . . . . . . . . . . . . . . . 45
2.33 Analog-to-digital converters (ADCs) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 45
2.34 Temperature sensor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 46
2.35 Digital-to-analog converter (DAC) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 46
2.36 Serial wire JTAG debug port (SWJ-DP) . . . . . . . . . . . . . . . . . . . . . . . . . . 46
2.37 Embedded Trace Macrocell™ . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 47
3 Pinouts and pin description . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48
4 Memory mapping . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 97
5 Electrical characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102
5.1 Parameter conditions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102
5.1.1 Minimum and maximum values . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102
5.1.2 Typical values . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102
5.1.3 Typical curves . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102
5.1.4 Loading capacitor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102
5.1.5 Pin input voltage . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102
5.1.6 Power supply scheme . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 103
4/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Contents
5.1.7 Current consumption measurement . . . . . . . . . . . . . . . . . . . . . . . . . . 105
5.2 Absolute maximum ratings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 105
5.3 Operating conditions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 107
5.3.1 General operating conditions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 107
5.3.2 VCAP1/VCAP2 external capacitor . . . . . . . . . . . . . . . . . . . . . . . . . . . . 109
5.3.3 Operating conditions at power-up / power-down (regulator ON) . . . . . 110
5.3.4 Operating conditions at power-up / power-down (regulator OFF) . . . . 110
5.3.5 Reset and power control block characteristics . . . . . . . . . . . . . . . . . . 110
5.3.6 Over-drive switching characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . 112
5.3.7 Supply current characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 112
5.3.8 Wakeup time from low-power modes . . . . . . . . . . . . . . . . . . . . . . . . . . 130
5.3.9 External clock source characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . 131
5.3.10 Internal clock source characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . 136
5.3.11 PLL characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 137
5.3.12 PLL spread spectrum clock generation (SSCG) characteristics . . . . . 140
5.3.13 USB OTG HS PHY PLLs characteristics (on STM32F723xx devices) 142
5.3.14 USB OTG HS PHY regulator characteristics (on
STM32F723xx devices) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 142
5.3.15 USB HS PHY external resistor characteristics (on
STM32F723xx devices) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 143
5.3.16 Memory characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 143
5.3.17 EMC characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 145
5.3.18 Absolute maximum ratings (electrical sensitivity) . . . . . . . . . . . . . . . . 146
5.3.19 I/O current injection characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . 147
5.3.20 I/O port characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 148
5.3.21 NRST pin characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 154
5.3.22 TIM timer characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155
5.3.23 RTC characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155
5.3.24 12-bit ADC characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155
5.3.25 Temperature sensor characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . 161
5.3.26 V monitoring characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 161
BAT
5.3.27 Reference voltage . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 161
5.3.28 DAC electrical characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 162
5.3.29 Communications interfaces . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 164
5.3.30 FMC characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 177
5.3.31 Quad-SPI interface characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . 197
5.3.32 SD/SDIO MMC card host interface (SDMMC) characteristics . . . . . . . 199
DocID029808 Rev 3 5/229
6

Contents STM32F722xx STM32F723xx
6 Package information . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 202
6.1 LQFP64 – 10 x 10 mm, low-profile quad flat package information . . . . . 202
6.2 LQFP100, 14 x 14 mm low-profile quad flat package information . . . . . 205
6.3 LQFP144, 20 x 20 mm low-profile quad flat package information . . . . . 208
6.4 LQFP176 24 x 24 mm low-profile quad flat package information . . . . . . .211
6.5 UFBGA144 package information . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 215
6.6 UFBGA176+25, 10 x 10, 0.65 mm ultra thin-pitch ball grid
array package information . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 218
6.7 WLCSP100 - 0.4 mm pitch wafer level chip scale package information 221
6.8 Thermal characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 225
7 Ordering information . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 226
Appendix A Recommendations when using internal reset OFF . . . . . . . . . . . 227
A.1 Operating conditions. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 227
Revision history . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 228
6/229 DocID029808 Rev 3

STM32F722xx STM32F723xx List of tables
List of tables
Table 1. Device summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2
Table 2. STM32F722xx and STM32F723xx features and peripheral counts . . . . . . . . . . . . . . . . . . 14
Table 3. Voltage regulator configuration mode versus device operating mode . . . . . . . . . . . . . . . . 31
Table 4. Regulator ON/OFF and internal reset ON/OFF availability. . . . . . . . . . . . . . . . . . . . . . . . . 34
Table 5. Voltage regulator modes in stop mode. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
Table 6. Timer feature comparison. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 37
Table 7. I2C implementation. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 40
Table 8. USART implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 41
Table 9. Legend/abbreviations used in the pinout table. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 58
Table 10. STM32F722xx and STM32F723xx pin and ball definition . . . . . . . . . . . . . . . . . . . . . . . . . 59
Table 11. FMC pin definition. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 83
Table 12. STM32F722xx and STM32F723xx alternate function mapping. . . . . . . . . . . . . . . . . . . . . 86
Table 13. STM32F722xx and STM32F723xx register boundary
addresses. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 98
Table 14. Voltage characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 105
Table 15. Current characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 106
Table 16. Thermal characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 107
Table 17. General operating conditions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 107
Table 18. Limitations depending on the operating power supply range. . . . . . . . . . . . . . . . . . . . . . 109
Table 19. VCAP1/VCAP2 operating conditions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 110
Table 20. VCAP1 operating conditions in the LQFP64 package . . . . . . . . . . . . . . . . . . . . . . . . . . . 110
Table 21. Operating conditions at power-up / power-down (regulator ON) . . . . . . . . . . . . . . . . . . . 110
Table 22. Operating conditions at power-up / power-down (regulator OFF). . . . . . . . . . . . . . . . . . . 110
Table 23. reset and power control block characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 111
Table 24. Over-drive switching characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 112
Table 25. Typical and maximum current consumption in Run mode, code with data processing
running from ITCM RAM, regulator ON. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 113
Table 26. Typical and maximum current consumption in Run mode, code with data processing
running from Flash memory (ART ON except prefetch / L1-cache ON)
or SRAM on AXI (L1-cache ON), regulator ON . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 114
Table 27. Typical and maximum current consumption in Run mode, code with data processing
running from Flash memory or SRAM on AXI (L1-cache disabled), regulator ON . . . . . 115
Table 28. Typical and maximum current consumption in Run mode, code with data processing
running from Flash memory on ITCM interface (ART disabled), regulator ON . . . . . . . . 116
Table 29. Typical and maximum current consumption in Run mode, code with data processing
running from Flash memory (ART ON except prefetch / L1-cache ON)
or SRAM on AXI (L1-cache ON), regulator OFF. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 117
Table 30. Typical and maximum current consumption in Sleep mode, regulator ON. . . . . . . . . . . . 118
Table 31. Typical and maximum current consumption in Sleep mode, regulator OFF. . . . . . . . . . . 118
Table 32. Typical and maximum current consumptions in Stop mode. . . . . . . . . . . . . . . . . . . . . . . 119
Table 33. Typical and maximum current consumptions in Standby mode . . . . . . . . . . . . . . . . . . . . 120
Table 34. Typical and maximum current consumptions in V mode. . . . . . . . . . . . . . . . . . . . . . . 121
BAT
Table 35. Switching output I/O current consumption . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 125
Table 36. Peripheral current consumption . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 127
Table 37. USB OTG HS and USB OTG PHY HS current consumption . . . . . . . . . . . . . . . . . . . . . . 130
Table 38. Low-power mode wakeup timings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 130
Table 39. High-speed external user clock characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 131
Table 40. Low-speed external user clock characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 132
DocID029808 Rev 3 7/229
9

List of tables STM32F722xx STM32F723xx
Table 41. HSE 4-26 MHz oscillator characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 133
Table 42. LSE oscillator characteristics (f = 32.768 kHz) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 134
LSE
Table 43. HSI oscillator characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 136
Table 44. LSI oscillator characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 137
Table 45. Main PLL characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 137
Table 46. PLLI2S characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 138
Table 47. PLLISAI characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 139
Table 48. SSCG parameters constraint . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 140
Table 49. USB OTG HS PLL1 characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 142
Table 50. USB OTG HS PLL2 characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 142
Table 51. USB OTG HS PHY regulator characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 142
Table 52. USB HS PHY external resistor characteristics (on STM32F723xx devices). . . . . . . . . . . 143
Table 53. Flash memory characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 143
Table 54. Flash memory programming. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 143
Table 55. Flash memory programming with VPP. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 144
Table 56. Flash memory endurance and data retention. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 144
Table 57. EMS characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 145
Table 58. EMI characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 146
Table 59. ESD absolute maximum ratings. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 146
Table 60. Electrical sensitivities . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 147
Table 61. I/O current injection susceptibility. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 147
Table 62. I/O static characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 148
Table 63. Output voltage characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 151
Table 64. I/O AC characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 152
Table 65. NRST pin characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 154
Table 66. TIMx characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155
Table 67. RTC characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155
Table 68. ADC characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155
Table 69. ADC static accuracy at f = 18 MHz. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 157
ADC
Table 70. ADC static accuracy at f = 30 MHz. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 157
ADC
Table 71. ADC static accuracy at f = 36 MHz. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 158
ADC
Table 72. ADC dynamic accuracy at f = 18 MHz - limited test conditions . . . . . . . . . . . . . . . . . 158
ADC
Table 73. ADC dynamic accuracy at f = 36 MHz - limited test conditions . . . . . . . . . . . . . . . . . 158
ADC
Table 74. Temperature sensor characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 161
Table 75. Temperature sensor calibration values. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 161
Table 76. V monitoring characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 161
BAT
Table 77. internal reference voltage . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 161
Table 78. Internal reference voltage calibration values . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 162
Table 79. DAC characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 162
Table 80. Minimum I2CCLK frequency in all I2C modes . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 165
Table 81. I2C analog filter characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 165
Table 82. SPI dynamic characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 166
Table 83. I2S dynamic characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 169
Table 84. SAI characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 171
Table 85. USB OTG full speed startup time. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 173
Table 86. USB OTG full speed DC electrical characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 173
Table 87. USB OTG full speed electrical characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 174
Table 88. USB HS DC electrical characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 174
Table 89. USB HS clock timing parameters. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 175
Table 90. Dynamic characteristics: USB ULPI. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 176
Table 91. USB OTG high speed DC electrical characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 176
Table 92. USB OTG high speed electrical characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 176
8/229 DocID029808 Rev 3

STM32F722xx STM32F723xx List of tables
Table 93. USB FS PHY BCD electrical characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 177
Table 94. Asynchronous non-multiplexed SRAM/PSRAM/NOR read timings . . . . . . . . . . . . . . . . . 179
Table 95. Asynchronous non-multiplexed SRAM/PSRAM/NOR read - NWAIT timings. . . . . . . . . . 179
Table 96. Asynchronous non-multiplexed SRAM/PSRAM/NOR write timings . . . . . . . . . . . . . . . . . 180
Table 97. Asynchronous non-multiplexed SRAM/PSRAM/NOR write - NWAIT timings. . . . . . . . . . 181
Table 98. Asynchronous multiplexed PSRAM/NOR read timings. . . . . . . . . . . . . . . . . . . . . . . . . . . 182
Table 99. Asynchronous multiplexed PSRAM/NOR read-NWAIT timings . . . . . . . . . . . . . . . . . . . . 182
Table 100. Asynchronous multiplexed PSRAM/NOR write timings . . . . . . . . . . . . . . . . . . . . . . . . . . 183
Table 101. Asynchronous multiplexed PSRAM/NOR write-NWAIT timings. . . . . . . . . . . . . . . . . . . . 184
Table 102. Synchronous multiplexed NOR/PSRAM read timings . . . . . . . . . . . . . . . . . . . . . . . . . . . 186
Table 103. Synchronous multiplexed PSRAM write timings. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 188
Table 104. Synchronous non-multiplexed NOR/PSRAM read timings. . . . . . . . . . . . . . . . . . . . . . . . 189
Table 105. Synchronous non-multiplexed PSRAM write timings . . . . . . . . . . . . . . . . . . . . . . . . . . . . 191
Table 106. Switching characteristics for NAND Flash read cycles. . . . . . . . . . . . . . . . . . . . . . . . . . . 193
Table 107. Switching characteristics for NAND Flash write cycles. . . . . . . . . . . . . . . . . . . . . . . . . . . 193
Table 108. SDRAM read timings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 195
Table 109. LPSDR SDRAM read timings. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 195
Table 110. SDRAM write timings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 196
Table 111. LPSDR SDRAM write timings. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 197
Table 112. Quad-SPI characteristics in SDR mode . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 197
Table 113. Quad-SPI characteristics in DDR mode. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 198
Table 114. Dynamic characteristics: SD / MMC characteristics, VDD=2.7V to 3.6V . . . . . . . . . . . . . 200
Table 115. Dynamic characteristics: eMMC characteristics, VDD=1.71V to 1.9V . . . . . . . . . . . . . . . 201
Table 116. LQFP64 – 10 x 10 mm, low-profile quad flat package mechanical data. . . . . . . . . . . . . . 202
Table 117. LQPF100, 14 x 14 mm 100-pin low-profile quad flat package mechanical data. . . . . . . . 205
Table 118. LQFP144, 20 x 20 mm, 144-pin low-profile quad flat package
mechanical data . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 208
Table 119. LQFP176, 24 x 24 mm, 176-pin low-profile quad flat package
mechanical data . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 211
Table 120. UFBGA144 - 144-ball, 7 x 7 mm, 0.50 mm pitch, ultra fine pitch ball grid
array package mechanical data . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 215
Table 121. UFBGA144 recommended PCB design rules (0.50 mm pitch BGA) . . . . . . . . . . . . . . . . 216
Table 122. UFBGA176+25, 10 × 10 × 0.65 mm ultra thin fine-pitch ball grid array
package mechanical data. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 218
Table 123. UFBGA176+25 recommended PCB design rules (0.65 mm pitch BGA) . . . . . . . . . . . . . 219
Table 124. WLCSP100 – 100L, 4.166 x 4.628 mm 0.4 mm pitch wafer level chip scale
package mechanical data. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 222
Table 125. WLCSP100 recommended PCB design rules (0.4 mm pitch) . . . . . . . . . . . . . . . . . . . . . 223
Table 126. Package thermal characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 225
Table 127. Ordering information scheme. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 226
Table 128. Limitations depending on the operating power supply range. . . . . . . . . . . . . . . . . . . . . . 227
Table 129. Document revision history . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 228
DocID029808 Rev 3 9/229
9

List of figures STM32F722xx STM32F723xx
List of figures
Figure 1. Compatible board design for LQFP100 package . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
Figure 2. Compatible board design for LQFP64 package . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
Figure 3. Compatible board design for LQFP144 package . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
Figure 4. Compatible board design for LQFP176 package . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
Figure 5. STM32F722xx and STM32F723xx block diagram . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 19
Figure 6. STM32F722xx and STM32F723xx AXI-AHB bus matrix architecture(1). . . . . . . . . . . . . . . 22
Figure 7. VDDUSB connected to VDD power supply . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27
Figure 8. VDDUSB connected to external power supply. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27
Figure 9. Power supply supervisor interconnection with internal reset OFF . . . . . . . . . . . . . . . . . . . 29
Figure 10. PDR_ON control with internal reset OFF . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
Figure 11. Regulator OFF . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 32
Figure 12. Startup in regulator OFF: slow V slope
DD
- power-down reset risen after V /V stabilization. . . . . . . . . . . . . . . . . . . . . . . . 33
CAP_1 CAP_2
Figure 13. Startup in regulator OFF mode: fast V slope
DD
- power-down reset risen before V /V stabilization . . . . . . . . . . . . . . . . . . . . . . 33
CAP_1 CAP_2
Figure 14. STM32F722xx LQFP64 pinout. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48
Figure 15. STM32F722xx LQFP100 pinout . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
Figure 16. STM32F723xx WLCSP100 ballout (with OTG PHY HS) . . . . . . . . . . . . . . . . . . . . . . . . . . 50
Figure 17. STM32F722xx LQFP144 pinout . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 51
Figure 18. STM32F723xx LQFP144 pinout . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 52
Figure 19. STM32F723xx UFBGA144 ballout (with OTG PHY HS). . . . . . . . . . . . . . . . . . . . . . . . . . . 53
Figure 20. STM32F722xx LQFP176 pinout. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 54
Figure 21. STM32F723xx LQFP176 pinout. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 55
Figure 22. STM32F723xx UFBGA176 ballout. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 56
Figure 23. STM32F723xx UFBGA176 ballout (with OTG PHY HS). . . . . . . . . . . . . . . . . . . . . . . . . . . 57
Figure 24. Memory map. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 97
Figure 25. Pin loading conditions. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102
Figure 26. Pin input voltage. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102
Figure 27. STM32F722xx power supply scheme. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 103
Figure 28. STM32F723xx power supply scheme. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 104
Figure 29. Current consumption measurement scheme . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 105
Figure 30. External capacitor C . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 109
EXT
Figure 31. Typical V current consumption (RTC ON/BKP SRAM OFF and
BAT
LSE in low drive mode). . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 122
Figure 32. Typical V current consumption (RTC ON/BKP SRAM OFF and
BAT
LSE in medium low drive mode). . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 122
Figure 33. Typical V current consumption (RTC ON/BKP SRAM OFF and
BAT
LSE in medium high drive mode) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 123
Figure 34. Typical V current consumption (RTC ON/BKP SRAM OFF and
BAT
LSE in high drive mode). . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 123
Figure 35. Typical V current consumption (RTC ON/BKP SRAM OFF and
BAT
LSE in high medium drive mode) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 124
Figure 36. High-speed external clock source AC timing diagram . . . . . . . . . . . . . . . . . . . . . . . . . . . 132
Figure 37. Low-speed external clock source AC timing diagram. . . . . . . . . . . . . . . . . . . . . . . . . . . . 133
Figure 38. Typical application with an 8 MHz crystal. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 134
Figure 39. Typical application with a 32.768 kHz crystal. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 135
Figure 40. ACCHSI versus temperature . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 136
Figure 41. LSI deviation versus temperature. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 137
10/229 DocID029808 Rev 3

STM32F722xx STM32F723xx List of figures
Figure 42. PLL output clock waveforms in center spread mode . . . . . . . . . . . . . . . . . . . . . . . . . . . . 141
Figure 43. PLL output clock waveforms in down spread mode. . . . . . . . . . . . . . . . . . . . . . . . . . . . . 141
Figure 44. FT I/O input characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 150
Figure 45. I/O AC characteristics definition . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 153
Figure 46. Recommended NRST pin protection . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 154
Figure 47. ADC accuracy characteristics. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 159
Figure 48. Typical connection diagram using the ADC . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 159
Figure 49. Power supply and reference decoupling (V not connected to V ). . . . . . . . . . . . . 160
REF+ DDA
Figure 50. Power supply and reference decoupling (V connected to V ). . . . . . . . . . . . . . . . 160
REF+ DDA
Figure 51. 12-bit buffered /non-buffered DAC . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 164
Figure 52. SPI timing diagram - slave mode and CPHA = 0 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 167
Figure 53. SPI timing diagram - slave mode and CPHA = 1 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 168
Figure 54. SPI timing diagram - master mode. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 168
Figure 55. I2S slave timing diagram (Philips protocol)(1) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 170
Figure 56. I2S master timing diagram (Philips protocol)(1). . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 170
Figure 57. SAI master timing waveforms. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 172
Figure 58. SAI slave timing waveforms . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 172
Figure 59. USB OTG full speed timings: definition of data signal rise and fall time. . . . . . . . . . . . . . 174
Figure 60. ULPI timing diagram. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 175
Figure 61. Asynchronous non-multiplexed SRAM/PSRAM/NOR read waveforms . . . . . . . . . . . . . . 178
Figure 62. Asynchronous non-multiplexed SRAM/PSRAM/NOR write waveforms . . . . . . . . . . . . . . 180
Figure 63. Asynchronous multiplexed PSRAM/NOR read waveforms. . . . . . . . . . . . . . . . . . . . . . . . 181
Figure 64. Asynchronous multiplexed PSRAM/NOR write waveforms . . . . . . . . . . . . . . . . . . . . . . . 183
Figure 65. Synchronous multiplexed NOR/PSRAM read timings . . . . . . . . . . . . . . . . . . . . . . . . . . . 185
Figure 66. Synchronous multiplexed PSRAM write timings. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 187
Figure 67. Synchronous non-multiplexed NOR/PSRAM read timings. . . . . . . . . . . . . . . . . . . . . . . . 189
Figure 68. Synchronous non-multiplexed PSRAM write timings . . . . . . . . . . . . . . . . . . . . . . . . . . . . 190
Figure 69. NAND controller waveforms for read access . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 192
Figure 70. NAND controller waveforms for write access . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 192
Figure 71. NAND controller waveforms for common memory read access. . . . . . . . . . . . . . . . . . . . 192
Figure 72. NAND controller waveforms for common memory write access. . . . . . . . . . . . . . . . . . . . 193
Figure 73. SDRAM read access waveforms (CL = 1) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 194
Figure 74. SDRAM write access waveforms . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 196
Figure 75. Quad-SPI timing diagram - SDR mode. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 199
Figure 76. Quad-SPI timing diagram - DDR mode . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 199
Figure 77. SDIO high-speed mode . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 200
Figure 78. SD default mode. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 200
Figure 79. LQFP64 – 10 x 10 mm, low-profile quad flat package outline . . . . . . . . . . . . . . . . . . . . . 202
Figure 80. LQFP64 – 10 x 10 mm, low-profile quad flat package recommended footprint . . . . . . . . 203
Figure 81. LQFP64 – 10 x 10 mm, low-profile quad flat package top view example . . . . . . . . . . . . 204
Figure 82. LQFP100, 14 x 14 mm 100-pin low-profile quad flat package outline . . . . . . . . . . . . . . . 205
Figure 83. LQFP100, 14 x 14 mm, 100-pin low-profile quad flat package
recommended footprint. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 206
Figure 84. LQFP100, 14 x 14 mm, 100-pin low-profile quad flat package
top view example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 207
Figure 85. LQFP144, 20 x 20 mm, 144-pin low-profile quad flat package outline. . . . . . . . . . . . . . . 208
Figure 86. LQFP144, 20 x 20 mm, 144-pin low-profile quad flat package
recommended footprint. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 209
Figure 87. LQFP144, 20 x 20mm, 144-pin low-profile quad flat package
top view example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 210
Figure 88. LQFP176, 24 x 24 mm, 176-pin low-profile quad flat package outline. . . . . . . . . . . . . . . 211
Figure 89. LQFP176, 24 x 24 mm, 176-pin low-profile quad flat package
DocID029808 Rev 3 11/229
12

List of figures STM32F722xx STM32F723xx
recommended footprint. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 213
Figure 90. LQFP176, 24 x 24 mm, 176-pin low-profile quad flat package
top view example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 214
Figure 91. UFBGA144 - 144-ball, 7 x 7 mm, 0.50 mm pitch, ultra fine pitch ball grid
array package outline. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 215
Figure 92. UFBGA144 - 144-ball, 7 x 7 mm, 0.50 mm pitch, ultra fine pitch ball grid
array package recommended footprint. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 216
Figure 93. UFBGA144- 144-ball, 7 x 7 mm, 0.50 mm pitch
package top view example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 217
Figure 94. UFBGA176+25, 10 × 10 × 0.65 mm ultra thin fine-pitch ball grid array
package outline. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 218
Figure 95. UFBGA176+25, 10 x 10 mm x 0.65 mm, ultra fine-pitch ball grid array
package recommended footprint . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 219
Figure 96. UFBGA176+25, 10 × 10 × 0.6 mm ultra thin fine-pitch ball grid array
package top view example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 220
Figure 97. WLCSP100 – 100L, 4.166 x 4.628 mm 0.4 mm pitch wafer level chip scale
package outline. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 221
Figure 98. WLCSP100 – 100L, 4.166 x 4.628 mm 0.4 mm pitch wafer level chip scale
package recommended footprint. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 223
Figure 99. WLCSP100 – 100L, 4.166 x 4.628 mm 0.4 mm pitch
top view example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 224
12/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Description
1 Description
The STM32F722xx and STM32F723xx devices are based on the high-performance ARM®
Cortex®-M7 32-bit RISC core operating at up to 216 MHz frequency. The Cortex®-M7 core
features a single floating point unit (SFPU) precision which supports ARM® single-precision
data-processing instructions and data types. It also implements a full set of DSP instructions
and a memory protection unit (MPU) which enhances the application security.
The STM32F722xx and STM32F723xx devices incorporate high-speed embedded
memories with a Flash memory up to 512 Kbytes, 256 Kbytes of SRAM (including
64 Kbytes of data TCM RAM for critical real-time data), 16 Kbytes of instruction TCM RAM
(for critical real-time routines), 4 Kbytes of backup SRAM available in the lowest power
modes, and an extensive range of enhanced I/Os and peripherals connected to two APB
buses, two AHB buses, a 32-bit multi-AHB bus matrix and a multi layer AXI interconnect
supporting internal and external memories access.
All the devices offer three 12-bit ADCs, two DACs, a low-power RTC, thirteen general-
purpose 16-bit timers including two PWM timers for motor control, two general-purpose 32-
bit timers, a true random number generator (RNG). They also feature standard and
advanced communication interfaces.
• Up to three I2Cs
• Five SPIs, three I2Ss in half duplex mode. To achieve the audio class accuracy, the I2S
peripherals can be clocked via a dedicated internal audio PLL or via an external clock
to allow synchronization.
• Four USARTs plus four UARTs
• An USB OTG full-speed and a USB OTG high-speed with full-speed capability (with the
ULPI in the STM32F722xx devices and with the integrated HS PHY in the
STM32F723xx devices)
• One CAN
• Two SAI serial audio interfaces
• Two SDMMC host interfaces
Advanced peripherals include two SDMMC interfaces, a flexible memory control (FMC)
interface, a Quad-SPI Flash memory interface.
The STM32F722xx and STM32F723xx devices operate in the –40 to +105 °C temperature
range from a 1.7 to 3.6 V power supply. Dedicated supply inputs for the USB (OTG_FS and
OTG_HS) and the SDMMC2 (clock, command and 4-bit data) are available on all the
packages except LQFP100 and LQFP64 for a greater power supply choice.
The supply voltage can drop to 1.7 V with the use of an external power supply supervisor. A
comprehensive set of power-saving mode allows the design of low-power applications.
The STM32F722xx and STM32F723xx devices offer devices in 7 packages ranging from 64
pins to 176 pins. The set of included peripherals changes with the device chosen.
DocID029808 Rev 3 13/229
47

| Description |     |     |     |     |     | STM32F722xx STM32F723xx |     |
| ----------- | --- | --- | --- | --- | --- | ----------------------- | --- |
These features make the STM32F722xx and STM32F723xx microcontrollers suitable for a
wide range of applications:
•
Motor drive and application control,
•
Medical equipment,
•
Industrial applications: PLC, inverters, circuit breakers,
•
Printers, and scanners,
•
Alarm systems, video intercom, and HVAC,
•
Home audio appliances,
•
Mobile applications, Internet of Things,
•
Wearable devices: smartwatches.
The following table lists the peripherals available on each part number.
 T         able 2. STM32F722xx and STM32F723xx features and peripheral counts
|                        | Peripherals |                  | STM32F72xRx | STM32F72xVx    |       | STM32F72xZx | STM32F72xIx |
| ---------------------- | ----------- | ---------------- | ----------- | -------------- | ----- | ----------- | ----------- |
| Flash memory in Kbytes |             |                  | 256 512     | 256 512        |       | 256 512     | 256 512     |
|                        |             | System           |             | 256(176+16+64) |       |             |             |
| SRAM in Kbytes         |             | Instruction      |             |                | 16    |             |             |
|                        |             | Backup           |             |                | 4     |             |             |
| FMC memory controller  |             |                  | No          |                |       | Yes(1)      |             |
| Quad-SPI               |             |                  |             |                | Yes   |             |             |
|                        |             | General-purpose  |             |                | 10(2) |             |             |
|                        |             | Advanced-control |             |                | 2     |             |             |
Timers
|                         |     | Basic         |                  |                  | 2   |                  |     |
| ----------------------- | --- | ------------- | ---------------- | ---------------- | --- | ---------------- | --- |
|                         |     | Low-power     | No               |                  |     | 1                |     |
| Random number generator |     |               |                  |                  | Yes |                  |     |
|                         |     | SPI / I2S     | 3/3 (simplex)(3) | 4/3 (simplex)(3) |     | 5/3 (simplex)(3) |     |
|                         |     | I2C           |                  |                  | 3   |                  |     |
|                         |     | USART/UART    | 4/2              |                  |     | 4/4              |     |
|                         |     | USB OTG FS    |                  |                  | Yes |                  |     |
|                         |     | USB OTG HS(4) |                  |                  | Yes |                  |     |
Communication
| interfaces |     | USB OTG PHY HS  |     |     |     |         |     |
| ---------- | --- | --------------- | --- | --- | --- | ------- | --- |
|            |     |                 | No  |     |     | Yes(10) |     |
controller (USBPHYC)
|     |     | CAN    |     |     | 1   |     |     |
| --- | --- | ------ | --- | --- | --- | --- | --- |
|     |     | SAI    |     |     | 2   |     |     |
|     |     | SDMMC1 |     |     | Yes |     |     |
Yes(5)(6)
|     |     | SDMMC2 | No  |                   |                    |     |                    |
| --- | --- | ------ | --- | ----------------- | ------------------ | --- | ------------------ |
|     |     |        |     | 82 in STM32F722xx | 114 in STM32F722xx |     | 140 in STM32F722xx |
GPIOs 50 79 in STM32F723xx 112 in STM32F723xx 138 in STM32F723xx
| 12-bit ADC |     |     |     |     | 3   |     |     |
| ---------- | --- | --- | --- | --- | --- | --- | --- |
|            |     |     |     | 16  |     |     | 24  |
Number of channels
12-bit DAC
Yes
| Number of channels    |     |     |                   |     | 2          |     |     |
| --------------------- | --- | --- | ----------------- | --- | ---------- | --- | --- |
| Maximum CPU frequency |     |     |                   |     | 216 MHz(7) |     |     |
| 14/229                |     |     | DocID029808 Rev 3 |     |            |     |     |

| STM32F722xx STM32F723xx |     |     |     |     | Description |
| ----------------------- | --- | --- | --- | --- | ----------- |
Table 2. STM32F722xx and STM32F723xx features and peripheral counts (continued)
|                   | Peripherals | STM32F72xRx | STM32F72xVx     | STM32F72xZx | STM32F72xIx |
| ----------------- | ----------- | ----------- | --------------- | ----------- | ----------- |
| Operating voltage |             |             | 1.7 to 3.6 V(8) |             |             |
Ambient temperatures: –40 to +85 °C /–40 to +105 °C
Operating temperatures
Junction temperature: –40 to + 125 °C
LQFP100(9)
|         |     |           |              | L Q F P 1 4 4  | U F B G A 1 7 6  |
| ------- | --- | --------- | ------------ | -------------- | ---------------- |
| Package |     | LQFP64(9) | WLCSP100(10) | (10)           |                  |
|         |     |           |              | UF B G A 1 4 4 | L Q F P 1 7 6    |
1. For the LQFP100 package, only FMC Bank1 is available. Bank1 can only support a multiplexed NOR/PSRAM memory
using the NE1 Chip Select.
2. On the STM32F723xx device packages, except the 176-pin ones, the TIM12 is not available, so there are 9 general-
purpose timers.
3. The SPI1, SPI2 and SPI3 interfaces give the flexibility to work in an exclusive way in either the SPI mode or the I2S audio
mode.
4. USB OTG HS with the ULPI on the STM32F722xx devices and with integrated HS PHY on the STM32F723xx devices.
5. The SDMMC2 supports a dedicated power rail for clock, command and data 0..4 lines, feature available starting from 144
pin package.
6. The SDMMC2 is not available on the STM32F723Vx devices.
7. 216 MHz maximum frequency for - 40°C to + 85°C ambient temperature range (200 MHz maximum frequency for - 40°C to
+ 105°C ambient temperature range).
8. V DD /V DDA  minimum value of 1.7 V is obtained when the internal reset is OFF (refer to Section 2.15.2: Internal reset OFF).
9. Available only on the STM32F722xx devices.
10. Available only on the STM32F723xx devices.
|     |     | DocID029808 Rev 3 |     |     | 15/229 |
| --- | --- | ----------------- | --- | --- | ------ |
47

Description STM32F722xx STM32F723xx
1.1 Full compatibility throughout the family
The STM32F722xx devices are fully pin-to-pin, compatible with the STM32F7x5xx,
STM32F7x6xx, STM32F7x7xx devices.
The STM32F722xx devices are fully pin-to-pin, compatible with the STM32F4xxxx devices,
allowing the user to try different peripherals, and reaching higher performances (higher
frequency) for a greater degree of freedom during the development cycle.
Figure 1 and Figure 2 give compatible board designs between the STM32F722xx and
STM32F4xx families.
Figure 1. Compatible board design for LQFP100 package
(cid:51)(cid:38)(cid:22) (cid:20)(cid:27)
(cid:57)(cid:39)(cid:39) (cid:20)(cid:28)
(cid:57)(cid:54)(cid:54)(cid:36) (cid:21)(cid:19)
(cid:57)(cid:53)(cid:40)(cid:41)(cid:14) (cid:21)(cid:20)
(cid:57)(cid:39)(cid:39)(cid:36) (cid:21)(cid:21)
(cid:21)(cid:22)
(cid:21)(cid:23)
(cid:21)(cid:24)
(cid:21)(cid:25)(cid:3)(cid:3)(cid:3)(cid:21)(cid:26)(cid:3)(cid:3)(cid:3)(cid:21)(cid:27)(cid:3)(cid:3)(cid:3)(cid:21)(cid:28)(cid:3)(cid:3)(cid:3)(cid:22)(cid:19)(cid:3)(cid:3)(cid:3)(cid:22)(cid:20)(cid:3)(cid:3)(cid:3)(cid:22)(cid:21)(cid:3)(cid:3)(cid:3)(cid:22)(cid:22)(cid:3)(cid:3)(cid:3)(cid:22)(cid:23)(cid:3)(cid:3)(cid:3)(cid:22)(cid:24)(cid:3)(cid:3)(cid:3)(cid:22)(cid:25)(cid:3)(cid:3)(cid:3)(cid:22)(cid:26)(cid:3)(cid:3)(cid:3)(cid:22)(cid:27)(cid:3)(cid:3)(cid:3)(cid:22)(cid:28)(cid:3)(cid:3)(cid:3)(cid:23)(cid:19)(cid:3)(cid:3)(cid:3)(cid:23)(cid:20)(cid:3)(cid:3)(cid:3)(cid:23)(cid:21)(cid:3)(cid:3)(cid:3)(cid:23)(cid:22)(cid:3)(cid:3)(cid:3)(cid:23)(cid:23)(cid:3)(cid:3)(cid:3)(cid:23)(cid:24)(cid:3)(cid:3)(cid:3)(cid:23)(cid:25)(cid:3)(cid:3)(cid:3)(cid:23)(cid:26)(cid:3)(cid:3)(cid:3)(cid:23)(cid:27)(cid:3)(cid:3)(cid:3)(cid:23)(cid:28)(cid:3)(cid:3)(cid:3)(cid:24)(cid:19)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:20)(cid:19)(cid:19)(cid:20)(cid:57)(cid:21)
16/229 DocID029808 Rev 3
(cid:22)(cid:36)(cid:51) (cid:54)(cid:54)(cid:57) (cid:39)(cid:39)(cid:57) (cid:23)(cid:36)(cid:51) (cid:24)(cid:36)(cid:51) (cid:25)(cid:36)(cid:51) (cid:26)(cid:36)(cid:51) (cid:23)(cid:38)(cid:51) (cid:24)(cid:38)(cid:51) (cid:19)(cid:37)(cid:51) (cid:20)(cid:37)(cid:51) (cid:21)(cid:37)(cid:51) (cid:26)(cid:40)(cid:51) (cid:27)(cid:40)(cid:51) (cid:28)(cid:40)(cid:51) (cid:19)(cid:20)(cid:40)(cid:51) (cid:20)(cid:20)(cid:40)(cid:51) (cid:21)(cid:20)(cid:40)(cid:51) (cid:22)(cid:20)(cid:40)(cid:51) (cid:23)(cid:20)(cid:40)(cid:51) (cid:24)(cid:20)(cid:40)(cid:51) (cid:19)(cid:20)(cid:37)(cid:51) (cid:20)(cid:20)(cid:37)(cid:51) (cid:20)(cid:51)(cid:36)(cid:38)(cid:57) (cid:39)(cid:39)(cid:57)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:21)(cid:26)(cid:91)(cid:91)(cid:3)(cid:18)(cid:3)(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:22)(cid:26)(cid:91)(cid:91)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:21)(cid:28)(cid:91)(cid:91)(cid:3)(cid:18)(cid:3)(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:22)(cid:28)(cid:91)(cid:91)(cid:3)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:20)(cid:24)(cid:91)(cid:91)(cid:3)(cid:18)(cid:3)(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:20)(cid:26)(cid:91)(cid:91)(cid:3)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:19)(cid:24)(cid:91)(cid:91)(cid:3)(cid:18)(cid:3)(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:19)(cid:26)(cid:91)(cid:91)(cid:3)(cid:3)
(cid:20)(cid:27) (cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:91)(cid:91)(cid:91)
(cid:20)(cid:28)
(cid:21)(cid:19)
(cid:21)(cid:20)
(cid:21)(cid:21)
(cid:21)(cid:22)
(cid:21)(cid:23)
(cid:21)(cid:24)
(cid:21)(cid:25)(cid:3)(cid:3)(cid:3)(cid:21)(cid:26)(cid:3)(cid:3)(cid:3)(cid:21)(cid:27)(cid:3)(cid:3)(cid:3)(cid:21)(cid:28)(cid:3)(cid:3)(cid:3)(cid:22)(cid:19)(cid:3)(cid:3)(cid:3)(cid:22)(cid:20)(cid:3)(cid:3)(cid:3)(cid:22)(cid:21)(cid:3)(cid:3)(cid:3)(cid:22)(cid:22)(cid:3)(cid:3)(cid:3)(cid:22)(cid:23)(cid:3)(cid:3)(cid:3)(cid:22)(cid:24)(cid:3)(cid:3)(cid:3)(cid:22)(cid:25)(cid:3)(cid:3)(cid:3)(cid:22)(cid:26)(cid:3)(cid:3)(cid:3)(cid:22)(cid:27)(cid:3)(cid:3)(cid:3)(cid:22)(cid:28)(cid:3)(cid:3)(cid:3)(cid:23)(cid:19)(cid:3)(cid:3)(cid:3)(cid:23)(cid:20)(cid:3)(cid:3)(cid:3)(cid:23)(cid:21)(cid:3)(cid:3)(cid:3)(cid:23)(cid:22)(cid:3)(cid:3)(cid:3)(cid:23)(cid:23)(cid:3)(cid:3)(cid:3)(cid:23)(cid:24)(cid:3)(cid:3)(cid:3)(cid:23)(cid:25)(cid:3)(cid:3)(cid:3)(cid:23)(cid:26)(cid:3)(cid:3)(cid:3)(cid:23)(cid:27)(cid:3)(cid:3)(cid:3)(cid:23)(cid:28)(cid:3)(cid:3)(cid:3)(cid:24)(cid:19)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)
(cid:54)(cid:54)(cid:57) (cid:39)(cid:39)(cid:57) (cid:23)(cid:36)(cid:51) (cid:24)(cid:36)(cid:51) (cid:25)(cid:36)(cid:51) (cid:26)(cid:36)(cid:51) (cid:23)(cid:38)(cid:51) (cid:24)(cid:38)(cid:51) (cid:19)(cid:37)(cid:51) (cid:20)(cid:37)(cid:51) (cid:21)(cid:37)(cid:51) (cid:26)(cid:40)(cid:51) (cid:27)(cid:40)(cid:51) (cid:28)(cid:40)(cid:51) (cid:19)(cid:20)(cid:40)(cid:51) (cid:20)(cid:20)(cid:40)(cid:51) (cid:21)(cid:20)(cid:40)(cid:51) (cid:22)(cid:20)(cid:40)(cid:51) (cid:23)(cid:20)(cid:40)(cid:51) (cid:24)(cid:20)(cid:40)(cid:51) (cid:19)(cid:20)(cid:37)(cid:51) (cid:20)(cid:20)(cid:37)(cid:51) (cid:20)(cid:51)(cid:36)(cid:38)(cid:57) (cid:54)(cid:54)(cid:57) (cid:39)(cid:39)(cid:57)
(cid:51)(cid:36)(cid:19)(cid:16)(cid:58)(cid:46)(cid:56)(cid:51)
(cid:51)(cid:36)(cid:20)
(cid:51)(cid:36)(cid:21)
(cid:51)(cid:38)(cid:22)
(cid:57)(cid:54)(cid:54)(cid:36)
(cid:57)(cid:53)(cid:40)(cid:41)(cid:14)
(cid:57)(cid:39)(cid:39)(cid:36)
(cid:51)(cid:36)(cid:19)(cid:16)(cid:58)(cid:46)(cid:56)(cid:51)
(cid:51)(cid:36)(cid:20) (cid:51)(cid:76)(cid:81)(cid:86)(cid:3)(cid:20)(cid:28)(cid:3)(cid:87)(cid:82)(cid:3)(cid:23)(cid:28)(cid:3)(cid:68)(cid:85)(cid:72)(cid:3)(cid:81)(cid:82)(cid:87)(cid:3)(cid:70)(cid:82)(cid:80)(cid:83)(cid:68)(cid:87)(cid:76)(cid:69)(cid:79)(cid:72)
(cid:51)(cid:36)(cid:21)
(cid:51)(cid:36)(cid:22)

STM32F722xx STM32F723xx Description
Figure 2. Compatible board design for LQFP64 package
| (cid:21)(cid:20)(cid:38)(cid:51) (cid:19)(cid:20)(cid:38)(cid:51)                                  |                                                  |                          | (cid:21)(cid:20)(cid:38)(cid:51)                                                 | (cid:19)(cid:20)(cid:38)(cid:51)                                   |                          |
| -------------------------------------------------------------------------------------------------- | ------------------------------------------------ | ------------------------ | -------------------------------------------------------------------------------- | ------------------------------------------------------------------ | ------------------------ |
| (cid:20)(cid:20)(cid:38)(cid:51) (cid:24)(cid:20)(cid:36)(cid:51) (cid:23)(cid:20)(cid:36)(cid:51) |                                                  |                          | (cid:20)(cid:20)(cid:38)(cid:51)                                                 | (cid:24)(cid:20)(cid:36)(cid:51) (cid:23)(cid:20)(cid:36)(cid:51)  |                          |
| (cid:24)(cid:22)(cid:24)(cid:21)(cid:24)(cid:20)(cid:24)(cid:19)(cid:23)(cid:28)                   |                                                  |                          | (cid:24)(cid:22)(cid:24)(cid:21)(cid:24)(cid:20)(cid:24)(cid:19)(cid:23)(cid:28) |                                                                    |                          |
| (cid:23)(cid:27)                                                                                   | (cid:57)(cid:39)(cid:39)                         | (cid:57)(cid:39)(cid:39) |                                                                                  | (cid:23)(cid:27) (cid:57)(cid:39)(cid:39)                          | (cid:57)(cid:39)(cid:39) |
| (cid:23)(cid:26)                                                                                   | (cid:57)(cid:38)(cid:36)(cid:51)(cid:66)(cid:21) |                          |                                                                                  | (cid:23)(cid:26) (cid:57)(cid:54)(cid:54)                          |                          |
| (cid:23)(cid:25)                                                                                   | (cid:51)(cid:36)(cid:20)(cid:22)                 |                          |                                                                                  | (cid:23)(cid:25) (cid:51)(cid:36)(cid:20)(cid:22)                  |                          |
| (cid:23)(cid:24)                                                                                   | (cid:51)(cid:36)(cid:20)(cid:21)                 |                          |                                                                                  | (cid:23)(cid:24) (cid:51)(cid:36)(cid:20)(cid:21)                  |                          |
| (cid:23)(cid:23)                                                                                   | (cid:51)(cid:36)(cid:20)(cid:20)                 |                          |                                                                                  | (cid:23)(cid:23) (cid:51)(cid:36)(cid:20)(cid:20)                  |                          |
| (cid:23)(cid:22)                                                                                   | (cid:51)(cid:36)(cid:20)(cid:19)                 |                          |                                                                                  | (cid:23)(cid:22) (cid:51)(cid:36)(cid:20)(cid:19)                  |                          |
| (cid:23)(cid:21)                                                                                   | (cid:51)(cid:36)(cid:28)                         |                          |                                                                                  | (cid:23)(cid:21) (cid:51)(cid:36)(cid:28) (cid:57)(cid:54)(cid:54) |                          |
|                                                                                                    | (cid:57)(cid:54)(cid:54)                         |                          |                                                                                  | (cid:23)(cid:20) (cid:51)(cid:36)(cid:27)                          |                          |
| (cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:19)(cid:24)(cid:18) (cid:23)(cid:20)  | (cid:51)(cid:36)(cid:27)                         |                          |                                                                                  |                                                                    |                          |
| (cid:23)(cid:19)                                                                                   | (cid:51)(cid:38)(cid:28)                         |                          | (cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:91)(cid:20)         | (cid:23)(cid:19) (cid:51)(cid:38)(cid:28)                          |                          |
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:20)(cid:24)(cid:3)(cid:79)(cid:76)(cid:81)(cid:72)
| (cid:22)(cid:28) | (cid:51)(cid:38)(cid:27)         |                                                                                                                                                                                                                             |     | (cid:22)(cid:28) (cid:51)(cid:38)(cid:27)         |     |
| ---------------- | -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- | ------------------------------------------------- | --- |
| (cid:22)(cid:27) | (cid:51)(cid:38)(cid:26)         |                                                                                                                                                                                                                             |     | (cid:22)(cid:27) (cid:51)(cid:38)(cid:26)         |     |
| (cid:22)(cid:26) | (cid:51)(cid:38)(cid:25)         |                                                                                                                                                                                                                             |     | (cid:22)(cid:26) (cid:51)(cid:38)(cid:25)         |     |
|                  |                                  | (cid:51)(cid:37)(cid:20)(cid:20)(cid:3)(cid:81)(cid:82)(cid:87)(cid:3)(cid:68)(cid:89)(cid:68)(cid:76)(cid:79)(cid:68)(cid:69)(cid:79)(cid:72)(cid:3)(cid:68)(cid:81)(cid:92)(cid:80)(cid:82)(cid:85)(cid:72)(cid:3)(cid:3) |     | (cid:22)(cid:25) (cid:51)(cid:37)(cid:20)(cid:24) |     |
| (cid:22)(cid:25) | (cid:51)(cid:37)(cid:20)(cid:24) |                                                                                                                                                                                                                             |     |                                                   |     |
| (cid:22)(cid:24) | (cid:51)(cid:37)(cid:20)(cid:23) | (cid:53)(cid:72)(cid:83)(cid:79)(cid:68)(cid:70)(cid:72)(cid:71)(cid:3)(cid:69)(cid:92)(cid:3)(cid:57)(cid:38)(cid:36)(cid:51)(cid:66)(cid:20)                                                                              |     | (cid:22)(cid:24) (cid:51)(cid:37)(cid:20)(cid:23) |     |
| (cid:22)(cid:23) | (cid:51)(cid:37)(cid:20)(cid:22) |                                                                                                                                                                                                                             |     | (cid:22)(cid:23) (cid:51)(cid:37)(cid:20)(cid:22) |     |
(cid:22)(cid:22) (cid:51)(cid:37)(cid:20)(cid:21)
| (cid:22)(cid:22)                                                                                                                                                     | (cid:51)(cid:37)(cid:20)(cid:21) |     |                                                                                                            |                                                   |     |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------- | --- | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------- | --- |
| (cid:21)(cid:27)(cid:21)(cid:28)(cid:22)(cid:19)(cid:22)(cid:20)(cid:22)(cid:21)                                                                                     |                                  |     | (cid:21)(cid:27)(cid:21)(cid:28)(cid:22)(cid:19)(cid:22)(cid:20)(cid:22)(cid:21)                           |                                                   |     |
| (cid:21)(cid:37)(cid:51) (cid:19)(cid:20)(cid:37)(cid:51) (cid:20)(cid:20)(cid:37)(cid:51) (cid:20)(cid:66)(cid:51)(cid:36)(cid:38)(cid:57) (cid:39)(cid:39)(cid:57) |                                  |     | (cid:21)(cid:37)(cid:51) (cid:19)(cid:20)(cid:37)(cid:51) (cid:20)(cid:66)(cid:51)(cid:36)(cid:38)(cid:57) | (cid:54)(cid:54)(cid:57) (cid:39)(cid:39)(cid:57) |     |
(cid:57)(cid:3)(cid:38)(cid:3)(cid:3)(cid:36)(cid:3)(cid:3)(cid:3)(cid:51)(cid:3)(cid:3)(cid:3)(cid:76)(cid:81)(cid:70)(cid:85)(cid:72)(cid:68)(cid:86)(cid:72)(cid:71)(cid:3)(cid:87)(cid:82)(cid:3)(cid:23)(cid:17)(cid:26)(cid:3)(cid:151)(cid:73)
(cid:40)(cid:54)(cid:53)(cid:3)(cid:20)(cid:3)(cid:82)(cid:75)(cid:80)(cid:3)(cid:82)(cid:85)(cid:3)(cid:69)(cid:72)(cid:79)(cid:82)(cid:90)(cid:3)(cid:20)(cid:3)(cid:82)(cid:75)(cid:80)(cid:3)(cid:3)
(cid:57)(cid:54)(cid:54) (cid:57)(cid:39)(cid:39)
(cid:57)(cid:54)(cid:54) (cid:57)(cid:39)(cid:39)
(cid:21)(cid:20)(cid:38)(cid:51) (cid:20)(cid:20)(cid:38)(cid:51) (cid:19)(cid:20)(cid:38)(cid:51)
|     | (cid:24)(cid:37)(cid:51) (cid:23)(cid:37)(cid:51) | (cid:22)(cid:37)(cid:51) (cid:21)(cid:39)(cid:51) (cid:24)(cid:20)(cid:36) | (cid:23)(cid:20)(cid:36) |     |     |
| --- | ------------------------------------------------- | -------------------------------------------------------------------------- | ------------------------ | --- | --- |
|     |                                                   | (cid:51)                                                                   | (cid:51)                 |     |     |
(cid:24)(cid:26)(cid:24)(cid:25)(cid:24)(cid:24)(cid:24)(cid:23)(cid:24)(cid:22)(cid:24)(cid:21)(cid:24)(cid:20)(cid:24)(cid:19)(cid:23)(cid:28)
|     |     |     | (cid:23)(cid:27) (cid:57)(cid:39)(cid:39) (cid:57)(cid:39)(cid:39) |     |     |
| --- | --- | --- | ------------------------------------------------------------------ | --- | --- |
(cid:23)(cid:26) (cid:57)(cid:54)(cid:54)
(cid:23)(cid:25) (cid:51)(cid:36)(cid:20)(cid:22)
(cid:23)(cid:24) (cid:51)(cid:36)(cid:20)(cid:21)
(cid:51)(cid:36)(cid:20)(cid:20)
(cid:23)(cid:23)
(cid:23)(cid:22) (cid:51)(cid:36)(cid:20)(cid:19)
(cid:23)(cid:21) (cid:51)(cid:36)(cid:28) (cid:57)(cid:54)(cid:54)
|     | (cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:21)(cid:91)(cid:91) |     | (cid:23)(cid:20) (cid:51)(cid:36)(cid:27) |     |     |
| --- | ---------------------------------------------------------------------------------------- | --- | ----------------------------------------- | --- | --- |
(cid:23)(cid:19) (cid:51)(cid:38)(cid:28)
(cid:22)(cid:28) (cid:51)(cid:38)(cid:27)
(cid:22)(cid:27) (cid:51)(cid:38)(cid:26)
(cid:22)(cid:26) (cid:51)(cid:38)(cid:25)
| (cid:51)(cid:38)(cid:24)(cid:3)(cid:81)(cid:82)(cid:87)(cid:3)(cid:68)(cid:89)(cid:68)(cid:76)(cid:79)(cid:68)(cid:69)(cid:79)(cid:72)(cid:3)(cid:68)(cid:81)(cid:92)(cid:80)(cid:82)(cid:85)(cid:72)(cid:3)(cid:3) |     |     | (cid:22)(cid:25) (cid:51)(cid:37)(cid:20)(cid:24) |     |     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- | ------------------------------------------------- | --- | --- |
| (cid:53)(cid:72)(cid:83)(cid:79)(cid:68)(cid:70)(cid:72)(cid:71)(cid:3)(cid:69)(cid:92)(cid:3)(cid:57)(cid:38)(cid:36)(cid:51)(cid:66)(cid:20)                                                                      |     |     | (cid:22)(cid:24) (cid:51)(cid:37)(cid:20)(cid:23) |     |     |
(cid:22)(cid:23) (cid:51)(cid:37)(cid:20)(cid:22)
(cid:22)(cid:22) (cid:51)(cid:37)(cid:20)(cid:21)
| (cid:20)(cid:26)(cid:20)(cid:27)(cid:20)(cid:28)(cid:21)(cid:19)(cid:21)(cid:20)(cid:21)(cid:21)(cid:21)(cid:22) | (cid:21)(cid:23)(cid:21)(cid:24)(cid:21)(cid:25)(cid:21)(cid:26)(cid:21)(cid:27)(cid:21)(cid:28)                             | (cid:22)(cid:19)(cid:22)(cid:20)(cid:22)(cid:21)                                                                                             |                          |     |     |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------ | --- | --- |
| (cid:54)(cid:54)(cid:57)                                                                                         |                                                                                                                              | (cid:20)(cid:66)(cid:51)(cid:36)(cid:38)(cid:57)                                                                                             |                          |     |     |
| (cid:22)(cid:36)(cid:51) (cid:39)(cid:39)(cid:57) (cid:23)(cid:36)(cid:51)                                       | (cid:24)(cid:36)(cid:51) (cid:25)(cid:36)(cid:51) (cid:26)(cid:36)(cid:51) (cid:23)(cid:38)(cid:51) (cid:19)(cid:37)(cid:51) | (cid:20)(cid:37)(cid:51) (cid:21)(cid:37)(cid:51) (cid:19)(cid:20)(cid:37)(cid:51) (cid:20)(cid:20)(cid:37)(cid:51) (cid:54)(cid:54)(cid:57) | (cid:39)(cid:39)(cid:57) |     |     |
(cid:49)(cid:82)(cid:87)(cid:3)(cid:70)(cid:82)(cid:80)(cid:83)(cid:68)(cid:87)(cid:76)(cid:69)(cid:79)(cid:72)(cid:3)(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:21)(cid:91)(cid:91)(cid:3)(cid:83)(cid:76)(cid:81)(cid:86)(cid:3)(cid:90)(cid:76)(cid:87)(cid:75)(cid:3)(cid:72)(cid:76)(cid:87)(cid:75)(cid:72)(cid:85)(cid:3)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:91)(cid:20)(cid:3)(cid:82)(cid:85)(cid:3)(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:23)(cid:19)(cid:24)(cid:18)(cid:41)(cid:23)(cid:20)(cid:24)(cid:3)(cid:82)(cid:85)(cid:3)(cid:69)(cid:82)(cid:87)(cid:75)
(cid:57)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)(cid:3)(cid:76)(cid:81)(cid:70)(cid:85)(cid:72)(cid:68)(cid:86)(cid:72)(cid:71)(cid:3)(cid:87)(cid:82)(cid:3)(cid:23)(cid:17)(cid:26)(cid:3)(cid:151)(cid:73)
(cid:38)(cid:36)(cid:51)
(cid:40)(cid:54)(cid:53)(cid:3)(cid:69)(cid:72)(cid:87)(cid:90)(cid:72)(cid:72)(cid:81)(cid:3)(cid:19)(cid:17)(cid:20)(cid:3)(cid:82)(cid:75)(cid:80)(cid:3)(cid:68)(cid:81)(cid:71)(cid:3)(cid:19)(cid:17)(cid:21)(cid:3)(cid:82)(cid:75)(cid:80)(cid:3)(cid:3)
|     |     | (cid:57)(cid:54)(cid:54) | (cid:57)(cid:39)(cid:39) |     |     |
| --- | --- | ------------------------ | ------------------------ | --- | --- |
(cid:48)(cid:54)(cid:89)(cid:23)(cid:20)(cid:19)(cid:19)(cid:26)(cid:57)(cid:22)
The STM32F722xx LQFP144, UFBGA176 and LQFP176 packages are fully pin to pin
compatible with the STM32F4xx devices.
|     | DocID029808 Rev 3 |     |     |     | 17/229 |
| --- | ----------------- | --- | --- | --- | ------ |
47

Description STM32F722xx STM32F723xx
1.2 STM32F723xx versus STM32F722xx LQFP144/LQFP176
packages:
Figure 3. Compatible board design for LQFP144 package
(cid:27)(cid:19) (cid:51)(cid:39)(cid:20)(cid:20)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:21)(cid:91)(cid:91) (cid:26)(cid:28) (cid:51)(cid:39)(cid:20)(cid:19)
(cid:26)(cid:27) (cid:51)(cid:39)(cid:28)
(cid:26)(cid:26) (cid:51)(cid:39)(cid:27)
(cid:26)(cid:25) (cid:51)(cid:37)(cid:20)(cid:24)
(cid:26)(cid:24) (cid:51)(cid:37)(cid:20)(cid:23)
(cid:26)(cid:23) (cid:51)(cid:37)(cid:20)(cid:22)
(cid:26)(cid:22) (cid:51)(cid:37)(cid:20)(cid:21)
(cid:26)(cid:21)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:20)(cid:19)(cid:28)(cid:27)(cid:57)(cid:20)
Figure 4. Compatible board design for LQFP176 package
Figure 5 shows the general block diagram of the device family.
18/229 DocID029808 Rev 3
(cid:39)(cid:39)(cid:57)
(cid:28)(cid:22) (cid:51)(cid:42)(cid:27)
(cid:28)(cid:21) (cid:51)(cid:42)(cid:26)
(cid:28)(cid:20) (cid:51)(cid:42)(cid:25)
(cid:28)(cid:19) (cid:51)(cid:42)(cid:24)
(cid:27)(cid:28) (cid:51)(cid:42)(cid:23)
(cid:27)(cid:27) (cid:51)(cid:42)(cid:22)
(cid:27)(cid:26) (cid:51)(cid:42)(cid:21)
(cid:27)(cid:25) (cid:51)(cid:39)(cid:20)(cid:24)
(cid:27)(cid:24) (cid:51)(cid:39)(cid:20)(cid:23)
(cid:27)(cid:23) (cid:57)(cid:39)(cid:39)
(cid:27)(cid:22) (cid:57)(cid:54)(cid:54)
(cid:27)(cid:21) (cid:51)(cid:39)(cid:20)(cid:22)
(cid:27)(cid:20) (cid:51)(cid:39)(cid:20)(cid:21) (cid:27)(cid:19) (cid:51)(cid:39)(cid:28)
(cid:26)(cid:28) (cid:51)(cid:39)(cid:27)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:22)(cid:91)(cid:91) (cid:26)(cid:27) (cid:51)(cid:37)(cid:20)(cid:24)
(cid:26)(cid:26) (cid:51)(cid:37)(cid:20)(cid:23)
(cid:26)(cid:25) (cid:57)(cid:39)(cid:39)(cid:20)(cid:21)(cid:50)(cid:55)(cid:42)(cid:43)(cid:54)
(cid:26)(cid:24) (cid:50)(cid:55)(cid:42)(cid:66)(cid:43)(cid:54)(cid:66)(cid:53)(cid:40)(cid:59)(cid:55)
(cid:26)(cid:23) (cid:51)(cid:37)(cid:20)(cid:22)
(cid:26)(cid:22) (cid:51)(cid:37)(cid:20)(cid:21)
(cid:26)(cid:21)
(cid:51)(cid:42)(cid:25)(cid:15)(cid:3)(cid:51)(cid:42)(cid:26)(cid:3)(cid:85)(cid:72)(cid:80)(cid:82)(cid:89)(cid:72)(cid:71)(cid:3)(cid:82)(cid:81)(cid:3)(cid:87)(cid:75)(cid:72)(cid:3)(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:22)(cid:91)(cid:91)
(cid:39)(cid:39)(cid:57)
(cid:28)(cid:22) (cid:51)(cid:42)(cid:27)
(cid:28)(cid:21) (cid:51)(cid:42)(cid:24)
(cid:28)(cid:20) (cid:51)(cid:42)(cid:23)
(cid:28)(cid:19) (cid:51)(cid:42)(cid:22)
(cid:27)(cid:28) (cid:51)(cid:42)(cid:21)
(cid:27)(cid:27) (cid:51)(cid:39)(cid:20)(cid:24)
(cid:27)(cid:26) (cid:51)(cid:39)(cid:20)(cid:23)
(cid:27)(cid:25) (cid:57)(cid:39)(cid:39)
(cid:27)(cid:24) (cid:57)(cid:54)(cid:54)
(cid:27)(cid:23) (cid:51)(cid:39)(cid:20)(cid:22)
(cid:27)(cid:22) (cid:51)(cid:39)(cid:20)(cid:21)
(cid:27)(cid:21) (cid:51)(cid:39)(cid:20)(cid:20)
(cid:27)(cid:20) (cid:51)(cid:39)(cid:20)(cid:19)
(cid:49)(cid:82)(cid:87)(cid:3)(cid:70)(cid:82)(cid:80)(cid:83)(cid:68)(cid:87)(cid:76)(cid:69)(cid:79)(cid:72)(cid:3)(cid:83)(cid:76)(cid:81)(cid:86)
(cid:28)(cid:25) (cid:51)(cid:39)(cid:27)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:21)(cid:91)(cid:91) (cid:28)(cid:24) (cid:51)(cid:37)(cid:20)(cid:24)
(cid:28)(cid:23) (cid:51)(cid:37)(cid:20)(cid:23)
(cid:28)(cid:22) (cid:51)(cid:37)(cid:20)(cid:22)
(cid:28)(cid:21) (cid:51)(cid:37)(cid:20)(cid:21)
(cid:28)(cid:20) (cid:57)(cid:39)(cid:39)
(cid:28)(cid:19) (cid:57)(cid:54)(cid:54)
(cid:27)(cid:28) (cid:51)(cid:43)(cid:20)(cid:21)
(cid:27)(cid:27)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:20)(cid:19)(cid:28)(cid:28)(cid:57)(cid:20)
(cid:20)(cid:20)(cid:43)(cid:51)
(cid:20)(cid:19)(cid:28) (cid:51)(cid:42)(cid:24)
(cid:20)(cid:19)(cid:27) (cid:51)(cid:42)(cid:23)
(cid:20)(cid:19)(cid:26) (cid:51)(cid:42)(cid:22)
(cid:20)(cid:19)(cid:25) (cid:51)(cid:42)(cid:21)
(cid:20)(cid:19)(cid:24) (cid:51)(cid:39)(cid:20)(cid:24)
(cid:20)(cid:19)(cid:23) (cid:51)(cid:39)(cid:20)(cid:23)
(cid:20)(cid:19)(cid:22) (cid:57)(cid:39)(cid:39)
(cid:20)(cid:19)(cid:21) (cid:57)(cid:54)(cid:54)
(cid:20)(cid:19)(cid:20) (cid:51)(cid:39)(cid:20)(cid:22)
(cid:20)(cid:19)(cid:19) (cid:51)(cid:39)(cid:20)(cid:21)
(cid:28)(cid:28) (cid:51)(cid:39)(cid:20)(cid:20)
(cid:28)(cid:27) (cid:51)(cid:39)(cid:20)(cid:19)
(cid:28)(cid:26) (cid:51)(cid:39)(cid:28)
(cid:51)(cid:37)(cid:20)(cid:23)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:22)(cid:91)(cid:91) (cid:57)(cid:39)(cid:39)(cid:20)(cid:21)(cid:50)(cid:55)(cid:42)(cid:43)(cid:54)
(cid:50)(cid:55)(cid:42)(cid:66)(cid:43)(cid:54)(cid:66)(cid:53)(cid:40)(cid:59)(cid:55)
(cid:51)(cid:37)(cid:20)(cid:22)
(cid:51)(cid:37)(cid:20)(cid:21)
(cid:57)(cid:39)(cid:39)
(cid:57)(cid:54)(cid:54)
(cid:51)(cid:43)(cid:20)(cid:21)
(cid:27)(cid:27)
(cid:51)(cid:42)(cid:25)(cid:15)(cid:3)(cid:51)(cid:42)(cid:26)(cid:3)(cid:85)(cid:72)(cid:80)(cid:82)(cid:89)(cid:72)(cid:71)(cid:3)(cid:82)(cid:81)(cid:3)(cid:87)(cid:75)(cid:72)(cid:3)(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:22)(cid:91)(cid:91) (cid:20)(cid:20)(cid:43)(cid:51)
(cid:20)(cid:20)(cid:21) (cid:51)(cid:42)(cid:27) (cid:20)(cid:20)(cid:21) (cid:51)(cid:42)(cid:27)
(cid:20)(cid:20)(cid:20) (cid:51)(cid:42)(cid:26) (cid:20)(cid:20)(cid:20) (cid:51)(cid:42)(cid:24)
(cid:20)(cid:20)(cid:19) (cid:51)(cid:42)(cid:25) (cid:20)(cid:20)(cid:19) (cid:51)(cid:42)(cid:23)
(cid:20)(cid:19)(cid:28) (cid:51)(cid:42)(cid:22)
(cid:20)(cid:19)(cid:27) (cid:51)(cid:42)(cid:21)
(cid:20)(cid:19)(cid:26) (cid:51)(cid:39)(cid:20)(cid:24)
(cid:20)(cid:19)(cid:25) (cid:51)(cid:39)(cid:20)(cid:23)
(cid:20)(cid:19)(cid:24) (cid:57)(cid:39)(cid:39)
(cid:20)(cid:19)(cid:23) (cid:57)(cid:54)(cid:54)
(cid:20)(cid:19)(cid:22) (cid:51)(cid:39)(cid:20)(cid:22)
(cid:20)(cid:19)(cid:21) (cid:51)(cid:39)(cid:20)(cid:21)
(cid:20)(cid:19)(cid:20) (cid:51)(cid:39)(cid:20)(cid:20)
(cid:20)(cid:19)(cid:19) (cid:51)(cid:39)(cid:20)(cid:19)
(cid:28)(cid:28) (cid:51)(cid:39)(cid:28)
(cid:28)(cid:27) (cid:51)(cid:39)(cid:27)
(cid:28)(cid:26) (cid:51)(cid:37)(cid:20)(cid:24)
(cid:28)(cid:25)
(cid:28)(cid:24)
(cid:28)(cid:23)
(cid:28)(cid:22)
(cid:28)(cid:21)
(cid:28)(cid:20)
(cid:28)(cid:19)
(cid:27)(cid:28)
(cid:49)(cid:82)(cid:87)(cid:3)(cid:70)(cid:82)(cid:80)(cid:83)(cid:68)(cid:87)(cid:76)(cid:69)(cid:79)(cid:72)(cid:3)(cid:83)(cid:76)(cid:81)(cid:86)

| STM32F722xx STM32F723xx |     |     |     |     |     |     |     |     |     |     | Description |
| ----------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ----------- |
Figure 5. STM32F722xx and STM32F723xx block diagram
|     |     | (cid:45)(cid:55)(cid:53)(cid:54)(cid:55)(cid:15)(cid:3)(cid:45)(cid:55)(cid:39)(cid:44)(cid:15)                         | (cid:45)(cid:55)(cid:36)(cid:42)(cid:3)(cid:9)(cid:3)(cid:54)(cid:58)    | (cid:48)(cid:51)(cid:56)(cid:3)(cid:41)(cid:51)(cid:56) |                                                          |     |                                                                                                        |     |     |     |     |
| --- | --- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------- | -------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------ | --- | --- | --- | --- |
|     |     | (cid:45) (cid:55) (cid:38) (cid:46) (cid:18)(cid:54) (cid:58) (cid:38) (cid:47) (cid:46)                                | (cid:40)(cid:55)(cid:48)                                                 | (cid:49)(cid:57)(cid:44)(cid:38)                        |                                                          |     | (cid:39)(cid:55)(cid:38)(cid:48)(cid:3)(cid:53)(cid:36)(cid:48)(cid:3)(cid:25)(cid:23)(cid:46)(cid:37) |     |     |     |     |
|     |     | (cid:45)(cid:55)(cid:39)(cid:50) (cid:18) (cid:54) (cid:58) (cid:39) (cid:15)(cid:3) (cid:45)(cid:55) (cid:39) (cid:50) |                                                                          | (cid:39)(cid:55)(cid:38)(cid:48)                        |                                                          |     |                                                                                                        |     |     |     |     |
|     |     | (cid:55)(cid:53)(cid:36)(cid:38)(cid:40)(cid:38)(cid:46)                                                                | (cid:36)(cid:53)(cid:48)(cid:3)(cid:3)(cid:38)(cid:51)(cid:56)           | (cid:44)(cid:38)(cid:55)(cid:48)                        |                                                          |     | (cid:44)(cid:55)(cid:38)(cid:48)(cid:3)(cid:53)(cid:36)(cid:48)(cid:3)(cid:20)(cid:25)(cid:46)(cid:37) |     |     |     |     |
|     |     | (cid:55)(cid:53)(cid:36)(cid:38)(cid:40)(cid:39)(cid:62)(cid:22)(cid:29)(cid:19)(cid:64)                                | (cid:38)(cid:82)(cid:85)(cid:87)(cid:72)(cid:91)(cid:16)(cid:48)(cid:26) |                                                         | (cid:44)(cid:59)(cid:36)(cid:21)(cid:37)(cid:43)(cid:36) |     |                                                                                                        |     |     |     |     |
(cid:36)(cid:59)(cid:44)(cid:48)
|     |     |     |                                                  | (cid:44)(cid:16)(cid:38)(cid:68)(cid:70)(cid:75)(cid:72)                           |     |                                                                                                                                                                | (cid:36)(cid:38)(cid:38)(cid:40)(cid:47)(cid:18)                                        |                                                                                         |     |                                                   |                                                                                                                                                                                       |
| --- | --- | --- | ------------------------------------------------ | ---------------------------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --- | ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|     |     |     |                                                  | (cid:3)(cid:27)(cid:46)(cid:37)                                                    |     |                                                                                                                                                                |                                                                                         | (cid:41)(cid:47)(cid:36)(cid:54)(cid:43)(cid:3)(cid:24)(cid:20)(cid:21)(cid:46)(cid:37) |     |                                                   |                                                                                                                                                                                       |
|     |     |     |                                                  | (cid:39)(cid:16)(cid:38)(cid:68)(cid:70)(cid:75)(cid:72)                           |     |                                                                                                                                                                | (cid:38)(cid:36)(cid:38)(cid:43)(cid:40)                                                |                                                                                         |     | (cid:53)(cid:49)(cid:42)                          |                                                                                                                                                                                       |
|     |     |     | (cid:21)(cid:20)(cid:25)(cid:48)(cid:43)(cid:93) | (cid:36)(cid:43)(cid:37)(cid:51)                                                   |     |                                                                                                                                                                |                                                                                         |                                                                                         |     |                                                   |                                                                                                                                                                                       |
|     |     |     |                                                  | (cid:3)(cid:27)(cid:46)(cid:37) (cid:36)(cid:43)(cid:37)(cid:54)                   |     | (cid:48)(cid:26)(cid:54)(cid:27)(cid:3)(cid:91)(cid:76)(cid:85)(cid:87)(cid:68)(cid:80)(cid:16)(cid:86)(cid:88)(cid:69)(cid:3)(cid:37)(cid:43)(cid:36)         |                                                                                         |                                                                                         |     |                                                   |                                                                                                                                                                                       |
|     |     |     |                                                  |                                                                                    |     |                                                                                                                                                                | (cid:54)(cid:53)(cid:36)(cid:48)(cid:20)(cid:3)(cid:20)(cid:26)(cid:25)(cid:46)(cid:37) |                                                                                         |     | (cid:50)(cid:41)(cid:44)(cid:41)                  | (cid:39) (cid:51)                                                                                                                                                                     |
|     |     |     |                                                  |                                                                                    |     |                                                                                                                                                                |                                                                                         |                                                                                         |     | (cid:56)(cid:54)(cid:37) (cid:60)(cid:43)(cid:51) | (cid:39) (cid:48)                                                                                                                                                                     |
|     |     |     |                                                  |                                                                                    |     | (cid:48)(cid:27)(cid:54)(cid:20)(cid:20)(cid:3)(cid:59)(cid:44)(cid:53)(cid:55)(cid:36)(cid:48)(cid:16)(cid:54)(cid:56)(cid:37)(cid:3)(cid:37)(cid:43)(cid:36) |                                                                                         |                                                                                         |     |                                                   | (cid:54)(cid:38)(cid:47)(cid:15)(cid:3)(cid:54)(cid:39)(cid:36)(cid:15)(cid:3)(cid:44)(cid:49)(cid:55)(cid:15)(cid:3)(cid:44)(cid:39)(cid:15)(cid:3)(cid:57)(cid:37)(cid:56)(cid:54)  |
|     |     |     |                                                  |                                                                                    |     |                                                                                                                                                                | (cid:54)(cid:53)(cid:36)(cid:48)(cid:21)(cid:3)(cid:20)(cid:25)(cid:46)(cid:37)         |                                                                                         |     | (cid:50)(cid:55)(cid:42)(cid:3)(cid:41)(cid:54)   |                                                                                                                                                                                       |
|     |     |     |                                                  | (cid:11)(cid:21)(cid:12) (cid:47)(cid:39)(cid:50) (cid:51)(cid:47)(cid:47)(cid:20) |     |                                                                                                                                                                |                                                                                         |                                                                                         |     |                                                   | (cid:38)(cid:47)(cid:46)(cid:15)(cid:3)(cid:49)(cid:40)(cid:3)(cid:62)(cid:22)(cid:29)(cid:19)(cid:64)(cid:15)(cid:3)(cid:36)(cid:62)(cid:21)(cid:22)(cid:29)(cid:19)(cid:64)(cid:15) |
(cid:56)(cid:54)(cid:37)(cid:3)(cid:43)(cid:54) (cid:36)(cid:43)(cid:37)(cid:21)(cid:3)(cid:21)(cid:20)(cid:25)(cid:3)(cid:48)(cid:43)(cid:93) (cid:39)(cid:62)(cid:22)(cid:20)(cid:29)(cid:19)(cid:64)(cid:15)(cid:3)(cid:49)(cid:50)(cid:40)(cid:49)(cid:15)(cid:3)(cid:49)(cid:58)(cid:40)(cid:49)(cid:15)
(cid:3)(cid:3)(cid:3)(cid:51)(cid:43)(cid:60) (cid:40)(cid:59)(cid:55)(cid:3)(cid:48)(cid:40)(cid:48)(cid:3)(cid:38)(cid:55)(cid:47)(cid:3)(cid:11)(cid:41)(cid:48)(cid:38)(cid:12) (cid:49)(cid:37)(cid:47)(cid:62)(cid:22)(cid:29)(cid:19)(cid:64)(cid:15)(cid:3)(cid:54)(cid:39)(cid:38)(cid:47)(cid:46)(cid:40)(cid:62)(cid:20)(cid:29)(cid:19)(cid:64)(cid:3)(cid:3)
|     |     |     |     | (cid:37)(cid:42)(cid:53) (cid:51)(cid:47)(cid:47)(cid:21) |     |     | (cid:54)(cid:53)(cid:36)(cid:48)(cid:15)(cid:3)(cid:54)(cid:39)(cid:53)(cid:36)(cid:48)(cid:15)(cid:3)(cid:49)(cid:50)(cid:53)(cid:16)(cid:41)(cid:79)(cid:68)(cid:86)(cid:75)(cid:15)(cid:3) |     |     |     | (cid:54)(cid:39)(cid:49)(cid:40)(cid:62)(cid:20)(cid:29)(cid:19)(cid:64)(cid:15)(cid:3)(cid:54)(cid:39)(cid:49)(cid:58)(cid:40)(cid:15)(cid:3)(cid:49)(cid:47) |
| --- | --- | --- | --- | --------------------------------------------------------- | --- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
(cid:49)(cid:53)(cid:36)(cid:54)(cid:15)(cid:3)(cid:49)(cid:38)(cid:36)(cid:54)(cid:15)(cid:3)(cid:49)(cid:36)(cid:39)(cid:57)
|     |     |     |     |     |     |     | (cid:49)(cid:36)(cid:49)(cid:39)(cid:16)(cid:41)(cid:79)(cid:68)(cid:86)(cid:75)(cid:15)(cid:3)(cid:54)(cid:39)(cid:53)(cid:36)(cid:48) |     |     |     | (cid:49)(cid:58)(cid:36)(cid:44)(cid:55)(cid:15)(cid:3)(cid:44)(cid:49)(cid:55)(cid:49) |
| --- | --- | --- | --- | --- | --- | --- | --------------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --------------------------------------------------------------------------------------- |
(cid:60)(cid:43)(cid:51)(cid:3)(cid:54)(cid:41) (cid:56)(cid:54)(cid:37)(cid:3)(cid:50)(cid:55)(cid:42)(cid:3)(cid:43)(cid:54)
(cid:39)(cid:51)(cid:15)(cid:3)(cid:39)(cid:48) (cid:39)(cid:48)(cid:36)(cid:18) (cid:52)(cid:88)(cid:68)(cid:71)(cid:16)(cid:54)(cid:51)(cid:44) (cid:38)(cid:47)(cid:46)(cid:15)(cid:3)(cid:38)(cid:54)(cid:15)(cid:39)(cid:62)(cid:26)(cid:29)(cid:19)(cid:64)
(cid:56)(cid:47)(cid:51)(cid:44)(cid:29)(cid:38)(cid:46)(cid:15)(cid:3)(cid:39)(cid:62)(cid:26)(cid:29)(cid:19)(cid:64)(cid:15)(cid:3)(cid:39)(cid:44)(cid:53)(cid:15)(cid:3)(cid:54)(cid:55)(cid:51)(cid:15)(cid:3)(cid:49)(cid:59)(cid:55) (cid:41)(cid:44)(cid:41)(cid:50) (cid:35)(cid:57)(cid:39)(cid:39)(cid:36)
(cid:54)(cid:38)(cid:47)(cid:18)(cid:54)(cid:39)(cid:36)(cid:15)(cid:3)(cid:44)(cid:49)(cid:55)(cid:15)(cid:3)(cid:44)(cid:39)(cid:15)(cid:3)(cid:57)(cid:37)(cid:56)(cid:54) (cid:51)(cid:47)(cid:47) (cid:47)(cid:39)(cid:50) (cid:36)(cid:43)(cid:37)(cid:20)(cid:3)(cid:21)(cid:20)(cid:25)(cid:3)(cid:48)(cid:43)(cid:93) (cid:51)(cid:50)(cid:53)(cid:3)(cid:3) (cid:54)(cid:56)(cid:51)(cid:51)(cid:47)(cid:60)(cid:3)
(cid:85)(cid:72)(cid:86)(cid:72)(cid:87) (cid:54)(cid:56)(cid:51)(cid:40)(cid:53)(cid:57)(cid:44)(cid:54)(cid:44)(cid:50)(cid:49)
(cid:51)(cid:50)(cid:53)(cid:18)(cid:51)(cid:39)(cid:53)
|     |     |     | (cid:42)(cid:51)(cid:16)(cid:39)(cid:48)(cid:36)(cid:21) | (cid:27)(cid:3)(cid:54)(cid:87)(cid:85)(cid:72)(cid:68)(cid:80)(cid:86) |     |     |     |     | (cid:44)(cid:81)(cid:87) | (cid:37)(cid:50)(cid:53) | (cid:57)(cid:39)(cid:39)(cid:36)(cid:15)(cid:3)(cid:57)(cid:54)(cid:54)(cid:36) |
| --- | --- | --- | -------------------------------------------------------- | ----------------------------------------------------------------------- | --- | --- | --- | --- | ------------------------ | ------------------------ | ------------------------------------------------------------------------------- |
(cid:41)(cid:44)(cid:41)(cid:50)
|     |     |     |                                                          |                                                                         |     |     |     | (cid:35)(cid:57)(cid:39)(cid:39)(cid:36) |                                          | (cid:51)(cid:57)(cid:39)                                                                                                                      | (cid:49)(cid:53)(cid:40)(cid:54)(cid:40)(cid:55)                                                                                                                             |
| --- | --- | --- | -------------------------------------------------------- | ----------------------------------------------------------------------- | --- | --- | --- | ---------------------------------------- | ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|     |     |     | (cid:42)(cid:51)(cid:16)(cid:39)(cid:48)(cid:36)(cid:20) | (cid:27)(cid:3)(cid:54)(cid:87)(cid:85)(cid:72)(cid:68)(cid:80)(cid:86) |     |     |     |                                          |                                          |                                                                                                                                               | (cid:58)(cid:46)(cid:56)(cid:51)(cid:62)(cid:23)(cid:29)(cid:19)(cid:64)                                                                                                     |
|     |     |     |                                                          | (cid:41)(cid:44)(cid:41)(cid:50)                                        |     |     |     | (cid:53)(cid:38)(cid:3)(cid:43)(cid:54)  |                                          | (cid:35)(cid:57)(cid:39)(cid:39)(cid:22)(cid:22)                                                                                              |                                                                                                                                                                              |
|     |     |     |                                                          |                                                                         |     |     |     |                                          | (cid:57)(cid:39)(cid:39)(cid:20)(cid:21) | (cid:37)(cid:37)(cid:74)(cid:72)(cid:81)(cid:3)(cid:14)(cid:3)(cid:51)(cid:50)(cid:58)(cid:40)(cid:53)(cid:3)(cid:48)(cid:49)(cid:42)(cid:55) | (cid:57)(cid:39)(cid:39)(cid:48)(cid:48)(cid:38)(cid:22)(cid:22)(cid:3)(cid:32)(cid:3)(cid:22)(cid:17)(cid:19)(cid:3)(cid:87)(cid:82)(cid:3)(cid:22)(cid:17)(cid:25)(cid:57) |
(cid:51)(cid:36)(cid:62)(cid:20)(cid:24)(cid:29)(cid:19)(cid:64) (cid:53)(cid:38)(cid:3)(cid:47)(cid:54) (cid:57)(cid:39)(cid:39)(cid:56)(cid:54)(cid:37)(cid:22)(cid:22)(cid:3)(cid:32)(cid:3)(cid:22)(cid:17)(cid:19)(cid:3)(cid:87)(cid:82)(cid:3)(cid:22)(cid:17)(cid:25)(cid:3)(cid:57)
|     |     |     |     | (cid:42)(cid:51)(cid:44)(cid:50)(cid:3)(cid:51)(cid:50)(cid:53)(cid:55)(cid:3)(cid:36) |     |     |     |                                                                                                                  |     | (cid:57)(cid:50)(cid:47)(cid:55)(cid:17)(cid:3)(cid:53)(cid:40)(cid:42)                                                                                 | (cid:57)(cid:39)(cid:39)(cid:3)(cid:32)(cid:3)(cid:20)(cid:17)(cid:27)(cid:3)(cid:87)(cid:82)(cid:3)(cid:22)(cid:17)(cid:25)(cid:3)(cid:57) |
| --- | --- | --- | --- | -------------------------------------------------------------------------------------- | --- | --- | --- | ---------------------------------------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
|     |     |     |     |                                                                                        |     |     |     | (cid:51)(cid:47)(cid:47)(cid:20)(cid:14)(cid:51)(cid:47)(cid:47)(cid:21)(cid:14)(cid:51)(cid:47)(cid:47)(cid:22) |     | (cid:47)(cid:53)(cid:55)(cid:38)(cid:53)(cid:58)(cid:51) (cid:22)(cid:17)(cid:22)(cid:57)(cid:3)(cid:55)(cid:50)(cid:3)(cid:20)(cid:17)(cid:21)(cid:57) | (cid:57)(cid:54)(cid:54)                                                                                                                    |
(cid:51)(cid:37)(cid:62)(cid:20)(cid:24)(cid:29)(cid:19)(cid:64) (cid:42)(cid:51)(cid:44)(cid:50)(cid:3)(cid:51)(cid:50)(cid:53)(cid:55)(cid:3)(cid:37) (cid:57)(cid:38)(cid:36)(cid:51)(cid:20)
|     |     | (cid:51)(cid:38)(cid:62)(cid:20)(cid:24)(cid:29)(cid:19)(cid:64) |     | (cid:42)(cid:51)(cid:44)(cid:50)(cid:3)(cid:51)(cid:50)(cid:53)(cid:55)(cid:3)(cid:38) |     |     |     |     |     | (cid:35)(cid:57)(cid:39)(cid:39)(cid:22)(cid:22)                |                                                  |
| --- | --- | ---------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------- | --- | --- | --- | --- | --- | --------------------------------------------------------------- | ------------------------------------------------ |
|     |     |                                                                  |     |                                                                                        |     |     |     |     |     | (cid:59)(cid:55)(cid:36)(cid:47)(cid:3)(cid:50)(cid:54)(cid:38) | (cid:50)(cid:54)(cid:38)(cid:66)(cid:44)(cid:49) |
(cid:50)(cid:54)(cid:38)(cid:66)(cid:50)(cid:56)(cid:55)
|     |     | (cid:51)(cid:39)(cid:62)(cid:20)(cid:24)(cid:29)(cid:19)(cid:64) |     | (cid:42)(cid:51)(cid:44)(cid:50)(cid:3)(cid:51)(cid:50)(cid:53)(cid:55)(cid:3)(cid:39) |     |     |     |                          |     | (cid:23)(cid:16)(cid:3)(cid:20)(cid:25)(cid:48)(cid:43)(cid:93) |     |
| --- | --- | ---------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------- | --- | --- | --- | ------------------------ | --- | --------------------------------------------------------------- | --- |
|     |     |                                                                  |     |                                                                                        |     |     |     | (cid:53)(cid:38)(cid:38) |     | (cid:58)(cid:39)(cid:42)(cid:22)(cid:21)(cid:46)                |     |
|     |     | (cid:51)(cid:40)(cid:62)(cid:20)(cid:24)(cid:29)(cid:19)(cid:64) |     | (cid:42)(cid:51)(cid:44)(cid:50)(cid:3)(cid:51)(cid:50)(cid:53)(cid:55)(cid:3)(cid:40) |     |     |     |                          |     |                                                                 |     |
(cid:53)(cid:48)(cid:72)(cid:86)(cid:72)(cid:87)(cid:3)(cid:9)(cid:3)(cid:70)(cid:42)(cid:82)(cid:55)(cid:81)(cid:87)(cid:85)(cid:82)(cid:79)
(cid:51)(cid:41)(cid:62)(cid:20)(cid:24)(cid:29)(cid:19)(cid:64) (cid:42)(cid:51)(cid:44)(cid:50)(cid:3)(cid:51)(cid:50)(cid:53)(cid:55)(cid:3)(cid:41) (cid:54)(cid:87)(cid:68)(cid:81)(cid:71)(cid:69)(cid:92) (cid:57)(cid:37)(cid:36)(cid:55)(cid:3)(cid:32)(cid:3)(cid:20)(cid:17)(cid:27)(cid:3)(cid:87)(cid:82)(cid:3)(cid:22)(cid:17)(cid:25)(cid:3)(cid:57)
(cid:76)(cid:81)(cid:87)(cid:72)(cid:85)(cid:73)(cid:68)(cid:70)(cid:72)
(cid:35)(cid:57)(cid:54)(cid:58)
(cid:51)(cid:42)(cid:62)(cid:20)(cid:24)(cid:29)(cid:19)(cid:64) (cid:42)(cid:51)(cid:44)(cid:50)(cid:3)(cid:51)(cid:50)(cid:53)(cid:55)(cid:3)(cid:42) (cid:46)(cid:47)(cid:38)(cid:21)(cid:51)(cid:37)(cid:51)(cid:36) (cid:46)(cid:47)(cid:38)(cid:20)(cid:51)(cid:37)(cid:51)(cid:36) (cid:46)(cid:47)(cid:38)(cid:51)(cid:21)(cid:37)(cid:43)(cid:36) (cid:46)(cid:47)(cid:38)(cid:51)(cid:20)(cid:37)(cid:43)(cid:36) (cid:50)(cid:54)(cid:38)(cid:22)(cid:21)(cid:66)(cid:44)(cid:49)
|     |     |                                                                  |     |                                                                                        |     |     |     | (cid:46)(cid:47)(cid:38)(cid:41) (cid:46)(cid:47)(cid:38)(cid:43) |                  | (cid:59)(cid:55)(cid:36)(cid:47)(cid:3)(cid:22)(cid:21)(cid:3)(cid:78)(cid:43)(cid:93)                                  | (cid:50)(cid:54)(cid:38)(cid:22)(cid:21)(cid:66)(cid:50)(cid:56)(cid:55)                                                          |
| --- | --- | ---------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------- | --- | --- | --- | ----------------------------------------------------------------- | ---------------- | ----------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
|     |     | (cid:51)(cid:43)(cid:62)(cid:20)(cid:24)(cid:29)(cid:19)(cid:64) |     | (cid:42)(cid:51)(cid:44)(cid:50)(cid:3)(cid:51)(cid:50)(cid:53)(cid:55)(cid:3)(cid:43) |     |     |     |                                                                   | (cid:54)(cid:47) |                                                                                                                         |                                                                                                                                   |
|     |     |                                                                  |     |                                                                                        |     |     |     |                                                                   |                  | (cid:53)(cid:55)(cid:38)                                                                                                | (cid:53)(cid:55)(cid:38)(cid:66)(cid:55)(cid:54)                                                                                  |
|     |     | (cid:51)(cid:44)(cid:62)(cid:20)(cid:20)(cid:29)(cid:19)(cid:64) |     |                                                                                        |     |     |     |                                                                   |                  | (cid:36)(cid:58)(cid:56)                                                                                                |                                                                                                                                   |
|     |     |                                                                  |     | (cid:42)(cid:51)(cid:44)(cid:50)(cid:3)(cid:51)(cid:50)(cid:53)(cid:55)(cid:3)(cid:44) |     |     |     |                                                                   |                  | (cid:37)(cid:68)(cid:70)(cid:78)(cid:88)(cid:83)(cid:3)(cid:85)(cid:72)(cid:74)(cid:76)(cid:86)(cid:87)(cid:72)(cid:85) | (cid:53)(cid:55)(cid:38)(cid:66)(cid:50)(cid:56)(cid:55) (cid:53)(cid:55)(cid:38)(cid:66)(cid:55)(cid:36)(cid:48)(cid:51)(cid:91) |
(cid:54)(cid:47)
|     |     |                                                               |                                                                                                |     |     |     |     | (cid:38)(cid:53)(cid:38) |     | (cid:23)(cid:3)(cid:46)(cid:37)(cid:3)(cid:37)(cid:46)(cid:51)(cid:53)(cid:36)(cid:48) |     |
| --- | --- | ------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --- | --- | --- | --- | ------------------------ | --- | -------------------------------------------------------------------------------------- | --- |
|     |     | (cid:20)(cid:25)(cid:27)(cid:3)(cid:36)(cid:41)(cid:3)(cid:3) | (cid:40)(cid:59)(cid:55)(cid:3)(cid:44)(cid:55)(cid:17)(cid:3)(cid:58)(cid:46)(cid:56)(cid:51) |     |     |     |     |                          |     |                                                                                        |     |
(cid:39)(cid:62)(cid:26)(cid:29)(cid:19)(cid:64) (cid:55)(cid:44)(cid:48)(cid:21) (cid:23)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:81)(cid:72)(cid:79)(cid:86)(cid:15)(cid:3)(cid:40)(cid:55)(cid:53)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
|     |     |     | (cid:54)(cid:39)(cid:48)(cid:48)(cid:38)(cid:20) | (cid:50)(cid:41)(cid:44)(cid:41) |     |     |     |     |     | (cid:22)(cid:21)(cid:69) |     |
| --- | --- | --- | ------------------------------------------------ | -------------------------------- | --- | --- | --- | --- | --- | ------------------------ | --- |
(cid:38)(cid:48)(cid:39)(cid:15)(cid:3)(cid:38)(cid:46)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
|     |     |                                                  |                                                  | (cid:50)(cid:41)(cid:44)(cid:41) |     |     |     |     |     | (cid:55)(cid:44)(cid:48)(cid:22) (cid:20)(cid:25)(cid:69) | (cid:23)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:81)(cid:72)(cid:79)(cid:86)(cid:15)(cid:3)(cid:40)(cid:55)(cid:53)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41) |
| --- | --- | ------------------------------------------------ | ------------------------------------------------ | -------------------------------- | --- | --- | --- | --- | --- | --------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|     |     | (cid:39)(cid:62)(cid:26)(cid:29)(cid:19)(cid:64) | (cid:54)(cid:39)(cid:48)(cid:48)(cid:38)(cid:21) |                                  |     |     |     |     |     |                                                           |                                                                                                                                                                      |
(cid:38)(cid:48)(cid:39)(cid:15)(cid:3)(cid:38)(cid:46)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41) (cid:42)(cid:51)(cid:39)(cid:48)(cid:36)(cid:21) (cid:42)(cid:51)(cid:39)(cid:48)(cid:36)(cid:20) (cid:55)(cid:44)(cid:48)(cid:23) (cid:20)(cid:25)(cid:69) (cid:23)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:81)(cid:72)(cid:79)(cid:86)(cid:15)(cid:3)(cid:40)(cid:55)(cid:53)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
(cid:23)(cid:3)(cid:70)(cid:82)(cid:80)(cid:83)(cid:79)(cid:17)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:17)(cid:3)(cid:11)(cid:55)(cid:44)(cid:48)(cid:20)(cid:66)(cid:38)(cid:43)(cid:20)(cid:62)(cid:20)(cid:29)(cid:23)(cid:64)(cid:49)(cid:12)(cid:15)
| (cid:23)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:17)(cid:3)(cid:11)(cid:55)(cid:44)(cid:48)(cid:20)(cid:66)(cid:38)(cid:43)(cid:20)(cid:62)(cid:20)(cid:29)(cid:23)(cid:64)(cid:40)(cid:55)(cid:53)(cid:15)(cid:3)(cid:37)(cid:46)(cid:44)(cid:49)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41) |                                                                                                                                                                                                                                                        |     | (cid:55)(cid:44)(cid:48)(cid:20)(cid:3)(cid:18)(cid:3)(cid:51)(cid:58)(cid:48) | (cid:20)(cid:25)(cid:69) |     |                                                                  |     | (cid:36)(cid:43)(cid:37)(cid:18) |     |                                                           |                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --- | ------------------------------------------------------------------------------ | ------------------------ | --- | ---------------------------------------------------------------- | --- | -------------------------------- | --- | --------------------------------------------------------- | ------------------------------------------------------------------------------- |
|                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                                                                        |     |                                                                                |                          |     | (cid:36)(cid:43)(cid:37)(cid:18)(cid:36)(cid:51)(cid:37)(cid:21) |     | (cid:36)(cid:51)(cid:37)(cid:20) |     | (cid:55)(cid:44)(cid:48)(cid:24) (cid:22)(cid:21)(cid:69) | (cid:23)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:81)(cid:72)(cid:79)(cid:86) |
|                                                                                                                                                                                                                                                                                                     | (cid:23)(cid:3)(cid:70)(cid:82)(cid:80)(cid:83)(cid:79)(cid:17)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:17)(cid:11)(cid:55)(cid:44)(cid:48)(cid:27)(cid:66)(cid:38)(cid:43)(cid:20)(cid:62)(cid:20)(cid:29)(cid:23)(cid:64)(cid:49)(cid:12)(cid:15) |     | (cid:55)(cid:44)(cid:48)(cid:27)(cid:3)(cid:18)(cid:3)(cid:51)(cid:58)(cid:48) | (cid:20)(cid:25)(cid:69) |     |                                                                  |     |                                  |     |                                                           |                                                                                 |
(cid:23)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:17)(cid:3)(cid:11)(cid:55)(cid:44)(cid:48)(cid:27)(cid:66)(cid:38)(cid:43)(cid:20)(cid:62)(cid:20)(cid:29)(cid:23)(cid:64)(cid:15)(cid:3)(cid:40)(cid:55)(cid:53)(cid:15)(cid:3)(cid:37)(cid:46)(cid:44)(cid:49)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41) (cid:55)(cid:44)(cid:48)(cid:20)(cid:21) (cid:20)(cid:25)(cid:69) (cid:21)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:81)(cid:72)(cid:79)(cid:86)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
(cid:20)(cid:25)(cid:69)
|     |     | (cid:21)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:81)(cid:72)(cid:79)(cid:86)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41) |     | (cid:55)(cid:44)(cid:48)(cid:28) |     |     |     |     |     |     |     |
| --- | --- | ----------------------------------------------------------------------------------------------------------------------------- | --- | -------------------------------- | --- | --- | --- | --- | --- | --- | --- |
(cid:20)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:81)(cid:72)(cid:79)(cid:3)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41) (cid:55)(cid:44)(cid:48)(cid:20)(cid:19) (cid:20)(cid:25)(cid:69) (cid:55)(cid:44)(cid:48)(cid:20)(cid:22) (cid:20)(cid:25)(cid:69) (cid:20)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:81)(cid:72)(cid:79)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
(cid:20)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:81)(cid:72)(cid:79)(cid:3)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41) (cid:55)(cid:44)(cid:48)(cid:20)(cid:20) (cid:20)(cid:25)(cid:69) (cid:12)(cid:91)(cid:68)(cid:80)(cid:11)(cid:3)(cid:93)(cid:43)(cid:48)(cid:3)(cid:27)(cid:19)(cid:20)(cid:3)(cid:3)(cid:3)(cid:21)(cid:37)(cid:51)(cid:36) (cid:55)(cid:44)(cid:48)(cid:20)(cid:23) (cid:20)(cid:25)(cid:69) (cid:20)(cid:3)(cid:70)(cid:75)(cid:68)(cid:81)(cid:81)(cid:72)(cid:79)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
(cid:53) (cid:59) (cid:15) (cid:3)(cid:55) (cid:59) (cid:15) (cid:3) (cid:54) (cid:38) (cid:46) (cid:15) (cid:86)(cid:80)(cid:70)(cid:68)(cid:85)(cid:71) (cid:86)(cid:80)(cid:70)(cid:68)(cid:85)(cid:71) (cid:53)(cid:59)(cid:15)(cid:3)(cid:55)(cid:59)(cid:15)(cid:3)(cid:54)(cid:38)(cid:46)
(cid:38)(cid:55) (cid:54) (cid:15)(cid:3) (cid:53) (cid:55) (cid:54) (cid:3) (cid:68) (cid:86) (cid:3)(cid:36) (cid:41) (cid:56)(cid:54)(cid:36)(cid:53)(cid:55)(cid:20) (cid:56)(cid:54)(cid:36)(cid:53)(cid:55)(cid:21) (cid:76)(cid:85)(cid:39)(cid:36) (cid:38)(cid:55)(cid:54)(cid:15)(cid:3)(cid:53)(cid:55)(cid:54)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
|     |     |     | (cid:76)(cid:85)(cid:39)(cid:36) |     |     |     | (cid:58)(cid:58)(cid:39)(cid:42) |     |     |     |     |
| --- | --- | --- | -------------------------------- | --- | --- | --- | -------------------------------- | --- | --- | --- | --- |
(cid:53) (cid:59) (cid:15) (cid:3)(cid:55) (cid:59) (cid:15)(cid:3) (cid:54) (cid:38) (cid:46) (cid:15) (cid:86) (cid:80) (cid:70)(cid:68)(cid:85)(cid:71) (cid:56)(cid:54)(cid:36)(cid:53)(cid:55)(cid:25) (cid:86) (cid:80) (cid:70) (cid:68)(cid:85)(cid:71) (cid:53) (cid:59) (cid:15)(cid:3)(cid:55) (cid:59) (cid:15) (cid:3)(cid:54) (cid:38) (cid:46)
(cid:38)(cid:55) (cid:54) (cid:15)(cid:3) (cid:53) (cid:55) (cid:54) (cid:3) (cid:68)(cid:86) (cid:3)(cid:36) (cid:41) (cid:76)(cid:85) (cid:39)(cid:36) (cid:56)(cid:54)(cid:36)(cid:53)(cid:55)(cid:22) (cid:76)(cid:85) (cid:39) (cid:36) (cid:38) (cid:55)(cid:54) (cid:15)(cid:3) (cid:53) (cid:55) (cid:54) (cid:3)(cid:68) (cid:86)(cid:3)(cid:36)(cid:41)
(cid:53)(cid:59)(cid:15)(cid:3)(cid:55)(cid:59)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
|     |     | (cid:48)(cid:50)(cid:54)(cid:44)(cid:15)(cid:3)(cid:48)(cid:44)(cid:54)(cid:50)(cid:15) |     | (cid:54)(cid:51)(cid:44)(cid:20)(cid:18)(cid:44)(cid:21)(cid:54)(cid:20) |     |     |     |     |     | (cid:56)(cid:36)(cid:53)(cid:55)(cid:23) |     |
| --- | --- | --------------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------ | --- | --- | --- | --- | --- | ---------------------------------------- | --- |
(cid:54)(cid:38)(cid:46)(cid:15)(cid:3)(cid:49)(cid:54)(cid:54)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41) (cid:47)(cid:51)(cid:55)(cid:44)(cid:48)(cid:20) (cid:20)(cid:25)(cid:69) (cid:56)(cid:36)(cid:53)(cid:55)(cid:24) (cid:53)(cid:59)(cid:15)(cid:3)(cid:55)(cid:59)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
|     |     | (cid:48) (cid:50) (cid:54) (cid:44)(cid:15)(cid:3) (cid:48) (cid:44)(cid:54) (cid:50) (cid:15) |     |     |     |     |     | (cid:93)(cid:43)(cid:48)(cid:22)(cid:19)(cid:20)(cid:37)(cid:51)(cid:36) |     |     |     |
| --- | --- | ---------------------------------------------------------------------------------------------- | --- | --- | --- | --- | --- | ------------------------------------------------------------------------ | --- | --- | --- |
(cid:54) (cid:38) (cid:46) (cid:15)(cid:3)(cid:49) (cid:54) (cid:54) (cid:3)(cid:68) (cid:86)(cid:3) (cid:36)(cid:41) (cid:54)(cid:51)(cid:44)(cid:23) (cid:12)(cid:91)(cid:68)(cid:80)(cid:11)(cid:3)(cid:93)(cid:43)(cid:48)(cid:3)(cid:23)(cid:24)(cid:3)(cid:3)(cid:3)(cid:20)(cid:37)(cid:51)(cid:36) (cid:56)(cid:36)(cid:53)(cid:55)(cid:26) (cid:53)(cid:59)(cid:15)(cid:3)(cid:55)(cid:59)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
(cid:48)(cid:50)(cid:54)(cid:44)(cid:15)(cid:3)(cid:48)(cid:44)(cid:54)(cid:50)(cid:15) (cid:54)(cid:51)(cid:44)(cid:24) (cid:56)(cid:36)(cid:53)(cid:55)(cid:27) (cid:53)(cid:59)(cid:15)(cid:3)(cid:55)(cid:59)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
(cid:54)(cid:38)(cid:46)(cid:15)(cid:3)(cid:49)(cid:54)(cid:54)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
|     |     |     |     | (cid:50)(cid:41)(cid:44)(cid:41) |     |     | (cid:55)(cid:44)(cid:48)(cid:25) | (cid:20)(cid:25)(cid:69) |     | (cid:54)(cid:51)(cid:44)(cid:21)(cid:18)(cid:44)(cid:21)(cid:54)(cid:21) | (cid:48)(cid:50)(cid:54)(cid:44)(cid:15)(cid:3)(cid:48)(cid:44)(cid:54)(cid:50)(cid:15)(cid:3)(cid:54)(cid:38)(cid:46) |
| --- | --- | --- | --- | -------------------------------- | --- | --- | -------------------------------- | ------------------------ | --- | ------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
(cid:54)(cid:39)(cid:15)(cid:3)(cid:54)(cid:38)(cid:46)(cid:15)(cid:3)(cid:41)(cid:54)(cid:15)(cid:3)(cid:48)(cid:38)(cid:47)(cid:46)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41) (cid:54)(cid:36)(cid:44)(cid:20) (cid:49)(cid:54)(cid:54)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
|     |     |     |     | (cid:50)(cid:41)(cid:44)(cid:41) |     |     | (cid:55)(cid:44)(cid:48)(cid:26) | (cid:20)(cid:25)(cid:69) |     | (cid:54)(cid:51)(cid:44)(cid:22)(cid:18)(cid:44)(cid:21)(cid:54)(cid:22) | (cid:48)(cid:50)(cid:54)(cid:44)(cid:15)(cid:3)(cid:48)(cid:44)(cid:54)(cid:50)(cid:15)(cid:3)(cid:54)(cid:38)(cid:46) |
| --- | --- | --- | --- | -------------------------------- | --- | --- | -------------------------------- | ------------------------ | --- | ------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
(cid:54)(cid:39)(cid:15)(cid:3)(cid:54)(cid:38)(cid:46)(cid:15)(cid:3)(cid:41)(cid:54)(cid:15)(cid:3)(cid:48)(cid:38)(cid:47)(cid:46)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41) (cid:54)(cid:36)(cid:44)(cid:21) (cid:49)(cid:54)(cid:54)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
|     |     |     |     |     |     |     |     |     |     | (cid:44)(cid:21)(cid:38)(cid:20)(cid:18)(cid:54)(cid:48)(cid:37)(cid:56)(cid:54) (cid:85)(cid:72)(cid:87)(cid:79)(cid:76)(cid:73)(cid:3)(cid:79)(cid:68)(cid:87)(cid:76)(cid:74)(cid:76)(cid:39) | (cid:54)(cid:38)(cid:47)(cid:15)(cid:3)(cid:54)(cid:39)(cid:36)(cid:15)(cid:3)(cid:54)(cid:48)(cid:37)(cid:36)(cid:47)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
(cid:56)(cid:47)(cid:51)(cid:44)(cid:29)(cid:38)(cid:46)(cid:15)(cid:3)(cid:39)(cid:62)(cid:26)(cid:29)(cid:19)(cid:64)(cid:15)(cid:3)(cid:39)(cid:44)(cid:53)(cid:15)(cid:3)(cid:54)(cid:55)(cid:51)(cid:15)(cid:3)(cid:49)(cid:59)(cid:55) (cid:50)(cid:55)(cid:42)(cid:3)(cid:43)(cid:54)(cid:3)(cid:51)(cid:43)(cid:60)(cid:3)(cid:11)(cid:21)(cid:12) (cid:44)(cid:21)(cid:38)(cid:21)(cid:18)(cid:54)(cid:48)(cid:37)(cid:56)(cid:54) (cid:54)(cid:38)(cid:47)(cid:15)(cid:3)(cid:54)(cid:39)(cid:36)(cid:15)(cid:3)(cid:54)(cid:48)(cid:37)(cid:36)(cid:47)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
(cid:54)(cid:60)(cid:54)(cid:38)(cid:41)(cid:42)
(cid:54)(cid:38)(cid:47)(cid:15)(cid:3)(cid:54)(cid:39)(cid:36)(cid:15)(cid:3)(cid:44)(cid:49)(cid:55)(cid:15)(cid:3)(cid:44)(cid:39)(cid:15)(cid:3)(cid:57)(cid:37)(cid:56)(cid:54) (cid:38)(cid:50)(cid:49)(cid:55)(cid:53)(cid:50)(cid:47)(cid:47)(cid:40)(cid:53) (cid:44)(cid:21)(cid:38)(cid:22)(cid:18)(cid:54)(cid:48)(cid:37)(cid:56)(cid:54) (cid:54)(cid:38)(cid:47)(cid:15)(cid:3)(cid:54)(cid:39)(cid:36)(cid:15)(cid:3)(cid:54)(cid:48)(cid:37)(cid:36)(cid:47)(cid:3)(cid:68)(cid:86)(cid:3)(cid:36)(cid:41)
(cid:35)(cid:57)(cid:39)(cid:39)(cid:36)
(cid:57)(cid:39)(cid:39)(cid:53)(cid:40)(cid:41)(cid:66)(cid:36)(cid:39)(cid:38) (cid:56)(cid:54)(cid:55)(cid:72)(cid:36)(cid:80)(cid:53)(cid:83)(cid:55)(cid:72)(cid:85)(cid:68)(cid:21)(cid:87)(cid:48)(cid:88)(cid:85)(cid:72)(cid:37)(cid:3)(cid:86)(cid:83)(cid:72)(cid:86)(cid:81)(cid:86)(cid:82)(cid:85) (cid:69)(cid:91)(cid:38)(cid:36)(cid:49)(cid:20) (cid:50)(cid:41)(cid:44)(cid:41)
(cid:27)(cid:3)(cid:68)(cid:81)(cid:68)(cid:79)(cid:82)(cid:74)(cid:3)(cid:76)(cid:81)(cid:83)(cid:88)(cid:87)(cid:86)(cid:3)(cid:70)(cid:82)(cid:80)(cid:80)(cid:82)(cid:81) (cid:55)(cid:59)(cid:15)(cid:3)(cid:53)(cid:59)
|     |     |     | (cid:36)(cid:39)(cid:38)(cid:20) |     |     |     | (cid:35)(cid:57)(cid:39)(cid:39)(cid:36) |     |     |     |     |
| --- | --- | --- | -------------------------------- | --- | --- | --- | ---------------------------------------- | --- | --- | --- | --- |
(cid:87)(cid:82)(cid:3)(cid:87)(cid:75)(cid:72)(cid:3)(cid:22)(cid:3)(cid:36)(cid:39)(cid:38)(cid:86)
|     | (cid:27)(cid:3)(cid:68)(cid:81)(cid:68)(cid:79)(cid:82)(cid:74)(cid:3)(cid:76)(cid:81)(cid:83)(cid:88)(cid:87)(cid:86)(cid:3)(cid:70)(cid:82)(cid:80)(cid:80)(cid:82)(cid:81)                |                                                                                                                     | (cid:36)(cid:39)(cid:38)(cid:21) |                                  |     |     | (cid:39)(cid:36)(cid:38)(cid:20)        |                                         |     |     |     |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | -------------------------------- | -------------------------------- | --- | --- | --------------------------------------- | --------------------------------------- | --- | --- | --- |
|     |                                                                                                                                                                                              | (cid:87)(cid:82)(cid:3)(cid:87)(cid:75)(cid:72)(cid:3)(cid:36)(cid:39)(cid:38)(cid:20)(cid:3)(cid:9)(cid:3)(cid:21) |                                  | (cid:44)(cid:44)(cid:41)(cid:41) |     |     |                                         | (cid:44)(cid:55)(cid:41)                |     |     |     |
|     | (cid:27)(cid:3)(cid:68)(cid:81)(cid:68)(cid:79)(cid:82)(cid:74)(cid:3)(cid:76)(cid:81)(cid:83)(cid:88)(cid:87)(cid:86)(cid:3)(cid:73)(cid:82)(cid:85)(cid:3)(cid:36)(cid:39)(cid:38)(cid:22) |                                                                                                                     | (cid:36)(cid:39)(cid:38)(cid:22) |                                  |     |     | (cid:39)(cid:36)(cid:38)(cid:21)        |                                         |     |     |     |
|     |                                                                                                                                                                                              |                                                                                                                     |                                  |                                  |     |     | (cid:39)(cid:36)(cid:38)(cid:20)        | (cid:39)(cid:36)(cid:38)(cid:21)        |     |     |     |
|     |                                                                                                                                                                                              |                                                                                                                     |                                  |                                  |     |     | (cid:68)(cid:86)(cid:3)(cid:36)(cid:41) | (cid:68)(cid:86)(cid:3)(cid:36)(cid:41) |     |     |     |
(cid:48)(cid:54)(cid:89)(cid:23)(cid:20)(cid:19)(cid:20)(cid:21)(cid:57)(cid:22)
1. The timers connected to APB2 are clocked from TIMxCLK up to 216 MHz, while the timers connected to APB1 are clocked
from TIMxCLK either up to 108 MHz or 216 MHz depending on TIMPRE bit configuration in the RCC_DCKCFGR register.
|     |     |     |     |     | DocID029808 Rev 3 |     |     |     |     |     | 19/229 |
| --- | --- | --- | --- | --- | ----------------- | --- | --- | --- | --- | --- | ------ |
47

Functional overview STM32F722xx STM32F723xx
2. Available only on the STM32F723xx devices.
2 Functional overview
® ®
2.1 ARM Cortex -M7 with FPU
The ARM® Cortex®-M7 with FPU processor is the latest generation of ARM processors for
embedded systems. It was developed to provide a low-cost platform that meets the needs of
MCU implementation, with a reduced pin count and low-power consumption, while
delivering outstanding computational performance and low interrupt latency.
The Cortex®-M7 processor is a highly efficient high-performance featuring:
– Six-stage dual-issue pipeline
– Dynamic branch prediction
– Harvard caches (8 Kbytes of I-cache and 8 Kbytes of D-cache)
– 64-bit AXI4 interface
– 64-bit ITCM interface
– 2x32-bit DTCM interfaces
The processor supports the following memory interfaces:
• Tightly Coupled Memory (TCM) interface.
• Harvard instruction and data caches and AXI master (AXIM) interface.
• Dedicated low-latency AHB-Lite peripheral (AHBP) interface.
The processor supports a set of DSP instructions which allow efficient signal processing and
complex algorithm execution.
It supports single precision FPU (floating point unit), speeds up software development by
using metalanguage development tools, while avoiding saturation.
Figure 5 shows the general block diagram of the STM32F722xx and STM32F723xx family.
Note: Cortex®-M7 with FPU core is binary compatible with the Cortex®-M4 core.
2.2 Memory protection unit
The memory protection unit (MPU) is used to manage the CPU accesses to memory to
prevent one task to accidentally corrupt the memory or resources used by any other active
task. This memory area is organized into up to 8 protected areas that can in turn be divided
up into 8 subareas. The protection area sizes are between 32 bytes and the whole 4
gigabytes of addressable memory.
The MPU is especially helpful for applications where some critical or certified code has to be
protected against the misbehavior of other tasks. It is usually managed by an RTOS (real-
time operating system). If a program accesses a memory location that is prohibited by the
MPU, the RTOS can detect it and take action. In an RTOS environment, the kernel can
dynamically update the MPU area setting, based on the process to be executed.
The MPU is optional and can be bypassed for applications that do not need it.
20/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Functional overview
2.3 Embedded Flash memory
The STM32F722xx and STM32F723xx devices embed a Flash memory of up to 512 Kbytes
available for storing programs and data.
The flexible protections can be configured thanks to option bytes:
• Readout protection (RDP) to protect the whole memory. Three levels are available:
– Level 0: no readout protection
– Level 1: No access (read, erase, program) to the Flash memory or backup SRAM
can be performed while the debug feature is connected or while booting from RAM
or system memory bootloader
– Level 2: debug/chip read protection disabled.
• Write protection (WRP): the protected area is protected against erasing and
programming.
• Proprietary code readout protection (PCROP): Flash memory user sectors (0 to 7) can
be protected against D-bus read accesses by using the proprietary readout protection
(PCROP). The protected area is execute-only.
2.4 CRC (cyclic redundancy check) calculation unit
The CRC (cyclic redundancy check) calculation unit is used to get a CRC code using a
configurable generator polynomial value and size.
Among other applications, CRC-based techniques are used to verify data transmission or
storage integrity. In the scope of the EN/IEC 60335-1 standard, they offer a means of
verifying the Flash memory integrity. The CRC calculation unit helps compute a signature of
the software during runtime, to be compared with a reference signature generated at link-
time and stored at a given memory location.
2.5 Embedded SRAM
All the devices feature:
• System SRAM up to 256 Kbytes:
– SRAM1 on AHB bus Matrix: 176 Kbytes
– SRAM2 on AHB bus Matrix: 16 Kbytes
– DTCM-RAM on TCM interface (Tighly Coupled Memory interface): 64 Kbytes for
critical real-time data.
• Instruction RAM (ITCM-RAM) 16 Kbytes:
– It is mapped on TCM interface and reserved only for CPU Execution/Instruction
useful for critical real-time routines.
The Data TCM RAM is accessible by the GP-DMAs and peripheral DMAs through the
specific AHB slave of the CPU.The instruction TCM RAM is reserved only for CPU. It is
accessed at CPU clock speed with 0 wait states.
• 4 Kbytes of backup SRAM
This area is accessible only from the CPU. Its content is protected against possible
unwanted write accesses, and is retained in Standby or VBAT mode.
DocID029808 Rev 3 21/229
47

Functional overview STM32F722xx STM32F723xx
2.6 AXI-AHB bus matrix
The STM32F722xx and STM32F723xx system architecture is based on 2 sub-systems:
• An AXI to multi AHB bridge converting AXI4 protocol to AHB-Lite protocol:
– 3x AXI to 32-bit AHB bridges connected to AHB bus matrix
– 1x AXI to 64-bit AHB bridge connected to the embedded Flash memory
• A multi-AHB Bus-Matrix
– The 32-bit multi-AHB bus matrix interconnects all the masters (CPU, DMAs, USB
HS) and the slaves (Flash memory, RAM, FMC, Quad-SPI, AHB and APB
peripherals) and ensures a seamless and efficient operation even when several
high-speed peripherals work simultaneously.
Figure 6. STM32F722xx and STM32F723xx AXI-AHB bus matrix architecture(1)
(cid:4)(cid:90)(cid:68)(cid:3)(cid:18)(cid:381)(cid:396)(cid:410)(cid:286)(cid:454)(cid:882)(cid:68)(cid:1011)
(cid:1007)(cid:1006)(cid:882)(cid:271)(cid:349)(cid:410)(cid:3)(cid:17)(cid:437)(cid:400)(cid:3)(cid:68)(cid:258)(cid:410)(cid:396)(cid:349)(cid:454)(cid:3)(cid:882)(cid:3)(cid:94)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:20)(cid:19)(cid:19)(cid:24)(cid:57)(cid:20)
1. The above figure has large wires for 64-bits bus and thin wires for 32-bits bus.
22/229 DocID029808 Rev 3
(cid:100)(cid:90)(cid:4)
(cid:38)(cid:62)(cid:4)(cid:94)(cid:44)
(cid:1009)(cid:1005)(cid:1006)(cid:60)(cid:17)
(cid:94)(cid:90)(cid:4)(cid:68)(cid:1005)(cid:3)(cid:3)
(cid:1005)(cid:1011)(cid:1010)(cid:60)(cid:17)
(cid:94)(cid:90)(cid:4)(cid:68)(cid:1006)
(cid:1005)(cid:1010)(cid:60)(cid:17)
(cid:4)(cid:44)(cid:17)
(cid:393)(cid:286)(cid:396)(cid:349)(cid:393)(cid:346)(cid:1006)
(cid:38)(cid:68)(cid:18)(cid:3)(cid:286)(cid:454)(cid:410)(cid:286)(cid:396)(cid:374)(cid:258)(cid:367)
(cid:68)(cid:286)(cid:373)(cid:18)(cid:410)(cid:367)
(cid:89)(cid:437)(cid:258)(cid:282)(cid:882)(cid:94)(cid:87)(cid:47)
(cid:87)(cid:17)(cid:44)(cid:4)
(cid:24)(cid:100)(cid:18)(cid:68)(cid:3)(cid:90)(cid:4)(cid:68)(cid:3)(cid:3)
(cid:47)(cid:100)(cid:18)(cid:68)(cid:3)(cid:90)(cid:4)(cid:68)
(cid:4)(cid:121)(cid:47)(cid:3)(cid:410)(cid:381)
(cid:3)(cid:373)(cid:437)(cid:367)(cid:410)(cid:349)(cid:882)(cid:4)(cid:44)(cid:17)(cid:3)
(cid:4)(cid:44)(cid:17)
(cid:87)(cid:286)(cid:396)(cid:349)(cid:393)(cid:346)(cid:1005)
(cid:68)(cid:18)(cid:100)(cid:24)
(cid:68)(cid:47)(cid:121)(cid:4)
(cid:68)(cid:18)(cid:100)(cid:47)
(cid:1010)(cid:1008)(cid:60)(cid:17)
(cid:1005)(cid:1010)(cid:60)(cid:17)
(cid:47)(cid:100)(cid:18)(cid:68)
(cid:1010)(cid:1008)(cid:882)(cid:271)(cid:349)(cid:410)(cid:3)(cid:4)(cid:44)(cid:17)
(cid:1010)(cid:1008)(cid:882)(cid:271)(cid:349)(cid:410)(cid:3)(cid:17)(cid:437)(cid:94)(cid:3)(cid:68)(cid:258)(cid:410)(cid:396)(cid:349)(cid:454)
(cid:4)(cid:87)(cid:17)(cid:1005)
(cid:4)(cid:87)(cid:17)(cid:1006)
(cid:94)(cid:17)(cid:44)(cid:4)
(cid:39)(cid:87) (cid:39)(cid:87) (cid:104)(cid:94)(cid:17)(cid:3)(cid:75)(cid:100)(cid:39)
(cid:24)(cid:68)(cid:4)(cid:1005) (cid:24)(cid:68)(cid:4)(cid:1006) (cid:44)(cid:94)
(cid:27)(cid:46)(cid:37)
(cid:44)(cid:18)(cid:39)(cid:3)(cid:38)(cid:68)(cid:70)(cid:75)(cid:72)
(cid:47)(cid:87)(cid:890)(cid:4)(cid:68)(cid:24) (cid:1005)(cid:68)(cid:28)(cid:68)(cid:890)(cid:4)(cid:68)(cid:24) (cid:1006)(cid:68)(cid:28)(cid:68)(cid:890)(cid:4)(cid:68)(cid:24) (cid:1006)(cid:87)(cid:890)(cid:4)(cid:68)(cid:24) (cid:68)(cid:890)(cid:94)(cid:44)(cid:890)(cid:17)(cid:94)(cid:104)

STM32F722xx STM32F723xx Functional overview
2.7 DMA controller (DMA)
The devices feature two general-purpose dual-port DMAs (DMA1 and DMA2) with 8
streams each. They are able to manage memory-to-memory, peripheral-to-memory and
memory-to-peripheral transfers. They feature dedicated FIFOs for APB/AHB peripherals,
support burst transfer and are designed to provide the maximum peripheral bandwidth
(AHB/APB).
The two DMA controllers support a circular buffer management, so that no specific code is
needed when the controller reaches the end of the buffer. The two DMA controllers also
have a double buffering feature, which automates the use and switching of two memory
buffers without requiring any special code.
Each stream is connected to dedicated hardware DMA requests, with support for software
trigger on each stream. The configuration is made by software and transfer sizes between
source and destination are independent.
The DMA can be used with the main peripherals:
• SPI and I2S
• I2C
• USART
• General-purpose, basic and advanced-control timers TIMx
• DAC
• SDMMC
• ADC
• SAI
• Quad-SPI
DocID029808 Rev 3 23/229
47

Functional overview STM32F722xx STM32F723xx
2.8 Flexible memory controller (FMC)
The Flexible memory controller (FMC) includes three memory controllers:
• The NOR/PSRAM memory controller
• The NAND/memory controller
• The Synchronous DRAM (SDRAM/Mobile LPSDR SDRAM) controller
The main features of the FMC controller are the following:
• Interface with static-memory mapped devices including:
– Static random access memory (SRAM)
– NOR Flash memory/OneNAND Flash memory
– PSRAM (4 memory banks)
– NAND Flash memory with ECC hardware to check up to 8 Kbytes of data
• Interface with synchronous DRAM (SDRAM/Mobile LPSDR SDRAM) memories
• 8-, 16-, 32-bit data bus width
• Independent Chip Select control for each memory bank
• Independent configuration for each memory bank
• Write FIFO
• Read FIFO for SDRAM controller
• The maximum FMC_CLK/FMC_SDCLK frequency for synchronous accesses is
HCLK/2
LCD parallel interface
The FMC can be configured to interface seamlessly with most graphic LCD controllers. It
supports the Intel 8080 and Motorola 6800 modes, and is flexible enough to adapt to
specific LCD interfaces. This LCD parallel interface capability makes it easy to build cost-
effective graphic applications using LCD modules with embedded controllers or high
performance solutions using external controllers with dedicated acceleration.
2.9 Quad-SPI memory interface (QUADSPI)
All the devices embed a Quad-SPI memory interface, which is a specialized communication
interface targetting Single, Dual or Quad-SPI Flash memories. It can work in:
• Direct mode through registers
• External Flash status register polling mode
• Memory mapped mode.
Up to 256 Mbytes of external Flash are memory mapped, supporting 8, 16 and 32-bit
access. The code execution is supported.
The opcode and the frame format are fully programmable. The communication can be either
in Single Data Rate or Dual Data Rate.
24/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Functional overview
2.10 Nested vectored interrupt controller (NVIC)
The devices embed a nested vectored interrupt controller able to manage 16 priority levels,
and handle up to 110 maskable interrupt channels plus the 16 interrupt lines of the Cortex®-
M7 with FPU core.
• Closely coupled NVIC gives low-latency interrupt processing
• Interrupt entry vector table address passed directly to the core
• Allows early processing of interrupts
• Processing of late arriving, higher-priority interrupts
• Support tail chaining
• Processor state automatically saved
• Interrupt entry restored on interrupt exit with no instruction overhead
This hardware block provides flexible interrupt management features with a minimum
interrupt latency.
2.11 External interrupt/event controller (EXTI)
The external interrupt/event controller consists of 24 edge-detector lines used to generate
interrupt/event requests. Each line can be independently configured to select the trigger
event (rising edge, falling edge, both) and can be masked independently. A pending register
maintains the status of the interrupt requests. The EXTI can detect an external line with a
pulse width shorter than the Internal APB2 clock period. Up to 140 GPIOs in the
STM32F722xx devices (138 GPIOs in the STM32F723xx devices) can be connected to the
16 external interrupt lines.
2.12 Clocks and startup
On reset the 16 MHz internal HSI RC oscillator is selected as the default CPU clock. The
16 MHz internal RC oscillator is factory-trimmed to offer 1% accuracy. The application can
then select as system clock either the RC oscillator or an external 4-26 MHz clock source.
This clock can be monitored for failure. If a failure is detected, the system automatically
switches back to the internal RC oscillator and a software interrupt is generated (if enabled).
This clock source is input to a PLL thus allowing to increase the frequency up to 216 MHz.
Similarly, a full interrupt management of the PLL clock entry is available when necessary
(for example if an indirectly used external oscillator fails).
Several prescalers allow the configuration of the two AHB buses, the high-speed APB
(APB2) and the low-speed APB (APB1) domains. The maximum frequency of the two AHB
buses is 216 MHz while the maximum frequency of the high-speed APB domains is
108 MHz. The maximum allowed frequency of the low-speed APB domain is 54 MHz.
The devices embed two dedicated PLLs (PLLI2S and PLLSAI) which allow to achieve audio
class performance. In this case, the I2S and SAI master clock can generate all standard
sampling frequencies from 8 kHz to 192 kHz.
The STM32F723xx devices embed two PLLs inside the PHY HS controller: PLL1 and PLL2.
The PLL1 allows to output 60 MHz used as an input for PLL2 which itself allows to generate
the 480 Mbps in the USB OTG High Speed mode.
The PLL1 has as input HSE clock.
DocID029808 Rev 3 25/229
47

Functional overview STM32F722xx STM32F723xx
2.13 Boot modes
At startup, the boot memory space is selected by the BOOT pin and BOOT_ADDx option
bytes, allowing to program any boot memory address from 0x0000 0000 to 0x3FFF FFFF
which includes:
• All Flash address space mapped on ITCM or AXIM interface
• All RAM address space: ITCM, DTCM RAMs and SRAMs mapped on AXIM interface
• The System memory bootloader
The boot loader is located in system memory. It is used to reprogram the Flash memory
through a serial interface.
2.14 Power supply schemes
• V = 1.7 to 3.6 V: external power supply for I/Os and the internal regulator (when
DD
enabled), provided externally through V pins.
DD
• V , V = 1.7 to 3.6 V: external analog power supplies for ADC, DAC, Reset
SSA DDA
blocks, RCs and PLL. V and V must be connected to V and V , respectively.
DDA SSA DD SS
• V = 1.65 to 3.6 V: power supply for RTC, external clock 32 kHz oscillator and
BAT
backup registers (through power switch) when V is not present.
DD
Note: The V
DD
/V
DDA
minimum value of 1.7 V is obtained when the internal reset is OFF (refer to
Section 2.15.2: Internal reset OFF). Refer to Table 3: Voltage regulator configuration mode
versus device operating mode to identify the packages supporting this option.
• The V can be connected either to V or an external independent power
DDSDMMC DD
supply (1.8 to 3.6V) for the SDMMC2 pins (clock, command, and 4-bit data). For
example, when the device is powered at 1.8V, an independent power supply 2.7V can
be connected to V .When the V is connected to a separated power
DDSDMMC DDSDMMC
supply, it is independent from V or V but it must be the last supply to be provided
DD DDA
and the first to disappear. The following conditions V must be respected:
DDSDMMC
– During the power-on phase (V < V ), V should be always lower
DD DD_MIN DDSDMMC
than V
DD
– During the power-down phase (V < V ), V should be always
DD DD_MIN DDSDMMC
lower than V
DD
– The V rising and falling time rate specifications must be respected
DDSDMMC
– In the operating mode phase, V
DDSDMMC
could be lower or higher than V
DD:
All associated GPIOs powered by V are operating between
DDSDMMC
V and V
DDSDMMC_MIN DDSDMMC_MAX.
• The V can be connected either to V or an external independent power supply
DDUSB DD
(3.0 to 3.6V) for USB transceivers (refer to Figure 7 and Figure 8). For example, when
the device is powered at 1.8V, an independent power supply 3.3V can be connected to
the V . When the V is connected to a separated power supply, it is
DDUSB DDUSB
independent from V or V but it must be the last supply to be provided and the first
DD DDA
to disappear. The following conditions V must be respected:
DDUSB
– During the power-on phase (V < V ), V should be always lower
DD DD_MIN DDUSB
than V
DD
– During the power-down phase (V < V ), V should be always lower
DD DD_MIN DDUSB
than V
DD
26/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Functional overview
– The V  rising and falling time rate specifications must be respected
DDUSB
– In the operating mode phase, V  could be lower or higher than V
DDUSB DD:
- If the USB (USB OTG_HS/OTG_FS) is used, the associated GPIOs powered by
| V DDUSB  | are operating between V |     |     | DDUSB_MIN |  and V | DDUSB_MAX | .   |
| -------- | ----------------------- | --- | --- | --------- | ------ | --------- | --- |
- The V DDUSB  supplies both USB transceiver (USB OTG_HS and USB OTG_FS).
If only one USB transceiver is used in the application, the GPIOs associated to the
| other USB transceiver are still supplied by V |     |     |     |     |     | .   |     |
| --------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
DDUSB
- If the USB (USB OTG_HS/OTG_FS) is not used, the associated GPIOs powered
| by V   | are operating between V |       |                 |        |  and V |               | .   |
| ------ | ----------------------- | ----- | --------------- | ------ | ------ | ------------- | --- |
| DDUSB  |                         |       |                 | DD_MIN |        | DD_MAX        |     |
|        | Figure 7. V             | DDUSB |  connected to V |        | DD     |  power supply |     |
(cid:57)(cid:39)(cid:39)
(cid:57)
(cid:39)(cid:39)(cid:66)(cid:48)(cid:36)(cid:59)
|     |     |     | (cid:57) (cid:39)(cid:39) | (cid:32)(cid:3)(cid:57) (cid:39)(cid:39)(cid:36) | (cid:32)(cid:3)(cid:57) (cid:39)(cid:39)(cid:56)(cid:54)(cid:37) |     |     |
| --- | --- | --- | ------------------------- | ------------------------------------------------ | ---------------------------------------------------------------- | --- | --- |
(cid:57)
(cid:39)(cid:39)(cid:66)(cid:48)(cid:44)(cid:49)
(cid:87)(cid:76)(cid:80)(cid:72)
| (cid:51)(cid:82)(cid:90)(cid:72)(cid:85)(cid:16)(cid:82)(cid:81) |     |     | (cid:50)(cid:83)(cid:72)(cid:85)(cid:68)(cid:87)(cid:76)(cid:81)(cid:74)(cid:3)(cid:80)(cid:82)(cid:71)(cid:72) |     |     |     | (cid:51)(cid:82)(cid:90)(cid:72)(cid:85)(cid:16)(cid:71)(cid:82)(cid:90)(cid:81) |
| ---------------------------------------------------------------- | --- | --- | --------------------------------------------------------------------------------------------------------------- | --- | --- | --- | -------------------------------------------------------------------------------- |
(cid:48)(cid:54)(cid:22)(cid:26)(cid:24)(cid:28)(cid:20)(cid:57)(cid:20)
|     | Figure 8. V | DDUSB |  connected to external power supply |     |     |     |     |
| --- | ----------- | ----- | ----------------------------------- | --- | --- | --- | --- |
(cid:57)
(cid:39)(cid:39)(cid:56)(cid:54)(cid:37)(cid:66)(cid:48)(cid:36)(cid:59)
(cid:56)(cid:54)(cid:37)(cid:73)(cid:88)(cid:81)(cid:70)(cid:87)(cid:76)(cid:82)(cid:81)(cid:68)(cid:79)(cid:3)(cid:68)(cid:85)(cid:72)(cid:68)
(cid:57)
(cid:39)(cid:39)(cid:56)(cid:54)(cid:37)
(cid:57)
(cid:39)(cid:39)(cid:56)(cid:54)(cid:37)(cid:66)(cid:48)(cid:44)(cid:49)
| (cid:56)(cid:54)(cid:37)(cid:3)(cid:81)(cid:82)(cid:81) |     |     |     |     |     |     | (cid:56)(cid:54)(cid:37)(cid:81)(cid:82)(cid:81) |
| ------------------------------------------------------- | --- | --- | --- | --- | --- | --- | ------------------------------------------------ |
(cid:73)(cid:88)(cid:81)(cid:70)(cid:87)(cid:76)(cid:82)(cid:81)(cid:68)(cid:79)
| (cid:73)(cid:88)(cid:81)(cid:70)(cid:87)(cid:76)(cid:82)(cid:81)(cid:68)(cid:79) |     |     |     | (cid:57) (cid:32)(cid:57) |                          |     |                                  |
| -------------------------------------------------------------------------------- | --- | --- | --- | ------------------------- | ------------------------ | --- | -------------------------------- |
|                                                                                  |     |     |     | (cid:39)(cid:39)          | (cid:39)(cid:39)(cid:36) |     | (cid:68)(cid:85)(cid:72)(cid:68) |
(cid:68)(cid:85)(cid:72)(cid:68)
(cid:57)
(cid:39)(cid:39)(cid:66)(cid:48)(cid:44)(cid:49)
(cid:87)(cid:76)(cid:80)(cid:72)
| (cid:51)(cid:82)(cid:90)(cid:72)(cid:85)(cid:16)(cid:82)(cid:81) |     |     | (cid:50)(cid:83)(cid:72)(cid:85)(cid:68)(cid:87)(cid:76)(cid:81)(cid:74)(cid:3)(cid:80)(cid:82)(cid:71)(cid:72) |     |     |     | (cid:51)(cid:82)(cid:90)(cid:72)(cid:85)(cid:16)(cid:71)(cid:82)(cid:90)(cid:81) |
| ---------------------------------------------------------------- | --- | --- | --------------------------------------------------------------------------------------------------------------- | --- | --- | --- | -------------------------------------------------------------------------------- |
(cid:48)(cid:54)(cid:22)(cid:26)(cid:24)(cid:28)(cid:19)(cid:57)(cid:20)
DocID029808 Rev 3 27/229
47

Functional overview STM32F722xx STM32F723xx
On the STM32F7x3xx devices, the USB OTG HS sub-system uses an additional power
supply pin:
• The VDD12OTGHS pin is the output of PHY HS regulator (1.2V). An external capacitor
of 2.2 µF must be connected on the VDD12OTGHS pin.
2.15 Power supply supervisor
2.15.1 Internal reset ON
On packages embedding the PDR_ON pin, the power supply supervisor is enabled by
holding PDR_ON high. On the other packages, the power supply supervisor is always
enabled.
The device has an integrated power-on reset (POR)/ power-down reset (PDR) circuitry
coupled with a Brownout reset (BOR) circuitry. At power-on, POR/PDR is always active and
ensures proper operation starting from 1.8 V. After the 1.8 V POR threshold level is
reached, the option byte loading process starts, either to confirm or modify default BOR
thresholds, or to disable BOR permanently. Three BOR thresholds are available through
option bytes. The device remains in reset mode when V is below a specified threshold,
DD
V or V , without the need for an external reset circuit.
POR/PDR BOR
The device also features an embedded programmable voltage detector (PVD) that monitors
the V /V power supply and compares it to the V threshold. An interrupt can be
DD DDA PVD
generated when V /V drops below the V threshold and/or when V /V is
DD DDA PVD DD DDA
higher than the V threshold. The interrupt service routine can then generate a warning
PVD
message and/or put the MCU into a safe state. The PVD is enabled by software.
2.15.2 Internal reset OFF
This feature is available only on packages featuring the PDR_ON pin. The internal power-on
reset (POR) / power-down reset (PDR) circuitry is disabled through the PDR_ON pin.
An external power supply supervisor should monitor V and NRST and should maintain
DD
the device in reset mode as long as V is below a specified threshold. PDR_ON should be
DD
connected to V . Refer to Figure 9: Power supply supervisor interconnection with internal
SS
reset OFF.
28/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Functional overview
Figure 9. Power supply supervisor interconnection with internal reset OFF
(cid:57)
(cid:39)(cid:39)
(cid:40)(cid:91)(cid:87)(cid:72)(cid:85)(cid:81)(cid:68)(cid:79)(cid:3)(cid:57) (cid:3)(cid:83)(cid:82)(cid:90)(cid:72)(cid:85)(cid:3)(cid:86)(cid:88)(cid:83)(cid:83)(cid:79)(cid:92)(cid:3)(cid:86)(cid:88)(cid:83)(cid:72)(cid:85)(cid:89)(cid:76)(cid:86)(cid:82)(cid:85)
(cid:39)(cid:39)
(cid:40)(cid:91)(cid:87)(cid:17)(cid:3)(cid:85)(cid:72)(cid:86)(cid:72)(cid:87)(cid:3)(cid:70)(cid:82)(cid:81)(cid:87)(cid:85)(cid:82)(cid:79)(cid:79)(cid:72)(cid:85)(cid:3)(cid:68)(cid:70)(cid:87)(cid:76)(cid:89)(cid:72)(cid:3)(cid:90)(cid:75)(cid:72)(cid:81)
(cid:57) (cid:3)(cid:31)(cid:3)(cid:20)(cid:17)(cid:26)(cid:3)(cid:57)(cid:3)(cid:3)
(cid:39)(cid:39)
(cid:36)(cid:83)(cid:83)(cid:79)(cid:76)(cid:70)(cid:68)(cid:87)(cid:76)(cid:82)(cid:81)(cid:3)(cid:85)(cid:72)(cid:86)(cid:72)(cid:87)
(cid:49)(cid:53)(cid:54)(cid:55) (cid:86)(cid:76)(cid:74)(cid:81)(cid:68)(cid:79)
(cid:51)(cid:39)(cid:53)(cid:66)(cid:50)(cid:49)
(cid:57)
(cid:39)(cid:39)
(cid:57)
(cid:54)(cid:54)
(cid:48)(cid:54)(cid:22)(cid:20)(cid:22)(cid:27)(cid:22)(cid:57)(cid:23)
The V specified threshold, below which the device must be maintained under reset, is
DD
1.7 V (see Figure 10).
A comprehensive set of power-saving mode allows to design low-power applications.
When the internal reset is OFF, the following integrated features are no more supported:
• The integrated power-on reset (POR) / power-down reset (PDR) circuitry is disabled
• The brownout reset (BOR) circuitry must be disabled
• The embedded programmable voltage detector (PVD) is disabled
• V functionality is no more available and V pin should be connected to V .
BAT BAT DD
All packages, except for the LQFP100, allow to disable the internal reset through the
PDR_ON signal when connected to V .
SS
Figure 10. PDR_ON control with internal reset OFF
(cid:57)(cid:39)(cid:39)
(cid:51)(cid:39)(cid:53)(cid:3)(cid:32)(cid:3)(cid:20)(cid:17)(cid:26)(cid:3)(cid:57)(cid:3)(cid:3)
(cid:87)(cid:76)(cid:80)(cid:72)
(cid:53)(cid:72)(cid:86)(cid:72)(cid:87)(cid:3)(cid:69)(cid:92)(cid:3)(cid:82)(cid:87)(cid:75)(cid:72)(cid:85)(cid:3)(cid:86)(cid:82)(cid:88)(cid:85)(cid:70)(cid:72)(cid:3)(cid:87)(cid:75)(cid:68)(cid:81)(cid:3)
(cid:83)(cid:82)(cid:90)(cid:72)(cid:85)(cid:3)(cid:86)(cid:88)(cid:83)(cid:83)(cid:79)(cid:92)(cid:3)(cid:86)(cid:88)(cid:83)(cid:72)(cid:85)(cid:89)(cid:76)(cid:86)(cid:82)(cid:85)(cid:3)(cid:3)
(cid:49)(cid:53)(cid:54)(cid:55)
(cid:51)(cid:39)(cid:53)(cid:66)(cid:50)(cid:49) (cid:51)(cid:39)(cid:53)(cid:66)(cid:50)(cid:49) (cid:87)(cid:76)(cid:80)(cid:72)
(cid:48)(cid:54)(cid:20)(cid:28)(cid:19)(cid:19)(cid:28)(cid:57)(cid:26)
DocID029808 Rev 3 29/229
47

Functional overview STM32F722xx STM32F723xx
2.16 Voltage regulator
The regulator has four operating modes:
• Regulator ON
– Main regulator mode (MR)
– Low power regulator (LPR)
– Power-down
• Regulator OFF
2.16.1 Regulator ON
On packages embedding the BYPASS_REG pin, the regulator is enabled by holding
BYPASS_REG low. On all other packages, the regulator is always enabled.
There are three power modes configured by software when the regulator is ON:
• MR mode used in Run/sleep modes or in Stop modes
– In Run/Sleep modes
The MR mode is used either in the normal mode (default mode) or the over-drive
mode (enabled by software). A different voltage scaling is provided to reach the
best compromise between maximum frequency and dynamic power consumption.
The over-drive mode allows operating at a higher frequency than the normal mode
for a given voltage scaling.
– In Stop modes
The MR can be configured in two ways during stop mode:
MR operates in normal mode (default mode of MR in stop mode)
MR operates in under-drive mode (reduced leakage mode).
• LPR is used in the Stop modes:
The LP regulator mode is configured by software when entering Stop mode.
Like the MR mode, the LPR can be configured in two ways during stop mode:
– LPR operates in normal mode (default mode when LPR is ON)
– LPR operates in under-drive mode (reduced leakage mode).
• Power-down is used in Standby mode.
The Power-down mode is activated only when entering in Standby mode. The regulator
output is in high impedance and the kernel circuitry is powered down, inducing zero
consumption. The contents of the registers and SRAM are lost.
Refer to Table 3 for a summary of voltage regulator modes versus device operating modes.
The V and V pins must be connected to 2*2.2 µF, ESR < 2 Ω (or 1*4.7 µF, ESR
CAP_1 CAP_2
between 0.1 Ω and 0.2 Ω if only the V pin is provided (on LQFP64 package)).
CAP_1
All the packages have the regulator ON feature.
30/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Functional overview
           Table 3. Voltage regulator configuration mode versus device operating mode(1)
Voltage regulator
|     |     |     | Run mode | Sleep mode |     |     | Stop mode | Standby mode |     |
| --- | --- | --- | -------- | ---------- | --- | --- | --------- | ------------ | --- |
configuration
|     | Normal mode |     | MR  |     | MR  |     | MR or LPR |     | -   |
| --- | ----------- | --- | --- | --- | --- | --- | --------- | --- | --- |
Over-drive
|                  | mode(2) |     | MR  |     | MR  |     | -         |     | -   |
| ---------------- | ------- | --- | --- | --- | --- | --- | --------- | --- | --- |
| Under-drive mode |         |     | -   |     | -   |     | MR or LPR |     | -   |
Power-down
|     |     |     | -   |     | -   |     | -   |     | Yes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
mode
1. ‘-’ means that the corresponding configuration is not available.
| 2.  | The over-drive mode is not available when V |     |     |  = 1.7 to 2.1 V. |     |     |     |     |     |
| --- | ------------------------------------------- | --- | --- | ---------------- | --- | --- | --- | --- | --- |
DD
2.16.2  Regulator OFF
This feature is available only on packages featuring the BYPASS_REG pin. The regulator is
disabled by holding BYPASS_REG high. The regulator OFF mode allows to supply
| externally a V |     |  voltage source through V |     |       |  and V |       |  pins. |     |     |
| -------------- | --- | ------------------------- | --- | ----- | ------ | ----- | ------ | --- | --- |
|                |     | 12                        |     | CAP_1 |        | CAP_2 |        |     |     |
Since the internal voltage scaling is not managed internally, the external voltage value must
be aligned with the targeted maximum frequency.The two 2.2 µF ceramic capacitors should
be replaced by two 100 nF decoupling capacitors.
When the regulator is OFF, there is no more internal monitoring on V . An external power
12
supply supervisor should be used to monitor the V  of the logic power domain. The PA0 pin
12
should be used for this purpose, and act as power-on reset on V 12  power domain.
In regulator OFF mode, the following features are no more supported:
• PA0 cannot be used as a GPIO pin since it allows to reset a part of the V  logic power
12
domain which is not reset by the NRST pin.
•
As long as PA0 is kept low, the debug mode cannot be used under power-on reset. As
a consequence, PA0 and NRST pins must be managed separately if the debug
connection under reset or pre-reset is required.
• The over-drive and under-drive modes are not available.
• The Standby mode is not available.
|     |     |     | DocID029808 Rev 3 |     |     |     |     |     | 31/229 |
| --- | --- | --- | ----------------- | --- | --- | --- | --- | --- | ------ |
47

| Functional overview |     |     |     |     |     |     | STM32F722xx STM32F723xx |
| ------------------- | --- | --- | --- | --- | --- | --- | ----------------------- |
Figure 11. Regulator OFF
(cid:57)(cid:20)(cid:21)
|     |     |     |     | (cid:40)(cid:91)(cid:87)(cid:72)(cid:85)(cid:81)(cid:68)(cid:79)(cid:3)(cid:57) | (cid:3)(cid:83)(cid:82)(cid:90)(cid:72)(cid:85)(cid:3) |     |     |
| --- | --- | --- | --- | ------------------------------------------------------------------------------- | ------------------------------------------------------ | --- | --- |
(cid:38)(cid:36)(cid:51)(cid:66)(cid:20)(cid:18)(cid:21)
|     |     |     |     | (cid:86)(cid:88)(cid:83)(cid:83)(cid:79)(cid:92)(cid:3)(cid:86)(cid:88)(cid:83)(cid:72)(cid:85)(cid:89)(cid:76)(cid:86)(cid:82)(cid:85)                                                                                              |                                                                      | (cid:36)(cid:83)(cid:83)(cid:79)(cid:76)(cid:70)(cid:68)(cid:87)(cid:76)(cid:82)(cid:81)(cid:3)(cid:85)(cid:72)(cid:86)(cid:72)(cid:87)(cid:3)        |     |
| --- | --- | --- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
|     |     |     |     | (cid:40)(cid:91)(cid:87)(cid:17)(cid:3)(cid:85)(cid:72)(cid:86)(cid:72)(cid:87)(cid:3)(cid:70)(cid:82)(cid:81)(cid:87)(cid:85)(cid:82)(cid:79)(cid:79)(cid:72)(cid:85)(cid:3)(cid:68)(cid:70)(cid:87)(cid:76)(cid:89)(cid:72)(cid:3) |                                                                      | (cid:86)(cid:76)(cid:74)(cid:81)(cid:68)(cid:79)(cid:3)(cid:11)(cid:82)(cid:83)(cid:87)(cid:76)(cid:82)(cid:81)(cid:68)(cid:79)(cid:12)(cid:3)(cid:3) |     |
|     |     |     |     | (cid:90)(cid:75)(cid:72)(cid:81)(cid:3)(cid:57)                                                                                                                                                                                      | (cid:3)(cid:3)(cid:31)(cid:3)(cid:48)(cid:76)(cid:81)(cid:3)(cid:57) | (cid:3)(cid:3)                                                                                                                                        |     |
|     |     |     |     |                                                                                                                                                                                                                                      | (cid:38)(cid:36)(cid:51)(cid:66)(cid:20)(cid:18)(cid:21)             | (cid:20)(cid:21)                                                                                                                                      |     |
(cid:57)
|     |     |     |     | (cid:39)(cid:39) | (cid:51)(cid:36)(cid:19) |     | (cid:49)(cid:53)(cid:54)(cid:55)(cid:3)(cid:3) |
| --- | --- | --- | --- | ---------------- | ------------------------ | --- | ---------------------------------------------- |
(cid:57) (cid:39)(cid:39)
(cid:37)(cid:60)(cid:51)(cid:36)(cid:54)(cid:54)(cid:66)(cid:53)(cid:40)(cid:42)
(cid:57)(cid:20)(cid:21)
(cid:57) (cid:38)(cid:36)(cid:51)(cid:66)(cid:20)
(cid:57)
(cid:38)(cid:36)(cid:51)(cid:66)(cid:21)
(cid:68)(cid:76)(cid:20)(cid:27)(cid:23)(cid:28)(cid:27)(cid:57)(cid:22)
The following conditions must be respected:
• V  should always be higher than V  and V to avoid current injection
|     |     | DD  |     |     | CAP_1 | CAP_2  |     |
| --- | --- | --- | --- | --- | ----- | ------ | --- |
between power domains.
•
If the time for V CAP_1  and V CAP_2  to reach V 12  minimum value is faster than the time for
V  to reach 1.7 V, then PA0 should be kept low to cover both conditions: until V
DD CAP_1
and V reach V minimum value and until V reaches 1.7 V (see Figure 12).
|     |     | CAP_2  | 12  |     |     | DD  |     |
| --- | --- | ------ | --- | --- | --- | --- | --- |
• Otherwise, if the time for V  and V to reach V minimum value is slower
|     |     |     |     | CAP_1 | CAP_2  |     | 12  |
| --- | --- | --- | --- | ----- | ------ | --- | --- |
than the time for V  to reach 1.7 V, then PA0 could be asserted low externally (see
DD
Figure 13).
• If V  and V  go below V minimum value and V  is higher than 1.7 V, then a
|     |     | CAP_1 | CAP_2 |     | 12  |     | DD  |
| --- | --- | ----- | ----- | --- | --- | --- | --- |
reset must be asserted on PA0 pin.
Note: The minimum value of V depends on the maximum frequency targeted in the application.
12
| Note: | On the LQFP64 pin package, the V |     |     |     | is not available. |     |     |
| ----- | -------------------------------- | --- | --- | --- | ----------------- | --- | --- |
CAP_2
| 32/229 |     |     |     | DocID029808 Rev 3 |     |     |     |
| ------ | --- | --- | --- | ----------------- | --- | --- | --- |

STM32F722xx STM32F723xx Functional overview
Figure 12. Startup in regulator OFF: slow V slope
DD
- power-down reset risen after V /V stabilization
CAP_1 CAP_2
(cid:57)
(cid:39)(cid:39)
(cid:51)(cid:39)(cid:53)(cid:3)(cid:32)(cid:3)(cid:20)(cid:17)(cid:26)(cid:3)(cid:57)(cid:3)(cid:82)(cid:85)(cid:3)(cid:20)(cid:17)(cid:27)(cid:3)(cid:57)
(cid:57) (cid:18)(cid:57)
(cid:38)(cid:36)(cid:51)(cid:66)(cid:20) (cid:38)(cid:36)(cid:51)(cid:66)(cid:21)
(cid:57)
(cid:20)(cid:21)
(cid:48)(cid:76)(cid:81)(cid:3)(cid:57)
(cid:20)(cid:21)
(cid:87)(cid:76)(cid:80)(cid:72)
(cid:49)(cid:53)(cid:54)(cid:55)
(cid:87)(cid:76)(cid:80)(cid:72) (cid:68)(cid:76)(cid:20)(cid:27)(cid:23)(cid:28)(cid:20)(cid:73)
1. This figure is valid whatever the internal reset mode (ON or OFF).
Figure 13. Startup in regulator OFF mode: fast V slope
DD
- power-down reset risen before V /V stabilization
CAP_1 CAP_2
(cid:57)(cid:39)(cid:39)
(cid:51)(cid:39)(cid:53)(cid:3)(cid:32)(cid:3)(cid:20)(cid:17)(cid:26)(cid:3)(cid:57)(cid:3)(cid:82)(cid:85)(cid:3)(cid:20)(cid:17)(cid:27)(cid:3)(cid:57)(cid:3)(cid:3)
(cid:57)(cid:38)(cid:36)(cid:51)(cid:66)(cid:20)(cid:15)(cid:57)(cid:38)(cid:36)(cid:51)(cid:66)(cid:21)
(cid:57)(cid:20)(cid:21)
(cid:48)(cid:76)(cid:81)(cid:3)(cid:57)(cid:20)(cid:21)
(cid:87)(cid:76)(cid:80)(cid:72)
(cid:49)(cid:53)(cid:54)(cid:55)
(cid:51)(cid:36)(cid:19)(cid:3)(cid:68)(cid:86)(cid:86)(cid:72)(cid:85)(cid:87)(cid:72)(cid:71)(cid:3)(cid:72)(cid:91)(cid:87)(cid:72)(cid:85)(cid:81)(cid:68)(cid:79)(cid:79)(cid:92)(cid:3)(cid:3)
(cid:87)(cid:76)(cid:80)(cid:72)
(cid:68)(cid:76)(cid:20)(cid:27)(cid:23)(cid:28)(cid:21)(cid:72)
1. This figure is valid whatever the internal reset mode (ON or OFF).
DocID029808 Rev 3 33/229
47

Functional overview STM32F722xx STM32F723xx
2.16.3 Regulator ON/OFF and internal reset ON/OFF availability
Table 4. Regulator ON/OFF and internal reset ON/OFF availability
Package Regulator ON Regulator OFF Internal reset ON Internal reset OFF
LQFP64,
Yes No
LQFP100
Yes No
LQFP144
Yes Yes
LQFP176, Yes Yes PDR_ON set to V PDR_ON set to V
DD SS
UFBGA144, BYPASS_REG set BYPASS_REG set
UFBGA176 to V to V
SS DD
2.17 Real-time clock (RTC), backup SRAM and backup registers
The RTC is an independent BCD timer/counter. It supports the following features:
• Calendar with subsecond, seconds, minutes, hours (12 or 24 format), week day, date,
month, year, in BCD (binary-coded decimal) format.
• Automatic correction for 28, 29 (leap year), 30, and 31 days of the month.
• Two programmable alarms.
• On-the-fly correction from 1 to 32767 RTC clock pulses. This can be used to
synchronize it with a master clock.
• Reference clock detection: a more precise second source clock (50 or 60 Hz) can be
used to enhance the calendar precision.
• Digital calibration circuit with 0.95 ppm resolution, to compensate for quartz crystal
inaccuracy.
• Three anti-tamper detection pins with programmable filter.
• Timestamp feature which can be used to save the calendar content. This function can
be triggered by an event on the timestamp pin, or by a tamper event, or by a switch to
V mode.
BAT
• 17-bit auto-reload wakeup timer (WUT) for periodic events with programmable
resolution and period.
The RTC and the 32 backup registers are supplied through a switch that takes power either
from the V supply when present or from the V pin.
DD BAT
The backup registers are 32-bit registers used to store 128 bytes of user application data
when VDD power is not present. They are not reset by a system or power reset, or when the
device wakes up from Standby mode.
The RTC clock sources can be:
• A 32.768 kHz external crystal (LSE)
• An external resonator or oscillator(LSE)
• The internal low power RC oscillator (LSI, with typical frequency of 32 kHz)
• The high-speed external clock (HSE) divided by 32
The RTC is functional in V mode and in all low-power modes when it is clocked by the
BAT
LSE. When clocked by the LSI, the RTC is not functional in V mode, but is functional in
BAT
all low-power modes.
34/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Functional overview
All the RTC events (Alarm, WakeUp Timer, Timestamp or Tamper) can generate an interrupt
and wakeup the device from the low-power modes.
2.18 Low-power modes
The devices support three low-power modes to achieve the best compromise between low
power consumption, short startup time and available wakeup sources:
• Sleep mode
In Sleep mode, only the CPU is stopped. All peripherals continue to operate and can
wake up the CPU when an interrupt/event occurs.
• Stop mode
The Stop mode achieves the lowest power consumption while retaining the contents of
SRAM and registers. All clocks in the 1.2 V domain are stopped, the PLL, the HSI RC
and the HSE crystal oscillators are disabled.
The voltage regulator can be put either in main regulator mode (MR) or in low-power
mode (LPR). Both modes can be configured as follows (see Table 5: Voltage regulator
modes in stop mode):
– Normal mode (default mode when MR or LPR is enabled)
– Under-drive mode.
The device can be woken up from the Stop mode by any of the EXTI line (the EXTI line
source can be one of the 16 external lines, the PVD output, the RTC alarm / wakeup /
tamper / time stamp events, the USB OTG FS/HS wakeup and the LPTIM1
asynchronous interrupt).
Table 5. Voltage regulator modes in stop mode
Voltage regulator
Main regulator (MR) Low-power regulator (LPR)
configuration
Normal mode MR ON LPR ON
Under-drive mode MR in under-drive mode LPR in under-drive mode
• Standby mode
The Standby mode is used to achieve the lowest power consumption. The internal
voltage regulator is switched off so that the entire 1.2 V domain is powered off. The
PLL, the HSI RC and the HSE crystal oscillators are also switched off. After entering
Standby mode, the SRAM and register contents are lost except for registers in the
backup domain and the backup SRAM when selected.
The device exits the Standby mode when an external reset (NRST pin), an IWDG reset,
a rising or falling edge on one of the 6 WKUP pins (PA0, PA2, PC1, PC13, PI8, PI11),
or an RTC alarm / wakeup / tamper /time stamp event occurs.
The Standby mode is not supported when the embedded voltage regulator is bypassed
and the 1.2 V domain is controlled by an external power.
DocID029808 Rev 3 35/229
47

Functional overview STM32F722xx STM32F723xx
2.19 V operation
BAT
The V pin allows to power the device V domain from an external battery, an external
BAT BAT
supercapacitor, or from V when no external battery and an external supercapacitor are
DD
present.
The V operation is activated when V is not present.
BAT DD
The V pin supplies the RTC, the backup registers and the backup SRAM.
BAT
Note: When the microcontroller is supplied from V , external interrupts and RTC alarm/events
BAT
do not exit it from V
BAT
operation.
When the PDR_ON pin is connected to V
SS
(Internal Reset OFF), the V
BAT
functionality is
no more available and the V
BAT
pin should be connected to VDD.
2.20 Timers and watchdogs
The devices include two advanced-control timers, eight general-purpose timers, two basic
timers and two watchdog timers.
All timer counters can be frozen in debug mode.
Table 6 compares the features of the advanced-control, general-purpose and basic timers.
36/229 DocID029808 Rev 3

| STM32F722xx STM32F723xx |     |     |     |     |     |     |     | Functional overview |     |
| ----------------------- | --- | --- | --- | --- | --- | --- | --- | ------------------- | --- |

Table 6. Timer feature comparison
|        |       |            |          |            |            |          |         | Max        | Max      |
| ------ | ----- | ---------- | -------- | ---------- | ---------- | -------- | ------- | ---------- | -------- |
|        |       |            |          |            | DMA        | Capture/ | Complem |            |          |
| Timer  |       | Counter    | Counter  | Prescaler  |            |          |         | interface  | timer    |
|        | Timer |            |          |            | request    | compare  | entary  |            |          |
| type   |       | resolution | type     | factor     |            |          |         | clock      | clock    |
|        |       |            |          |            | generation | channels | output  |            | (MHz)(1) |
(MHz)
Any
Up,
| Advanced | TIM1,  |        |        | integer    |     |     |     |     |     |
| -------- | ------ | ------ | ------ | ---------- | --- | --- | --- | --- | --- |
|          |        | 16-bit | Down,  |            | Yes | 4   | Yes | 108 | 216 |
| -control | TIM8   |        |        | between 1  |     |     |     |     |     |
Up/down
and 65536
Any
Up,
|     | TIM2,  |        |        | integer    |     |     |     |     |         |
| --- | ------ | ------ | ------ | ---------- | --- | --- | --- | --- | ------- |
|     |        | 32-bit | Down,  |            | Yes | 4   | No  | 54  | 108/216 |
|     | TIM5   |        |        | between 1  |     |     |     |     |         |
Up/down
and 65536
Any
Up,
|     | TIM3,  |        |        | integer    |     |     |     |     |         |
| --- | ------ | ------ | ------ | ---------- | --- | --- | --- | --- | ------- |
|     |        | 16-bit | Down,  |            | Yes | 4   | No  | 54  | 108/216 |
|     | TIM4   |        |        | between 1  |     |     |     |     |         |
Up/down
and 65536
Any
integer
|     | TIM9 | 16-bit | Up  |     | No  | 2   | No  | 108 | 216 |
| --- | ---- | ------ | --- | --- | --- | --- | --- | --- | --- |
between 1
and 65536
General
purpose
Any
|     | TIM10,  |        |     | integer    |     |     |     |     |     |
| --- | ------- | ------ | --- | ---------- | --- | --- | --- | --- | --- |
|     |         | 16-bit | Up  |            | No  | 1   | No  | 108 | 216 |
|     | TIM11   |        |     | between 1  |     |     |     |     |     |
and 65536
Any
integer
|     | TIM12 | 16-bit | Up  |     | No  | 2   | No  | 54  | 108/216 |
| --- | ----- | ------ | --- | --- | --- | --- | --- | --- | ------- |
between 1
and 65536
Any
|     | TIM13,  |        |     | integer    |     |     |     |     |         |
| --- | ------- | ------ | --- | ---------- | --- | --- | --- | --- | ------- |
|     |         | 16-bit | Up  |            | No  | 1   | No  | 54  | 108/216 |
|     | TIM14   |        |     | between 1  |     |     |     |     |         |
and 65536
Any
|       | TIM6,  |        |     | integer    |     |     |     |     |         |
| ----- | ------ | ------ | --- | ---------- | --- | --- | --- | --- | ------- |
| Basic |        | 16-bit | Up  |            | Yes | 0   | No  | 54  | 108/216 |
|       | TIM7   |        |     | between 1  |     |     |     |     |         |
and 65536
1. The maximum timer clock is either 108 or 216 MHz depending on TIMPRE bit configuration in the RCC_DCKCFGR
register.
|     |     |     |     | DocID029808 Rev 3 |     |     |     |     | 37/229 |
| --- | --- | --- | --- | ----------------- | --- | --- | --- | --- | ------ |
47

Functional overview STM32F722xx STM32F723xx
2.20.1 Advanced-control timers (TIM1, TIM8)
The advanced-control timers (TIM1, TIM8) can be seen as three-phase PWM generators
multiplexed on 6 channels. They have complementary PWM outputs with programmable
inserted dead times. They can also be considered as complete general-purpose timers.
Their 4 independent channels can be used for:
• Input capture
• Output compare
• PWM generation (edge- or center-aligned modes)
• One-pulse mode output
If configured as standard 16-bit timers, they have the same features as the general-purpose
TIMx timers. If configured as 16-bit PWM generators, they have full modulation capability (0-
100%).
The advanced-control timer can work together with the TIMx timers via the Timer Link
feature for synchronization or event chaining.
The TIM1 and TIM8 support independent DMA request generation.
2.20.2 General-purpose timers (TIMx)
There are ten synchronizable general-purpose timers embedded in the STM32F722xx and
STM32F723xx devices (see Table 6 for differences).
• TIM2, TIM3, TIM4, TIM5
The STM32F722xx and STM32F723xx include 4 full-featured general-purpose timers:
TIM2, TIM5, TIM3, and TIM4.The TIM2 and TIM5 timers are based on a 32-bit auto-
reload up/downcounter and a 16-bit prescaler. The TIM3 and TIM4 timers are based on
a 16-bit auto-reload up/downcounter and a 16-bit prescaler. They all feature 4
independent channels for input capture/output compare, PWM or one-pulse mode
output. This gives up to 16 input capture/output compare/PWMs on the largest
packages.
The TIM2, TIM3, TIM4, TIM5 general-purpose timers can work together, or with the
other general-purpose timers and the advanced-control timers TIM1 and TIM8 via the
Timer Link feature for synchronization or event chaining.
Any of these general-purpose timers can be used to generate PWM outputs.
TIM2, TIM3, TIM4, TIM5 all have independent DMA request generation. They are
capable of handling quadrature (incremental) encoder signals and the digital outputs
from 1 to 4 hall-effect sensors.
• TIM9, TIM10, TIM11, TIM12, TIM13, and TIM14
These timers are based on a 16-bit auto-reload upcounter and a 16-bit prescaler.
TIM10, TIM11, TIM13, and TIM14 feature one independent channel, whereas TIM9
and TIM12 have two independent channels for input capture/output compare, PWM or
one-pulse mode output. They can be synchronized with the TIM2, TIM3, TIM4, TIM5
full-featured general-purpose timers. They can also be used as simple time bases.
2.20.3 Basic timers TIM6 and TIM7
These timers are mainly used for the DAC trigger and waveform generation. They can also
be used as a generic 16-bit time base.
The TIM6 and TIM7 support independent DMA request generation.
38/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Functional overview
2.20.4 Low-power timer (LPTIM1)
The low-power timer has an independent clock and is running also in Stop mode if it is
clocked by LSE, LSI or an external clock. It is able to wakeup the devices from Stop mode.
This low-power timer supports the following features:
• 16-bit up counter with 16-bit autoreload register
• 16-bit compare register
• Configurable output: pulse, PWM
• Continuous / one-shot mode
• Selectable software / hardware input trigger
• Selectable clock source:
• Internal clock source: LSE, LSI, HSI or APB clock
• External clock source over LPTIM input (working even with no internal clock source
running, used by the Pulse Counter Application)
• Programmable digital glitch filter
• Encoder mode
2.20.5 Independent watchdog
The independent watchdog is based on a 12-bit downcounter and 8-bit prescaler. It is
clocked from an independent 32 kHz internal RC and as it operates independently from the
main clock, it can operate in Stop and Standby modes. It can be used either as a watchdog
to reset the device when a problem occurs, or as a free-running timer for application timeout
management. It is hardware- or software-configurable through the option bytes.
2.20.6 Window watchdog
The window watchdog is based on a 7-bit downcounter that can be set as free-running. It
can be used as a watchdog to reset the device when a problem occurs. It is clocked from
the main clock. It has an early warning interrupt capability and the counter can be frozen in
debug mode.
2.20.7 SysTick timer
This timer is dedicated to real-time operating systems, but could also be used as a standard
downcounter. It features:
• A 24-bit downcounter
• Autoreload capability
• Maskable system interrupt generation when the counter reaches 0
• Programmable clock source
DocID029808 Rev 3 39/229
47

| Functional overview |     |     |     | STM32F722xx STM32F723xx |     |
| ------------------- | --- | --- | --- | ----------------------- | --- |
2
| 2.21  | Inter-integrated circuit interface (I |     | C)  |     |     |
| ----- | ------------------------------------- | --- | --- | --- | --- |
The device embeds 3 I2Cs. Refer to Table 7: I2C implementation for the features
implementation.
The I2C bus interface handles communications between the microcontroller and the serial
I2C bus. It controls all I2C bus-specific sequencing, protocol, arbitration and timing.
The I2C peripheral supports:
•
I2C-bus specification and user manual rev. 5 compatibility:
– Slave and master modes, multimaster capability
– Standard-mode (Sm), with a bitrate up to 100 kbit/s
– Fast-mode (Fm), with a bitrate up to 400 kbit/s
– Fast-mode Plus (Fm+), with a bitrate up to 1 Mbit/s and 20 mA output drive I/Os
– 7-bit and 10-bit addressing mode, multiple 7-bit slave addresses
– Programmable setup and hold times
– Optional clock stretching
•
System Management Bus (SMBus) specification rev 2.0 compatibility:
– Hardware PEC (Packet Error Checking) generation and verification with ACK
control
– Address resolution protocol (ARP) support
– SMBus alert
• Power System Management Protocol (PMBusTM) specification rev 1.1 compatibility
• Independent clock: a choice of independent clock sources allowing the I2C
communication speed to be independent from the PCLK reprogramming.
•
Programmable analog and digital noise filters
•
1-byte buffer with DMA capability
|     |                                  | Table 7. I2C implementation |     |           |      |
| --- | -------------------------------- | --------------------------- | --- | --------- | ---- |
|     |                                  | I2C features(1)             |     | I2C1 I2C2 | I2C3 |
|     | Standard-mode (up to 100 kbit/s) |                             |     | X X       | X    |
|     | Fast-mode (up to 400 kbit/s)     |                             |     | X X       | X    |
Fast-mode Plus with 20 mA output drive I/Os (up to 1 Mbit/s) X X X
|     | Programmable analog and digital noise filters |     |     | X X | X   |
| --- | --------------------------------------------- | --- | --- | --- | --- |
|     | SMBus/PMBus hardware support                  |     |     | X X | X   |
|     | Independent clock                             |     |     | X X | X   |
1. X: supported.
| 40/229 |     | DocID029808 Rev 3 |     |     |     |
| ------ | --- | ----------------- | --- | --- | --- |

STM32F722xx STM32F723xx Functional overview
2.22 Universal synchronous/asynchronous receiver transmitters
(USART)
The device embeds USARTs. Refer to Table 8: USART implementation for the features
implementation.
The universal synchronous asynchronous receiver transmitter (USART) offers a flexible
means of full-duplex data exchange with external equipment requiring an industry standard
NRZ asynchronous serial data format.
The USART peripheral supports:
• Full-duplex asynchronous communications
• Configurable oversampling method by 16 or 8 to give flexibility between speed and
clock tolerance
• Dual clock domain allowing convenient baud rate programming independent from the
PCLK reprogramming
• A common programmable transmit and receive baud rate of up to 27 Mbit/s when
USART clock source is system clock frequency (max is 216 MHz) and oversampling by
8 is used.
• Auto baud rate detection
• Programmable data word length (7 or 8 or 9 bits) word length
• Programmable data order with MSB-first or LSB-first shifting
• Progarmmable parity (odd, even, no parity)
• Configurable stop bits (1 or 1.5 or 2 stop bits)
• Synchronous mode and clock output for synchronous communications
• Single-wire half-duplex communications
• Separate signal polarity control for transmission and reception
• Swappable Tx/Rx pin configuration
• Hardware flow control for modem and RS-485 transceiver
• Multiprocessor communications
• LIN master synchronous break send capability and LIN slave break detection capability
• IrDA SIR encoder decoder supporting 3/16 bit duration for normal mode
• Smartcard mode ( T=0 and T=1 asynchronous protocols for Smartcards as defined in
the ISO/IEC 7816-3 standard)
• Support for Modbus communication
Table 8 summarizes the implementation of all U(S)ARTs instances
Table 8. USART implementation
features(1) USART1/2/3/6 UART4/5/7/8
Data Length 7, 8 and 9 bits
Hardware flow control for modem X X
Continuous communication using DMA X X
Multiprocessor communication X X
Synchronous mode X -
DocID029808 Rev 3 41/229
47

Functional overview STM32F722xx STM32F723xx
Table 8. USART implementation (continued)
features(1)
| USART1/2/3/6                          | UART4/5/7/8 |     |
| ------------------------------------- | ----------- | --- |
| Smartcard mode                        | X           | -   |
| Single-wire half-duplex communication | X           | X   |
| IrDA SIR ENDEC block                  | X           | X   |
| LIN mode                              | X           | X   |
| Dual clock domain                     | X           | X   |
| Receiver timeout interrupt            | X           | X   |
| Modbus communication                  | X           | X   |
| Auto baud rate detection              | X           | X   |
| Driver Enable                         | X           | X   |
1. X: supported.
2.23  Serial peripheral interface (SPI)/inter- integrated sound
interfaces (I 2 S)
The devices feature up to five SPIs in slave and master modes in full-duplex and simplex
communication modes. SPI1, SPI4, and SPI5 can communicate at up to 50 Mbit/s, SPI2
and SPI3 can communicate at up to 25 Mbit/s. The 3-bit prescaler gives 8 master mode
frequencies and the frame is configurable from 4 to 16 bits. The SPI interfaces support the
NSS pulse mode, TI mode and Hardware CRC calculation. All the SPIs can be served by
the DMA controller.
Three standard I2S interfaces (multiplexed with SPI1, SPI2 and SPI3) are available. They
can be operated in master or slave mode, in simplex communication modes, and can be
configured to operate with a 16-/32-bit resolution as an input or output channel. Audio
sampling frequencies from 8 kHz up to 192 kHz are supported. When either or both of the
I2S interfaces is/are configured in master mode, the master clock can be output to the
external DAC/CODEC at 256 times the sampling frequency.
All I2Sx can be served by the DMA controller.
2.24  Serial audio interface (SAI)
The devices embed two serial audio interfaces.
The serial audio interface is based on two independent audio subblocks which can operate
as transmitter or receiver with their FIFO. Many audio protocols are supported by each
block: I2S standards, LSB or MSB-justified, PCM/DSP, TDM, AC’97 and SPDIF output,
supporting audio sampling frequencies from 8 kHz up to 192 kHz. Both subblocks can be
configured in master or in slave mode.
In master mode, the master clock can be output to the external DAC/CODEC at 256 times of
the sampling frequency.
The two sub-blocks can be configured in synchronous mode when full-duplex mode is
required.
42/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Functional overview
SAI1 and SAI2 can be served by the DMA controller
2.25 Audio PLL (PLLI2S)
The devices feature an additional dedicated PLL for audio I2S and SAI applications. It allows
to achieve an error-free I2S sampling clock accuracy without compromising on the CPU
performance, while using USB peripherals.
The PLLI2S configuration can be modified to manage an I2S/SAI sample rate change
without disabling the main PLL (PLL) used for CPU and USB interfaces.
The audio PLL can be programmed with very low error to obtain sampling rates ranging
from 8 KHz to 192 KHz.
In addition to the audio PLL, a master clock input pin can be used to synchronize the
I2S/SAI flow with an external PLL (or Codec output).
2.26 Audio PLL (PLLSAI)
An additional PLL dedicated to audio is used for the SAI1 peripheral in case the PLLI2S is
programmed to achieve another audio sampling frequency (49.152 MHz or 11.2896 MHz)
and the audio application requires both sampling frequencies simultaneously.
2.27 SD/SDIO/MMC card host interface (SDMMC)
SDMMC host interfaces are available, that support MultiMediaCard System Specification
Version 4.2 in three different databus modes: 1-bit (default), 4-bit and 8-bit.
The interface allows data transfer at up to 50 MHz, and is compliant with the SD Memory
Card Specification Version 2.0.
The SDMMC Card Specification Version 2.0 is also supported with two different databus
modes: 1-bit (default) and 4-bit.
The current version supports only one SD/SDMMC/MMC4.2 card at any one time and a
stack of MMC4.1 or previous.
The SDMMC can be served by the DMA controller
2.28 Controller area network (bxCAN)
The CAN is compliant with the 2.0A and B (active) specifications with a bit rate up to 1
Mbit/s. It can receive and transmit standard frames with 11-bit identifiers as well as
extended frames with 29-bit identifiers. The CAN has three transmit mailboxes, two receive
FIFOs with 3 stages and 28 shared scalable filter banks (all of them can be used even if one
CAN is used). 256 bytes of SRAM are allocated to the CAN.
DocID029808 Rev 3 43/229
47

Functional overview STM32F722xx STM32F723xx
2.29 Universal serial bus on-the-go full-speed (OTG_FS)
The device embeds an USB OTG full-speed device/host/OTG peripheral with integrated
transceivers. The USB OTG FS peripheral is compliant with the USB 2.0 specification and
with the OTG 2.0 specification. It has software-configurable endpoint setting and supports
suspend/resume. The USB OTG controller requires a dedicated 48 MHz clock that is
generated by a PLL connected to the HSE oscillator.
The major features are:
• Combined Rx and Tx FIFO size of 1.28 Kbytes with dynamic FIFO sizing
• Supports the session request protocol (SRP) and host negotiation protocol (HNP)
• 1 bidirectional control endpoint + 5 IN endpoints + 5 OUT endpoints
• 12 host channels with periodic OUT support
• Software configurable to OTG1.3 and OTG2.0 modes of operation
• USB 2.0 LPM (Link Power Management) support
• Internal FS OTG PHY support
• HNP/SNP/IP inside (no need for any external resistor)
• BCD support
For the OTG/Host modes, a power switch is needed in case bus-powered devices are
connected
2.30 Universal serial bus on-the-go high-speed (OTG_HS)
The device embeds an USB OTG high-speed (up to 480 Mbit/s) device/host/OTG
peripheral. The USB OTG HS supports both full-speed and high-speed operations. It
integrates the transceivers for full-speed operation (12 Mbit/s).
The STM32F722xx devices feature a UTMI low-pin interface (ULPI) for high-speed
operation (480 Mbit/s). When using the USB OTG HS in HS mode, an external PHY device
connected to the ULPI is required.
The STM32F723xx devices feature an integrated PHY HS.
The USB OTG HS peripheral is compliant with the USB 2.0 specification and with the OTG
2.0 specification. It has a software-configurable endpoint setting and supports
suspend/resume. The USB OTG controller requires a dedicated 48 MHz clock that is
generated by a PLL connected to the HSE oscillator.
The major features are:
• Combined Rx and Tx FIFO size of 4 Kbytes with dynamic FIFO sizing
• Supports the session request protocol (SRP) and host negotiation protocol (HNP)
• 8 bidirectional endpoints
• 16 host channels with periodic OUT support
• Software configurable to OTG1.3 and OTG2.0 modes of operation
• USB 2.0 LPM (Link Power Management) support
• For the STM32F722xx devices: External HS or HS OTG operation supporting ULPI in
SDR mode. The OTG PHY is connected to the microcontroller ULPI port through 12
signals. It can be clocked using the 60 MHz output.
• For the STM32F723xx devices: Internal HS OTG PHY support.
44/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Functional overview
• Internal USB DMA
• HNP/SNP/IP inside (no need for any external resistor)
• For OTG/Host modes, a power switch is needed in case bus-powered devices are
connected
Universal Serial Bus controller on-the-go High-Speed PHY controller
(USBPHYC) only on STM32F723xx devices.
The USB HS PHY controller:
– Sets the PHYPLL1/2 values for the PHY HS
– Sets the other controls on the PHY HS
– Controls and monitors the USB PHY’s LDO
2.31 Random number generator (RNG)
All the devices embed an RNG that delivers 32-bit random numbers generated by an
integrated analog circuit.
2.32 General-purpose input/outputs (GPIOs)
Each of the GPIO pins can be configured by software as output (push-pull or open-drain,
with or without pull-up or pull-down), as input (floating, with or without pull-up or pull-down)
or as peripheral alternate function. Most of the GPIO pins are shared with digital or analog
alternate functions. All GPIOs are high-current-capable and have speed selection to better
manage internal noise, power consumption and electromagnetic emission.
The I/O configuration can be locked if needed by following a specific sequence in order to
avoid spurious writing to the I/Os registers.
A Fast I/O handling allows a maximum I/O toggling up to 108 MHz.
2.33 Analog-to-digital converters (ADCs)
Three 12-bit analog-to-digital converters are embedded and each ADC shares up to 16
external channels, performing conversions in the single-shot or scan mode. In the scan
mode, an automatic conversion is performed on a selected group of analog inputs.
Additional logic functions embedded in the ADC interface allow:
• Simultaneous sample and hold
• Interleaved sample and hold
The ADC can be served by the DMA controller. An analog watchdog feature allows very
precise monitoring of the converted voltage of one, some or all selected channels. An
interrupt is generated when the converted voltage is outside the programmed thresholds.
To synchronize A/D conversion and timers, the ADCs could be triggered by any of TIM1,
TIM2, TIM3, TIM4, TIM5, or TIM8 timer.
DocID029808 Rev 3 45/229
47

Functional overview STM32F722xx STM32F723xx
2.34 Temperature sensor
The temperature sensor has to generate a voltage that varies linearly with the temperature.
The conversion range is between 1.7 V and 3.6 V. The temperature sensor is internally
connected to the same input channel as V , ADC1_IN18, which is used to convert the
BAT
sensor output voltage into a digital value. When the temperature sensor and V
BAT
conversion are enabled at the same time, only V conversion is performed.
BAT
As the offset of the temperature sensor varies from chip to chip due to process variation, the
internal temperature sensor is mainly suitable for applications that detect temperature
changes instead of absolute temperatures. If an accurate temperature reading is needed,
then an external temperature sensor part should be used.
2.35 Digital-to-analog converter (DAC)
The two 12-bit buffered DAC channels can be used to convert two digital signals into two
analog voltage signal outputs.
This dual digital Interface supports the following features:
• Two DAC converters: one for each output channel
• 8-bit or 12-bit monotonic output
• Left or right data alignment in 12-bit mode
• Synchronized update capability
• Noise-wave generation
• Triangular-wave generation
• Dual DAC channel independent or simultaneous conversions
• DMA capability for each channel
• External triggers for conversion
• Input voltage reference V
REF+
Eight DAC trigger inputs are used in the device. The DAC channels are triggered through
the timer update outputs that are also connected to different DMA streams.
2.36 Serial wire JTAG debug port (SWJ-DP)
The ARM SWJ-DP interface is embedded, and is a combined JTAG and serial wire debug
port that enables either a serial wire debug or a JTAG probe to be connected to the target.
The debug is performed using 2 pins only instead of 5 required by the JTAG (JTAG pins
could be re-used as GPIO with alternate function): the JTAG TMS and TCK pins are shared
with SWDIO and SWCLK, respectively, and a specific sequence on the TMS pin is used to
switch between JTAG-DP and SW-DP.
46/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Functional overview
2.37 Embedded Trace Macrocell™
The ARM Embedded Trace Macrocell provides a greater visibility of the instruction and data
flow inside the CPU core by streaming compressed data at a very high rate from the
STM32F722xx and STM32F723xx device through a small number of ETM pins to an
external hardware trace port analyzer (TPA) device. The TPA is connected to a host
computer using the USB or any other high-speed channel. The real-time instruction and
data flow activity can be recorded and then formatted for display on the host computer that
runs the debugger software. The TPA hardware is commercially available from common
development tool vendors.
The Embedded Trace Macrocell operates with third party debugger software tools.
DocID029808 Rev 3 47/229
47

Pinouts and pin description STM32F722xx STM32F723xx
3  Pinouts and pin description
Figure 14. STM32F722xx LQFP64 pinout
(cid:19)(cid:55)(cid:50)(cid:50)(cid:37)
(cid:3)(cid:3)(cid:3)(cid:3)(cid:21)(cid:39)(cid:51)
|     |     |                                                                            |                                   |                                                                            |                                                    | (cid:21)(cid:20)(cid:38)(cid:51) (cid:20)(cid:20)(cid:38)(cid:51) (cid:19)(cid:20)(cid:38)(cid:51) | (cid:24)(cid:20)(cid:36)(cid:51) (cid:23)(cid:20)(cid:36)(cid:51) |
| --- | --- | -------------------------------------------------------------------------- | --------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
|     |     | (cid:39)(cid:39)(cid:57) (cid:54)(cid:54)(cid:57) (cid:28)(cid:37)(cid:51) | (cid:27)(cid:37)(cid:51)          | (cid:26)(cid:37)(cid:51) (cid:25)(cid:37)(cid:51) (cid:24)(cid:37)(cid:51) | (cid:23)(cid:37)(cid:51) (cid:22)(cid:37)(cid:51)  |                                                                                                    |                                                                   |
|     |     | (cid:25)(cid:23) (cid:25)(cid:22) (cid:25)(cid:21)                         | (cid:25)(cid:20) (cid:25)(cid:19) | (cid:24)(cid:28) (cid:24)(cid:27) (cid:24)(cid:26)                         | (cid:24)(cid:25) (cid:24)(cid:24) (cid:24)(cid:23) | (cid:24)(cid:22) (cid:24)(cid:21) (cid:24)(cid:20)                                                 | (cid:24)(cid:19) (cid:23)(cid:28)                                 |
(cid:23)(cid:27) (cid:57)(cid:39)(cid:39)
(cid:57)(cid:37)(cid:36)(cid:55) (cid:20)
(cid:57)(cid:54)(cid:54)
|                                                                                                          | (cid:51)(cid:38)(cid:20)(cid:22) | (cid:21) |     |     |     |     | (cid:23)(cid:26)                                  |
| -------------------------------------------------------------------------------------------------------- | -------------------------------- | -------- | --- | --- | --- | --- | ------------------------------------------------- |
| (cid:51)(cid:38)(cid:20)(cid:23)(cid:16)(cid:50)(cid:54)(cid:38)(cid:22)(cid:21)(cid:66)(cid:44)(cid:49) |                                  | (cid:22) |     |     |     |     | (cid:23)(cid:25) (cid:51)(cid:36)(cid:20)(cid:22) |
(cid:51)(cid:38)(cid:20)(cid:24)(cid:16)(cid:50)(cid:54)(cid:38)(cid:22)(cid:21)(cid:66)(cid:50)(cid:56)(cid:55) (cid:23) (cid:23)(cid:24) (cid:51)(cid:36)(cid:20)(cid:21)
| (cid:51)(cid:43)(cid:19)(cid:16)(cid:50)(cid:54)(cid:38)(cid:66)(cid:44)(cid:49) |     | (cid:24) |     |     |     |     | (cid:23)(cid:23) (cid:51)(cid:36)(cid:20)(cid:20) |
| -------------------------------------------------------------------------------- | --- | -------- | --- | --- | --- | --- | ------------------------------------------------- |
(cid:51)(cid:36)(cid:20)(cid:19)
| (cid:51)(cid:43)(cid:20)(cid:16)(cid:50)(cid:54)(cid:38)(cid:66)(cid:50)(cid:56)(cid:55) |                                  | (cid:25)(cid:3)(cid:3) |     |                                                  |     |     | (cid:23)(cid:22)                          |
| ---------------------------------------------------------------------------------------- | -------------------------------- | ---------------------- | --- | ------------------------------------------------ | --- | --- | ----------------------------------------- |
|                                                                                          | (cid:49)(cid:53)(cid:54)(cid:55) | (cid:26)(cid:3)(cid:3) |     |                                                  |     |     | (cid:23)(cid:21) (cid:51)(cid:36)(cid:28) |
|                                                                                          | (cid:51)(cid:38)(cid:19)         |                        |     |                                                  |     |     | (cid:51)(cid:36)(cid:27)                  |
|                                                                                          |                                  | (cid:27)(cid:3)(cid:3) |     |                                                  |     |     | (cid:23)(cid:20)                          |
|                                                                                          | (cid:51)(cid:38)(cid:20)         | (cid:28)(cid:3)(cid:3) |     | (cid:47)(cid:52)(cid:41)(cid:51)(cid:25)(cid:23) |     |     | (cid:23)(cid:19) (cid:51)(cid:38)(cid:28) |
|                                                                                          | (cid:51)(cid:38)(cid:21)         |                        |     |                                                  |     |     | (cid:22)(cid:28) (cid:51)(cid:38)(cid:27) |
(cid:20)(cid:19)
|     | (cid:51)(cid:38)(cid:22)         | (cid:20)(cid:20) |     |     |     |     | (cid:22)(cid:27) (cid:51)(cid:38)(cid:26) |
| --- | -------------------------------- | ---------------- | --- | --- | --- | --- | ----------------------------------------- |
|     | (cid:57)(cid:54)(cid:54)(cid:36) |                  |     |     |     |     | (cid:22)(cid:26) (cid:51)(cid:38)(cid:25) |
(cid:20)(cid:21)
|                                                                  | (cid:57)(cid:39)(cid:39)(cid:36) | (cid:20)(cid:22) |     |     |     |     | (cid:22)(cid:25) (cid:51)(cid:37)(cid:20)(cid:24) |
| ---------------------------------------------------------------- | -------------------------------- | ---------------- | --- | --- | --- | --- | ------------------------------------------------- |
| (cid:51)(cid:36)(cid:19)(cid:16)(cid:58)(cid:46)(cid:56)(cid:51) |                                  | (cid:20)(cid:23) |     |     |     |     | (cid:22)(cid:24) (cid:51)(cid:37)(cid:20)(cid:23) |
(cid:51)(cid:37)(cid:20)(cid:22)
|     | (cid:51)(cid:36)(cid:20) | (cid:20)(cid:24)                                                           |                                                   |                                                                            |                                                                            |                                                                                                                    | (cid:22)(cid:23)                                  |
| --- | ------------------------ | -------------------------------------------------------------------------- | ------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------- |
|     | (cid:51)(cid:36)(cid:21) | (cid:20)(cid:25)                                                           |                                                   |                                                                            |                                                                            |                                                                                                                    | (cid:22)(cid:22) (cid:51)(cid:37)(cid:20)(cid:21) |
|     |                          | (cid:20)(cid:26) (cid:20)(cid:27) (cid:20)(cid:28)                         | (cid:21)(cid:19) (cid:21)(cid:20)                 | (cid:21)(cid:21) (cid:21)(cid:22) (cid:21)(cid:23)                         | (cid:21)(cid:24) (cid:21)(cid:25) (cid:21)(cid:26)                         | (cid:21)(cid:27) (cid:21)(cid:28) (cid:22)(cid:19)                                                                 | (cid:22)(cid:20) (cid:22)(cid:21)                 |
|     |                          | (cid:22)(cid:36)(cid:51) (cid:54)(cid:54)(cid:57) (cid:39)(cid:39)(cid:57) | (cid:23)(cid:36)(cid:51) (cid:24)(cid:36)(cid:51) | (cid:25)(cid:36)(cid:51) (cid:26)(cid:36)(cid:51) (cid:23)(cid:38)(cid:51) | (cid:19)(cid:37)(cid:51) (cid:20)(cid:37)(cid:51) (cid:21)(cid:37)(cid:51) | (cid:19)(cid:20)(cid:37)(cid:51) (cid:20)(cid:20)(cid:37)(cid:51) (cid:20)(cid:66)(cid:51)(cid:36)(cid:38)(cid:57) | (cid:54)(cid:54)(cid:57) (cid:39)(cid:39)(cid:57) |
(cid:48)(cid:54)(cid:23)(cid:19)(cid:23)(cid:24)(cid:24)(cid:57)(cid:22)
1. The above figure shows the package top view.
48/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Pinouts and pin description
Figure 15. STM32F722xx LQFP100 pinout
(cid:3)(cid:1004)(cid:100)(cid:75)(cid:75)(cid:17)
|                                                                                               |                                                                                                                                                                                         | (cid:3)(cid:3)(cid:3)(cid:3)(cid:1011)(cid:24)(cid:87) (cid:3)(cid:3)(cid:3)(cid:3)(cid:1010)(cid:24)(cid:87) (cid:3)(cid:3)(cid:3)(cid:3)(cid:1009)(cid:24)(cid:87) (cid:3)(cid:3)(cid:3)(cid:3)(cid:1008)(cid:24)(cid:87) (cid:3)(cid:3)(cid:3)(cid:3)(cid:1007)(cid:24)(cid:87) | (cid:3)(cid:3)(cid:3)(cid:3)(cid:1006)(cid:24)(cid:87) (cid:3)(cid:3)(cid:3)(cid:3)(cid:1005)(cid:24)(cid:87) (cid:3)(cid:3)(cid:3)(cid:3)(cid:1004)(cid:24)(cid:87) |                                                                                                              |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| (cid:24)(cid:24)(cid:115) (cid:1005)(cid:28)(cid:87) (cid:3)(cid:3)(cid:1004)(cid:28)(cid:87) | (cid:3)(cid:1013)(cid:17)(cid:87) (cid:3)(cid:1012)(cid:17)(cid:87) (cid:3)(cid:1011)(cid:17)(cid:87) (cid:3)(cid:3)(cid:1010)(cid:17)(cid:87) (cid:3)(cid:3)(cid:1009)(cid:17)(cid:87) | (cid:1008)(cid:17)(cid:87) (cid:1007)(cid:17)(cid:87)                                                                                                                                                                                                                              | (cid:1006)(cid:1005)(cid:18)(cid:87) (cid:1005)(cid:1005)(cid:18)(cid:87)                                                                                            | (cid:1004)(cid:1005)(cid:18)(cid:87) (cid:1009)(cid:1005)(cid:4)(cid:87) (cid:1008)(cid:1005)(cid:4)(cid:87) |
(cid:94)(cid:94)(cid:115)
(cid:1004)(cid:1004)(cid:1005)
| (cid:1013)(cid:1013) (cid:1012)(cid:1013) (cid:1011)(cid:1013) | (cid:1010)(cid:1013) (cid:1009)(cid:1013) (cid:1008)(cid:1013) (cid:1007)(cid:1013) (cid:1006)(cid:1013) (cid:1005)(cid:1013) | (cid:1004)(cid:1013) (cid:1013)(cid:1012) (cid:1012)(cid:1012) (cid:1011)(cid:1012) (cid:1010)(cid:1012) (cid:1009)(cid:1012) (cid:1008)(cid:1012) | (cid:1007)(cid:1012) (cid:1006)(cid:1012) (cid:1005)(cid:1012) (cid:1004)(cid:1012) (cid:1013)(cid:1011) | (cid:1012)(cid:1011) (cid:1011)(cid:1011) (cid:1010)(cid:1011) |
| -------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
(cid:87)(cid:28)(cid:1006)
| (cid:1005)                            |     |     |     | (cid:1011)(cid:1009) (cid:115)(cid:24)(cid:24) |
| ------------------------------------- | --- | --- | --- | ---------------------------------------------- |
| (cid:87)(cid:28)(cid:1007) (cid:1006) |     |     |     | (cid:1011)(cid:1008) (cid:115)(cid:94)(cid:94) |
(cid:87)(cid:28)(cid:1008) (cid:1007) (cid:1011)(cid:1007) (cid:115)(cid:18)(cid:4)(cid:87)(cid:890)(cid:1006)(cid:3)(cid:3)(cid:3)(cid:3)
| (cid:87)(cid:28)(cid:1009) (cid:1008) |     |     |     | (cid:1011)(cid:1006) (cid:87)(cid:4)(cid:1005)(cid:1007) |
| ------------------------------------- | --- | --- | --- | -------------------------------------------------------- |
| (cid:87)(cid:28)(cid:1010) (cid:1009) |     |     |     | (cid:1011)(cid:1005) (cid:87)(cid:4)(cid:1005)(cid:1006) |
(cid:115)(cid:17)(cid:4)(cid:100) (cid:1010) (cid:1011)(cid:1004) (cid:87)(cid:4)(cid:1005)(cid:1005)
(cid:87)(cid:18)(cid:1005)(cid:1007) (cid:1011) (cid:1010)(cid:1013) (cid:87)(cid:4)(cid:1005)(cid:1004)
(cid:87)(cid:18)(cid:1005)(cid:1008)(cid:882)(cid:75)(cid:94)(cid:18)(cid:1007)(cid:1006)(cid:890)(cid:47)(cid:69) (cid:1012) (cid:1010)(cid:1012)
(cid:87)(cid:4)(cid:1013)
(cid:87)(cid:18)(cid:1005)(cid:1009)(cid:882)(cid:75)(cid:94)(cid:18)(cid:1007)(cid:1006)(cid:890)(cid:75)(cid:104)(cid:100) (cid:1013) (cid:1010)(cid:1011) (cid:87)(cid:4)(cid:1012)
| (cid:115)(cid:94)(cid:94) (cid:1005)(cid:1004) |     |     |     | (cid:1010)(cid:1010) (cid:87)(cid:18)(cid:1013) |
| ---------------------------------------------- | --- | --- | --- | ----------------------------------------------- |
| (cid:115)(cid:24)(cid:24) (cid:1005)(cid:1005) |     |     |     | (cid:1010)(cid:1009) (cid:87)(cid:18)(cid:1012) |
(cid:87)(cid:44)(cid:1004)(cid:882)(cid:75)(cid:94)(cid:18)(cid:890)(cid:47)(cid:69) (cid:1005)(cid:1006) (cid:1010)(cid:1008) (cid:87)(cid:18)(cid:1011)
(cid:87)(cid:44)(cid:1005)(cid:882)(cid:75)(cid:94)(cid:18)(cid:890)(cid:75)(cid:104)(cid:100) (cid:1005)(cid:1007) (cid:47)(cid:52)(cid:41)(cid:51)(cid:20)(cid:19)(cid:19) (cid:1010)(cid:1007) (cid:87)(cid:18)(cid:1010)
(cid:87)(cid:24)(cid:1005)(cid:1009)
| (cid:69)(cid:90)(cid:94)(cid:100) (cid:1005)(cid:1008) |     |     |     | (cid:1010)(cid:1006) |
| ------------------------------------------------------ | --- | --- | --- | -------------------- |
(cid:87)(cid:18)(cid:1004) (cid:1005)(cid:1009) (cid:1010)(cid:1005) (cid:87)(cid:24)(cid:1005)(cid:1008)
(cid:87)(cid:18)(cid:1005) (cid:1005)(cid:1010) (cid:1010)(cid:1004) (cid:87)(cid:24)(cid:1005)(cid:1007)
(cid:87)(cid:18)(cid:1006) (cid:1005)(cid:1011) (cid:1009)(cid:1013) (cid:87)(cid:24)(cid:1005)(cid:1006)
(cid:87)(cid:18)(cid:1007) (cid:1005)(cid:1012) (cid:1009)(cid:1012) (cid:87)(cid:24)(cid:1005)(cid:1005)
(cid:115)(cid:94)(cid:94)(cid:4) (cid:1005)(cid:1013) (cid:1009)(cid:1011) (cid:87)(cid:24)(cid:1005)(cid:1004)
(cid:115)(cid:90)(cid:28)(cid:38)(cid:1085) (cid:1006)(cid:1004) (cid:1009)(cid:1010) (cid:87)(cid:24)(cid:1013)
(cid:115)(cid:24)(cid:24)(cid:4) (cid:1006)(cid:1005) (cid:1009)(cid:1009) (cid:87)(cid:24)(cid:1012)
(cid:87)(cid:4)(cid:1004)(cid:882)(cid:116)(cid:60)(cid:104)(cid:87) (cid:1006)(cid:1006) (cid:1009)(cid:1008) (cid:87)(cid:17)(cid:1005)(cid:1009)
| (cid:87)(cid:4)(cid:1005) (cid:1006)(cid:1007)                                                          |                                                                                                                                                                 |                                                                                                                               |                                                                                                                                                                                          | (cid:1009)(cid:1007) (cid:87)(cid:17)(cid:1005)(cid:1008)      |
| ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| (cid:87)(cid:4)(cid:1006) (cid:1006)(cid:1008)                                                          |                                                                                                                                                                 |                                                                                                                               |                                                                                                                                                                                          | (cid:1009)(cid:1006) (cid:87)(cid:17)(cid:1005)(cid:1007)      |
| (cid:1006)(cid:1009)                                                                                    |                                                                                                                                                                 |                                                                                                                               |                                                                                                                                                                                          | (cid:1009)(cid:1005)                                           |
| (cid:87)(cid:4)(cid:1007)                                                                               |                                                                                                                                                                 |                                                                                                                               |                                                                                                                                                                                          | (cid:87)(cid:17)(cid:1005)(cid:1006)                           |
| (cid:1010)(cid:1006) (cid:1011)(cid:1006) (cid:1012)(cid:1006) (cid:1013)(cid:1006)                     | (cid:1004)(cid:1007) (cid:1005)(cid:1007) (cid:1006)(cid:1007) (cid:1007)(cid:1007) (cid:1008)(cid:1007) (cid:1009)(cid:1007)                                   | (cid:1010)(cid:1007) (cid:1011)(cid:1007) (cid:1012)(cid:1007) (cid:1013)(cid:1007) (cid:1004)(cid:1008) (cid:1005)(cid:1008) | (cid:1006)(cid:1008) (cid:1007)(cid:1008) (cid:1008)(cid:1008) (cid:1009)(cid:1008) (cid:1010)(cid:1008) (cid:1011)(cid:1008)                                                            | (cid:1012)(cid:1008) (cid:1013)(cid:1008) (cid:1004)(cid:1009) |
|                                                                                                         |                                                                                                                                                                 | (cid:1004)(cid:1005)(cid:28)(cid:87) (cid:1005)(cid:1005)(cid:28)(cid:87) (cid:1006)(cid:1005)(cid:28)(cid:87)                | (cid:1007)(cid:1005)(cid:28)(cid:87) (cid:1008)(cid:1005)(cid:28)(cid:87) (cid:1009)(cid:1005)(cid:28)(cid:87) (cid:1004)(cid:1005)(cid:17)(cid:87) (cid:1005)(cid:1005)(cid:17)(cid:87) | (cid:1005)(cid:890)(cid:87)(cid:4)(cid:18)(cid:115)            |
| (cid:94)(cid:94)(cid:115) (cid:24)(cid:24)(cid:115) (cid:1008)(cid:4)(cid:87) (cid:1009)(cid:4)(cid:87) | (cid:1010)(cid:4)(cid:87) (cid:1011)(cid:4)(cid:87) (cid:1008)(cid:18)(cid:87) (cid:1009)(cid:18)(cid:87) (cid:1004)(cid:17)(cid:87) (cid:1005)(cid:17)(cid:87) | (cid:1006)(cid:17)(cid:87) (cid:1011)(cid:28)(cid:87) (cid:1012)(cid:28)(cid:87) (cid:1013)(cid:28)(cid:87)                   |                                                                                                                                                                                          | (cid:94)(cid:94)(cid:115) (cid:24)(cid:24)(cid:115)            |
(cid:48)(cid:54)(cid:89)(cid:23)(cid:19)(cid:23)(cid:24)(cid:26)(cid:57)(cid:20)
1. The above figure shows the package top view.
DocID029808 Rev 3 49/229
96

Pinouts and pin description STM32F722xx STM32F723xx
Figure 16. STM32F723xx WLCSP100 ballout (with OTG PHY HS)
(cid:20) (cid:21) (cid:22) (cid:23) (cid:24) (cid:25) (cid:26) (cid:27) (cid:28) (cid:20)(cid:19)
(cid:36) (cid:57)(cid:39)(cid:39) (cid:57)(cid:54)(cid:54) (cid:51)(cid:38)(cid:20)(cid:19) (cid:51)(cid:39)(cid:20) (cid:51)(cid:39)(cid:24) (cid:51)(cid:37)(cid:22) (cid:37)(cid:50)(cid:50)(cid:55)(cid:19) (cid:57)(cid:54)(cid:54) (cid:57)(cid:39)(cid:39) (cid:51)(cid:40)(cid:22)
(cid:37) (cid:51)(cid:36)(cid:20)(cid:22) (cid:51)(cid:36)(cid:20)(cid:21) (cid:57)(cid:38)(cid:36)(cid:51)(cid:66)(cid:21) (cid:51)(cid:36)(cid:20)(cid:24) (cid:51)(cid:39)(cid:19) (cid:51)(cid:39)(cid:23) (cid:51)(cid:37)(cid:23) (cid:51)(cid:37)(cid:26) (cid:51)(cid:40)(cid:20) (cid:51)(cid:40)(cid:25)
(cid:38) (cid:51)(cid:36)(cid:20)(cid:20) (cid:51)(cid:36)(cid:20)(cid:19) (cid:51)(cid:36)(cid:28) (cid:51)(cid:36)(cid:20)(cid:23) (cid:51)(cid:38)(cid:20)(cid:20) (cid:51)(cid:39)(cid:22) (cid:51)(cid:37)(cid:24) (cid:51)(cid:37)(cid:27) (cid:51)(cid:40)(cid:21) (cid:57)(cid:37)(cid:36)(cid:55)
(cid:39) (cid:51)(cid:38)(cid:28) (cid:51)(cid:38)(cid:27) (cid:51)(cid:36)(cid:27) (cid:51)(cid:38)(cid:26) (cid:51)(cid:38)(cid:20)(cid:21) (cid:51)(cid:39)(cid:25) (cid:51)(cid:37)(cid:25) (cid:51)(cid:37)(cid:28) (cid:51)(cid:40)(cid:23) (cid:51)(cid:38)(cid:20)(cid:22)
(cid:40) (cid:51)(cid:38)(cid:25) (cid:51)(cid:39)(cid:20)(cid:24) (cid:51)(cid:39)(cid:20)(cid:22) (cid:51)(cid:40)(cid:20)(cid:19) (cid:51)(cid:39)(cid:21) (cid:51)(cid:39)(cid:26) (cid:51)(cid:40)(cid:19) (cid:51)(cid:40)(cid:24) (cid:51)(cid:38)(cid:20)(cid:23) (cid:51)(cid:38)(cid:20)(cid:24)
(cid:41) (cid:51)(cid:39)(cid:20)(cid:23) (cid:51)(cid:39)(cid:20)(cid:21) (cid:51)(cid:39)(cid:20)(cid:20) (cid:51)(cid:40)(cid:20)(cid:24) (cid:51)(cid:37)(cid:19) (cid:51)(cid:36)(cid:24) (cid:51)(cid:38)(cid:22) (cid:51)(cid:38)(cid:19) (cid:57)(cid:54)(cid:54) (cid:57)(cid:39)(cid:39)
(cid:42) (cid:57) (cid:50) (cid:39) (cid:55) (cid:39) (cid:42) (cid:20) (cid:43) (cid:21) (cid:54) (cid:3) (cid:50) (cid:66)(cid:53) (cid:55) (cid:40) (cid:42) (cid:59) (cid:66) (cid:55) (cid:43)(cid:54) (cid:51)(cid:37)(cid:20)(cid:19) (cid:51)(cid:40)(cid:20)(cid:20) (cid:51)(cid:37)(cid:20) (cid:51)(cid:36)(cid:25) (cid:51)(cid:36)(cid:23) (cid:51)(cid:36)(cid:19) (cid:49)(cid:53)(cid:54)(cid:55) (cid:51)(cid:43)(cid:19)
(cid:43) (cid:51)(cid:37)(cid:20)(cid:24) (cid:51)(cid:37)(cid:20)(cid:22) (cid:51)(cid:37)(cid:20)(cid:20) (cid:51)(cid:40)(cid:20)(cid:21) (cid:51)(cid:40)(cid:27) (cid:51)(cid:38)(cid:23) (cid:51)(cid:36)(cid:22) (cid:51)(cid:36)(cid:21) (cid:51)(cid:38)(cid:20) (cid:51)(cid:43)(cid:20)
(cid:45) (cid:51)(cid:37)(cid:20)(cid:23) (cid:51)(cid:37)(cid:20)(cid:21) (cid:57)(cid:38)(cid:36)(cid:51)(cid:66)(cid:20) (cid:51)(cid:40)(cid:20)(cid:22) (cid:51)(cid:40)(cid:26) (cid:51)(cid:38)(cid:24) (cid:57)(cid:39)(cid:39) (cid:51)(cid:36)(cid:20) (cid:57)(cid:53)(cid:40)(cid:41)(cid:14) (cid:51)(cid:38)(cid:21)
(cid:46) (cid:57)(cid:39)(cid:39) (cid:57)(cid:39)(cid:39) (cid:57)(cid:54)(cid:54) (cid:51)(cid:40)(cid:20)(cid:23) (cid:51)(cid:40)(cid:28) (cid:51)(cid:37)(cid:21) (cid:51)(cid:36)(cid:26) (cid:57)(cid:54)(cid:54) (cid:57)(cid:39)(cid:39)(cid:36) (cid:57)(cid:54)(cid:54)(cid:36)
(cid:56)(cid:54)(cid:37)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:21)(cid:19)(cid:19)(cid:21)(cid:57)(cid:21)
1. The above figure shows the package top view.
50/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Pinouts and pin description
Figure 17. STM32F722xx LQFP144 pinout
(cid:35)(cid:45)(cid:45)(cid:36)(cid:51)(cid:36)(cid:36)
(cid:46)(cid:47)(cid:63)(cid:50)(cid:36)(cid:48)
(cid:16)(cid:52)(cid:47)(cid:47)(cid:34)
|                                                                                                     |                                                                                                                                                       | (cid:21)(cid:17)(cid:39)(cid:48) (cid:20)(cid:17)(cid:39)(cid:48)                                                                                     | (cid:19)(cid:17)(cid:39)(cid:48) (cid:18)(cid:17)(cid:39)(cid:48) (cid:17)(cid:17)(cid:39)(cid:48) (cid:16)(cid:17)(cid:39)(cid:48) |                                                                                                                                                                                | (cid:18)(cid:17)(cid:35)(cid:48) (cid:17)(cid:17)(cid:35)(cid:48) (cid:16)(cid:17)(cid:35)(cid:48)                           | (cid:21)(cid:17)(cid:33)(cid:48) (cid:20)(cid:17)(cid:33)(cid:48)          |
| --------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| (cid:36)(cid:36) (cid:17)(cid:37)(cid:48) (cid:16)(cid:37)(cid:48)                                  | (cid:25)(cid:34)(cid:48) (cid:24)(cid:34)(cid:48) (cid:23)(cid:34)(cid:48) (cid:22)(cid:34)(cid:48) (cid:21)(cid:34)(cid:48)                          | (cid:20)(cid:34)(cid:48) (cid:19)(cid:34)(cid:48) (cid:36)(cid:36) (cid:51)(cid:51)                                                                   | (cid:25)(cid:39)(cid:48)                                                                                                            | (cid:23)(cid:36)(cid:48) (cid:22)(cid:36)(cid:48) (cid:51)(cid:51) (cid:21)(cid:36)(cid:48) (cid:20)(cid:36)(cid:48) (cid:19)(cid:36)(cid:48)                                  | (cid:18)(cid:36)(cid:48) (cid:17)(cid:36)(cid:48) (cid:16)(cid:36)(cid:48)                                                   |                                                                            |
| (cid:54)                                                                                            |                                                                                                                                                       | (cid:54) (cid:54)                                                                                                                                     |                                                                                                                                     | (cid:54) (cid:54)                                                                                                                                                              |                                                                                                                              |                                                                            |
| (cid:20)(cid:20)(cid:17) (cid:19)(cid:20)(cid:17) (cid:18)(cid:20)(cid:17) (cid:17)(cid:20)(cid:17) | (cid:16)(cid:20)(cid:17) (cid:25)(cid:19)(cid:17) (cid:24)(cid:19)(cid:17) (cid:23)(cid:19)(cid:17) (cid:22)(cid:19)(cid:17) (cid:21)(cid:19)(cid:17) | (cid:20)(cid:19)(cid:17) (cid:19)(cid:19)(cid:17) (cid:18)(cid:19)(cid:17) (cid:17)(cid:19)(cid:17) (cid:16)(cid:19)(cid:17) (cid:25)(cid:18)(cid:17) | (cid:24)(cid:18)(cid:17) (cid:23)(cid:18)(cid:17) (cid:22)(cid:18)(cid:17) (cid:21)(cid:18)(cid:17) (cid:20)(cid:18)(cid:17)        | (cid:19)(cid:18)(cid:17) (cid:18)(cid:18)(cid:17) (cid:17)(cid:18)(cid:17) (cid:16)(cid:18)(cid:17) (cid:25)(cid:17)(cid:17) (cid:24)(cid:17)(cid:17) (cid:23)(cid:17)(cid:17) | (cid:22)(cid:17)(cid:17) (cid:21)(cid:17)(cid:17) (cid:20)(cid:17)(cid:17) (cid:19)(cid:17)(cid:17) (cid:18)(cid:17)(cid:17) | (cid:17)(cid:17)(cid:17) (cid:16)(cid:17)(cid:17) (cid:25)(cid:16)(cid:17) |
(cid:48)(cid:37)(cid:18) (cid:17) (cid:17)(cid:16)(cid:24) (cid:54)
(cid:36)(cid:36)
(cid:48)(cid:37)(cid:19) (cid:18) (cid:17)(cid:16)(cid:23) (cid:54)
| (cid:48)(cid:37)(cid:20) |     |     |     |     |     | (cid:51)(cid:51) |
| ------------------------ | --- | --- | --- | --- | --- | ---------------- |
(cid:19) (cid:17)(cid:16)(cid:22) (cid:54) (cid:35)(cid:33)(cid:48)(cid:63)(cid:18)
| (cid:48)(cid:37)(cid:21) (cid:20) |     |     |     |     |     | (cid:17)(cid:16)(cid:21) |
| --------------------------------- | --- | --- | --- | --- | --- | ------------------------ |
(cid:48)(cid:33)(cid:17)(cid:19)
(cid:48)(cid:37)(cid:22) (cid:21) (cid:17)(cid:16)(cid:20) (cid:48)(cid:33)(cid:17)(cid:18)
(cid:54)(cid:34)(cid:33)(cid:52) (cid:22) (cid:17)(cid:16)(cid:19) (cid:48)(cid:33)(cid:17)(cid:17)
(cid:48)(cid:35)(cid:17)(cid:19) (cid:23) (cid:17)(cid:16)(cid:18) (cid:48)(cid:33)(cid:17)(cid:16)
(cid:48)(cid:35)(cid:17)(cid:20) (cid:24) (cid:17)(cid:16)(cid:17)
(cid:48)(cid:33)(cid:25)
(cid:48)(cid:35)(cid:17)(cid:21) (cid:25) (cid:17)(cid:16)(cid:16) (cid:48)(cid:33)(cid:24)
(cid:48)(cid:38)(cid:16) (cid:17)(cid:16) (cid:25)(cid:25) (cid:48)(cid:35)(cid:25)
(cid:48)(cid:38)(cid:17) (cid:17)(cid:17) (cid:25)(cid:24) (cid:48)(cid:35)(cid:24)
(cid:48)(cid:38)(cid:18) (cid:17)(cid:18) (cid:25)(cid:23) (cid:48)(cid:35)(cid:23)
| (cid:48)(cid:38)(cid:19) (cid:17)(cid:19) |     |     |     |     |     | (cid:25)(cid:22) |
| ----------------------------------------- | --- | --- | --- | --- | --- | ---------------- |
(cid:48)(cid:35)(cid:22)
(cid:48)(cid:38)(cid:20) (cid:17)(cid:20) (cid:25)(cid:21) (cid:54)
(cid:36)(cid:36)(cid:53)(cid:51)(cid:34)
(cid:48)(cid:38)(cid:21) (cid:17)(cid:21) (cid:25)(cid:20) (cid:54)
(cid:51)(cid:51)
(cid:54) (cid:51)(cid:51) (cid:17)(cid:22) (cid:25)(cid:19) (cid:48)(cid:39)(cid:24)
| (cid:54) (cid:17)(cid:23)                 |     |     |     |     |     | (cid:25)(cid:18)         |
| ----------------------------------------- | --- | --- | --- | --- | --- | ------------------------ |
| (cid:36)(cid:36)                          |     |     |     |     |     | (cid:48)(cid:39)(cid:23) |
| (cid:48)(cid:38)(cid:22) (cid:17)(cid:24) |     |     |     |     |     | (cid:25)(cid:17)         |
(cid:48)(cid:39)(cid:22)
(cid:48)(cid:38)(cid:23) (cid:17)(cid:25) (cid:47)(cid:52)(cid:41)(cid:51)(cid:20)(cid:23)(cid:23) (cid:25)(cid:16) (cid:48)(cid:39)(cid:21)
(cid:48)(cid:38)(cid:24) (cid:18)(cid:16) (cid:24)(cid:25) (cid:48)(cid:39)(cid:20)
(cid:48)(cid:38)(cid:25) (cid:18)(cid:17) (cid:24)(cid:24) (cid:48)(cid:39)(cid:19)
(cid:48)(cid:38)(cid:17)(cid:16) (cid:18)(cid:18) (cid:24)(cid:23)
(cid:48)(cid:39)(cid:18)
(cid:48)(cid:40)(cid:16) (cid:18)(cid:19) (cid:24)(cid:22) (cid:48)(cid:36)(cid:17)(cid:21)
(cid:48)(cid:40)(cid:17) (cid:18)(cid:20) (cid:24)(cid:21) (cid:48)(cid:36)(cid:17)(cid:20)
(cid:46)(cid:50)(cid:51)(cid:52) (cid:18)(cid:21) (cid:24)(cid:20) (cid:54)
| (cid:18)(cid:22) |     |     |     |     |     | (cid:36)(cid:36) |
| ---------------- | --- | --- | --- | --- | --- | ---------------- |
(cid:48)(cid:35)(cid:16) (cid:24)(cid:19) (cid:54) (cid:51)(cid:51)
(cid:48)(cid:35)(cid:17) (cid:18)(cid:23)
(cid:24)(cid:18) (cid:48)(cid:36)(cid:17)(cid:19)
(cid:48)(cid:35)(cid:18) (cid:18)(cid:24) (cid:24)(cid:17) (cid:48)(cid:36)(cid:17)(cid:18)
(cid:48)(cid:35)(cid:19) (cid:18)(cid:25) (cid:24)(cid:16) (cid:48)(cid:36)(cid:17)(cid:17)
(cid:54) (cid:36)(cid:36) (cid:19)(cid:16) (cid:23)(cid:25) (cid:48)(cid:36)(cid:17)(cid:16)
(cid:54) (cid:19)(cid:17)
(cid:51)(cid:51)(cid:33) (cid:23)(cid:24) (cid:48)(cid:36)(cid:25)
| (cid:54) (cid:19)(cid:18)        |     |     |     |     |     | (cid:23)(cid:23)         |
| -------------------------------- | --- | --- | --- | --- | --- | ------------------------ |
| (cid:50)(cid:37)(cid:38)(cid:11) |     |     |     |     |     | (cid:48)(cid:36)(cid:24) |
(cid:54) (cid:19)(cid:19) (cid:23)(cid:22) (cid:48)(cid:34)(cid:17)(cid:21)
(cid:36)(cid:36)(cid:33)
(cid:48)(cid:33)(cid:16) (cid:19)(cid:20) (cid:23)(cid:21) (cid:48)(cid:34)(cid:17)(cid:20)
(cid:19)(cid:21)
(cid:48)(cid:33)(cid:17) (cid:23)(cid:20) (cid:48)(cid:34)(cid:17)(cid:19)
(cid:48)(cid:33)(cid:18) (cid:19)(cid:22)
(cid:23)(cid:19) (cid:48)(cid:34)(cid:17)(cid:18)
| (cid:23)(cid:19) (cid:24)(cid:19) (cid:25)(cid:19) (cid:16)(cid:20) | (cid:17)(cid:20) (cid:18)(cid:20) (cid:19)(cid:20) (cid:20)(cid:20) (cid:21)(cid:20) (cid:22)(cid:20) | (cid:23)(cid:20) (cid:24)(cid:20) (cid:25)(cid:20) (cid:16)(cid:21) (cid:17)(cid:21) (cid:18)(cid:21) | (cid:19)(cid:21) (cid:20)(cid:21) (cid:21)(cid:21) (cid:22)(cid:21) (cid:23)(cid:21) | (cid:24)(cid:21) (cid:25)(cid:21) (cid:16)(cid:22) (cid:17)(cid:22) (cid:18)(cid:22) (cid:19)(cid:22) (cid:20)(cid:22) | (cid:21)(cid:22) (cid:22)(cid:22) (cid:23)(cid:22) (cid:24)(cid:22) (cid:25)(cid:22) | (cid:16)(cid:23) (cid:17)(cid:23) (cid:18)(cid:23) |
| ------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | -------------------------------------------------- |
(cid:17)(cid:63)(cid:48)(cid:33)(cid:35)
| (cid:19)(cid:33)(cid:48) (cid:51)(cid:51) (cid:36)(cid:36) (cid:20)(cid:33)(cid:48) | (cid:21)(cid:33)(cid:48) (cid:22)(cid:33)(cid:48) (cid:23)(cid:33)(cid:48) (cid:20)(cid:35)(cid:48) (cid:21)(cid:35)(cid:48) (cid:16)(cid:34)(cid:48) | (cid:17)(cid:34)(cid:48) (cid:18)(cid:34)(cid:48) (cid:17)(cid:17)(cid:38)(cid:48) (cid:18)(cid:17)(cid:38)(cid:48) | (cid:19)(cid:17)(cid:38)(cid:48) (cid:20)(cid:17)(cid:38)(cid:48) (cid:21)(cid:17)(cid:38)(cid:48) (cid:16)(cid:39)(cid:48) (cid:17)(cid:39)(cid:48) | (cid:23)(cid:37)(cid:48) (cid:24)(cid:37)(cid:48) (cid:25)(cid:37)(cid:48) (cid:16)(cid:17)(cid:37)(cid:48) (cid:17)(cid:17)(cid:37)(cid:48) | (cid:18)(cid:17)(cid:37)(cid:48) (cid:19)(cid:17)(cid:37)(cid:48) (cid:20)(cid:17)(cid:37)(cid:48) (cid:21)(cid:17)(cid:37)(cid:48) (cid:16)(cid:17)(cid:34)(cid:48) | (cid:17)(cid:17)(cid:34)(cid:48) |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
|                                                                                     |                                                                                                                                                       | (cid:51)(cid:51) (cid:36)(cid:36)                                                                                   |                                                                                                                                                      | (cid:51)(cid:51) (cid:36)(cid:36)                                                                                                            |                                                                                                                                                                      | (cid:36)(cid:36)                 |
| (cid:54) (cid:54)                                                                   |                                                                                                                                                       | (cid:54) (cid:54)                                                                                                   |                                                                                                                                                      | (cid:54) (cid:54)                                                                                                                            |                                                                                                                                                                      | (cid:54)                         |
(cid:54)
(cid:48)(cid:54)(cid:22)(cid:28)(cid:20)(cid:22)(cid:21)(cid:57)(cid:20)
1. The above figure shows the package top view.
DocID029808 Rev 3 51/229
96

Pinouts and pin description STM32F722xx STM32F723xx
Figure 18. STM32F723xx LQFP144 pinout
1. The above figure shows the package top view.
52/229 DocID029808 Rev 3
(cid:54)
(cid:36)(cid:36)
(cid:46)(cid:47)(cid:63)(cid:50)(cid:36)(cid:48)
(cid:17)(cid:37)(cid:48) (cid:16)(cid:37)(cid:48) (cid:25)(cid:34)(cid:48) (cid:24)(cid:34)(cid:48)
(cid:16)(cid:52)(cid:47)(cid:47)(cid:34)
(cid:23)(cid:34)(cid:48) (cid:22)(cid:34)(cid:48) (cid:21)(cid:34)(cid:48) (cid:20)(cid:34)(cid:48) (cid:19)(cid:34)(cid:48)
(cid:21)(cid:17)(cid:39)(cid:48)
(cid:54)
(cid:36)(cid:36)
(cid:54)
(cid:51)(cid:51)
(cid:20)(cid:17)(cid:39)(cid:48) (cid:19)(cid:17)(cid:39)(cid:48) (cid:18)(cid:17)(cid:39)(cid:48) (cid:17)(cid:17)(cid:39)(cid:48) (cid:16)(cid:17)(cid:39)(cid:48)
(cid:25)(cid:39)(cid:48) (cid:23)(cid:36)(cid:48) (cid:22)(cid:36)(cid:48)
(cid:54)
(cid:35)(cid:45)(cid:45)(cid:36)(cid:51)(cid:36)(cid:36)
(cid:54)
(cid:51)(cid:51) (cid:21)(cid:36)(cid:48) (cid:20)(cid:36)(cid:48) (cid:19)(cid:36)(cid:48) (cid:18)(cid:36)(cid:48) (cid:17)(cid:36)(cid:48) (cid:16)(cid:36)(cid:48)
(cid:18)(cid:17)(cid:35)(cid:48) (cid:17)(cid:17)(cid:35)(cid:48) (cid:16)(cid:17)(cid:35)(cid:48) (cid:21)(cid:17)(cid:33)(cid:48) (cid:20)(cid:17)(cid:33)(cid:48)
(cid:48)(cid:37)(cid:18) (cid:54)
(cid:36)(cid:36)
(cid:48)(cid:37)(cid:19) (cid:54)
(cid:51)(cid:51)
(cid:48)(cid:37)(cid:20)
(cid:48)(cid:37)(cid:21) (cid:48)(cid:33)(cid:17)(cid:19)
(cid:48)(cid:37)(cid:22) (cid:48)(cid:33)(cid:17)(cid:18)
(cid:54)(cid:34)(cid:33)(cid:52) (cid:48)(cid:33)(cid:17)(cid:17)
(cid:48)(cid:35)(cid:17)(cid:19) (cid:48)(cid:33)(cid:17)(cid:16)
(cid:48)(cid:35)(cid:17)(cid:20) (cid:48)(cid:33)(cid:25)
(cid:48)(cid:35)(cid:17)(cid:21) (cid:48)(cid:33)(cid:24)
(cid:48)(cid:38)(cid:16) (cid:48)(cid:35)(cid:25)
(cid:48)(cid:38)(cid:17) (cid:48)(cid:35)(cid:24)
(cid:48)(cid:38)(cid:18) (cid:48)(cid:35)(cid:23)
(cid:48)(cid:38)(cid:19) (cid:48)(cid:35)(cid:22)
(cid:48)(cid:38)(cid:20) (cid:54)
(cid:36)(cid:36)(cid:53)(cid:51)(cid:34)
(cid:48)(cid:38)(cid:21) (cid:54)
(cid:51)(cid:51)
(cid:54) (cid:51)(cid:51) (cid:48)(cid:39)(cid:24)
(cid:54) (cid:36)(cid:36) (cid:48)(cid:39)(cid:21)
(cid:48)(cid:38)(cid:22) (cid:48)(cid:39)(cid:20)
(cid:48)(cid:38)(cid:23) (cid:48)(cid:39)(cid:19)
(cid:48)(cid:38)(cid:24) (cid:48)(cid:39)(cid:18)
(cid:48)(cid:38)(cid:25) (cid:48)(cid:36)(cid:17)(cid:21)
(cid:48)(cid:38)(cid:17)(cid:16) (cid:48)(cid:36)(cid:17)(cid:20)
(cid:48)(cid:40)(cid:16) (cid:54)
(cid:36)(cid:36)
(cid:48)(cid:40)(cid:17) (cid:54)
(cid:51)(cid:51)
(cid:46)(cid:50)(cid:51)(cid:52) (cid:48)(cid:36)(cid:17)(cid:19)
(cid:48)(cid:35)(cid:16) (cid:48)(cid:36)(cid:17)(cid:18)
(cid:48)(cid:35)(cid:17) (cid:48)(cid:36)(cid:17)(cid:17)
(cid:48)(cid:35)(cid:18) (cid:48)(cid:36)(cid:17)(cid:16)
(cid:48)(cid:35)(cid:19)
(cid:54) (cid:36)(cid:36)
(cid:54) (cid:51)(cid:51)(cid:33) (cid:48)(cid:34)(cid:17)(cid:21)
(cid:54) (cid:50)(cid:37)(cid:38)(cid:11) (cid:48)(cid:34)(cid:17)(cid:20)
(cid:54) (cid:36)(cid:36)(cid:33)
(cid:48)(cid:33)(cid:16)
(cid:48)(cid:33)(cid:17) (cid:48)(cid:34)(cid:17)(cid:19)
(cid:48)(cid:33)(cid:18) (cid:48)(cid:34)(cid:17)(cid:18)
(cid:20)(cid:20)(cid:17)
(cid:19)(cid:33)(cid:48)
(cid:19)(cid:20)(cid:17)
(cid:54)
(cid:51)(cid:51)
(cid:18)(cid:20)(cid:17)
(cid:54)
(cid:36)(cid:36)
(cid:17)(cid:20)(cid:17)
(cid:20)(cid:33)(cid:48)
(cid:16)(cid:20)(cid:17)
(cid:21)(cid:33)(cid:48)
(cid:25)(cid:19)(cid:17)
(cid:22)(cid:33)(cid:48)
(cid:24)(cid:19)(cid:17)
(cid:23)(cid:33)(cid:48)
(cid:23)(cid:19)(cid:17)
(cid:20)(cid:35)(cid:48)
(cid:22)(cid:19)(cid:17)
(cid:21)(cid:35)(cid:48)
(cid:21)(cid:19)(cid:17)
(cid:16)(cid:34)(cid:48)
(cid:20)(cid:19)(cid:17)
(cid:17)(cid:34)(cid:48)
(cid:19)(cid:19)(cid:17)
(cid:18)(cid:34)(cid:48)
(cid:18)(cid:19)(cid:17)
(cid:17)(cid:17)(cid:38)(cid:48)
(cid:17)(cid:19)(cid:17)
(cid:18)(cid:17)(cid:38)(cid:48)
(cid:16)(cid:19)(cid:17) (cid:25)(cid:18)(cid:17)
(cid:54)
(cid:36)(cid:36)
(cid:24)(cid:18)(cid:17)
(cid:19)(cid:17)(cid:38)(cid:48)
(cid:23)(cid:18)(cid:17)
(cid:20)(cid:17)(cid:38)(cid:48)
(cid:22)(cid:18)(cid:17)
(cid:21)(cid:17)(cid:38)(cid:48)
(cid:21)(cid:18)(cid:17)
(cid:16)(cid:39)(cid:48)
(cid:20)(cid:18)(cid:17)
(cid:17)(cid:39)(cid:48)
(cid:19)(cid:18)(cid:17)
(cid:23)(cid:37)(cid:48)
(cid:18)(cid:18)(cid:17)
(cid:24)(cid:37)(cid:48)
(cid:17)(cid:18)(cid:17)
(cid:25)(cid:37)(cid:48)
(cid:54)
(cid:51)(cid:51)
(cid:54)
(cid:36)(cid:36) (cid:16)(cid:17)(cid:37)(cid:48) (cid:17)(cid:17)(cid:37)(cid:48) (cid:18)(cid:17)(cid:37)(cid:48) (cid:19)(cid:17)(cid:37)(cid:48) (cid:20)(cid:17)(cid:37)(cid:48) (cid:21)(cid:17)(cid:37)(cid:48) (cid:16)(cid:17)(cid:34)(cid:48) (cid:17)(cid:17)(cid:34)(cid:48)
(cid:25)(cid:16)(cid:17)
(cid:54)
(cid:36)(cid:36)
(cid:17) (cid:17)(cid:16)(cid:24)
(cid:18) (cid:17)(cid:16)(cid:23)
(cid:19) (cid:17)(cid:16)(cid:22)
(cid:20) (cid:17)(cid:16)(cid:21)
(cid:21) (cid:17)(cid:16)(cid:20)
(cid:22) (cid:17)(cid:16)(cid:19)
(cid:23) (cid:17)(cid:16)(cid:18)
(cid:24) (cid:17)(cid:16)(cid:17)
(cid:25) (cid:17)(cid:16)(cid:16)
(cid:17)(cid:16) (cid:25)(cid:25)
(cid:17)(cid:17) (cid:25)(cid:24)
(cid:17)(cid:18) (cid:25)(cid:23)
(cid:17)(cid:19) (cid:25)(cid:22)
(cid:17)(cid:20) (cid:25)(cid:21)
(cid:17)(cid:21) (cid:25)(cid:20)
(cid:17)(cid:22) (cid:25)(cid:19)
(cid:17)(cid:23) (cid:25)(cid:18)
(cid:17)(cid:24) (cid:25)(cid:17)
(cid:17)(cid:25) (cid:25)(cid:16)
(cid:18)(cid:16) (cid:24)(cid:25)
(cid:18)(cid:17) (cid:24)(cid:24)
(cid:18)(cid:18) (cid:24)(cid:23)
(cid:18)(cid:19) (cid:24)(cid:22)
(cid:18)(cid:20) (cid:24)(cid:21)
(cid:18)(cid:21) (cid:24)(cid:20)
(cid:23)(cid:19) (cid:24)(cid:19) (cid:25)(cid:19) (cid:16)(cid:20) (cid:17)(cid:20) (cid:18)(cid:20) (cid:19)(cid:20) (cid:20)(cid:20) (cid:21)(cid:20) (cid:22)(cid:20) (cid:23)(cid:20) (cid:24)(cid:20) (cid:25)(cid:20) (cid:16)(cid:21) (cid:17)(cid:21) (cid:18)(cid:21) (cid:19)(cid:21) (cid:20)(cid:21) (cid:21)(cid:21) (cid:22)(cid:21) (cid:23)(cid:21) (cid:24)(cid:21) (cid:25)(cid:21) (cid:16)(cid:22) (cid:18)(cid:23)
(cid:3)(cid:3)(cid:3)(cid:47)(cid:52)(cid:41)(cid:51)(cid:20)(cid:23)(cid:23)(cid:3)
(cid:90)(cid:76)(cid:87)(cid:75)(cid:3)(cid:43)(cid:54)(cid:3)(cid:51)(cid:43)(cid:60)
(cid:16)(cid:18)(cid:17)
(cid:17)(cid:22)
(cid:25)(cid:17)(cid:17)
(cid:18)(cid:22)
(cid:24)(cid:17)(cid:17)
(cid:19)(cid:22)
(cid:23)(cid:17)(cid:17)
(cid:20)(cid:22)
(cid:22)(cid:17)(cid:17)
(cid:21)(cid:22)
(cid:21)(cid:17)(cid:17)
(cid:22)(cid:22)
(cid:20)(cid:17)(cid:17)
(cid:23)(cid:22)
(cid:19)(cid:17)(cid:17)
(cid:24)(cid:22)
(cid:18)(cid:17)(cid:17)
(cid:25)(cid:22)
(cid:17)(cid:17)(cid:17)
(cid:16)(cid:23)
(cid:16)(cid:17)(cid:17)
(cid:17)(cid:23)
(cid:54)
(cid:35)(cid:33)(cid:48)(cid:63)(cid:18)
(cid:18)(cid:22) (cid:24)(cid:19)
(cid:18)(cid:23) (cid:24)(cid:18)
(cid:18)(cid:24) (cid:24)(cid:17)
(cid:18)(cid:25) (cid:24)(cid:16)
(cid:19)(cid:16) (cid:23)(cid:25)
(cid:19)(cid:17) (cid:23)(cid:24)
(cid:19)(cid:18) (cid:23)(cid:23)
(cid:19)(cid:19) (cid:23)(cid:22)
(cid:19)(cid:20) (cid:23)(cid:21)
(cid:19)(cid:21) (cid:23)(cid:20)
(cid:19)(cid:22) (cid:23)(cid:19)
(cid:54)
(cid:51)(cid:51)
(cid:48)(cid:54)(cid:23)(cid:20)(cid:19)(cid:20)(cid:23)(cid:57)(cid:20)
(cid:54)
(cid:17)(cid:63)(cid:48)(cid:33)(cid:35)
(cid:48)(cid:36)(cid:25)
(cid:48)(cid:36)(cid:24)
(cid:54)(cid:36)(cid:36)(cid:17)(cid:18)(cid:47)(cid:52)(cid:39)(cid:40)(cid:51)
(cid:47)(cid:52)(cid:39)(cid:63)(cid:40)(cid:51)(cid:63)(cid:50)(cid:37)(cid:56)(cid:52)

STM32F722xx STM32F723xx Pinouts and pin description
Figure 19. STM32F723xx UFBGA144 ballout (with OTG PHY HS)
(cid:20) (cid:21) (cid:22) (cid:23) (cid:24) (cid:25) (cid:26) (cid:27) (cid:28) (cid:20)(cid:19) (cid:20)(cid:20) (cid:20)(cid:21)
(cid:36) (cid:51)(cid:38)(cid:20)(cid:22) (cid:51)(cid:40)(cid:22) (cid:51)(cid:40)(cid:21) (cid:51)(cid:40)(cid:20) (cid:51)(cid:40)(cid:19) (cid:51)(cid:37)(cid:23) (cid:51)(cid:37)(cid:22) (cid:51)(cid:39)(cid:25) (cid:51)(cid:39)(cid:26) (cid:51)(cid:36)(cid:20)(cid:24) (cid:51)(cid:36)(cid:20)(cid:23) (cid:51)(cid:36)(cid:20)(cid:22)
(cid:37) (cid:50)(cid:54) (cid:51) (cid:38) (cid:38) (cid:22) (cid:20) (cid:21) (cid:23) (cid:66) (cid:16) (cid:44)(cid:49) (cid:51)(cid:40)(cid:23) (cid:51)(cid:40)(cid:24) (cid:51)(cid:40)(cid:25) (cid:51)(cid:37)(cid:28) (cid:51)(cid:37)(cid:24) (cid:51)(cid:42)(cid:20)(cid:24) (cid:51)(cid:42)(cid:20)(cid:21) (cid:51)(cid:39)(cid:24) (cid:51)(cid:38)(cid:20)(cid:20) (cid:51)(cid:38)(cid:20)(cid:19) (cid:51)(cid:36)(cid:20)(cid:21)
(cid:38) (cid:50)(cid:54)(cid:38) (cid:51) (cid:22) (cid:38) (cid:21) (cid:20) (cid:66) (cid:24) (cid:50) (cid:16) (cid:56)(cid:55) (cid:57)(cid:37)(cid:36)(cid:55) (cid:51)(cid:41)(cid:19) (cid:51)(cid:41)(cid:20) (cid:51)(cid:37)(cid:27) (cid:51)(cid:37)(cid:25) (cid:51)(cid:42)(cid:20)(cid:23) (cid:51)(cid:42)(cid:20)(cid:20) (cid:51)(cid:39)(cid:23) (cid:51)(cid:38)(cid:20)(cid:21) (cid:57)(cid:39)(cid:39)(cid:56)(cid:54)(cid:37) (cid:51)(cid:36)(cid:20)(cid:20)
(cid:39) (cid:50) (cid:51) (cid:54) (cid:43) (cid:38) (cid:19) (cid:66) (cid:3) (cid:44) (cid:16) (cid:49) (cid:3) (cid:57)(cid:54)(cid:54) (cid:57)(cid:39)(cid:39) (cid:51)(cid:41)(cid:21) (cid:37)(cid:50)(cid:50)(cid:55)(cid:19) (cid:51)(cid:37)(cid:26) (cid:51)(cid:42)(cid:20)(cid:22) (cid:51)(cid:42)(cid:20)(cid:19) (cid:51)(cid:39)(cid:22) (cid:51)(cid:39)(cid:20) (cid:51)(cid:36)(cid:20)(cid:19) (cid:51)(cid:36)(cid:28)
(cid:40) (cid:50)(cid:54) (cid:51) (cid:38) (cid:43) (cid:66) (cid:20) (cid:50) (cid:3)(cid:16) (cid:56) (cid:3) (cid:55) (cid:51)(cid:41)(cid:22) (cid:51)(cid:41)(cid:23) (cid:51)(cid:41)(cid:24) (cid:51)(cid:39)(cid:53)(cid:66)(cid:50)(cid:49) (cid:57)(cid:54)(cid:54) (cid:57)(cid:54)(cid:54) (cid:51)(cid:42)(cid:28) (cid:51)(cid:39)(cid:21) (cid:51)(cid:39)(cid:19) (cid:51)(cid:38)(cid:28) (cid:51)(cid:36)(cid:27)
(cid:41) (cid:49)(cid:53)(cid:54)(cid:55) (cid:51)(cid:41)(cid:26) (cid:51)(cid:41)(cid:25) (cid:57)(cid:39)(cid:39) (cid:57)(cid:39)(cid:39) (cid:57)(cid:39)(cid:39) (cid:57)(cid:39)(cid:39) (cid:57)(cid:39)(cid:39) (cid:57)(cid:39)(cid:39) (cid:57)(cid:39)(cid:39) (cid:51)(cid:38)(cid:27) (cid:51)(cid:38)(cid:26)
(cid:42) (cid:51)(cid:41)(cid:20)(cid:19) (cid:51)(cid:41)(cid:28) (cid:51)(cid:41)(cid:27) (cid:57)(cid:54)(cid:54) (cid:57)(cid:39)(cid:39) (cid:57)(cid:39)(cid:39) (cid:57)(cid:39)(cid:39) (cid:57)(cid:54)(cid:54) (cid:57)(cid:38)(cid:36)(cid:51)(cid:66)(cid:21) (cid:57)(cid:54)(cid:54) (cid:51)(cid:42)(cid:27) (cid:51)(cid:38)(cid:25)
(cid:43) (cid:51)(cid:38)(cid:19) (cid:51)(cid:38)(cid:20) (cid:51)(cid:38)(cid:21) (cid:51)(cid:38)(cid:22) (cid:37)(cid:60) (cid:53) (cid:51) (cid:40) (cid:36) (cid:42) (cid:54)(cid:54)(cid:66) (cid:57)(cid:54)(cid:54) (cid:57)(cid:38)(cid:36)(cid:51)(cid:66)(cid:20) (cid:51)(cid:40)(cid:20)(cid:20) (cid:51)(cid:39)(cid:20)(cid:20) (cid:57)(cid:39)(cid:39) (cid:43) (cid:20)(cid:21) (cid:54) (cid:50)(cid:55)(cid:42) (cid:50) (cid:66) (cid:55) (cid:53) (cid:42) (cid:40) (cid:66) (cid:59) (cid:43) (cid:55) (cid:54) (cid:51)(cid:42)(cid:24)
(cid:45) (cid:57)(cid:54)(cid:54)(cid:36) (cid:51)(cid:36)(cid:19) (cid:51)(cid:36)(cid:23) (cid:51)(cid:38)(cid:23) (cid:51)(cid:37)(cid:21) (cid:51)(cid:42)(cid:20) (cid:51)(cid:40)(cid:20)(cid:19) (cid:51)(cid:40)(cid:20)(cid:21) (cid:51)(cid:39)(cid:20)(cid:19) (cid:51)(cid:42)(cid:23) (cid:51)(cid:42)(cid:22) (cid:51)(cid:42)(cid:21)
(cid:46) (cid:57)(cid:53)(cid:40)(cid:41)(cid:16) (cid:51)(cid:36)(cid:20) (cid:51)(cid:36)(cid:24) (cid:51)(cid:38)(cid:24) (cid:51)(cid:41)(cid:20)(cid:22) (cid:51)(cid:42)(cid:19) (cid:51)(cid:40)(cid:28) (cid:51)(cid:40)(cid:20)(cid:22) (cid:51)(cid:39)(cid:28) (cid:51)(cid:39)(cid:20)(cid:22) (cid:51)(cid:39)(cid:20)(cid:23) (cid:51)(cid:39)(cid:20)(cid:24)
(cid:47) (cid:57)(cid:53)(cid:40)(cid:41)(cid:14) (cid:51)(cid:36)(cid:21) (cid:51)(cid:36)(cid:25) (cid:51)(cid:37)(cid:19) (cid:51)(cid:41)(cid:20)(cid:21) (cid:51)(cid:41)(cid:20)(cid:24) (cid:51)(cid:40)(cid:27) (cid:51)(cid:40)(cid:20)(cid:23) (cid:51)(cid:39)(cid:27) (cid:51)(cid:39)(cid:20)(cid:21) (cid:51)(cid:37)(cid:20)(cid:23) (cid:51)(cid:37)(cid:20)(cid:24)
(cid:48) (cid:57)(cid:39)(cid:39)(cid:36) (cid:51)(cid:36)(cid:22) (cid:51)(cid:36)(cid:26) (cid:51)(cid:37)(cid:20) (cid:51)(cid:41)(cid:20)(cid:20) (cid:51)(cid:41)(cid:20)(cid:23) (cid:51)(cid:40)(cid:26) (cid:51)(cid:40)(cid:20)(cid:24) (cid:51)(cid:37)(cid:20)(cid:19) (cid:51)(cid:37)(cid:20)(cid:20) (cid:51)(cid:37)(cid:20)(cid:21) (cid:51)(cid:37)(cid:20)(cid:22)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:21)(cid:19)(cid:19)(cid:19)(cid:57)(cid:20)
1. The above figure shows the package top view.
DocID029808 Rev 3 53/229
96

Pinouts and pin description STM32F722xx STM32F723xx
Figure 20. STM32F722xx LQFP176 pinout
(cid:45)(cid:51)(cid:20)(cid:17)(cid:16)(cid:17)(cid:21)(cid:54)(cid:17)
1. The above figure shows the package top view.
54/229 DocID029808 Rev 3
(cid:23)(cid:41)(cid:48) (cid:22)(cid:41)(cid:48) (cid:36)(cid:36)(cid:54)
(cid:46)(cid:47)(cid:63)(cid:50)(cid:36)(cid:48)
(cid:17)(cid:37)(cid:48) (cid:16)(cid:37)(cid:48) (cid:25)(cid:34)(cid:48) (cid:24)(cid:34)(cid:48)
(cid:16)(cid:52)(cid:47)(cid:47)(cid:34)
(cid:23)(cid:34)(cid:48) (cid:22)(cid:34)(cid:48) (cid:21)(cid:34)(cid:48) (cid:20)(cid:34)(cid:48) (cid:19)(cid:34)(cid:48) (cid:21)(cid:17)(cid:39)(cid:48) (cid:36)(cid:36)(cid:54) (cid:51)(cid:51)(cid:54) (cid:20)(cid:17)(cid:39)(cid:48) (cid:19)(cid:17)(cid:39)(cid:48) (cid:18)(cid:17)(cid:39)(cid:48) (cid:17)(cid:17)(cid:39)(cid:48) (cid:16)(cid:17)(cid:39)(cid:48) (cid:25)(cid:39)(cid:48) (cid:23)(cid:36)(cid:48) (cid:22)(cid:36)(cid:48)
(cid:35)(cid:45)(cid:45)(cid:36)(cid:51)(cid:36)(cid:36)(cid:54)
(cid:51)(cid:51)(cid:54) (cid:21)(cid:36)(cid:48) (cid:20)(cid:36)(cid:48) (cid:19)(cid:36)(cid:48) (cid:18)(cid:36)(cid:48) (cid:17)(cid:36)(cid:48) (cid:16)(cid:36)(cid:48) (cid:18)(cid:17)(cid:35)(cid:48) (cid:17)(cid:17)(cid:35)(cid:48) (cid:16)(cid:17)(cid:35)(cid:48)
(cid:48)(cid:37)(cid:18)
(cid:48)(cid:37)(cid:19)
(cid:48)(cid:37)(cid:20)
(cid:48)(cid:37)(cid:21)
(cid:48)(cid:37)(cid:22)
(cid:54)(cid:34)(cid:33)(cid:52) (cid:54)(cid:36)(cid:36)
(cid:48)(cid:41)(cid:24) (cid:54)(cid:51)(cid:51)
(cid:48)(cid:35)(cid:17)(cid:20) (cid:48)(cid:33)(cid:17)(cid:19)
(cid:48)(cid:35)(cid:17)(cid:21) (cid:48)(cid:33)(cid:17)(cid:18)
(cid:48)(cid:33)(cid:17)(cid:17)
(cid:48)(cid:33)(cid:17)(cid:16)
(cid:48)(cid:33)(cid:25)
(cid:48)(cid:33)(cid:24)
(cid:48)(cid:35)(cid:25)
(cid:48)(cid:38)(cid:16) (cid:48)(cid:35)(cid:24)
(cid:48)(cid:38)(cid:17) (cid:48)(cid:35)(cid:23)
(cid:48)(cid:38)(cid:18) (cid:48)(cid:35)(cid:22)
(cid:48)(cid:38)(cid:19) (cid:54)(cid:36)(cid:36)(cid:53)(cid:51)(cid:34)
(cid:48)(cid:38)(cid:20) (cid:54)(cid:51)(cid:51)
(cid:48)(cid:38)(cid:21) (cid:48)(cid:39)(cid:24)
(cid:48)(cid:39)(cid:23)
(cid:48)(cid:39)(cid:22)
(cid:48)(cid:38)(cid:22) (cid:48)(cid:39)(cid:21)
(cid:48)(cid:38)(cid:23) (cid:48)(cid:39)(cid:20)
(cid:48)(cid:38)(cid:24) (cid:48)(cid:39)(cid:19)
(cid:48)(cid:38)(cid:25) (cid:48)(cid:39)(cid:18)
(cid:48)(cid:38)(cid:17)(cid:16) (cid:48)(cid:36)(cid:17)(cid:21)
(cid:48)(cid:40)(cid:16) (cid:48)(cid:36)(cid:17)(cid:20)
(cid:48)(cid:40)(cid:17) (cid:54)(cid:36)(cid:36)
(cid:46)(cid:50)(cid:51)(cid:52) (cid:54)(cid:51)(cid:51)
(cid:48)(cid:35)(cid:16) (cid:48)(cid:36)(cid:17)(cid:19)
(cid:48)(cid:35)(cid:17) (cid:48)(cid:36)(cid:17)(cid:18)
(cid:48)(cid:35)(cid:18) (cid:48)(cid:36)(cid:17)(cid:17)
(cid:48)(cid:35)(cid:19) (cid:48)(cid:36)(cid:17)(cid:16)
(cid:48)(cid:36)(cid:25)
(cid:48)(cid:36)(cid:24)
(cid:54)(cid:50)(cid:37)(cid:38)(cid:11) (cid:48)(cid:34)(cid:17)(cid:21)
(cid:48)(cid:34)(cid:17)(cid:20)
(cid:48)(cid:33)(cid:16) (cid:48)(cid:34)(cid:17)(cid:19)
(cid:48)(cid:33)(cid:17) (cid:48)(cid:34)(cid:17)(cid:18)
(cid:48)(cid:33)(cid:18)
(cid:22)(cid:23)(cid:17) (cid:21)(cid:23)(cid:17) (cid:20)(cid:23)(cid:17)
(cid:19)(cid:33)(cid:48)
(cid:19)(cid:23)(cid:17)
(cid:39)(cid:37)(cid:50)(cid:63)(cid:51)(cid:51)(cid:33)(cid:48)(cid:57)(cid:34)
(cid:18)(cid:23)(cid:17)
(cid:36)(cid:36)(cid:54)
(cid:17)(cid:23)(cid:17)
(cid:20)(cid:33)(cid:48)
(cid:16)(cid:23)(cid:17)
(cid:21)(cid:33)(cid:48)
(cid:25)(cid:22)(cid:17)
(cid:22)(cid:33)(cid:48)
(cid:24)(cid:22)(cid:17)
(cid:23)(cid:33)(cid:48)
(cid:23)(cid:22)(cid:17)
(cid:20)(cid:35)(cid:48)
(cid:22)(cid:22)(cid:17)
(cid:21)(cid:35)(cid:48)
(cid:21)(cid:22)(cid:17)
(cid:16)(cid:34)(cid:48)
(cid:20)(cid:22)(cid:17)
(cid:17)(cid:34)(cid:48)
(cid:19)(cid:22)(cid:17)
(cid:18)(cid:34)(cid:48)
(cid:18)(cid:22)(cid:17)
(cid:17)(cid:17)(cid:38)(cid:48)
(cid:17)(cid:22)(cid:17)
(cid:18)(cid:17)(cid:38)(cid:48)
(cid:16)(cid:22)(cid:17)
(cid:51)(cid:51)(cid:54)
(cid:25)(cid:21)(cid:17)
(cid:36)(cid:36)(cid:54)
(cid:24)(cid:21)(cid:17)
(cid:19)(cid:17)(cid:38)(cid:48)
(cid:23)(cid:21)(cid:17)
(cid:20)(cid:17)(cid:38)(cid:48)
(cid:22)(cid:21)(cid:17)
(cid:21)(cid:17)(cid:38)(cid:48)
(cid:21)(cid:21)(cid:17)
(cid:16)(cid:39)(cid:48)
(cid:20)(cid:21)(cid:17)
(cid:17)(cid:39)(cid:48)
(cid:19)(cid:21)(cid:17)
(cid:23)(cid:37)(cid:48) (cid:24)(cid:37)(cid:48) (cid:25)(cid:37)(cid:48) (cid:51)(cid:51)(cid:54) (cid:36)(cid:36)(cid:54) (cid:16)(cid:17)(cid:37)(cid:48) (cid:17)(cid:17)(cid:37)(cid:48) (cid:18)(cid:17)(cid:37)(cid:48) (cid:19)(cid:17)(cid:37)(cid:48) (cid:20)(cid:17)(cid:37)(cid:48) (cid:21)(cid:17)(cid:37)(cid:48) (cid:16)(cid:17)(cid:34)(cid:48)
(cid:17)(cid:20)(cid:17)
(cid:17)(cid:17)(cid:34)(cid:48) (cid:17)(cid:63)(cid:48)(cid:33)(cid:35)(cid:54) (cid:36)(cid:36)(cid:54)
(cid:17) (cid:17)(cid:19)(cid:18)
(cid:18) (cid:17)(cid:19)(cid:17)
(cid:19) (cid:17)(cid:19)(cid:16)
(cid:20) (cid:17)(cid:18)(cid:25)
(cid:21) (cid:17)(cid:18)(cid:24)
(cid:22) (cid:17)(cid:18)(cid:23)
(cid:23) (cid:17)(cid:18)(cid:22)
(cid:24) (cid:17)(cid:18)(cid:21)
(cid:25) (cid:17)(cid:18)(cid:20)
(cid:17)(cid:16) (cid:17)(cid:18)(cid:19)
(cid:17)(cid:17) (cid:17)(cid:18)(cid:18)
(cid:17)(cid:18) (cid:17)(cid:18)(cid:17)
(cid:17)(cid:19) (cid:17)(cid:18)(cid:16)
(cid:17)(cid:20) (cid:17)(cid:17)(cid:25)
(cid:17)(cid:21) (cid:17)(cid:17)(cid:24)
(cid:17)(cid:22) (cid:17)(cid:17)(cid:23)
(cid:17)(cid:23) (cid:17)(cid:17)(cid:22)
(cid:17)(cid:24) (cid:17)(cid:17)(cid:21)
(cid:17)(cid:25) (cid:17)(cid:17)(cid:20)
(cid:18)(cid:16) (cid:17)(cid:17)(cid:19)
(cid:18)(cid:17) (cid:17)(cid:17)(cid:18)
(cid:18)(cid:18) (cid:17)(cid:17)(cid:17)
(cid:18)(cid:19) (cid:17)(cid:17)(cid:16)
(cid:18)(cid:20) (cid:17)(cid:16)(cid:25)
(cid:18)(cid:21) (cid:17)(cid:16)(cid:24)
(cid:21)(cid:20) (cid:22)(cid:20) (cid:23)(cid:20) (cid:24)(cid:20) (cid:25)(cid:20) (cid:16)(cid:21) (cid:17)(cid:21) (cid:18)(cid:21) (cid:19)(cid:21) (cid:20)(cid:21) (cid:21)(cid:21) (cid:22)(cid:21) (cid:23)(cid:21) (cid:24)(cid:21) (cid:25)(cid:21) (cid:16)(cid:22) (cid:17)(cid:22) (cid:18)(cid:22) (cid:19)(cid:22) (cid:20)(cid:22) (cid:21)(cid:22) (cid:22)(cid:22) (cid:23)(cid:22) (cid:24)(cid:22) (cid:16)(cid:24)
(cid:47)(cid:52)(cid:41)(cid:51)(cid:20)(cid:26)(cid:25)
(cid:18)(cid:21)(cid:17)
(cid:25)(cid:22)
(cid:17)(cid:21)(cid:17)
(cid:16)(cid:23)
(cid:16)(cid:21)(cid:17)
(cid:17)(cid:23)
(cid:25)(cid:20)(cid:17)
(cid:18)(cid:23)
(cid:24)(cid:20)(cid:17)
(cid:19)(cid:23)
(cid:23)(cid:20)(cid:17)
(cid:20)(cid:23)
(cid:22)(cid:20)(cid:17)
(cid:21)(cid:23)
(cid:21)(cid:20)(cid:17)
(cid:22)(cid:23)
(cid:20)(cid:20)(cid:17)
(cid:23)(cid:23)
(cid:19)(cid:20)(cid:17)
(cid:24)(cid:23)
(cid:18)(cid:20)(cid:17)
(cid:25)(cid:23)
(cid:54)(cid:35)(cid:33)(cid:48)(cid:63)(cid:18)
(cid:18)(cid:22) (cid:17)(cid:16)(cid:23)
(cid:18)(cid:23) (cid:17)(cid:16)(cid:22)
(cid:18)(cid:24) (cid:17)(cid:16)(cid:21)
(cid:18)(cid:25) (cid:17)(cid:16)(cid:20)
(cid:19)(cid:16) (cid:17)(cid:16)(cid:19)
(cid:19)(cid:17) (cid:17)(cid:16)(cid:18)
(cid:19)(cid:18) (cid:17)(cid:16)(cid:17)
(cid:19)(cid:19) (cid:17)(cid:16)(cid:16)
(cid:19)(cid:20) (cid:25)(cid:25)
(cid:19)(cid:21) (cid:25)(cid:24)
(cid:19)(cid:22)
(cid:24)(cid:25)
(cid:20)(cid:40)(cid:48) (cid:21)(cid:40)(cid:48)
(cid:21)(cid:41)(cid:48) (cid:20)(cid:41)(cid:48)
(cid:16)(cid:20)(cid:17)
(cid:17)(cid:24)
(cid:25)(cid:19)(cid:17)
(cid:18)(cid:24)
(cid:21)(cid:17)(cid:33)(cid:48)
(cid:24)(cid:19)(cid:17)
(cid:19)(cid:24)
(cid:22)(cid:40)(cid:48)
(cid:20)(cid:17)(cid:33)(cid:48)
(cid:23)(cid:19)(cid:17)
(cid:20)(cid:24)
(cid:23)(cid:40)(cid:48)
(cid:36)(cid:36)(cid:54)
(cid:22)(cid:19)(cid:17)
(cid:21)(cid:24)
(cid:24)(cid:40)(cid:48)
(cid:51)(cid:51)(cid:54)
(cid:21)(cid:19)(cid:17)
(cid:22)(cid:24)
(cid:25)(cid:40)(cid:48)
(cid:19)(cid:41)(cid:48)
(cid:20)(cid:19)(cid:17)
(cid:23)(cid:24)
(cid:16)(cid:17)(cid:40)(cid:48)
(cid:18)(cid:41)(cid:48)
(cid:19)(cid:19)(cid:17)
(cid:24)(cid:24)
(cid:17)(cid:17)(cid:40)(cid:48)
(cid:48)(cid:41)(cid:17)
(cid:48)(cid:41)(cid:16)
(cid:48)(cid:40)(cid:17)(cid:21)
(cid:48)(cid:40)(cid:17)(cid:20)
(cid:48)(cid:40)(cid:17)(cid:19)
(cid:48)(cid:35)(cid:17)(cid:19)
(cid:48)(cid:41)(cid:25)
(cid:48)(cid:41)(cid:17)(cid:16)
(cid:48)(cid:41)(cid:17)(cid:17)
(cid:54)(cid:51)(cid:51)
(cid:54)(cid:36)(cid:36)
(cid:54)(cid:51)(cid:51)
(cid:54)(cid:36)(cid:36)
(cid:54)(cid:36)(cid:36) (cid:25)(cid:23)
(cid:54)(cid:51)(cid:51)(cid:33) (cid:19)(cid:23) (cid:25)(cid:22)
(cid:19)(cid:24) (cid:25)(cid:21)
(cid:54)(cid:36)(cid:36)(cid:33) (cid:19)(cid:25) (cid:25)(cid:20)
(cid:20)(cid:16) (cid:25)(cid:19)
(cid:20)(cid:17) (cid:25)(cid:18)
(cid:20)(cid:18) (cid:25)(cid:17) (cid:54)(cid:36)(cid:36)
(cid:48)(cid:40)(cid:18) (cid:20)(cid:19) (cid:25)(cid:16) (cid:54)(cid:51)(cid:51)
(cid:48)(cid:40)(cid:19) (cid:20)(cid:20) (cid:48)(cid:40)(cid:17)(cid:18)

STM32F722xx STM32F723xx Pinouts and pin description
Figure 21. STM32F723xx LQFP176 pinout
(cid:48)(cid:54)(cid:23)(cid:20)(cid:19)(cid:27)(cid:21)(cid:57)(cid:20)
1. The above figure shows the package top view.
DocID029808 Rev 3 55/229
96
(cid:23)(cid:41)(cid:48) (cid:22)(cid:41)(cid:48) (cid:36)(cid:36)(cid:54)
(cid:46)(cid:47)(cid:63)(cid:50)(cid:36)(cid:48)
(cid:17)(cid:37)(cid:48) (cid:16)(cid:37)(cid:48) (cid:25)(cid:34)(cid:48) (cid:24)(cid:34)(cid:48)
(cid:16)(cid:52)(cid:47)(cid:47)(cid:34)
(cid:23)(cid:34)(cid:48) (cid:22)(cid:34)(cid:48) (cid:21)(cid:34)(cid:48) (cid:20)(cid:34)(cid:48) (cid:19)(cid:34)(cid:48) (cid:21)(cid:17)(cid:39)(cid:48) (cid:36)(cid:36)(cid:54) (cid:51)(cid:51)(cid:54) (cid:20)(cid:17)(cid:39)(cid:48) (cid:19)(cid:17)(cid:39)(cid:48) (cid:18)(cid:17)(cid:39)(cid:48) (cid:17)(cid:17)(cid:39)(cid:48) (cid:16)(cid:17)(cid:39)(cid:48) (cid:25)(cid:39)(cid:48) (cid:23)(cid:36)(cid:48) (cid:22)(cid:36)(cid:48)
(cid:35)(cid:45)(cid:45)(cid:36)(cid:51)(cid:36)(cid:36)(cid:54)
(cid:51)(cid:51)(cid:54) (cid:21)(cid:36)(cid:48) (cid:20)(cid:36)(cid:48) (cid:19)(cid:36)(cid:48) (cid:18)(cid:36)(cid:48) (cid:17)(cid:36)(cid:48) (cid:16)(cid:36)(cid:48) (cid:18)(cid:17)(cid:35)(cid:48) (cid:17)(cid:17)(cid:35)(cid:48) (cid:16)(cid:17)(cid:35)(cid:48)
(cid:48)(cid:37)(cid:18)
(cid:48)(cid:37)(cid:19)
(cid:48)(cid:37)(cid:20)
(cid:48)(cid:37)(cid:21)
(cid:48)(cid:37)(cid:22)
(cid:54)(cid:34)(cid:33)(cid:52) (cid:54)(cid:36)(cid:36)
(cid:48)(cid:41)(cid:24) (cid:54)(cid:51)(cid:51)
(cid:48)(cid:35)(cid:17)(cid:20) (cid:48)(cid:33)(cid:17)(cid:19)
(cid:48)(cid:35)(cid:17)(cid:21) (cid:48)(cid:33)(cid:17)(cid:18)
(cid:48)(cid:33)(cid:17)(cid:17)
(cid:48)(cid:33)(cid:17)(cid:16)
(cid:48)(cid:33)(cid:25)
(cid:48)(cid:33)(cid:24)
(cid:48)(cid:35)(cid:25)
(cid:48)(cid:38)(cid:16) (cid:48)(cid:35)(cid:24)
(cid:48)(cid:38)(cid:17) (cid:48)(cid:35)(cid:23)
(cid:48)(cid:38)(cid:18) (cid:48)(cid:35)(cid:22)
(cid:48)(cid:38)(cid:19) (cid:54)(cid:36)(cid:36)(cid:53)(cid:51)(cid:34)
(cid:48)(cid:38)(cid:20) (cid:54)(cid:51)(cid:51)
(cid:48)(cid:38)(cid:21) (cid:48)(cid:39)(cid:24)
(cid:48)(cid:39)(cid:21)
(cid:48)(cid:39)(cid:20)
(cid:48)(cid:38)(cid:22) (cid:48)(cid:39)(cid:19)
(cid:48)(cid:38)(cid:23) (cid:48)(cid:39)(cid:18)
(cid:48)(cid:38)(cid:24) (cid:48)(cid:36)(cid:17)(cid:21)
(cid:48)(cid:38)(cid:25) (cid:48)(cid:36)(cid:17)(cid:20)
(cid:48)(cid:38)(cid:17)(cid:16) (cid:54)(cid:36)(cid:36)
(cid:48)(cid:40)(cid:16) (cid:54)(cid:51)(cid:51)
(cid:48)(cid:40)(cid:17)
(cid:46)(cid:50)(cid:51)(cid:52)
(cid:48)(cid:35)(cid:16) (cid:48)(cid:36)(cid:17)(cid:17)
(cid:48)(cid:35)(cid:17) (cid:48)(cid:36)(cid:17)(cid:16)
(cid:48)(cid:35)(cid:18) (cid:48)(cid:36)(cid:25)
(cid:48)(cid:35)(cid:19) (cid:48)(cid:36)(cid:24)
(cid:48)(cid:34)(cid:17)(cid:21)
(cid:48)(cid:34)(cid:17)(cid:20)
(cid:54)(cid:50)(cid:37)(cid:38)(cid:11) (cid:54)(cid:36)(cid:36)(cid:17)(cid:18)(cid:47)(cid:52)(cid:39)(cid:40)(cid:51)
(cid:47)(cid:52)(cid:39)(cid:63)(cid:40)(cid:51)(cid:63)(cid:50)(cid:37)(cid:56)(cid:52)
(cid:48)(cid:33)(cid:16) (cid:48)(cid:34)(cid:17)(cid:19)
(cid:48)(cid:33)(cid:17) (cid:48)(cid:34)(cid:17)(cid:18)
(cid:48)(cid:33)(cid:18)
(cid:22)(cid:23)(cid:17) (cid:21)(cid:23)(cid:17) (cid:20)(cid:23)(cid:17)
(cid:19)(cid:33)(cid:48)
(cid:19)(cid:23)(cid:17)
(cid:39)(cid:37)(cid:50)(cid:63)(cid:51)(cid:51)(cid:33)(cid:48)(cid:57)(cid:34)
(cid:18)(cid:23)(cid:17)
(cid:36)(cid:36)(cid:54)
(cid:17)(cid:23)(cid:17)
(cid:20)(cid:33)(cid:48)
(cid:16)(cid:23)(cid:17)
(cid:21)(cid:33)(cid:48)
(cid:25)(cid:22)(cid:17)
(cid:22)(cid:33)(cid:48)
(cid:24)(cid:22)(cid:17)
(cid:23)(cid:33)(cid:48)
(cid:23)(cid:22)(cid:17)
(cid:20)(cid:35)(cid:48)
(cid:22)(cid:22)(cid:17)
(cid:21)(cid:35)(cid:48)
(cid:21)(cid:22)(cid:17)
(cid:16)(cid:34)(cid:48)
(cid:20)(cid:22)(cid:17)
(cid:17)(cid:34)(cid:48)
(cid:19)(cid:22)(cid:17)
(cid:18)(cid:34)(cid:48)
(cid:18)(cid:22)(cid:17)
(cid:17)(cid:17)(cid:38)(cid:48)
(cid:17)(cid:22)(cid:17)
(cid:18)(cid:17)(cid:38)(cid:48)
(cid:16)(cid:22)(cid:17)
(cid:51)(cid:51)(cid:54)
(cid:25)(cid:21)(cid:17)
(cid:36)(cid:36)(cid:54)
(cid:24)(cid:21)(cid:17)
(cid:19)(cid:17)(cid:38)(cid:48)
(cid:23)(cid:21)(cid:17)
(cid:20)(cid:17)(cid:38)(cid:48)
(cid:22)(cid:21)(cid:17)
(cid:21)(cid:17)(cid:38)(cid:48)
(cid:21)(cid:21)(cid:17)
(cid:16)(cid:39)(cid:48)
(cid:20)(cid:21)(cid:17)
(cid:17)(cid:39)(cid:48)
(cid:19)(cid:21)(cid:17)
(cid:23)(cid:37)(cid:48) (cid:24)(cid:37)(cid:48) (cid:25)(cid:37)(cid:48) (cid:51)(cid:51)(cid:54) (cid:36)(cid:36)(cid:54) (cid:16)(cid:17)(cid:37)(cid:48) (cid:17)(cid:17)(cid:37)(cid:48) (cid:18)(cid:17)(cid:37)(cid:48) (cid:19)(cid:17)(cid:37)(cid:48) (cid:20)(cid:17)(cid:37)(cid:48) (cid:21)(cid:17)(cid:37)(cid:48) (cid:16)(cid:17)(cid:34)(cid:48)
(cid:17)(cid:20)(cid:17)
(cid:17)(cid:17)(cid:34)(cid:48) (cid:17)(cid:63)(cid:48)(cid:33)(cid:35)(cid:54) (cid:36)(cid:36)(cid:54)
(cid:17) (cid:17)(cid:19)(cid:18)
(cid:18) (cid:17)(cid:19)(cid:17)
(cid:19) (cid:17)(cid:19)(cid:16)
(cid:20) (cid:17)(cid:18)(cid:25)
(cid:21) (cid:17)(cid:18)(cid:24)
(cid:22) (cid:17)(cid:18)(cid:23)
(cid:23) (cid:17)(cid:18)(cid:22)
(cid:24) (cid:17)(cid:18)(cid:21)
(cid:25) (cid:17)(cid:18)(cid:20)
(cid:17)(cid:16) (cid:17)(cid:18)(cid:19)
(cid:17)(cid:17) (cid:17)(cid:18)(cid:18)
(cid:17)(cid:18) (cid:17)(cid:18)(cid:17)
(cid:17)(cid:19) (cid:17)(cid:18)(cid:16)
(cid:17)(cid:20) (cid:17)(cid:17)(cid:25)
(cid:17)(cid:21) (cid:17)(cid:17)(cid:24)
(cid:17)(cid:22) (cid:17)(cid:17)(cid:23)
(cid:17)(cid:23) (cid:17)(cid:17)(cid:22)
(cid:17)(cid:24) (cid:17)(cid:17)(cid:21)
(cid:17)(cid:25) (cid:17)(cid:17)(cid:20)
(cid:18)(cid:16) (cid:17)(cid:17)(cid:19)
(cid:18)(cid:17) (cid:17)(cid:17)(cid:18)
(cid:18)(cid:18) (cid:17)(cid:17)(cid:17)
(cid:18)(cid:19) (cid:17)(cid:17)(cid:16)
(cid:18)(cid:20) (cid:17)(cid:16)(cid:25)
(cid:18)(cid:21) (cid:17)(cid:16)(cid:24)
(cid:21)(cid:20) (cid:22)(cid:20) (cid:23)(cid:20) (cid:24)(cid:20) (cid:25)(cid:20) (cid:16)(cid:21) (cid:17)(cid:21) (cid:18)(cid:21) (cid:19)(cid:21) (cid:20)(cid:21) (cid:21)(cid:21) (cid:22)(cid:21) (cid:23)(cid:21) (cid:24)(cid:21) (cid:25)(cid:21) (cid:16)(cid:22) (cid:17)(cid:22) (cid:18)(cid:22) (cid:19)(cid:22) (cid:20)(cid:22) (cid:21)(cid:22) (cid:22)(cid:22) (cid:23)(cid:22) (cid:24)(cid:22) (cid:16)(cid:24)
(cid:3)(cid:3)(cid:47)(cid:52)(cid:41)(cid:51)(cid:20)(cid:26)(cid:25)
(cid:90)(cid:76)(cid:87)(cid:75)(cid:3)(cid:43)(cid:54)(cid:3)(cid:51)(cid:43)(cid:60)(cid:3)
(cid:18)(cid:21)(cid:17)
(cid:25)(cid:22)
(cid:17)(cid:21)(cid:17)
(cid:16)(cid:23)
(cid:16)(cid:21)(cid:17)
(cid:17)(cid:23)
(cid:25)(cid:20)(cid:17)
(cid:18)(cid:23)
(cid:24)(cid:20)(cid:17)
(cid:19)(cid:23)
(cid:23)(cid:20)(cid:17)
(cid:20)(cid:23)
(cid:22)(cid:20)(cid:17)
(cid:21)(cid:23)
(cid:21)(cid:20)(cid:17)
(cid:22)(cid:23)
(cid:20)(cid:20)(cid:17)
(cid:23)(cid:23)
(cid:19)(cid:20)(cid:17)
(cid:24)(cid:23)
(cid:18)(cid:20)(cid:17)
(cid:25)(cid:23)
(cid:54)(cid:35)(cid:33)(cid:48)(cid:63)(cid:18)
(cid:18)(cid:22) (cid:17)(cid:16)(cid:23)
(cid:18)(cid:23) (cid:17)(cid:16)(cid:22)
(cid:18)(cid:24) (cid:17)(cid:16)(cid:21)
(cid:18)(cid:25) (cid:17)(cid:16)(cid:20)
(cid:19)(cid:16) (cid:17)(cid:16)(cid:19)
(cid:19)(cid:17) (cid:17)(cid:16)(cid:18)
(cid:19)(cid:18) (cid:17)(cid:16)(cid:17)
(cid:19)(cid:19) (cid:17)(cid:16)(cid:16)
(cid:19)(cid:20) (cid:25)(cid:25)
(cid:19)(cid:21) (cid:25)(cid:24)
(cid:19)(cid:22)
(cid:24)(cid:25)
(cid:20)(cid:40)(cid:48) (cid:21)(cid:40)(cid:48)
(cid:21)(cid:41)(cid:48) (cid:20)(cid:41)(cid:48)
(cid:16)(cid:20)(cid:17)
(cid:17)(cid:24)
(cid:25)(cid:19)(cid:17)
(cid:18)(cid:24)
(cid:21)(cid:17)(cid:33)(cid:48)
(cid:24)(cid:19)(cid:17)
(cid:19)(cid:24)
(cid:22)(cid:40)(cid:48)
(cid:20)(cid:17)(cid:33)(cid:48)
(cid:23)(cid:19)(cid:17)
(cid:20)(cid:24)
(cid:23)(cid:40)(cid:48)
(cid:36)(cid:36)(cid:54)
(cid:22)(cid:19)(cid:17)
(cid:21)(cid:24)
(cid:24)(cid:40)(cid:48)
(cid:51)(cid:51)(cid:54)
(cid:21)(cid:19)(cid:17)
(cid:22)(cid:24)
(cid:25)(cid:40)(cid:48)
(cid:19)(cid:41)(cid:48)
(cid:20)(cid:19)(cid:17)
(cid:23)(cid:24)
(cid:16)(cid:17)(cid:40)(cid:48)
(cid:18)(cid:41)(cid:48)
(cid:19)(cid:19)(cid:17)
(cid:24)(cid:24)
(cid:17)(cid:17)(cid:40)(cid:48)
(cid:48)(cid:41)(cid:17)
(cid:48)(cid:41)(cid:16)
(cid:48)(cid:40)(cid:17)(cid:21)
(cid:48)(cid:40)(cid:17)(cid:20)
(cid:48)(cid:40)(cid:17)(cid:19)
(cid:48)(cid:35)(cid:17)(cid:19)
(cid:48)(cid:41)(cid:25)
(cid:48)(cid:41)(cid:17)(cid:16)
(cid:48)(cid:41)(cid:17)(cid:17)
(cid:54)(cid:51)(cid:51)
(cid:54)(cid:36)(cid:36)
(cid:54)(cid:51)(cid:51)
(cid:54)(cid:36)(cid:36)
(cid:48)(cid:36)(cid:17)(cid:19)
(cid:48)(cid:36)(cid:17)(cid:18)
(cid:54)(cid:36)(cid:36) (cid:25)(cid:23)
(cid:54)(cid:51)(cid:51)(cid:33) (cid:19)(cid:23) (cid:25)(cid:22)
(cid:19)(cid:24) (cid:25)(cid:21)
(cid:54)(cid:36)(cid:36)(cid:33) (cid:19)(cid:25) (cid:25)(cid:20)
(cid:20)(cid:16) (cid:25)(cid:19)
(cid:20)(cid:17) (cid:25)(cid:18)
(cid:20)(cid:18) (cid:25)(cid:17) (cid:54)(cid:36)(cid:36)
(cid:48)(cid:40)(cid:18) (cid:20)(cid:19) (cid:25)(cid:16) (cid:54)(cid:51)(cid:51)
(cid:48)(cid:40)(cid:19) (cid:20)(cid:20) (cid:48)(cid:40)(cid:17)(cid:18)

| Pinouts and pin description |     |     |     |     |     |     | STM32F722xx STM32F723xx |     |
| --------------------------- | --- | --- | --- | --- | --- | --- | ----------------------- | --- |
Figure 22. STM32F723xx UFBGA176 ballout
(cid:17) (cid:18) (cid:19) (cid:20) (cid:21) (cid:22) (cid:23) (cid:24) (cid:25) (cid:17)(cid:16) (cid:17)(cid:17) (cid:17)(cid:18) (cid:17)(cid:19) (cid:17)(cid:20) (cid:17)(cid:21)
| (cid:33) (cid:48)(cid:37)(cid:19) | (cid:48)(cid:37)(cid:18) | (cid:48)(cid:37)(cid:17) (cid:48)(cid:37)(cid:16) | (cid:48)(cid:34)(cid:24) (cid:48)(cid:34)(cid:21) |                                                                   |                          |                                                   |                                                                   |                                                                   |
| --------------------------------- | ------------------------ | ------------------------------------------------- | ------------------------------------------------- | ----------------------------------------------------------------- | ------------------------ | ------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
|                                   |                          |                                                   |                                                   | (cid:48)(cid:39)(cid:17)(cid:20) (cid:48)(cid:39)(cid:17)(cid:19) | (cid:48)(cid:34)(cid:20) | (cid:48)(cid:34)(cid:19) (cid:48)(cid:36)(cid:23) | (cid:48)(cid:35)(cid:17)(cid:18) (cid:48)(cid:33)(cid:17)(cid:21) | (cid:48)(cid:33)(cid:17)(cid:20) (cid:48)(cid:33)(cid:17)(cid:19) |
|                                   |                          | (cid:48)(cid:34)(cid:25)                          | (cid:48)(cid:34)(cid:23)                          |                                                                   |                          |                                                   |                                                                   |                                                                   |
(cid:34) (cid:48)(cid:37)(cid:20) (cid:48)(cid:37)(cid:21) (cid:48)(cid:37)(cid:22) (cid:48)(cid:34)(cid:22) (cid:48)(cid:39)(cid:17)(cid:21) (cid:48)(cid:39)(cid:17)(cid:18) (cid:48)(cid:39)(cid:17)(cid:17) (cid:48)(cid:39)(cid:17)(cid:16) (cid:48)(cid:36)(cid:22) (cid:48)(cid:36)(cid:16) (cid:48)(cid:35)(cid:17)(cid:17) (cid:48)(cid:35)(cid:17)(cid:16) (cid:48)(cid:33)(cid:17)(cid:18)
| (cid:54)(cid:34)(cid:33)(cid:52) | (cid:48)(cid:41)(cid:23) | (cid:48)(cid:41)(cid:22) (cid:48)(cid:41)(cid:21) | (cid:54)(cid:36)(cid:36) (cid:48)(cid:36)(cid:50)(cid:63)(cid:47)(cid:46) | (cid:54) (cid:36) | (cid:36) (cid:0) |     |     |     |
| -------------------------------- | ------------------------ | ------------------------------------------------- | ------------------------------------------------------------------------- | ----------------- | ---------------- | --- | --- | --- |
(cid:35) (cid:54)(cid:36)(cid:36) (cid:51) (cid:36) (cid:45) (cid:45)(cid:35) (cid:54)(cid:36)(cid:36) (cid:48)(cid:39)(cid:25) (cid:48)(cid:36)(cid:21) (cid:48)(cid:36)(cid:17) (cid:48)(cid:41)(cid:19) (cid:48)(cid:41)(cid:18) (cid:48)(cid:33)(cid:17)(cid:17)
(cid:36) (cid:48)(cid:35)(cid:17)(cid:19) (cid:48)(cid:41)(cid:24) (cid:48)(cid:41)(cid:25) (cid:48)(cid:41)(cid:20) (cid:54)(cid:51)(cid:51) (cid:34)(cid:47)(cid:47)(cid:52)(cid:16) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:48)(cid:36)(cid:20) (cid:48)(cid:36)(cid:19) (cid:48)(cid:36)(cid:18) (cid:48)(cid:40)(cid:17)(cid:21) (cid:48)(cid:41)(cid:17) (cid:48)(cid:33)(cid:17)(cid:16)
(cid:48)(cid:35)(cid:17)(cid:20) (cid:48)(cid:38)(cid:16) (cid:48)(cid:41)(cid:17)(cid:16) (cid:48)(cid:41)(cid:17)(cid:17) (cid:48)(cid:40)(cid:17)(cid:19) (cid:48)(cid:40)(cid:17)(cid:20) (cid:48)(cid:41)(cid:16) (cid:48)(cid:33)(cid:25)
(cid:37)
(cid:38) (cid:48)(cid:35)(cid:17)(cid:21) (cid:54)(cid:51)(cid:51) (cid:54)(cid:36)(cid:36) (cid:48)(cid:40)(cid:18) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:35)(cid:33)(cid:48)(cid:18) (cid:48)(cid:35)(cid:25) (cid:48)(cid:33)(cid:24)
(cid:39) (cid:48)(cid:40)(cid:16) (cid:54)(cid:51)(cid:51) (cid:54)(cid:36)(cid:36) (cid:48)(cid:40)(cid:19) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:36)(cid:36) (cid:48)(cid:35)(cid:24) (cid:48)(cid:35)(cid:23)
(cid:40) (cid:48)(cid:40)(cid:17) (cid:48)(cid:38)(cid:18) (cid:48)(cid:38)(cid:17) (cid:48)(cid:40)(cid:20) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:36)(cid:36)(cid:53)(cid:51)(cid:34) (cid:48)(cid:39)(cid:24) (cid:48)(cid:35)(cid:22)
(cid:42) (cid:46)(cid:50)(cid:51)(cid:52) (cid:48)(cid:38)(cid:19)(cid:0) (cid:48)(cid:38)(cid:20)(cid:0) (cid:48)(cid:40)(cid:21) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:36)(cid:36) (cid:54)(cid:36)(cid:36) (cid:48)(cid:39)(cid:23) (cid:48)(cid:39)(cid:22)
(cid:48)(cid:38)(cid:21)
(cid:43) (cid:48)(cid:38)(cid:23) (cid:48)(cid:38)(cid:22) (cid:54)(cid:36)(cid:36) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:48)(cid:40)(cid:17)(cid:18) (cid:48)(cid:39)(cid:21) (cid:48)(cid:39)(cid:20) (cid:48)(cid:39)(cid:19)
(cid:44) (cid:48)(cid:38)(cid:25) (cid:48)(cid:38)(cid:24) (cid:34)(cid:57) (cid:48)(cid:33) (cid:51) (cid:51)(cid:63) (cid:48)(cid:40)(cid:17)(cid:17) (cid:48)(cid:40)(cid:17)(cid:16) (cid:48)(cid:36)(cid:17)(cid:21) (cid:48)(cid:39)(cid:18)
| (cid:48)(cid:38)(cid:17)(cid:16)          |                          | (cid:50) (cid:37)                                 | (cid:39)                 |                                                   |                          |                                                                           |                                                   |                                                                   |
| ----------------------------------------- | ------------------------ | ------------------------------------------------- | ------------------------ | ------------------------------------------------- | ------------------------ | ------------------------------------------------------------------------- | ------------------------------------------------- | ----------------------------------------------------------------- |
|                                           |                          |                                                   | (cid:48)(cid:34)(cid:18) | (cid:48)(cid:39)(cid:17) (cid:54)(cid:51)(cid:51) | (cid:54)(cid:51)(cid:51) | (cid:54)(cid:35)(cid:33)(cid:48)(cid:63)(cid:17) (cid:48)(cid:40)(cid:22) | (cid:48)(cid:40)(cid:24) (cid:48)(cid:40)(cid:25) | (cid:48)(cid:36)(cid:17)(cid:20) (cid:48)(cid:36)(cid:17)(cid:19) |
| (cid:45) (cid:54)(cid:51)(cid:51)(cid:33) | (cid:48)(cid:35)(cid:16) | (cid:48)(cid:35)(cid:17) (cid:48)(cid:35)(cid:18) | (cid:48)(cid:35)(cid:19) |                                                   |                          |                                                                           |                                                   |                                                                   |
(cid:46) (cid:54)(cid:50)(cid:37)(cid:38)(cid:13) (cid:48)(cid:33)(cid:17) (cid:48)(cid:33)(cid:16) (cid:48)(cid:33)(cid:20) (cid:48)(cid:35)(cid:20) (cid:48)(cid:38)(cid:17)(cid:19) (cid:48)(cid:39)(cid:16) (cid:54)(cid:36)(cid:36) (cid:54)(cid:36)(cid:36) (cid:54)(cid:36)(cid:36) (cid:48)(cid:37)(cid:17)(cid:19) (cid:48)(cid:40)(cid:23) (cid:48)(cid:36)(cid:17)(cid:18) (cid:48)(cid:36)(cid:17)(cid:17) (cid:48)(cid:36)(cid:17)(cid:16)
|     | (cid:48)(cid:33)(cid:18) | (cid:48)(cid:33)(cid:22) (cid:48)(cid:33)(cid:21) | (cid:48)(cid:35)(cid:21) (cid:48)(cid:38)(cid:17)(cid:18) | (cid:48)(cid:38)(cid:17)(cid:21) (cid:48)(cid:37)(cid:24) | (cid:48)(cid:37)(cid:25) | (cid:48)(cid:37)(cid:17)(cid:17) (cid:48)(cid:37)(cid:17)(cid:20) | (cid:48)(cid:34)(cid:17)(cid:18) (cid:48)(cid:34)(cid:17)(cid:19) | (cid:48)(cid:36)(cid:25) (cid:48)(cid:36)(cid:24) |
| --- | ------------------------ | ------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | ------------------------ | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ------------------------------------------------- |
(cid:48) (cid:54)(cid:50)(cid:37)(cid:38)(cid:11)
(cid:50) (cid:54)(cid:36)(cid:36)(cid:33) (cid:48)(cid:33)(cid:19) (cid:48)(cid:33)(cid:23) (cid:48)(cid:34)(cid:17) (cid:48)(cid:34)(cid:16) (cid:48)(cid:38)(cid:17)(cid:17) (cid:48)(cid:38)(cid:17)(cid:20) (cid:48)(cid:37)(cid:23) (cid:48)(cid:37)(cid:17)(cid:16) (cid:48)(cid:37)(cid:17)(cid:18) (cid:48)(cid:37)(cid:17)(cid:21) (cid:48)(cid:34)(cid:17)(cid:16) (cid:48)(cid:34)(cid:17)(cid:17) (cid:48)(cid:34)(cid:17)(cid:20)(cid:0) (cid:48)(cid:34)(cid:17)(cid:21)
(cid:45)(cid:51)(cid:19)(cid:25)(cid:17)(cid:19)(cid:16)(cid:54)(cid:17)
1. The above figure shows the package top view.
| 56/229 |     |     |     | DocID029808 Rev 3 |     |     |     |     |
| ------ | --- | --- | --- | ----------------- | --- | --- | --- | --- |

STM32F722xx STM32F723xx Pinouts and pin description
Figure 23. STM32F723xx UFBGA176 ballout (with OTG PHY HS)
(cid:17) (cid:18) (cid:19) (cid:20) (cid:21) (cid:22) (cid:23) (cid:24) (cid:25) (cid:17)(cid:16) (cid:17)(cid:17) (cid:17)(cid:18) (cid:17)(cid:19) (cid:17)(cid:20) (cid:17)(cid:21)
(cid:33) (cid:48)(cid:37)(cid:19) (cid:48)(cid:37)(cid:18) (cid:48)(cid:37)(cid:17) (cid:48)(cid:37)(cid:16) (cid:48)(cid:34)(cid:24) (cid:48)(cid:34)(cid:21) (cid:48)(cid:39)(cid:17)(cid:20) (cid:48)(cid:39)(cid:17)(cid:19) (cid:48)(cid:34)(cid:20) (cid:48)(cid:34)(cid:19) (cid:48)(cid:36)(cid:23) (cid:48)(cid:35)(cid:17)(cid:18) (cid:48)(cid:33)(cid:17)(cid:21) (cid:48)(cid:33)(cid:17)(cid:20) (cid:48)(cid:33)(cid:17)(cid:19)
(cid:34) (cid:48)(cid:37)(cid:20) (cid:48)(cid:37)(cid:21) (cid:48)(cid:37)(cid:22) (cid:48)(cid:34)(cid:25) (cid:48)(cid:34)(cid:23) (cid:48)(cid:34)(cid:22) (cid:48)(cid:39)(cid:17)(cid:21) (cid:48)(cid:39)(cid:17)(cid:18) (cid:48)(cid:39)(cid:17)(cid:17) (cid:48)(cid:39)(cid:17)(cid:16) (cid:48)(cid:36)(cid:22) (cid:48)(cid:36)(cid:16) (cid:48)(cid:35)(cid:17)(cid:17) (cid:48)(cid:35)(cid:17)(cid:16) (cid:48)(cid:33)(cid:17)(cid:18)
(cid:35) (cid:54)(cid:34)(cid:33)(cid:52) (cid:48)(cid:41)(cid:23) (cid:48)(cid:41)(cid:22) (cid:48)(cid:41)(cid:21) (cid:54)(cid:36)(cid:36) (cid:48)(cid:36)(cid:50)(cid:63)(cid:47)(cid:46) (cid:54)(cid:36)(cid:36) (cid:54) (cid:51) (cid:36) (cid:36) (cid:36) (cid:45) (cid:0) (cid:45)(cid:35) (cid:54)(cid:36)(cid:36) (cid:48)(cid:39)(cid:25) (cid:48)(cid:36)(cid:21) (cid:48)(cid:36)(cid:17) (cid:48)(cid:41)(cid:19) (cid:48)(cid:41)(cid:18) (cid:48)(cid:33)(cid:17)(cid:17)
(cid:36) (cid:48)(cid:35)(cid:17)(cid:19) (cid:48)(cid:41)(cid:24) (cid:48)(cid:41)(cid:25) (cid:48)(cid:41)(cid:20) (cid:54)(cid:51)(cid:51) (cid:34)(cid:47)(cid:47)(cid:52)(cid:16) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:48)(cid:36)(cid:20) (cid:48)(cid:36)(cid:19) (cid:48)(cid:36)(cid:18) (cid:48)(cid:40)(cid:17)(cid:21) (cid:48)(cid:41)(cid:17) (cid:48)(cid:33)(cid:17)(cid:16)
(cid:37) (cid:48)(cid:35)(cid:17)(cid:20) (cid:48)(cid:38)(cid:16) (cid:48)(cid:41)(cid:17)(cid:16) (cid:48)(cid:41)(cid:17)(cid:17) (cid:48)(cid:40)(cid:17)(cid:19) (cid:48)(cid:40)(cid:17)(cid:20) (cid:48)(cid:41)(cid:16) (cid:48)(cid:33)(cid:25)
(cid:38) (cid:48)(cid:35)(cid:17)(cid:21) (cid:54)(cid:51)(cid:51) (cid:54)(cid:36)(cid:36) (cid:48)(cid:40)(cid:18) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:35)(cid:33)(cid:48)(cid:18) (cid:48)(cid:35)(cid:25) (cid:48)(cid:33)(cid:24)
(cid:39) (cid:48)(cid:40)(cid:16) (cid:54)(cid:51)(cid:51) (cid:54)(cid:36)(cid:36) (cid:48)(cid:40)(cid:19) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:36)(cid:36) (cid:48)(cid:35)(cid:24) (cid:48)(cid:35)(cid:23)
(cid:40) (cid:48)(cid:40)(cid:17) (cid:48)(cid:38)(cid:18) (cid:48)(cid:38)(cid:17) (cid:48)(cid:40)(cid:20) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:36)(cid:36)(cid:53)(cid:51)(cid:34) (cid:48)(cid:39)(cid:24) (cid:48)(cid:35)(cid:22)
(cid:42) (cid:46)(cid:50)(cid:51)(cid:52) (cid:48)(cid:38)(cid:19)(cid:0) (cid:48)(cid:38)(cid:20)(cid:0) (cid:48)(cid:40)(cid:21) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:36)(cid:36) (cid:54)(cid:36)(cid:36) (cid:54) (cid:47) (cid:36) (cid:52)(cid:39) (cid:36)(cid:17) (cid:40) (cid:18) (cid:51) (cid:0) (cid:47) (cid:63)(cid:50) (cid:52) (cid:37) (cid:39) (cid:56) (cid:63) (cid:52) (cid:40)(cid:51)(cid:0)
(cid:43) (cid:48)(cid:38)(cid:23) (cid:48)(cid:38)(cid:22) (cid:48)(cid:38)(cid:21) (cid:54)(cid:36)(cid:36) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:48)(cid:40)(cid:17)(cid:18) (cid:48)(cid:39)(cid:21) (cid:48)(cid:39)(cid:20) (cid:48)(cid:39)(cid:19)
(cid:44) (cid:48)(cid:38)(cid:17)(cid:16) (cid:48)(cid:38)(cid:25) (cid:48)(cid:38)(cid:24) (cid:34)(cid:57) (cid:50) (cid:48)(cid:33) (cid:37) (cid:51) (cid:39) (cid:51)(cid:63) (cid:48)(cid:40)(cid:17)(cid:17) (cid:48)(cid:40)(cid:17)(cid:16) (cid:48)(cid:36)(cid:17)(cid:21) (cid:48)(cid:39)(cid:18)
(cid:45) (cid:54)(cid:51)(cid:51)(cid:33) (cid:48)(cid:35)(cid:16) (cid:48)(cid:35)(cid:17) (cid:48)(cid:35)(cid:18) (cid:48)(cid:35)(cid:19) (cid:48)(cid:34)(cid:18) (cid:48)(cid:39)(cid:17) (cid:54)(cid:51)(cid:51) (cid:54)(cid:51)(cid:51) (cid:54)(cid:35)(cid:33)(cid:48)(cid:63)(cid:17) (cid:48)(cid:40)(cid:22) (cid:48)(cid:40)(cid:24) (cid:48)(cid:40)(cid:25) (cid:48)(cid:36)(cid:17)(cid:20) (cid:48)(cid:36)(cid:17)(cid:19)
(cid:46) (cid:54)(cid:50)(cid:37)(cid:38)(cid:13) (cid:48)(cid:33)(cid:17) (cid:48)(cid:33)(cid:16) (cid:48)(cid:33)(cid:20) (cid:48)(cid:35)(cid:20) (cid:48)(cid:38)(cid:17)(cid:19) (cid:48)(cid:39)(cid:16) (cid:54)(cid:36)(cid:36) (cid:54)(cid:36)(cid:36) (cid:54)(cid:36)(cid:36) (cid:48)(cid:37)(cid:17)(cid:19) (cid:48)(cid:40)(cid:23) (cid:48)(cid:36)(cid:17)(cid:18) (cid:48)(cid:36)(cid:17)(cid:17) (cid:48)(cid:36)(cid:17)(cid:16)
(cid:48) (cid:54)(cid:50)(cid:37)(cid:38)(cid:11) (cid:48)(cid:33)(cid:18) (cid:48)(cid:33)(cid:22) (cid:48)(cid:33)(cid:21) (cid:48)(cid:35)(cid:21) (cid:48)(cid:38)(cid:17)(cid:18) (cid:48)(cid:38)(cid:17)(cid:21) (cid:48)(cid:37)(cid:24) (cid:48)(cid:37)(cid:25) (cid:48)(cid:37)(cid:17)(cid:17) (cid:48)(cid:37)(cid:17)(cid:20) (cid:48)(cid:34)(cid:17)(cid:18) (cid:48)(cid:34)(cid:17)(cid:19) (cid:48)(cid:36)(cid:25) (cid:48)(cid:36)(cid:24)
(cid:50) (cid:54)(cid:36)(cid:36)(cid:33) (cid:48)(cid:33)(cid:19) (cid:48)(cid:33)(cid:23) (cid:48)(cid:34)(cid:17) (cid:48)(cid:34)(cid:16) (cid:48)(cid:38)(cid:17)(cid:17) (cid:48)(cid:38)(cid:17)(cid:20) (cid:48)(cid:37)(cid:23) (cid:48)(cid:37)(cid:17)(cid:16) (cid:48)(cid:37)(cid:17)(cid:18) (cid:48)(cid:37)(cid:17)(cid:21) (cid:48)(cid:34)(cid:17)(cid:16) (cid:48)(cid:34)(cid:17)(cid:17) (cid:48)(cid:34)(cid:17)(cid:20)(cid:0) (cid:48)(cid:34)(cid:17)(cid:21)
(cid:45)(cid:51)(cid:20)(cid:18)(cid:16)(cid:16)(cid:17)(cid:54)(cid:17)
1. The above figure shows the package top view.
DocID029808 Rev 3 57/229
96

Pinouts and pin description STM32F722xx STM32F723xx

Table 9. Legend/abbreviations used in the pinout table
| Name | Abbreviation | Definition |
| ---- | ------------ | ---------- |
Unless otherwise specified in brackets below the pin name, the pin function during and after
Pin name
reset is the same as the actual pin name
|          | S                                     | Supply pin         |
| -------- | ------------------------------------- | ------------------ |
| Pin type | I                                     | Input only pin     |
|          | I/O                                   | Input / output pin |
|          | FT                                    | 5 V tolerant I/O   |
|          | FTf  5V tolerant I/O, I2C Fm+ option. |                    |
I/O structure TTa 3.3 V tolerant I/O directly connected to ADC
|     | B   | Dedicated BOOT pin |
| --- | --- | ------------------ |
RST Bidirectional reset pin with weak pull-up resistor
Notes Unless otherwise specified by a note, all I/Os are set as floating inputs during and after reset
Alternate
Functions selected through GPIOx_AFR registers
functions
Additional
Functions directly selected/enabled through peripheral registers
functions
58/229 DocID029808 Rev 3

STM32F722xx STM32F723xx
Table 10. STM32F722xx and STM32F723xx pin and ball definition
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |          |                   |          | Pin name         | epyt niP |                     |           |
| --- | -------- | ----------------- | -------- | ---------------- | -------- | ------------------- | --------- |
|     |          |                   |          |                  | setoN    | Additional          |           |
|     |          |                   |          | (function after  |          | Alternate functions |           |
|     |          |                   |          | reset)(1)        |          |                     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |          |                     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL | 671PFQL |     |     |     |
| ------- | ------- | --- | ------- | ------- | --- | --- | --- |
46PFQL
TRACECLK, SPI4_SCK,
SAI1_MCLK_A,
| - 1 1 | A2 1 | C9 A2 | A3 1 | 1 PE2 | I/O FT - |     | -   |
| ----- | ---- | ----- | ---- | ----- | -------- | --- | --- |
QUADSPI_BK1_IO2, FMC_A23,
EVENTOUT
DocID029808 Rev 3
TRACED0, SAI1_SD_B,
| - 2 2 | A1 2 | A10 A1 | A2 2 | 2 PE3 | I/O FT - |     | -   |
| ----- | ---- | ------ | ---- | ----- | -------- | --- | --- |
FMC_A19, EVENTOUT
TRACED1, SPI4_NSS,
| - 3 3 | B1 3 | D9 B1 | B2 3 | 3 PE4 | I/O FT - | SAI1_FS_A, FMC_A20,  | -   |
| ----- | ---- | ----- | ---- | ----- | -------- | -------------------- | --- |
EVENTOUT
TRACED2, TIM9_CH1,
- 4 4 B2 4 E8 B2 B3 4 4 PE5 I/O FT - SPI4_MISO, SAI1_SCK_A,  - Pinouts and pin description
FMC_A21, EVENTOUT
TRACED3, TIM1_BKIN2,
TIM9_CH2, SPI4_MOSI,
| - 5 5 | B3 5 | B10 B3 | B4 5 | 5 PE6 | I/O FT - |     | -   |
| ----- | ---- | ------ | ---- | ----- | -------- | --- | --- |
SAI1_SD_A, SAI2_MCK_B,
FMC_A22, EVENTOUT
| 1 6 6 | C1 6 | C10 C1 | C2 6 | 6 VBAT | S - - | -   | -   |
| ----- | ---- | ------ | ---- | ------ | ----- | --- | --- |
59/229

60/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |          |                   |          | Pin name         | epyt niP |                     |             |
| --- | -------- | ----------------- | -------- | ---------------- | -------- | ------------------- | ----------- |
|     |          |                   |          |                  | setoN    |                     | Additional  |
|     |          |                   |          | (function after  |          | Alternate functions |             |
|     |          |                   |          | reset)(1)        |          |                     | functions   |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |          |                     |             |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
RTC_TAMP2/
(2)
| - - - | D2 7 | - D2 | - - 7 | PI8 | I/O FT | EVENTOUT |          |
| ----- | ---- | ---- | ----- | --- | ------ | -------- | -------- |
|       |      |      |       |     | (3)    |          | RTC_TS,  |
WKUP5
RTC_TAMP1/
(2)
DocID029808 Rev 3 RTC_TS/
| 2 7 7 | D1 8 | D10 D1 | A1 7 8 | PC13 | I/O FT | EVENTOUT |           |
| ----- | ---- | ------ | ------ | ---- | ------ | -------- | --------- |
|       |      |        |        |      | (3)    |          | RTC_OUT,  |
WKUP4
|     |     |     |     | PC14- | (2) |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- |
3 8 8 E1 9 E9 E1 B1 8 9 OSC32_IN(PC1 I/O FT EVENTOUT OSC32_IN
(3)
4)
|     |     |     |     | PC15- | (2) |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- |
4 9 9 F1 10 E10 F1 C1 9 10 OSC32_OUT(P I/O FT EVENTOUT OSC32_OUT
(3)
C15)
UART4_RX, CAN1_RX,
| - - - | D3 11 | - D3 | - - 11 | PI9 | I/O FT - |     | -   |
| ----- | ----- | ---- | ------ | --- | -------- | --- | --- |
FMC_D30, EVENTOUT
STM32F722xx STM32F723xx
| - - - | E3 12 | - E3 | - - 12 | PI10 | I/O FT - | FMC_D31, EVENTOUT | -   |
| ----- | ----- | ---- | ------ | ---- | -------- | ----------------- | --- |
OTG_HS_ULPI_DIR,
(4)
| - - - | E4 13 | - E4 | - - 13 | PI11 | I/O FT |     | WKUP6 |
| ----- | ----- | ---- | ------ | ---- | ------ | --- | ----- |
EVENTOUT
| - - - | F2 14 | - F2 | - - 14 | VSS | S - - | -   | -   |
| ----- | ----- | ---- | ------ | --- | ----- | --- | --- |
| - - - | F3 15 | - F3 | - - 15 | VDD | S - - | -   | -   |

Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) STM32F722xx STM32F723xx
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL | 671PFQL |     |     |     |
| ------- | ------- | --- | ------- | ------- | --- | --- | --- |
46PFQL
I2C2_SDA, FMC_A0,
| - - 10 | E2 16 | - E2 | C3 10 | 16 PF0 | I/O FTf - |     | -   |
| ------ | ----- | ---- | ----- | ------ | --------- | --- | --- |
EVENTOUT
I2C2_SCL, FMC_A1,
| - - 11 | H3 17 | - H3 | C4 11 | 17 PF1 | I/O FTf - |     | -   |
| ------ | ----- | ---- | ----- | ------ | --------- | --- | --- |
EVENTOUT
DocID029808 Rev 3 I2C2_SMBA, FMC_A2,
| - - 12 | H2 18 | - H2 | D4 12 | 18 PF2 | I/O FT - |     | -   |
| ------ | ----- | ---- | ----- | ------ | -------- | --- | --- |
EVENTOUT
- - 13 J2 19 - J2 E2 13 19 PF3 I/O FT - FMC_A3, EVENTOUT ADC3_IN9
- - 14 J3 20 - J3 E3 14 20 PF4 I/O FT - FMC_A4, EVENTOUT ADC3_IN14
- - 15 K3 21 - K3 E4 15 21 PF5 I/O FT - FMC_A5, EVENTOUT ADC3_IN15
| - 10 16 | G2 22 | F9 G2  | D2 16 | 22 VSS | S - - | -   | -   |
| ------- | ----- | ------ | ----- | ------ | ----- | --- | --- |
| - 11 17 | G3 23 | F10 G3 | D3 17 | 23 VDD | S - - | -   | -   |
TIM10_CH1, SPI5_NSS,
SAI1_SD_B, UART7_RX,
- - 18 K2 24 - K2 F3 18 24 PF6 I/O FT - ADC3_IN4 Pinouts and pin description
QUADSPI_BK1_IO3,
EVENTOUT
TIM11_CH1, SPI5_SCK,
SAI1_MCLK_B, UART7_TX,
| - - 19 | K1 25 | - K1 | F2 19 | 25 PF7 | I/O FT - |     | ADC3_IN5 |
| ------ | ----- | ---- | ----- | ------ | -------- | --- | -------- |
QUADSPI_BK1_IO2,
EVENTOUT
61/229

62/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  |     | Alternate functions |           |
| --- | -------- | ----------------- | -------- | ---------------- | --- | ------------------- | --------- |
|     |          |                   |          | reset)(1)        |     |                     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |     |                     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
SPI5_MISO, SAI1_SCK_B,
UART7_RTS, TIM13_CH1,
| - - 20 | L3 26 | - L3 | G3 20 26 | PF8 | I/O FT - |     | ADC3_IN6 |
| ------ | ----- | ---- | -------- | --- | -------- | --- | -------- |
QUADSPI_BK1_IO0,
EVENTOUT
DocID029808 Rev 3
SPI5_MOSI, SAI1_FS_B,
UART7_CTS, TIM14_CH1,
| - - 21 | L2 27 | - L2 | G2 21 27 | PF9 | I/O FT - |     | ADC3_IN7 |
| ------ | ----- | ---- | -------- | --- | -------- | --- | -------- |
QUADSPI_BK1_IO1,
EVENTOUT
| - - 22 | L1 28 | - L1 | G1 22 28 | PF10 | I/O FT - |  EVENTOUT | ADC3_IN8 |
| ------ | ----- | ---- | -------- | ---- | -------- | --------- | -------- |
5 12 23 G1 29 G10 G1 D1 23 29 PH0-OSC_IN I/O FT - EVENTOUT OSC_IN(5)
OSC_OUT(5)
| 6 13 24 | H1 30 | H10 H1 | E1 24 30 PH1-OSC_OUT |     | I/O FT - | EVENTOUT |     |
| ------- | ----- | ------ | -------------------- | --- | -------- | -------- | --- |
RS
| 7 14 25 | J1 31 | G9 J1 | F1 25 31 | NRST | I/O - | -   | -   |
| ------- | ----- | ----- | -------- | ---- | ----- | --- | --- |
T
STM32F722xx STM32F723xx
|     |     |     |     |     |     | SAI2_FS_B,  | ADC1_IN10,  |
| --- | --- | --- | --- | --- | --- | ----------- | ----------- |
(4)
8 15 26 M2 32 F8 M2 H1 26 32 PC0 I/O FT OTG_HS_ULPI_STP,  ADC2_IN10,
(5)
|     |     |     |     |     | FMC_SDNWE, EVENTOUT |     | ADC3_IN10 |
| --- | --- | --- | --- | --- | ------------------- | --- | --------- |
ADC1_IN11,
|     |     |     |     |     |     | TRACED0,  | ADC2_IN11,  |
| --- | --- | --- | --- | --- | --- | --------- | ----------- |
9 16 27 M3 33 H9 M3 H2 27 33 PC1 I/O FT (5) SPI2_MOSI/I2S2_SD,  ADC3_IN11,
|     |     |     |     |     | SAI1_SD_A, EVENTOUT |     | RTC_TAMP3,  |
| --- | --- | --- | --- | --- | ------------------- | --- | ----------- |
WKUP3

Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) STM32F722xx STM32F723xx
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL | 671PFQL |     |     |     |
| ------- | ------- | --- | ------- | ------- | --- | --- | --- |
46PFQL
|     |     |     |     |     | SPI2_MISO,  | ADC1_IN12,  |     |
| --- | --- | --- | --- | --- | ----------- | ----------- | --- |
(4)
10 17 28 M4 34 J10 M4 H3 28 34 PC2 I/O FT OTG_HS_ULPI_DIR,  ADC2_IN12,
(5)
FMC_SDNE0, EVENTOUT ADC3_IN12
DocID029808 Rev 3
SPI2_MOSI/I2S2_SD,  ADC1_IN13,
(4)
11 18 29 M5 35 F7 M5 H4 29 35 PC3 I/O FT OTG_HS_ULPI_NXT,  ADC2_IN13,
(5)
FMC_SDCKE0, EVENTOUT ADC3_IN13
| - - 30   | - 36   | J7 -   | F10 30 | 36 VDD   | S - - | -   | -   |
| -------- | ------ | ------ | ------ | -------- | ----- | --- | --- |
| 12 19 31 | M1 37  | K10 M1 | J1 31  | 37 VSSA  | S - - | -   | -   |
| - -      | - N1 - | - N1   | K1 -   | - VREF-  | S - - | -   | -   |
| 13 20 32 | P1 38  | J9 P1  | L1 32  | 38 VREF+ | S - - | -   | -   |
| - 21 33  | R1 39  | K9 R1  | M1 33  | 39 VDDA  | S - - | -   | -   |
Pinouts and pin description
TIM2_CH1/TIM2_ETR,  ADC1_IN0,
(5) TIM5_CH1, TIM8_ETR,  ADC2_IN0,
| 14 22 34 | N3 40 | G8 N3 | J2 34 | 40 PA0-WKUP | I/O FT (6) |     |     |
| -------- | ----- | ----- | ----- | ----------- | ---------- | --- | --- |
USART2_CTS, UART4_TX,  ADC3_IN0,
SAI2_SD_B, EVENTOUT WKUP1
63/229

64/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL | 671PFQL |     |     |     |
| ------- | ------- | --- | ------- | ------- | --- | --- | --- |
46PFQL
TIM2_CH2, TIM5_CH2,
ADC1_IN1,
USART2_RTS, UART4_RX,
| 15 23 35 | N2 41 | J8 N2 | K2 35 | 41 PA1 | I/O FT (5) |     | ADC2_IN1,  |
| -------- | ----- | ----- | ----- | ------ | ---------- | --- | ---------- |
QUADSPI_BK1_IO3,
ADC3_IN1
SAI2_MCK_B, EVENTOUT
DocID029808 Rev 3
ADC1_IN2,
TIM2_CH3, TIM5_CH3,
ADC2_IN2,
16 24 36 P2 42 H8 P2 L2 36 42 PA2 I/O FT (5) TIM9_CH1, USART2_TX,
ADC3_IN2,
SAI2_SCK_B, EVENTOUT
WKUP2
LPTIM1_IN2,
QUADSPI_BK2_IO0,
| - - - | F4 43 | - F4 | - - | 43 PH2 | I/O FT |     | -   |
| ----- | ----- | ---- | --- | ------ | ------ | --- | --- |
SAI2_SCK_B, FMC_SDCKE0,
EVENTOUT
QUADSPI_BK2_IO1,
- - - G4 44 - G4 - - 44 PH3 I/O FT - SAI2_MCK_B, FMC_SDNE0,  -
EVENTOUT
STM32F722xx STM32F723xx
I2C2_SCL, OTG_HS_ULPI_NXT,
| - - - | H4 45 | - H4 | - - | 45 PH4 | I/O FTf (4) |     | -   |
| ----- | ----- | ---- | --- | ------ | ----------- | --- | --- |
EVENTOUT
I2C2_SDA, SPI5_NSS,
| - - - | J4 46 | - J4 | - - | 46 PH5 | I/O FTf - |     | -   |
| ----- | ----- | ---- | --- | ------ | --------- | --- | --- |
FMC_SDNWE, EVENTOUT
TIM2_CH4, TIM5_CH4,  ADC1_IN3,
(4)
17 25 37 R2 47 H7 R2 M2 37 47 PA3 I/O FT TIM9_CH2, USART2_RX,  ADC2_IN3,
(5)
OTG_HS_ULPI_D0, EVENTOUT ADC3_IN3
| 18 26 38 | - -   | K8 - | G4 38 | - VSS         | S - -  | -   | -   |
| -------- | ----- | ---- | ----- | ------------- | ------ | --- | --- |
| - - -    | L4 48 | - L4 | H5 -  | 48 BYPASS_REG | I FT - | -   | -   |

Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) STM32F722xx STM32F723xx
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |          |                   |          | Pin name         | epyt niP |                     |     |             |
| --- | -------- | ----------------- | -------- | ---------------- | -------- | ------------------- | --- | ----------- |
|     |          |                   |          |                  | setoN    |                     |     | Additional  |
|     |          |                   |          | (function after  |          | Alternate functions |     |             |
|     |          |                   |          | reset)(1)        |          |                     |     | functions   |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |          |                     |     |             |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL | 671PFQL |     |     |     |     |
| ------- | ------- | --- | ------- | ------- | --- | --- | --- | --- |
46PFQL
| 19 27 39 | K4 49 | - K4 | F4 39 | 49 VDD | S - - |     | -   | -   |
| -------- | ----- | ---- | ----- | ------ | ----- | --- | --- | --- |
SPI1_NSS/I2S1_WS,
ADC1_IN4,
SPI3_NSS/I2S3_WS,
(5)
| 20 28 40 | N4 50 | G7 N4 | J3 40 | 50 PA4 | I/O TTa |     |     | ADC2_IN4,  |
| -------- | ----- | ----- | ----- | ------ | ------- | --- | --- | ---------- |
USART2_CK, OTG_HS_SOF,
DAC_OUT1
EVENTOUT
DocID029808 Rev 3
TIM2_CH1/TIM2_ETR,
ADC1_IN5,
(4) TIM8_CH1N,
| 21 29 41 | P4 51 | F6 P4 | K3 41 | 51 PA5 | I/O TTa (5) |     |     | ADC2_IN5,  |
| -------- | ----- | ----- | ----- | ------ | ----------- | --- | --- | ---------- |
SPI1_SCK/I2S1_CK,
DAC_OUT2
OTG_HS_ULPI_CK, EVENTOUT
TIM1_BKIN, TIM3_CH1,
ADC1_IN6,
22 30 42 P3 52 G6 P3 L3 42 52 PA6 I/O FT (5) TIM8_BKIN, SPI1_MISO,
ADC2_IN6
TIM13_CH1, EVENTOUT
TIM1_CH1N, TIM3_CH2,
TIM8_CH1N,
ADC1_IN7,
23 31 43 R3 53 K7 R3 M3 43 53 PA7 I/O FT (5) SPI1_MOSI/I2S1_SD,
ADC2_IN7
TIM14_CH1, FMC_SDNWE,
Pinouts and pin description
EVENTOUT
|          |       |       |       |        |            | I2S1_MCK, FMC_SDNE0,  |     | ADC1_IN14,  |
| -------- | ----- | ----- | ----- | ------ | ---------- | --------------------- | --- | ----------- |
| 24 32 44 | N5 54 | H6 N5 | J4 44 | 54 PC4 | I/O FT (5) |                       |     |             |
|          |       |       |       |        |            | EVENTOUT              |     | ADC2_IN14   |
ADC1_IN15,
(5)
| - 33 45 | P5 55 | J6 P5 | K4 45 | 55 PC5 | I/O FT | FMC_SDCKE0, EVENTOUT |     |     |
| ------- | ----- | ----- | ----- | ------ | ------ | -------------------- | --- | --- |
ADC2_IN15
65/229

66/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |          |                   |          | Pin name         | epyt niP |                     |           |
| --- | -------- | ----------------- | -------- | ---------------- | -------- | ------------------- | --------- |
|     |          |                   |          |                  | setoN    | Additional          |           |
|     |          |                   |          | (function after  |          | Alternate functions |           |
|     |          |                   |          | reset)(1)        |          |                     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |          |                     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL | 671PFQL |     |     |     |
| ------- | ------- | --- | ------- | ------- | --- | --- | --- |
46PFQL
(4) TIM1_CH2N, TIM3_CH3,
ADC1_IN8,
25 34 46 R5 56 F5 R5 L4 46 56 PB0 I/O FT TIM8_CH2N, UART4_CTS,
|     |     |     |     |     | (5) |     | ADC2_IN8 |
| --- | --- | --- | --- | --- | --- | --- | -------- |
OTG_HS_ULPI_D1, EVENTOUT
(4) TIM1_CH3N, TIM3_CH4,
DocID029808 Rev 3 ADC1_IN9,
| 26 35 47 | R4 57 | G5 R4 | M4 47 | 57 PB1 | I/O FT (5) | TIM8_CH3N,  |     |
| -------- | ----- | ----- | ----- | ------ | ---------- | ----------- | --- |
ADC2_IN9
OTG_HS_ULPI_D2, EVENTOUT
SAI1_SD_A,
27 36 48 M6 58 K6 M6 J5 48 58 PB2 I/O FT - SPI3_MOSI/I2S3_SD,  -
QUADSPI_CLK, EVENTOUT
SPI5_MOSI, SAI2_SD_B,
| - - 49 | R6 59 | - R6 | M5 49 | 59 PF11 | I/O FT - |     | -   |
| ------ | ----- | ---- | ----- | ------- | -------- | --- | --- |
FMC_SDNRAS, EVENTOUT
| - - 50 | P6 60 | - P6 | L5 50 | 60 PF12 | I/O FT - | FMC_A6, EVENTOUT | -   |
| ------ | ----- | ---- | ----- | ------- | -------- | ---------------- | --- |
| - - 51 | M8 61 | - M8 | - 51  | 61 VSS  | S - -    | -                | -   |
- - 52 N8 62 - N8 G5 52 62 VDD S - - - - STM32F722xx STM32F723xx
| - - 53 | N6 63 | - N6 | K5 53 | 63 PF13 | I/O FT - | FMC_A7, EVENTOUT  | -   |
| ------ | ----- | ---- | ----- | ------- | -------- | ----------------- | --- |
| - - 54 | R7 64 | - R7 | M6 54 | 64 PF14 | I/O FT - | FMC_A8, EVENTOUT  | -   |
| - - 55 | P7 65 | - P7 | L6 55 | 65 PF15 | I/O FT - | FMC_A9, EVENTOUT  | -   |
| - - 56 | N7 66 | - N7 | K6 56 | 66 PG0  | I/O FT - | FMC_A10, EVENTOUT | -   |
| - - 57 | M7 67 | - M7 | J6 57 | 67 PG1  | I/O FT - | FMC_A11, EVENTOUT | -   |

Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) STM32F722xx STM32F723xx
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   | (function after  |           | Alternate functions |     |           |
| --- | -------- | ----------------- | ---------------- | --------- | ------------------- | --- | --------- |
|     |          |                   |                  | reset)(1) |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU         |           |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
TIM1_ETR, UART7_Rx,
- 37 58 R8 68 J5 R8 M7 58 68 PE7 I/O FT - QUADSPI_BK2_IO0, FMC_D4,  -
EVENTOUT
TIM1_CH1N, UART7_Tx,
- 38 59 P8 69 H5 P8 L7 59 69 PE8 I/O FT - QUADSPI_BK2_IO1, FMC_D5,  -
DocID029808 Rev 3
EVENTOUT
TIM1_CH1, UART7_RTS,
- 39 60 P9 70 K5 P9 K7 60 70 PE9 I/O FT - QUADSPI_BK2_IO2, FMC_D6,  -
EVENTOUT
| - - 61 | M9 71 | - M9 | H6 61 71 | VSS | S - - | -   | -   |
| ------ | ----- | ---- | -------- | --- | ----- | --- | --- |
| - - 62 | N9 72 | - N9 | G6 62 72 | VDD | S - - | -   | -   |
TIM1_CH2N, UART7_CTS,
- 40 63 R9 73 E4 R9 J7 63 73 PE10 I/O FT - QUADSPI_BK2_IO3, FMC_D7,  -
EVENTOUT
TIM1_CH2, SPI4_NSS,
Pinouts and pin description
- 41 64 P10 74 G4 P10 H8 64 74 PE11 I/O FT - SAI2_SD_B, FMC_D8,  -
EVENTOUT
TIM1_CH3N, SPI4_SCK,
- 42 65 R10 75 H4 R10 J8 65 75 PE12 I/O FT - SAI2_SCK_B, FMC_D9,  -
EVENTOUT
TIM1_CH3, SPI4_MISO,
- 43 66 N11 76 J4 N11 K8 66 76 PE13 I/O FT - SAI2_FS_B, FMC_D10,  -
EVENTOUT
67/229

68/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
|     | 441PFQL 671PFQL |     | 441PFQL | 671PFQL |     |     |     |
| --- | --------------- | --- | ------- | ------- | --- | --- | --- |
46PFQL
TIM1_CH4, SPI4_MOSI,
- 44 67 P11 77 K4 P11 L8 67 77 PE14 I/O FT - SAI2_MCK_B, FMC_D11,,  -
EVENTOUT
TIM1_BKIN, FMC_D12,
| - 45 | 68 R11 78 | F4 R11 | M8 68 | 78 PE15 | I/O FT - |     | -   |
| ---- | --------- | ------ | ----- | ------- | -------- | --- | --- |
EVENTOUT
DocID029808 Rev 3
TIM2_CH3, I2C2_SCL,
SPI2_SCK/I2S2_CK,
(4)
| 28 46 | 69 R12 79 | G3 R12 | M9 69 | 79 PB10 | I/O FTf |     | -   |
| ----- | --------- | ------ | ----- | ------- | ------- | --- | --- |
USART3_TX,
OTG_HS_ULPI_D3, EVENTOUT
TIM2_CH4, I2C2_SDA,
29 47 70 R13 80 H3 R13 M10 70 80 PB11 I/O FTf (4) USART3_RX,  -
OTG_HS_ULPI_D4, EVENTOUT
| 30 48 | 71 M10 81 | J3 M10 | H7 71 | 81 VCAP_1 | S - - | -   | -   |
| ----- | --------- | ------ | ----- | --------- | ----- | --- | --- |
| 31 49 | - - -     | K3 -   | - -   | - VSS     | S - - | -   | -   |
STM32F722xx STM32F723xx
| 32 50 | 72 N10 82 | K2 N10 | G7 72 | 82 VDD | S - - | -   | -   |
| ----- | --------- | ------ | ----- | ------ | ----- | --- | --- |
I2C2_SMBA, SPI5_SCK,
- - - M11 83 - M11 - - 83 PH6 I/O FT - TIM12_CH1, FMC_SDNE1,  -
EVENTOUT
I2C3_SCL, SPI5_MISO,
| - - | - N12 84 | - N12 | - - | 84 PH7 | I/O FTf - |     | -   |
| --- | -------- | ----- | --- | ------ | --------- | --- | --- |
FMC_SDCKE1, EVENTOUT
I2C3_SDA, FMC_D16,
| - - | - M12 85 | - M12 | - - | 85 PH8 | I/O FTf - |     | -   |
| --- | -------- | ----- | --- | ------ | --------- | --- | --- |
EVENTOUT

Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) STM32F722xx STM32F723xx
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
I2C3_SMBA, TIM12_CH2,
| - - | - M13 86 | - M13 | - - 86 | PH9 | I/O FT - |     | -   |
| --- | -------- | ----- | ------ | --- | -------- | --- | --- |
FMC_D17, EVENTOUT
TIM5_CH1, FMC_D18,
| - - | - L13 87 | - L13 | - - 87 | PH10 | I/O FT - |     | -   |
| --- | -------- | ----- | ------ | ---- | -------- | --- | --- |
EVENTOUT
DocID029808 Rev 3 TIM5_CH2, FMC_D19,
| - - | - L12 88 | - L12 | - - 88 | PH11 | I/O FT - |     | -   |
| --- | -------- | ----- | ------ | ---- | -------- | --- | --- |
EVENTOUT
TIM5_CH3, FMC_D20,
| - - | - K12 89 | - K12 | - - 89 | PH12 | I/O FT - |     | -   |
| --- | -------- | ----- | ------ | ---- | -------- | --- | --- |
EVENTOUT
| - - | - H12 90 | - H12  | - - 90 | VSS | S - - | -   | -   |
| --- | -------- | ------ | ------ | --- | ----- | --- | --- |
| - - | - J12 91 | K2 J12 | - - 91 | VDD | S - - | -   | -   |
TIM1_BKIN, I2C2_SMBA,
SPI2_NSS/I2S2_WS,
33 51 73 P12 92 J2 P12 M11 73 92 PB12 I/O FT (4) USART3_CK,  -
OTG_HS_ULPI_D5,
OTG_HS_ID, EVENTOUT
Pinouts and pin description
TIM1_CH1N,
(4) SPI2_SCK/I2S2_CK,
| 34 52 74 | P13 93 | H2 P13 | M12 74 93 | PB13 | I/O FT |     | OTG_HS_VBUS |
| -------- | ------ | ------ | --------- | ---- | ------ | --- | ----------- |
USART3_CTS,
OTG_HS_ULPI_D6, EVENTOUT
- - - - - G2 J15 H11 75 94 OTG_HS_REXT - - - USB HS OTG PHY calibration resistor
| - - | - - - | G1 J14 | H10 76 95 | VDD12OTGHS | - - - | -   | -   |
| --- | ----- | ------ | --------- | ---------- | ----- | --- | --- |
69/229

70/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  |     | Alternate functions |           |
| --- | -------- | ----------------- | -------- | ---------------- | --- | ------------------- | --------- |
|     |          |                   |          | reset)(1)        |     |                     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |     |                     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
TIM1_CH2N, TIM8_CH2N,
SPI2_MISO, USART3_RTS,
| 35 53 75 | R14 94 | - - | - - - | PB14 | I/O FT - |     | -   |
| -------- | ------ | --- | ----- | ---- | -------- | --- | --- |
TIM12_CH1, SDMMC2_D0,
OTG_HS_DM, EVENTOUT
DocID029808 Rev 3
| - - | - - - | J1 R14 | L11 77 96 | PB14 | I/O FT - | OTG_HS_DM | -   |
| --- | ----- | ------ | --------- | ---- | -------- | --------- | --- |
RTC_REFIN, TIM1_CH3N,
TIM8_CH3N,
36 54 76 R15 95 - - - - - PB15 I/O FT - SPI2_MOSI/I2S2_SD,  -
TIM12_CH2, SDMMC2_D1,
OTG_HS_DP, EVENTOUT
| - - | - - - | H1 R15 | L12 78 97 | PB15 | I/O FT - | OTG_HS_DP | -   |
| --- | ----- | ------ | --------- | ---- | -------- | --------- | --- |
STM32F722xx STM32F723xx
USART3_TX, FMC_D13,
| - 55 77 | P15 96 | - P15 | L9 79 98 | PD8 | I/O FT - |     | -   |
| ------- | ------ | ----- | -------- | --- | -------- | --- | --- |
EVENTOUT
USART3_RX, FMC_D14,
| - 56 78 | P14 97 | - P14 | K9 80 99 | PD9 | I/O FT - |     | -   |
| ------- | ------ | ----- | -------- | --- | -------- | --- | --- |
EVENTOUT
USART3_CK, FMC_D15,
| - 57 79 | N15 98 | - N15 | J9 81 100 | PD10 | I/O FT - |     | -   |
| ------- | ------ | ----- | --------- | ---- | -------- | --- | --- |
EVENTOUT

Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) STM32F722xx STM32F723xx
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  |     | Alternate functions |           |
| --- | -------- | ----------------- | -------- | ---------------- | --- | ------------------- | --------- |
|     |          |                   |          | reset)(1)        |     |                     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |     |                     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
USART3_CTS,
QUADSPI_BK1_IO0,
| - 58 80 | N14 99 | F3 N14 | H9 82 101 | PD11 | I/O FT - | SAI2_SD_A,  | -   |
| ------- | ------ | ------ | --------- | ---- | -------- | ----------- | --- |
FMC_A16/FMC_CLE,
EVENTOUT
DocID029808 Rev 3
TIM4_CH1, LPTIM1_IN1,
USART3_RTS,
QUADSPI_BK1_IO1,
| - 59 81 | N13 100 | F2 N13 | L10 83 102 | PD12 | I/O FT - |     | -   |
| ------- | ------- | ------ | ---------- | ---- | -------- | --- | --- |
SAI2_FS_A,
FMC_A17/FMC_ALE,
EVENTOUT
TIM4_CH2, LPTIM1_OUT,
QUADSPI_BK1_IO3,
| - 60 82 | M15 101 | E3 M15 | K10 84 103 | PD13 | I/O FT - |     | -   |
| ------- | ------- | ------ | ---------- | ---- | -------- | --- | --- |
SAI2_SCK_A, FMC_A18,
EVENTOUT
| - - 83 | - 102 | - - | G8 85 104 | VSS | S - - | -   | -   |
| ------ | ----- | --- | --------- | --- | ----- | --- | --- |
Pinouts and pin description
| - - 84 | J13 103 | - J13 | F8 86 105 | VDD | S - - | -   | -   |
| ------ | ------- | ----- | --------- | --- | ----- | --- | --- |
TIM4_CH3, UART8_CTS,
| - 61 85 | M14 104 | F1 M14 | K11 87 106 | PD14 | I/O FT - |     | -   |
| ------- | ------- | ------ | ---------- | ---- | -------- | --- | --- |
FMC_D0, EVENTOUT
TIM4_CH4, UART8_RTS,
| - 62 86 | L14 105 | E2 L14 | K12 88 107 | PD15 | I/O FT - |     | -   |
| ------- | ------- | ------ | ---------- | ---- | -------- | --- | --- |
FMC_D1, EVENTOUT
- - 87 L15 106 - L15 J12 89 108 PG2 I/O FT - FMC_A12, EVENTOUT -
- - 88 K15 107 - K15 J11 90 109 PG3 I/O FT - FMC_A13, EVENTOUT -
71/229

72/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
FMC_A14/FMC_BA0,
| - - 89 | K14 108 | - K14 | J10 91 110 | PG4 | I/O FT - |     | -   |
| ------ | ------- | ----- | ---------- | --- | -------- | --- | --- |
EVENTOUT
FMC_A15/FMC_BA1,
| - - 90 | K13 109 | - K13 | H12 92 111 | PG5 | I/O FT - |     | -   |
| ------ | ------- | ----- | ---------- | --- | -------- | --- | --- |
EVENTOUT
DocID029808 Rev 3 - - 91 J15 110 - - - - - PG6 I/O FT - EVENTOUT -
USART6_CK, FMC_INT,
| - - 92 | J14 111 | - - | - - - | PG7 | I/O FT - |     | -   |
| ------ | ------- | --- | ----- | --- | -------- | --- | --- |
EVENTOUT
USART6_RTS, FMC_SDCLK,
| - - 93 | H14 112 | - H14 | G11 93 112 | PG8 | I/O FT - |     | -   |
| ------ | ------- | ----- | ---------- | --- | -------- | --- | --- |
EVENTOUT
| - - 94 | G12 113 | - G12  | - 94 113   | VSS    | S - - | -   | -   |
| ------ | ------- | ------ | ---------- | ------ | ----- | --- | --- |
|        |         | - -    | F10 - -    | VDD    |       |     |     |
| - - 95 | H13 114 | K1 H13 | C11 95 114 | VDDUSB | S - - | -   | -   |
TIM3_CH1, TIM8_CH1,
STM32F722xx STM32F723xx
I2S2_MCK, USART6_TX,
| 37 63 96 | H15 115 | E1 H15 | G12 96 115 | PC6 | I/O FT - |     | -   |
| -------- | ------- | ------ | ---------- | --- | -------- | --- | --- |
SDMMC2_D6, SDMMC1_D6,
EVENTOUT
TIM3_CH2, TIM8_CH2,
I2S3_MCK, USART6_RX,
| 38 64 97 | G15 116 | D4 G15 | F12 97 116 | PC7 | I/O FT - |     | -   |
| -------- | ------- | ------ | ---------- | --- | -------- | --- | --- |
SDMMC2_D7, SDMMC1_D7,
EVENTOUT

DocID029808
Rev
3
73/229
STM32F722xx
STM32F723xx
Pinouts
and
pin
description
Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued)
Pin Number
Pin name
(function after
reset)(1)
TRACED1, TIM3_CH3,
TIM8_CH3, UART5_RTS,
39 65 98 G14 117 D2 G14 F11 98 117 PC8 I/O FT - -
USART6_CK, SDMMC1_D0,
EVENTOUT
MCO2, TIM3_CH4, TIM8_CH4,
I2C3_SDA, I2S_CKIN,
40 66 99 F14 118 D1 F14 E11 99 118 PC9 I/O FTf - UART5_CTS, -
QUADSPI_BK1_IO0,
SDMMC1_D1, EVENTOUT
MCO1, TIM1_CH1, TIM8_BKIN2,
41 67 100 F15 119 D3 F15 E12 100 119 PA8 I/O FTf - I2C3_SCL, USART1_CK, -
OTG_FS_SOF, EVENTOUT
TIM1_CH2, I2C3_SMBA,
42 68 101 E15 120 C3 E15 D12 101 120 PA9 I/O FT - SPI2_SCK/I2S2_CK, OTG_FS_VBUS
USART1_TX, EVENTOUT
TIM1_CH3, USART1_RX,
43 69 102 D15 121 C2 D15 D11 102 121 PA10 I/O FT - - OTG_FS_ID, EVENTOUT
TIM1_CH4, USART1_CTS,
44 70 103 C15 122 C1 C15 C12 103 122 PA11 I/O FT - CAN1_RX, OTG_FS_DM, -
EVENTOUT
TIM1_ETR, USART1_RTS,
45 71 104 B15 123 B2 B15 B12 104 123 PA12 I/O FT - SAI2_FS_B, CAN1_TX, -
OTG_FS_DP, EVENTOUT
PA13(JTMS-
46 72 105 A15 124 B1 A15 A12 105 124 I/O FT - JTMS-SWDIO, EVENTOUT -
SWDIO)
epyt
niP
erutcurts
O/I
setoN
STM32F722xx STM32F723xx
Additional
Alternate functions
functions
46PFQL
001PFQL 441PFQL
671AGBFU
671PFQL
001PSCLW 671AGBFU 441AGBFU
441PFQL 671PFQL

74/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
| - 73 106  | F13 125 | B3 F13 | G9 106 125  | VCAP_2 | S - - | -   | -   |
| --------- | ------- | ------ | ----------- | ------ | ----- | --- | --- |
| 47 74 107 | F12 126 | A2 F12 | G10 107 126 | VSS    | S - - | -   | -   |
| 48 75 108 | G13 127 | A1 G13 | F9 108 127  | VDD    | S - - | -   | -   |
TIM8_CH1N, UART4_TX,
DocID029808 Rev 3
- - - E12 128 - E12 - - 128 PH13 I/O FT - CAN1_TX, FMC_D21,  -
EVENTOUT
TIM8_CH2N, UART4_RX,
- - - E13 129 - E13 - - 129 PH14 I/O FT - CAN1_RX, FMC_D22,  -
EVENTOUT
TIM8_CH3N, FMC_D23,
| - - | - D13 130 | - D13 | - - 130 | PH15 | I/O FT - |     | -   |
| --- | --------- | ----- | ------- | ---- | -------- | --- | --- |
EVENTOUT
TIM5_CH4, SPI2_NSS/I2S2_WS,
| - - | - E14 131 | - E14 | - - 131 | PI0 | I/O FT - |     | -   |
| --- | --------- | ----- | ------- | --- | -------- | --- | --- |
FMC_D24, EVENTOUT
TIM8_BKIN2,  STM32F722xx STM32F723xx
- - - D14 132 - D14 - - 132 PI1 I/O FT - SPI2_SCK/I2S2_CK, FMC_D25,  -
EVENTOUT
TIM8_CH4, SPI2_MISO,
| - - | - C14 133 | - C14 | - - 133 | PI2 | I/O FT - |     | -   |
| --- | --------- | ----- | ------- | --- | -------- | --- | --- |
FMC_D26, EVENTOUT
TIM8_ETR,
- - - C13 134 - C13 - - 134 PI3 I/O FT - SPI2_MOSI/I2S2_SD, FMC_D27,  -
EVENTOUT
| - - | - D9 135 | - D9 | - - 135 | VSS | S - - | -   | -   |
| --- | -------- | ---- | ------- | --- | ----- | --- | --- |

Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) STM32F722xx STM32F723xx
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
| - - | - C9 136 | - C9 | - - 136 | VDD | S - - | -   | -   |
| --- | -------- | ---- | ------- | --- | ----- | --- | --- |
PA14(JTCK-
49 76 109 A14 137 C4 A14 A11 109 137 I/O FT - JTCK-SWCLK, EVENTOUT -
SWCLK)
JTDI, TIM2_CH1/TIM2_ETR,
DocID029808 Rev 3 SPI1_NSS/I2S1_WS,
| 50 77 110 | A13 138 | B4 A13 | A10 110 138 | PA15(JTDI) | I/O FT - |     | -   |
| --------- | ------- | ------ | ----------- | ---------- | -------- | --- | --- |
SPI3_NSS/I2S3_WS,
UART4_RTS, EVENTOUT
SPI3_SCK/I2S3_CK,
USART3_TX, UART4_TX,
| 51 78 111 | B14 139 | A3 B14 | B11 111 139 | PC10 | I/O FT - |     | -   |
| --------- | ------- | ------ | ----------- | ---- | -------- | --- | --- |
QUADSPI_BK1_IO1,
SDMMC1_D2, EVENTOUT
SPI3_MISO, USART3_RX,
UART4_RX,
| 52 79 112 | B13 140 | C5 B13 | B10 112 140 | PC11 | I/O FT - |     | -   |
| --------- | ------- | ------ | ----------- | ---- | -------- | --- | --- |
QUADSPI_BK2_NCS,
SDMMC1_D3, EVENTOUT
TRACED3,  Pinouts and pin description
SPI3_MOSI/I2S3_SD,
| 53 80 113 | A12 141 | D5 A12 | C10 113 141 | PC12 | I/O FT - |     | -   |
| --------- | ------- | ------ | ----------- | ---- | -------- | --- | --- |
USART3_CK, UART5_TX,
SDMMC1_CK, EVENTOUT
CAN1_RX, FMC_D2,
| - 81 114 | B12 142 | B5 B12 | E10 114 142 | PD0 | I/O FT - |     | -   |
| -------- | ------- | ------ | ----------- | --- | -------- | --- | --- |
EVENTOUT
CAN1_TX, FMC_D3,
| - 82 115 | C12 143 | A4 C12 | D10 115 143 | PD1 | I/O FT - |     | -   |
| -------- | ------- | ------ | ----------- | --- | -------- | --- | --- |
EVENTOUT
75/229

76/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
TRACED2, TIM3_ETR,
54 83 116 D12 144 E5 D12 E9 116 144 PD2 I/O FT - UART5_RX, SDMMC1_CMD,  -
EVENTOUT
SPI2_SCK/I2S2_CK,
- 84 117 D11 145 C6 D11 D9 117 145 PD3 I/O FT - USART2_CTS, FMC_CLK,  -
DocID029808 Rev 3
EVENTOUT
USART2_RTS, FMC_NOE,
| - 85 118 | D10 146 | B6 D10 | C9 118 146 | PD4 | I/O FT - |     | -   |
| -------- | ------- | ------ | ---------- | --- | -------- | --- | --- |
EVENTOUT
USART2_TX, FMC_NWE,
| - 86 119 | C11 147 | A5 C11 | B9 119 147 | PD5 | I/O FT - |     | -   |
| -------- | ------- | ------ | ---------- | --- | -------- | --- | --- |
EVENTOUT
| - - 120 | D8 148 | - D8 | E7 120 148 | VSS      | S - - | -   | -   |
| ------- | ------ | ---- | ---------- | -------- | ----- | --- | --- |
| - - 121 | C8 149 | - C8 | F7 121 149 | VDDSDMMC | S - - | -   | -   |
SPI3_MOSI/I2S3_SD,
SAI1_SD_A, USART2_RX,
| - 87 122 | B11 150 | D6 B11 | A8 122 150 | PD6 | I/O FT - |     | -   |
| -------- | ------- | ------ | ---------- | --- | -------- | --- | --- |
SDMMC2_CK, FMC_NWAIT,
STM32F722xx STM32F723xx
EVENTOUT
USART2_CK SDMMC2_CMD,
| - 88 123 | A11 151 | E6 A11 | A9 123 151 | PD7 | I/O FT - |     | -   |
| -------- | ------- | ------ | ---------- | --- | -------- | --- | --- |
FMC_NE1, EVENTOUT
USART6_RX,
QUADSPI_BK2_IO2,
- - 124 C10 152 - C10 E8 124 152 PG9 I/O FT - SAI2_FS_B, SDMMC2_D0,  -
FMC_NE2/FMC_NCE,
EVENTOUT

Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) STM32F722xx STM32F723xx
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
SAI2_SD_B, SDMMC2_D1,
| - - 125 | B10 153 | - B10 | D8 125 153 | PG10 | I/O FT - |     | -   |
| ------- | ------- | ----- | ---------- | ---- | -------- | --- | --- |
FMC_NE3, EVENTOUT
DocID029808 Rev 3 SDMMC2_D2, FMC_INT,
| - - 126 | B9 154 | - B9 | C8 126 154 | PG11 | I/O FT - |     | -   |
| ------- | ------ | ---- | ---------- | ---- | -------- | --- | --- |
EVENTOUT
LPTIM1_IN1, USART6_RTS,
- - 127 B8 155 - B8 B8 127 155 PG12 I/O FT - SDMMC2_D3, FMC_NE4,  -
EVENTOUT
TRACED0, LPTIM1_OUT,  Pinouts and pin description
- - 128 A8 156 - A8 D7 128 156 PG13 I/O FT - USART6_CTS, FMC_A24,  -
EVENTOUT
TRACED1, LPTIM1_ETR,
USART6_TX,
| - - 129 | A7 157 | - A7 | C7 129 157 | PG14 | I/O FT - |     | -   |
| ------- | ------ | ---- | ---------- | ---- | -------- | --- | --- |
QUADSPI_BK2_IO3, FMC_A25,
EVENTOUT
77/229
| - - 130 | D7 158 | - D7 | - 130 158 | VSS | S - - | -   | -   |
| ------- | ------ | ---- | --------- | --- | ----- | --- | --- |

78/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
|     | STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| --- | ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |     |          |                   |          | (function after  |     | Alternate functions |           |
| --- | --- | -------- | ----------------- | -------- | ---------------- | --- | ------------------- | --------- |
|     |     |          |                   |          | reset)(1)        |     |                     | functions |
|     |     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |     |                     |           |
 001PFQL
|     | 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| --- | ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
|     | - - 131 | C7 159 | - C7 | F6 131 159 | VDD | S - - | -   | -   |
| --- | ------- | ------ | ---- | ---------- | --- | ----- | --- | --- |
USART6_CTS, FMC_SDNCAS,
|     | - - 132 | B7 160 | - B7 | B7 132 160 | PG15 | I/O FT - |     | -   |
| --- | ------- | ------ | ---- | ---------- | ---- | -------- | --- | --- |
EVENTOUT
JTDO/TRACESWO, TIM2_CH2,
| DocID029808 Rev 3 |           |         |        |            | PB3(JTDO/TRA |          | SPI1_SCK/I2S1_CK,  |     |
| ----------------- | --------- | ------- | ------ | ---------- | ------------ | -------- | ------------------ | --- |
|                   | 55 89 133 | A10 161 | A6 A10 | A7 133 161 |              | I/O FT - |                    | -   |
|                   |           |         |        |            | CESWO)       |          | SPI3_SCK/I2S3_CK,  |     |
SDMMC2_D2, EVENTOUT
NJTRST, TIM3_CH1,
SPI1_MISO, SPI3_MISO,
|     | 56 90 134 | A9 162 | B7 A9 | A6 134 162 | PB4(NJTRST) | I/O FT - |     | -   |
| --- | --------- | ------ | ----- | ---------- | ----------- | -------- | --- | --- |
SPI2_NSS/I2S2_WS,
SDMMC2_D3, EVENTOUT
TIM3_CH2, I2C1_SMBA,
SPI1_MOSI/I2S1_SD,
57 91 135 A6 163 C7 A6 B6 135 163 PB5 I/O FT (4) SPI3_MOSI/I2S3_SD,  -
OTG_HS_ULPI_D7,
STM32F722xx STM32F723xx
FMC_SDCKE1, EVENTOUT
TIM4_CH1, I2C1_SCL,
USART1_TX,
|     | 58 92 136 | B6 164 | D7 B6 | C6 136 164 | PB6 | I/O FTf - |     | -   |
| --- | --------- | ------ | ----- | ---------- | --- | --------- | --- | --- |
QUAD SPI_BK1_NCS,
FMC_SDNE1, EVENTOUT

Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) STM32F722xx STM32F723xx
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
|     | 441PFQL 671PFQL |     | 441PFQL | 671PFQL |     |     |     |
| --- | --------------- | --- | ------- | ------- | --- | --- | --- |
46PFQL
TIM4_CH2, I2C1_SDA,
59 93 137 B5 165 B8 B5 D6 137 165 PB7 I/O FTf - USART1_RX, FMC_NL,  -
EVENTOUT
DocID029808 Rev 3 60 94 138 D6 166 A7 D6 D5 138 166 BOOT I B - - VPP
TIM4_CH3, TIM10_CH1,
I2C1_SCL, CAN1_RX,
| 61 95 | 139 A5 167 | C8 A5 | C5 139 | 167 PB8 | I/O FTf - |     | -   |
| ----- | ---------- | ----- | ------ | ------- | --------- | --- | --- |
SDMMC2_D4, SDMMC1_D4,
EVENTOUT
TIM4_CH4, TIM11_CH1,
I2C1_SDA, SPI2_NSS/I2S2_WS,
| 62 96 | 140 B4 168 | D8 B4 | B5 140 | 168 PB9 | I/O FTf - |     | -   |
| ----- | ---------- | ----- | ------ | ------- | --------- | --- | --- |
CAN1_TX, SDMMC2_D5,
SDMMC1_D5, EVENTOUT
Pinouts and pin description
TIM4_ETR, LPTIM1_ETR,
- 97 141 A4 169 E7 A4 A5 141 169 PE0 I/O FT - UART8_Rx, SAI2_MCK_A,  -
FMC_NBL0, EVENTOUT
LPTIM1_IN2, UART8_Tx,
| - 98 | 142 A3 170 | B9 A3 | A4 142 | 170 PE1 | I/O FT - |     | -   |
| ---- | ---------- | ----- | ------ | ------- | -------- | --- | --- |
FMC_NBL1, EVENTOUT
79/229
| 63 99 | - D5 - | A8 D5 | E6 - | - VSS | S - - | -   | -   |
| ----- | ------ | ----- | ---- | ----- | ----- | --- | --- |

80/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   |          | (function after  | Alternate functions |     |           |
| --- | -------- | ----------------- | -------- | ---------------- | ------------------- | --- | --------- |
|     |          |                   |          | reset)(1)        |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU |                  |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
| - - 143    | C6 171 | - C6  | E5 143 171 | PDR_ON | S - - | -   | -   |
| ---------- | ------ | ----- | ---------- | ------ | ----- | --- | --- |
| 64 100 144 | C5 172 | A9 C5 | F5 144 172 | VDD    | S - - | -   | -   |
TIM8_BKIN, SAI2_MCK_A,
| - - | - D4 173 | - D4 | - - 173 | PI4 | I/O FT - |     | -   |
| --- | -------- | ---- | ------- | --- | -------- | --- | --- |
DocID029808 Rev 3 FMC_NBL2, EVENTOUT
TIM8_CH1, SAI2_SCK_A,
| - - | - C4 174 | - C4 | - - 174 | PI5 | I/O FT - |     | -   |
| --- | -------- | ---- | ------- | --- | -------- | --- | --- |
FMC_NBL3, EVENTOUT
TIM8_CH2, SAI2_SD_A,
| - - | - C3 175 | - C3 | - - 175 | PI6 | I/O FT - |     | -   |
| --- | -------- | ---- | ------- | --- | -------- | --- | --- |
FMC_D28, EVENTOUT
STM32F722xx STM32F723xx
TIM8_CH3, SAI2_FS_A,
| - - | - C2 176 | - C2 | - - 176 | PI7 | I/O FT - |     | -   |
| --- | -------- | ---- | ------- | --- | -------- | --- | --- |
FMC_D29, EVENTOUT
| - - | - F6 -  | - F6  | - - - | VSS | S - - | -   | -   |
| --- | ------- | ----- | ----- | --- | ----- | --- | --- |
| - - | - F7 -  | - F7  | - - - | VSS | S - - | -   | -   |
| - - | - F8 -  | - F8  | - - - | VSS | S - - | -   | -   |
| - - | - F9 -  | - F9  | - - - | VSS | S - - | -   | -   |
| - - | - F10 - | - F10 | - - - | VSS | S - - | -   | -   |

Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) STM32F722xx STM32F723xx
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   | (function after  |           | Alternate functions |     |           |
| --- | -------- | ----------------- | ---------------- | --------- | ------------------- | --- | --------- |
|     |          |                   |                  | reset)(1) |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU         |           |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
| - - | - G6 - | - G6 | - - - | VSS | S - - | -   | -   |
| --- | ------ | ---- | ----- | --- | ----- | --- | --- |
| - - | - G7 - | - G7 | - - - | VSS | S - - | -   | -   |
| - - | - G8 - | - G8 | - - - | VSS | S - - | -   | -   |
| - - | - G9 - | - G9 | - - - | VSS | S - - | -   | -   |
DocID029808 Rev 3
| - - | - G10 - | - G10 | - - - | VSS | S - - | -   | -   |
| --- | ------- | ----- | ----- | --- | ----- | --- | --- |
| - - | - H6 -  | - H6  | - - - | VSS | S - - | -   | -   |
| - - | - H7 -  | - H7  | - - - | VSS | S - - | -   | -   |
| - - | - H8 -  | - H8  | - - - | VSS | S - - | -   | -   |
| - - | - H9 -  | - H9  | - - - | VSS | S - - | -   | -   |
| - - | - H10 - | - H10 | - - - | VSS | S - - | -   | -   |
| - - | - J6 -  | - J6  | - - - | VSS | S - - | -   | -   |
| - - | - J7 -  | - J7  | - - - | VSS | S - - | -   | -   |
Pinouts and pin description
| - - | - J8 -  | - J8  | - - - | VSS | S - - | -   | -   |
| --- | ------- | ----- | ----- | --- | ----- | --- | --- |
| - - | - J9 -  | - J9  | - - - | VSS | S - - | -   | -   |
| - - | - J10 - | - J10 | - - - | VSS | S - - | -   | -   |
| - - | - K6 -  | - K6  | - - - | VSS | S - - | -   | -   |
| - - | - K7 -  | - K7  | - - - | VSS | S - - | -   | -   |
| - - | - K8 -  | - K8  | - - - | VSS | S - - | -   | -   |
81/229

82/229 Table 10. STM32F722xx and STM32F723xx pin and ball definition (continued) Pinouts and pin description
Pin Number
| STM32F722xx |     | STM32F723xx |     |     |     |     |     |
| ----------- | --- | ----------- | --- | --- | --- | --- | --- |
erutcurts O/I
|     |     |     |     | Pin name  | epyt niP |     |     |
| --- | --- | --- | --- | --------- | -------- | --- | --- |
setoN Additional
|     |          |                   | (function after  |           | Alternate functions |     |           |
| --- | -------- | ----------------- | ---------------- | --------- | ------------------- | --- | --------- |
|     |          |                   |                  | reset)(1) |                     |     | functions |
|     | 671AGBFU | 001PSCLW 671AGBFU | 441AGBFU         |           |                     |     |           |
 001PFQL
| 441PFQL | 671PFQL |     | 441PFQL 671PFQL |     |     |     |     |
| ------- | ------- | --- | --------------- | --- | --- | --- | --- |
46PFQL
| - - | - K9 -  | - K9  | - - - | VSS | S - - | -   | -   |
| --- | ------- | ----- | ----- | --- | ----- | --- | --- |
| - - | - K10 - | - K10 | - - - | VSS | S - - | -   | -   |
1. Function availability depends on the chosen device.
2. PC13, PC14, PC15 and PI8 are supplied through the power switch. Since the switch only sinks a limited amount of current (3 mA), the use of GPIOs PC13 to
DocID029808 Rev 3 PC15 and PI8 in output mode is limited:
      - The speed should not exceed 2 MHz with a maximum load of 30 pF.
      - These I/Os must not be used as a current source (e.g. to drive an LED).
3. Main function after the first backup domain power-up. Later on, it depends on the contents of the RTC registers even after reset (because these registers are not
reset by the main reset).
4. ULPI signals not available on the STM32F723xx devices.
5. FT = 5 V tolerant except when in analog mode or oscillator mode (for PC14, PC15, PH0 and PH1).
6. If the device is in regulator OFF/internal reset ON mode (BYPASS_REG pin is set to VDD), then PA0 is used as an internal reset (active low).
STM32F722xx STM32F723xx

STM32F722xx STM32F723xx Pinouts and pin description
Table 11. FMC pin definition
| NOR/PSRAM/SR |                   | NOR/PSRAM  |        |        |
| ------------ | ----------------- | ---------- | ------ | ------ |
| Pin name     |                   |            | NAND16 | SDRAM  |
|              | AM                | Mux        |        |        |
| PF0          | A0                | -          | -      | A0     |
| PF1          | A1                | -          | -      | A1     |
| PF2          | A2                | -          | -      | A2     |
| PF3          | A3                | -          | -      | A3     |
| PF4          | A4                | -          | -      | A4     |
| PF5          | A5                | -          | -      | A5     |
| PF12         | A6                | -          | -      | A6     |
| PF13         | A7                | -          | -      | A7     |
| PF14         | A8                | -          | -      | A8     |
| PF15         | A9                | -          | -      | A9     |
| PG0          | A10               | -          | -      | A10    |
| PG1          | A11               | -          | -      | A11    |
| PG2          | A12               | -          | -      | A12    |
| PG3          | A13               | -          | -      | -      |
| PG4          | A14               | -          | -      | BA0    |
| PG5          | A15               | -          | -      | BA1    |
| PD11         | A16               | A16        | CLE    | -      |
| PD12         | A17               | A17        | ALE    | -      |
| PD13         | A18               | A18        | -      | -      |
| PE3          | A19               | A19        | -      | -      |
| PE4          | A20               | A20        | -      | -      |
| PE5          | A21               | A21        | -      | -      |
| PE6          | A22               | A22        | -      | -      |
| PE2          | A23               | A23        | -      | -      |
| PG13         | A24               | A24        | -      | -      |
| PG14         | A25               | A25        | -      | -      |
| PD14         | D0                | DA0        | D0     | D0     |
| PD15         | D1                | DA1        | D1     | D1     |
| PD0          | D2                | DA2        | D2     | D2     |
| PD1          | D3                | DA3        | D3     | D3     |
| PE7          | D4                | DA4        | D4     | D4     |
| PE8          | D5                | DA5        | D5     | D5     |
| PE9          | D6                | DA6        | D6     | D6     |
|              | DocID029808 Rev 3 |            |        | 83/229 |
96

Pinouts and pin description STM32F722xx STM32F723xx
Table 11. FMC pin definition (continued)
| NOR/PSRAM/SR |       | NOR/PSRAM  |        |       |
| ------------ | ----- | ---------- | ------ | ----- |
| Pin name     |       |            | NAND16 | SDRAM |
|              | AM    | Mux        |        |       |
| PE10         | D7    | DA7        | D7     | D7    |
| PE11         | D8    | DA8        | D8     | D8    |
| PE12         | D9    | DA9        | D9     | D9    |
| PE13         | D10   | DA10       | D10    | D10   |
| PE14         | D11   | DA11       | D11    | D11   |
| PE15         | D12   | DA12       | D12    | D12   |
| PD8          | D13   | DA13       | D13    | D13   |
| PD9          | D14   | DA14       | D14    | D14   |
| PD10         | D15   | DA15       | D15    | D15   |
| PH8          | D16   | -          | -      | D16   |
| PH9          | D17   | -          | -      | D17   |
| PH10         | D18   | -          | -      | D18   |
| PH11         | D19   | -          | -      | D19   |
| PH12         | D20   | -          | -      | D20   |
| PH13         | D21   | -          | -      | D21   |
| PH14         | D22   | -          | -      | D22   |
| PH15         | D23   | -          | -      | D23   |
| PI0          | D24   | -          | -      | D24   |
| PI1          | D25   | -          | -      | D25   |
| PI2          | D26   | -          | -      | D26   |
| PI3          | D27   | -          | -      | D27   |
| PI6          | D28   | -          | -      | D28   |
| PI7          | D29   | -          | -      | D29   |
| PI9          | D30   | -          | -      | D30   |
| PI10         | D31   | -          | -      | D31   |
| PD7          | NE1   | NE1        | -      | -     |
| PG9          | NE2   | NE2        | NCE    | -     |
| PG10         | NE3   | NE3        | -      | -     |
| PG11         | -     | -          | -      | -     |
| PG12         | NE4   | NE4        | -      | -     |
| PD3          | CLK   | CLK        | -      | -     |
| PD4          | NOE   | NOE        | NOE    | -     |
| PD5          | NWE   | NWE        | NWE    | -     |
| PD6          | NWAIT | NWAIT      | NWAIT  | -     |
84/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Pinouts and pin description
Table 11. FMC pin definition (continued)
| NOR/PSRAM/SR |                   | NOR/PSRAM  |        |        |
| ------------ | ----------------- | ---------- | ------ | ------ |
| Pin name     |                   |            | NAND16 | SDRAM  |
|              | AM                | Mux        |        |        |
| PB7          | NADV              | NADV       | -      | -      |
| PF6          | -                 | -          | -      | -      |
| PF7          | -                 | -          | -      | -      |
| PF8          | -                 | -          | -      | -      |
| PF9          | -                 | -          | -      | -      |
| PF10         | -                 | -          | -      | -      |
| PG6          | -                 | -          | -      | -      |
| PG7          | -                 | -          | INT    | -      |
| PE0          | NBL0              | NBL0       | -      | NBL0   |
| PE1          | NBL1              | NBL1       | -      | NBL1   |
| PI4          | NBL2              | -          | -      | NBL2   |
| PI5          | NBL3              | -          | -      | NBL3   |
| PG8          | -                 | -          | -      | SDCLK  |
| PC0          | -                 | -          | -      | SDNWE  |
| PF11         | -                 | -          | -      | SDNRAS |
| PG15         | -                 | -          | -      | SDNCAS |
| PH2          | -                 | -          | -      | SDCKE0 |
| PH3          | -                 | -          | -      | SDNE0  |
| PH6          | -                 | -          | -      | SDNE1  |
| PH7          | -                 | -          | -      | SDCKE1 |
| PH5          | -                 | -          | -      | SDNWE  |
| PC2          | -                 | -          | -      | SDNE0  |
| PC3          | -                 | -          | -      | SDCKE0 |
| PB5          | -                 | -          | -      | SDCKE1 |
| PB6          | -                 | -          | -      | SDNE1  |
|              | DocID029808 Rev 3 |            |        | 85/229 |
96

86/229 Pinouts and pin description

Table 12.  STM32F722xx and STM32F723xx alternate function mapping
|     |      | AF0 | AF1 | AF2 | AF3         | AF4        | AF5        | AF6        | AF7         | AF8        | AF9        | AF10      | AF11 | AF12    | AF15 |
| --- | ---- | --- | --- | --- | ----------- | ---------- | ---------- | ---------- | ----------- | ---------- | ---------- | --------- | ---- | ------- | ---- |
|     |      |     |     |     |             |            | SPI1/I2S1/ | SPI2/I2S2/ | SPI2/I2S2/S |            | CAN1/TIM1  | SAI2/QUAD |      | UART7/F |      |
|     | Port |     |     |     |             |            |            | SPI3/I2S3/ |             | SAI2/USART | 2/13/14/QU | SPI/SDMM  |      |         |      |
|     |      |     |     |     | TIM8/9/10/1 | I2C1/2/3/U | SPI2/I2S2/ |            | PI3/I2S3/US |            |            |           |      | MC/SDM  |      |
SYS TIM1/2 TIM3/4/5 SPI3/I2S3/ 6/UART4/5/7/ ADSPI/ C2/OTG2_ SDMMC2 SYS
|     |     |     |     |     | 1/LPTIM1 | SART1 | SPI3/I2S3/ | SAI1/ | ART1/2/3/UA | 8/OTG1_FS | FMC/    | HS/OTG1_ |     | MC1/    |     |
| --- | --- | --- | --- | --- | -------- | ----- | ---------- | ----- | ----------- | --------- | ------- | -------- | --- | ------- | --- |
|     |     |     |     |     |          |       | SPI4/5     |       | RT5         |           |         |          |     | OTG2_FS |     |
|     |     |     |     |     |          |       |            | UART4 |             |           | OTG2_HS | FS       |     |         |     |
TIM2_CH1
|     |     |     |     |     |     |     |     |     | USART2_CT |     |     |     |     |     | EVEN |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | --- | --- | ---- |
PA0 - /TIM2_ET TIM5_CH1 TIM8_ETR - - - UART4_ TX - SAI2_SD_B - -
|     |     |     |     |     |     |     |     |     | S   |     |     |     |     |     | TOUT |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
R
|     |     |     |          |          |     |     |     |     | USART2_RT |          | QUADSPI_ | SAI2_MCK |     |     | EVEN |
| --- | --- | --- | -------- | -------- | --- | --- | --- | --- | --------- | -------- | -------- | -------- | --- | --- | ---- |
|     | PA1 | -   | TIM2_CH2 | TIM5_CH2 | -   | -   | -   | -   |           | UART4_RX |          |          | -   | -   |      |
|     |     |     |          |          |     |     |     |     | S         |          | BK1_IO3  | _B       |     |     | TOUT |
EVEN
PA2 - TIM2_CH3 TIM5_CH3 TIM9_CH1 - - - USART2_TX SAI2_SCK_B - - - -
TOUT
DocID029808 Rev 3 PA3 - TIM2_CH4 TIM5_CH4 TIM9_CH2 - - - USART2_RX - - OTG_HS_U - - EVEN
|     |     |     |     |     |     |     |          |          |           |     |     | LPI_D0 |     |         | TOUT |
| --- | --- | --- | --- | --- | --- | --- | -------- | -------- | --------- | --- | --- | ------ | --- | ------- | ---- |
|     |     |     |     |     |     |     | SPI1_NSS | SPI3_NSS |           |     |     |        |     | OTG_HS_ | EVEN |
|     | PA4 | -   | -   | -   | -   | -   |          |          | USART2_CK | -   | -   | -      | -   |         |      |
|     |     |     |     |     |     |     | /I2S1_WS | /I2S3_WS |           |     |     |        |     | SOF     | TOUT |
TIM2_CH1
|        |     |     |          |          | TIM8_CH1  |     | SPI1_SCK  |     |     |     |           | OTG_HS_U |     |         | EVEN |
| ------ | --- | --- | -------- | -------- | --------- | --- | --------- | --- | --- | --- | --------- | -------- | --- | ------- | ---- |
|        | PA5 | -   | /TIM2_ET | -        |           | -   |           | -   | -   | -   | -         |          | -   | -       |      |
| Port A |     |     | R        |          | N         |     | /I2S1_CK  |     |     |     |           | LPI_CK   |     |         | TOUT |
|        |     |     | TIM1_BKI |          |           |     | SPI1_MIS  |     |     |     |           |          |     |         | EVEN |
|        | PA6 | -   |          | TIM3_CH1 | TIM8_BKIN | -   |           | -   | -   | -   | TIM13_CH1 | -        | -   | -       |      |
|        |     |     | N        |          |           |     | O         |     |     |     |           |          |     |         | TOUT |
|        |     |     | TIM1_CH1 |          | TIM8_CH1  |     | SPI1_MO   |     |     |     |           |          |     | FMC_SDN | EVEN |
|        | PA7 | -   |          | TIM3_CH2 |           | -   | SI/I2S1_S | -   | -   | -   | TIM14_CH1 | -        | -   |         |      |
|        |     |     | N        |          | N         |     |           |     |     |     |           |          |     | WE      | TOUT |
D
|     |     |     |     |     | TIM8_BKIN |     |     |     |     |     |     | OTG_FS_S |     |     | EVEN |
| --- | --- | --- | --- | --- | --------- | --- | --- | --- | --- | --- | --- | -------- | --- | --- | ---- |
PA8 MCO1 TIM1_CH1 - I2C3_SCL - - USART1_CK - - - - STM32F722xx STM32F723xx
|     |      |     |          |     | 2   |          |          |     |           |     |         | OF       |     |     | TOUT |
| --- | ---- | --- | -------- | --- | --- | -------- | -------- | --- | --------- | --- | ------- | -------- | --- | --- | ---- |
|     |      |     |          |     |     | I2C3_SMB | SPI2_SCK |     |           |     |         |          |     |     | EVEN |
|     | PA9  | -   | TIM1_CH2 | -   | -   | A        | /I2S2_CK | -   | USART1_TX | -   | -       | -        | -   | -   | TOUT |
|     |      |     |          |     |     |          |          |     |           |     |         | OTG_FS_I |     |     | EVEN |
|     | PA10 | -   | TIM1_CH3 | -   | -   | -        | -        | -   | USART1_RX | -   | -       |          | -   | -   |      |
|     |      |     |          |     |     |          |          |     |           |     |         | D        |     |     | TOUT |
|     |      |     |          |     |     |          |          |     | USART1_CT |     |         | OTG_FS_D |     |     | EVEN |
|     | PA11 | -   | TIM1_CH4 | -   | -   | -        | -        | -   |           | -   | CAN1_RX |          | -   | -   |      |
|     |      |     |          |     |     |          |          |     | S         |     |         | M        |     |     | TOUT |

Table 12.  STM32F722xx and STM32F723xx alternate function mapping (continued) STM32F722xx STM32F723xx
|     |     |      | AF0 | AF1 | AF2 | AF3         | AF4        | AF5        | AF6        | AF7         | AF8        | AF9        | AF10      | AF11 | AF12    | AF15 |
| --- | --- | ---- | --- | --- | --- | ----------- | ---------- | ---------- | ---------- | ----------- | ---------- | ---------- | --------- | ---- | ------- | ---- |
|     |     |      |     |     |     |             |            | SPI1/I2S1/ | SPI2/I2S2/ | SPI2/I2S2/S |            | CAN1/TIM1  | SAI2/QUAD |      | UART7/F |      |
|     |     | Port |     |     |     |             |            |            | SPI3/I2S3/ |             | SAI2/USART | 2/13/14/QU | SPI/SDMM  |      |         |      |
|     |     |      |     |     |     | TIM8/9/10/1 | I2C1/2/3/U | SPI2/I2S2/ |            | PI3/I2S3/US |            |            |           |      | MC/SDM  |      |
SYS TIM1/2 TIM3/4/5 SPI3/I2S3/ 6/UART4/5/7/ ADSPI/ C2/OTG2_ SDMMC2 SYS
|     |     |      |       |          |     | 1/LPTIM1 | SART1 | SPI3/I2S3/ | SAI1/ | ART1/2/3/UA | 8/OTG1_FS | FMC/    | HS/OTG1_ |     | MC1/    |      |
| --- | --- | ---- | ----- | -------- | --- | -------- | ----- | ---------- | ----- | ----------- | --------- | ------- | -------- | --- | ------- | ---- |
|     |     |      |       |          |     |          |       | SPI4/5     |       | RT5         |           |         |          |     | OTG2_FS |      |
|     |     |      |       |          |     |          |       |            | UART4 |             |           | OTG2_HS | FS       |     |         |      |
|     |     |      |       |          |     |          |       |            |       | USART1_RT   |           |         | OTG_FS_D |     |         | EVEN |
|     |     | PA12 | -     | TIM1_ETR | -   | -        | -     | -          | -     |             | SAI2_FS_B | CAN1_TX |          | -   | -       |      |
|     |     |      |       |          |     |          |       |            |       | S           |           |         | P        |     |         | TOUT |
|     |     |      | JTMS- |          |     |          |       |            |       |             |           |         |          |     |         | EVEN |
|     |     | PA13 |       | -        | -   | -        | -     | -          | -     | -           | -         | -       | -        | -   | -       |      |
|     |     |      | SWDIO |          |     |          |       |            |       |             |           |         |          |     |         | TOUT |
Port A
|     |     |      | JTCK- |     |     |     |     |     |     |     |     |     |     |     |     | EVEN |
| --- | --- | ---- | ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
|     |     | PA14 |       | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |      |
|     |     |      | SWCLK |     |     |     |     |     |     |     |     |     |     |     |     | TOUT |
TIM2_CH1
PA15 JTDI /TIM2_ET - - - SPI1_NSS SPI3_NSS - UART4_RTS - - - - EVEN
|     |     |     |     |     |     |     |     | /I2S1_WS | /I2S3_WS |     |     |     |     |     |     | TOUT |
| --- | --- | --- | --- | --- | --- | --- | --- | -------- | -------- | --- | --- | --- | --- | --- | --- | ---- |
R
| DocID029808 Rev 3 |        |     |         | TIM1_CH2 |          | TIM8_CH2 |          |           |           |             |           |          | OTG_HS_U |     |         | EVEN |
| ----------------- | ------ | --- | ------- | -------- | -------- | -------- | -------- | --------- | --------- | ----------- | --------- | -------- | -------- | --- | ------- | ---- |
|                   |        | PB0 | -       |          | TIM3_CH3 |          | -        | -         | -         | -           | UART4_CTS |          |          | -   | -       |      |
|                   |        |     |         | N        |          | N        |          |           |           |             |           |          | LPI_D1   |     |         | TOUT |
|                   |        | PB1 | -       | TIM1_CH3 | TIM3_CH4 | TIM8_CH3 | -        | -         | -         | -           | -         |          | OTG_HS_U | -   | -       | EVEN |
|                   |        |     |         | N        |          | N        |          |           |           |             |           |          | LPI_D2   |     |         | TOUT |
|                   |        |     |         |          |          |          |          |           | SAI1_SD_  | SPI3_MOSI/I |           | QUADSPI_ |          |     |         | EVEN |
|                   |        | PB2 | -       | -        | -        | -        | -        | -         |           |             |           |          | -        | -   | -       |      |
|                   |        |     |         |          |          |          |          |           | A         | 2S3_SD      |           | CLK      |          |     |         | TOUT |
|                   |        |     | JTDO/TR |          |          |          |          | SPI1_SCK  | SPI3_SCK  |             |           |          | SDMMC2_  |     |         | EVEN |
|                   |        | PB3 |         | TIM2_CH2 | -        | -        | -        |           |           | -           | -         | -        |          | -   | -       |      |
|                   |        |     | ACESWO  |          |          |          |          | /I2S1_CK  | /I2S3_CK  |             |           |          | D2       |     |         | TOUT |
|                   |        |     |         |          |          |          |          | SPI1_MIS  | SPI3_MIS  | SPI2_NSS/I2 |           |          | SDMMC2_  |     |         | EVEN |
|                   | Port B | PB4 | NJTRST  | -        | TIM3_CH1 | -        | -        | O         | O         | S2_WS       | -         | -        | D3       | -   | -       | TOUT |
|                   |        |     |         |          |          |          |          | SPI1_MO   | SPI3_MO   |             |           |          |          |     |         |      |
|                   |        |     |         |          |          |          | I2C1_SMB |           |           |             |           |          | OTG_HS_U |     | FMC_SDC | EVEN |
|                   |        | PB5 | -       | -        | TIM3_CH2 | -        |          | SI/I2S1_S | SI/I2S3_S | -           | -         | -        |          | -   |         |      |
|                   |        |     |         |          |          |          | A        |           |           |             |           |          | LPI_D7   |     | KE1     | TOUT |
|                   |        |     |         |          |          |          |          | D         | D         |             |           |          |          |     |         |      |
Pinouts and pin description
PB6 - - TIM4_CH1 - I2C1_SCL - - USART1_TX - - QUADSPI_ - FMC_SDN EVEN
|     |     |     |     |     |     |     |     |     |     |     |     |     | BK1_NCS |     | E1  | TOUT |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- | --- | ---- |
EVEN
|     |     | PB7 | -   | -   | TIM4_CH2 | -   | I2C1_SDA | -   | -   | USART1_RX | -   | -   | -   | -   | FMC_NL |     |
| --- | --- | --- | --- | --- | -------- | --- | -------- | --- | --- | --------- | --- | --- | --- | --- | ------ | --- |
TOUT
|     |     |     |     |     |          | TIM10_CH |          |     |     |     |     |         | SDMMC2_ |     | SDMMC1 | EVEN |
| --- | --- | --- | --- | --- | -------- | -------- | -------- | --- | --- | --- | --- | ------- | ------- | --- | ------ | ---- |
|     |     | PB8 | -   | -   | TIM4_CH3 | 1        | I2C1_SCL | -   | -   | -   | -   | CAN1_RX | D4      | -   | _D4    | TOUT |
87/229

88/229 Table 12.  STM32F722xx and STM32F723xx alternate function mapping (continued) Pinouts and pin description
|     |      | AF0 | AF1 | AF2 | AF3         | AF4        | AF5        | AF6        | AF7         | AF8        | AF9        | AF10      | AF11 | AF12    | AF15 |     |
| --- | ---- | --- | --- | --- | ----------- | ---------- | ---------- | ---------- | ----------- | ---------- | ---------- | --------- | ---- | ------- | ---- | --- |
|     |      |     |     |     |             |            | SPI1/I2S1/ | SPI2/I2S2/ | SPI2/I2S2/S |            | CAN1/TIM1  | SAI2/QUAD |      | UART7/F |      |     |
|     | Port |     |     |     |             |            |            | SPI3/I2S3/ |             | SAI2/USART | 2/13/14/QU | SPI/SDMM  |      |         |      |     |
|     |      |     |     |     | TIM8/9/10/1 | I2C1/2/3/U | SPI2/I2S2/ |            | PI3/I2S3/US |            |            |           |      | MC/SDM  |      |     |
SYS TIM1/2 TIM3/4/5 SPI3/I2S3/ 6/UART4/5/7/ ADSPI/ C2/OTG2_ SDMMC2 SYS
|        |      |     |          |          | 1/LPTIM1  | SART1    | SPI3/I2S3/ | SAI1/ | ART1/2/3/UA | 8/OTG1_FS | FMC/    | HS/OTG1_ |     | MC1/    |      |     |
| ------ | ---- | --- | -------- | -------- | --------- | -------- | ---------- | ----- | ----------- | --------- | ------- | -------- | --- | ------- | ---- | --- |
|        |      |     |          |          |           |          | SPI4/5     |       | RT5         |           |         |          |     | OTG2_FS |      |     |
|        |      |     |          |          |           |          |            | UART4 |             |           | OTG2_HS | FS       |     |         |      |     |
|        |      |     |          |          |           |          | SPI2_NSS   |       |             |           |         | SDMMC2_  |     | SDMMC1  | EVEN |     |
|        | PB9  | -   | -        | TIM4_CH4 | TIM11_CH1 | I2C1_SDA |            | -     | -           | -         | CAN1_TX |          | -   |         |      |     |
|        |      |     |          |          |           |          | /I2S2_WS   |       |             |           |         | D5       |     | _D5     | TOUT |     |
|        |      |     |          |          |           |          | SPI2_SCK   |       |             |           |         | OTG_HS_U |     |         | EVEN |     |
|        | PB10 | -   | TIM2_CH3 | -        | -         | I2C2_SCL |            | -     | USART3_TX   | -         | -       |          | -   | -       |      |     |
|        |      |     |          |          |           |          | /I2S2_CK   |       |             |           |         | LPI_D3   |     |         | TOUT |     |
|        |      |     |          |          |           |          |            |       |             |           |         | OTG_HS_U |     |         | EVEN |     |
|        | PB11 | -   | TIM2_CH4 | -        | -         | I2C2_SDA | -          | -     | USART3_RX   | -         | -       |          | -   | -       |      |     |
|        |      |     |          |          |           |          |            |       |             |           |         | LPI_D4   |     |         | TOUT |     |
|        |      |     | TIM1_BKI |          |           | I2C2_SMB | SPI2_NSS   |       |             |           |         | OTG_HS_U |     | OTG_HS_ | EVEN |     |
| Port B | PB12 | -   |          | -        | -         |          |            | -     | USART3_CK   | -         | -       |          | -   |         |      |     |
|        |      |     | N        |          |           | A        | /I2S2_WS   |       |             |           |         | LPI_D5   |     | ID      | TOUT |     |
DocID029808 Rev 3
|     |      |     | TIM1_CH1 |     |          |     | SPI2_SCK |     | USART3_CT |     |           | OTG_HS_U |     |         | EVEN |     |
| --- | ---- | --- | -------- | --- | -------- | --- | -------- | --- | --------- | --- | --------- | -------- | --- | ------- | ---- | --- |
|     | PB13 | -   |          | -   | -        | -   |          | -   |           | -   | -         |          | -   | -       |      |     |
|     |      |     | N        |     |          |     | /I2S2_CK |     | S         |     |           | LPI_D6   |     |         | TOUT |     |
|     |      |     | TIM1_CH2 |     | TIM8_CH2 |     | SPI2_MIS |     | USART3_RT |     |           | SDMMC2_  |     | OTG_HS_ | EVEN |     |
|     | PB14 | -   | N        | -   | N        | -   | O        | -   | S         | -   | TIM12_CH1 | D0       | -   | DM      | TOUT |     |
SPI2_MO
|     |      | RTC_REF | TIM1_CH3 |     | TIM8_CH3 |     |           |     |     |     |           | SDMMC2_ |     | OTG_HS_ | EVEN |     |
| --- | ---- | ------- | -------- | --- | -------- | --- | --------- | --- | --- | --- | --------- | ------- | --- | ------- | ---- | --- |
|     | PB15 |         |          | -   |          | -   | SI/I2S2_S | -   | -   | -   | TIM12_CH2 |         | -   |         |      |     |
|     |      | IN      | N        |     | N        |     |           |     |     |     |           | D1      |     | DP      | TOUT |     |
D
|     | PC0 | -   | -   | -   | -   | -   | -   | -   | -   | SAI2_FS_B | -   | OTG_HS_U | -   | FMC_SDN | EVEN |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --------- | --- | -------- | --- | ------- | ---- | --- |
|     |     |     |     |     |     |     |     |     |     |           |     | LPI_STP  |     | WE      | TOUT |     |
SPI2_MO
|     |     |         |     |     |     |     |           | SAI1_SD_ |     |     |     |     |     |     | EVEN |     |
| --- | --- | ------- | --- | --- | --- | --- | --------- | -------- | --- | --- | --- | --- | --- | --- | ---- | --- |
|     | PC1 | TRACED0 | -   | -   | -   | -   | SI/I2S2_S |          | -   | -   | -   | -   | -   | -   |      |     |
|     |     |         |     |     |     |     | D         | A        |     |     |     |     |     |     | TOUT |     |
Port C
|     |     |     |     |     |     |     | SPI2_MIS |     |     |     |     | OTG_HS_U |     | FMC_SDN | EVEN |                         |
| --- | --- | --- | --- | --- | --- | --- | -------- | --- | --- | --- | --- | -------- | --- | ------- | ---- | ----------------------- |
|     | PC2 | -   | -   | -   | -   | -   |          | -   | -   | -   | -   |          | -   |         |      | STM32F722xx STM32F723xx |
|     |     |     |     |     |     |     | O        |     |     |     |     | LPI_DIR  |     | E0      | TOUT |                         |
SPI2_MO
|     |     |     |     |     |     |     |           |     |     |     |     | OTG_HS_U |     | FMC_SDC | EVEN |     |
| --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | --- | -------- | --- | ------- | ---- | --- |
|     | PC3 | -   | -   | -   | -   | -   | SI/I2S2_S | -   | -   | -   | -   | LPI_NXT  | -   | KE0     | TOUT |     |
D

Table 12.  STM32F722xx and STM32F723xx alternate function mapping (continued) STM32F722xx STM32F723xx
|      | AF0 | AF1 | AF2 | AF3         | AF4        | AF5        | AF6        | AF7         | AF8        | AF9        | AF10      | AF11 | AF12    | AF15 |
| ---- | --- | --- | --- | ----------- | ---------- | ---------- | ---------- | ----------- | ---------- | ---------- | --------- | ---- | ------- | ---- |
|      |     |     |     |             |            | SPI1/I2S1/ | SPI2/I2S2/ | SPI2/I2S2/S |            | CAN1/TIM1  | SAI2/QUAD |      | UART7/F |      |
| Port |     |     |     |             |            |            | SPI3/I2S3/ |             | SAI2/USART | 2/13/14/QU | SPI/SDMM  |      |         |      |
|      |     |     |     | TIM8/9/10/1 | I2C1/2/3/U | SPI2/I2S2/ |            | PI3/I2S3/US |            |            |           |      | MC/SDM  |      |
SYS TIM1/2 TIM3/4/5 SPI3/I2S3/ 6/UART4/5/7/ ADSPI/ C2/OTG2_ SDMMC2 SYS
|     |     |     |          | 1/LPTIM1 | SART1 | SPI3/I2S3/ | SAI1/ | ART1/2/3/UA | 8/OTG1_FS | FMC/    | HS/OTG1_ |     | MC1/    |      |
| --- | --- | --- | -------- | -------- | ----- | ---------- | ----- | ----------- | --------- | ------- | -------- | --- | ------- | ---- |
|     |     |     |          |          |       | SPI4/5     |       | RT5         |           |         |          |     | OTG2_FS |      |
|     |     |     |          |          |       |            | UART4 |             |           | OTG2_HS | FS       |     |         |      |
| PC4 | -   | -   | -        | -        | -     | I2S1_MCK   | -     | -           | -         | -       | -        | -   | FMC_SDN | EVEN |
|     |     |     |          |          |       |            |       |             |           |         |          |     | E0      | TOUT |
| PC5 | -   | -   | -        | -        | -     | -          | -     | -           | -         | -       | -        | -   | FMC_SDC | EVEN |
|     |     |     |          |          |       |            |       |             |           |         |          |     | KE0     | TOUT |
|     |     |     |          |          |       |            |       |             |           |         | SDMMC2_  |     | SDMMC1  | EVEN |
| PC6 | -   | -   | TIM3_CH1 | TIM8_CH1 | -     | I2S2_MCK   | -     | -           | USART6_TX | -       |          | -   |         |      |
|     |     |     |          |          |       |            |       |             |           |         | D6       |     | _D6     | TOUT |
|     |     |     |          |          |       |            |       |             |           |         | SDMMC2_  |     | SDMMC1  | EVEN |
PC7 - - TIM3_CH2 TIM8_CH2 - - I2S3_MCK - USART6_RX - D7 - _D7 TOUT
|     |     |     |     |     |     |     |     |     |     |     |     |     | SDMMC1 | EVEN |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | ---- |
PC8 TRACED1 - TIM3_CH3 TIM8_CH3 - - - UART5_RTS USART6_CK - - -
| DocID029808 Rev 3 |     |     |     |     |     |     |     |     |     |          |     |     | _D0    | TOUT |
| ----------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | -------- | --- | --- | ------ | ---- |
|                   |     |     |     |     |     |     |     |     |     | QUADSPI_ |     |     | SDMMC1 | EVEN |
PC9 MCO2 - TIM3_CH4 TIM8_CH4 I2C3_SDA I2S_CKIN - UART5_CTS - - -
|     |     |     |     |     |     |     |     |     |     | BK1_IO0 |     |     | _D1 | TOUT |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- | --- | --- | ---- |
Port C
|     |     |     |     |     |     |     | SPI3_SCK |     |     | QUADSPI_ |     |     | SDMMC1 | EVEN |
| --- | --- | --- | --- | --- | --- | --- | -------- | --- | --- | -------- | --- | --- | ------ | ---- |
PC10 - - - - - - /I2S3_CK USART3_TX UART4_TX BK1_IO1 - - _D2 TOUT
PC11 - - - - - - SPI3_MIS USART3_RX UART4_RX QUADSPI_ - - SDMMC1 EVEN
|     |     |     |     |     |     |     | O   |     |     | BK2_NCS |     |     | _D3 | TOUT |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- | --- | --- | ---- |
SPI3_MO
|      |         |     |     |     |     |     |           |           |          |     |     |     | SDMMC1 | EVEN |
| ---- | ------- | --- | --- | --- | --- | --- | --------- | --------- | -------- | --- | --- | --- | ------ | ---- |
| PC12 | TRACED3 | -   | -   | -   | -   | -   | SI/I2S3_S | USART3_CK | UART5_TX | -   | -   | -   |        |      |
|      |         |     |     |     |     |     | D         |           |          |     |     |     | _CK    | TOUT |
EVEN
| PC13 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |     |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
TOUT
EVEN Pinouts and pin description
| PC14 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |     |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
TOUT
| PC15 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | EVEN |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
TOUT
89/229

90/229 Table 12.  STM32F722xx and STM32F723xx alternate function mapping (continued) Pinouts and pin description
|      | AF0 | AF1 | AF2 | AF3         | AF4        | AF5        | AF6        | AF7         | AF8        | AF9        | AF10      | AF11 | AF12    | AF15 |
| ---- | --- | --- | --- | ----------- | ---------- | ---------- | ---------- | ----------- | ---------- | ---------- | --------- | ---- | ------- | ---- |
|      |     |     |     |             |            | SPI1/I2S1/ | SPI2/I2S2/ | SPI2/I2S2/S |            | CAN1/TIM1  | SAI2/QUAD |      | UART7/F |      |
| Port |     |     |     |             |            |            | SPI3/I2S3/ |             | SAI2/USART | 2/13/14/QU | SPI/SDMM  |      |         |      |
|      |     |     |     | TIM8/9/10/1 | I2C1/2/3/U | SPI2/I2S2/ |            | PI3/I2S3/US |            |            |           |      | MC/SDM  |      |
SYS TIM1/2 TIM3/4/5 SPI3/I2S3/ 6/UART4/5/7/ ADSPI/ C2/OTG2_ SDMMC2 SYS
|     |     |     |     | 1/LPTIM1 | SART1 | SPI3/I2S3/ | SAI1/ | ART1/2/3/UA | 8/OTG1_FS | FMC/    | HS/OTG1_ |     | MC1/    |     |
| --- | --- | --- | --- | -------- | ----- | ---------- | ----- | ----------- | --------- | ------- | -------- | --- | ------- | --- |
|     |     |     |     |          |       | SPI4/5     |       | RT5         |           |         |          |     | OTG2_FS |     |
|     |     |     |     |          |       |            | UART4 |             |           | OTG2_HS | FS       |     |         |     |
EVEN
| PD0 | -   | -   | -   | -   | -   | -   | -   | -   | -   | CAN1_RX | -   | -   | FMC_D2 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- | --- | ------ | --- |
TOUT
EVEN
| PD1 | -   | -   | -   | -   | -   | -   | -   | -   | -   | CAN1_TX | -   | -   | FMC_D3 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- | --- | ------ | --- |
TOUT
| PD2 | TRACED2 | -   | TIM3_ETR | -   | -   | -        | -   | -         | UART5_RX | -   | -   | -   | SDMMC1  | EVEN |
| --- | ------- | --- | -------- | --- | --- | -------- | --- | --------- | -------- | --- | --- | --- | ------- | ---- |
|     |         |     |          |     |     |          |     |           |          |     |     |     | _CMD    | TOUT |
|     |         |     |          |     |     | SPI2_SCK |     | USART2_CT |          |     |     |     |         | EVEN |
| PD3 | -       | -   | -        | -   | -   |          | -   |           | -        | -   | -   | -   | FMC_CLK |      |
|     |         |     |          |     |     | /I2S2_CK |     | S         |          |     |     |     |         | TOUT |
|     |         |     |          |     |     |          |     | USART2_RT |          |     |     |     | FMC_NO  | EVEN |
| PD4 | -       | -   | -        | -   | -   | -        | -   | S         | -        | -   | -   | -   | E       | TOUT |
DocID029808 Rev 3
|     |     |     |     |     |     |     |     |           |     |     |     |     | FMC_NW | EVEN |
| --- | --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | --- | ------ | ---- |
| PD5 | -   | -   | -   | -   | -   | -   | -   | USART2_TX | -   | -   | -   | -   |        |      |
|     |     |     |     |     |     |     |     |           |     |     |     |     | E      | TOUT |
SPI3_MO
|     |     |     |     |     |     |           | SAI1_SD_ |           |     |     |     | SDMMC2 | FMC_NW | EVEN |
| --- | --- | --- | --- | --- | --- | --------- | -------- | --------- | --- | --- | --- | ------ | ------ | ---- |
| PD6 | -   | -   | -   | -   | -   | SI/I2S3_S | A        | USART2_RX | -   | -   | -   | _CK    | AIT    | TOUT |
D
Port D
|     |     |     |     |     |     |     |     |           |     |     |     | SDMMC2 |         | EVEN |
| --- | --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | ------ | ------- | ---- |
| PD7 | -   | -   | -   | -   | -   | -   | -   | USART2_CK | -   | -   | -   |        | FMC_NE1 |      |
|     |     |     |     |     |     |     |     |           |     |     |     | _CMD   |         | TOUT |
EVEN
| PD8 | -   | -   | -   | -   | -   | -   | -   | USART3_TX | -   | -   | -   | -   | FMC_D13 | TOUT |
| --- | --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | --- | ------- | ---- |
EVEN
| PD9 | -   | -   | -   | -   | -   | -   | -   | USART3_RX | -   | -   | -   | -   | FMC_D14 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | --- | ------- | --- |
TOUT
EVEN
PD10 - - - - - - - USART3_CK - - - - FMC_D15 STM32F722xx STM32F723xx
TOUT
PD11 - - - - - - - USART3_CT - QUADSPI_ SAI2_SD_A - FMC_A16/ EVEN
|      |     |     |          |           |     |     |     | S         |     | BK1_IO0  |           |     | FMC_CLE  | TOUT |
| ---- | --- | --- | -------- | --------- | --- | --- | --- | --------- | --- | -------- | --------- | --- | -------- | ---- |
|      |     |     |          | LPTIM1_IN |     |     |     | USART3_RT |     | QUADSPI_ |           |     | FMC_A17/ | EVEN |
| PD12 | -   | -   | TIM4_CH1 |           | -   | -   | -   |           | -   |          | SAI2_FS_A | -   |          |      |
|      |     |     |          | 1         |     |     |     | S         |     | BK1_IO1  |           |     | FMC_ALE  | TOUT |
|      |     |     |          | LPTIM1_O  |     |     |     |           |     | QUADSPI_ | SAI2_SCK_ |     |          | EVEN |
| PD13 | -   | -   | TIM4_CH2 | UT        | -   | -   | -   | -         | -   | BK1_IO3  | A         | -   | FMC_A18  | TOUT |
EVEN
| PD14 | -   | -   | TIM4_CH3 | -   | -   | -   | -   | -   | UART8_CTS | -   | -   | -   | FMC_D0 |     |
| ---- | --- | --- | -------- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | ------ | --- |
TOUT
Port D
EVEN
| PD15 | -   | -   | TIM4_CH4 | -   | -   | -   | -   | -   | UART8_RTS | -   | -   | -   | FMC_D1 |     |
| ---- | --- | --- | -------- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | ------ | --- |
TOUT

Table 12.  STM32F722xx and STM32F723xx alternate function mapping (continued) STM32F722xx STM32F723xx
|     |      | AF0 | AF1 | AF2 | AF3         | AF4        | AF5        | AF6        | AF7         | AF8        | AF9        | AF10      | AF11 | AF12    | AF15 |
| --- | ---- | --- | --- | --- | ----------- | ---------- | ---------- | ---------- | ----------- | ---------- | ---------- | --------- | ---- | ------- | ---- |
|     |      |     |     |     |             |            | SPI1/I2S1/ | SPI2/I2S2/ | SPI2/I2S2/S |            | CAN1/TIM1  | SAI2/QUAD |      | UART7/F |      |
|     | Port |     |     |     |             |            |            | SPI3/I2S3/ |             | SAI2/USART | 2/13/14/QU | SPI/SDMM  |      |         |      |
|     |      |     |     |     | TIM8/9/10/1 | I2C1/2/3/U | SPI2/I2S2/ |            | PI3/I2S3/US |            |            |           |      | MC/SDM  |      |
SYS TIM1/2 TIM3/4/5 SPI3/I2S3/ 6/UART4/5/7/ ADSPI/ C2/OTG2_ SDMMC2 SYS
|                   |     |         |          |          | 1/LPTIM1  | SART1 | SPI3/I2S3/ | SAI1/    | ART1/2/3/UA | 8/OTG1_FS | FMC/     | HS/OTG1_ |     | MC1/    |      |
| ----------------- | --- | ------- | -------- | -------- | --------- | ----- | ---------- | -------- | ----------- | --------- | -------- | -------- | --- | ------- | ---- |
|                   |     |         |          |          |           |       | SPI4/5     |          | RT5         |           |          |          |     | OTG2_FS |      |
|                   |     |         |          |          |           |       |            | UART4    |             |           | OTG2_HS  | FS       |     |         |      |
|                   |     |         |          |          | LPTIM1_ET |       |            |          |             |           |          | SAI2_MCK |     | FMC_NBL | EVEN |
|                   | PE0 | -       | -        | TIM4_ETR |           | -     | -          | -        | -           | UART8_Rx  | -        |          | -   |         |      |
|                   |     |         |          |          | R         |       |            |          |             |           |          | _A       |     | 0       | TOUT |
|                   |     |         |          |          | LPTIM1_IN |       |            |          |             |           |          |          |     | FMC_NBL | EVEN |
|                   | PE1 | -       | -        | -        |           | -     | -          | -        | -           | UART8_Tx  | -        | -        | -   |         |      |
|                   |     |         |          |          | 2         |       |            |          |             |           |          |          |     | 1       | TOUT |
|                   |     | TRACECL |          |          |           |       |            | SAI1_MCL |             |           | QUADSPI_ |          |     |         | EVEN |
|                   | PE2 | K       | -        | -        | -         | -     | SPI4_SCK   | K_A      | -           | -         | BK1_IO2  | -        | -   | FMC_A23 | TOUT |
|                   | PE3 | TRACED0 | -        | -        | -         | -     | -          | SAI1_SD_ | -           | -         | -        | -        | -   | FMC_A19 | EVEN |
|                   |     |         |          |          |           |       |            | B        |             |           |          |          |     |         | TOUT |
|                   |     |         |          |          |           |       |            | SAI1_FS_ |             |           |          |          |     |         | EVEN |
|                   | PE4 | TRACED1 | -        | -        | -         | -     | SPI4_NSS   |          | -           | -         | -        | -        | -   | FMC_A20 |      |
| DocID029808 Rev 3 |     |         |          |          |           |       |            | A        |             |           |          |          |     |         | TOUT |
|                   |     |         |          |          |           |       | SPI4_MIS   | SAI1_SCK |             |           |          |          |     |         | EVEN |
|                   | PE5 | TRACED2 | -        | -        | TIM9_CH1  | -     | O          | _A       | -           | -         | -        | -        | -   | FMC_A21 | TOUT |
|                   |     |         | TIM1_BKI |          |           |       | SPI4_MO    | SAI1_SD_ |             |           |          | SAI2_MCK |     |         | EVEN |
|                   | PE6 | TRACED3 |          | -        | TIM9_CH2  | -     |            |          | -           | -         | -        |          | -   | FMC_A22 |      |
|                   |     |         | N2       |          |           |       | SI         | A        |             |           |          | _B       |     |         | TOUT |
Port E
|     |      |     |          |     |     |     |     |     |     |           |     | QUADSPI_ |     |        | EVEN |
| --- | ---- | --- | -------- | --- | --- | --- | --- | --- | --- | --------- | --- | -------- | --- | ------ | ---- |
|     | PE7  | -   | TIM1_ETR | -   | -   | -   | -   | -   | -   | UART7_Rx  | -   |          | -   | FMC_D4 |      |
|     |      |     |          |     |     |     |     |     |     |           |     | BK2_IO0  |     |        | TOUT |
|     | PE8  | -   | TIM1_CH1 | -   | -   | -   | -   | -   | -   | UART7_Tx  | -   | QUADSPI_ | -   | FMC_D5 | EVEN |
|     |      |     | N        |     |     |     |     |     |     |           |     | BK2_IO1  |     |        | TOUT |
|     |      |     |          |     |     |     |     |     |     |           |     | QUADSPI_ |     |        | EVEN |
|     | PE9  | -   | TIM1_CH1 | -   | -   | -   | -   | -   | -   | UART7_RTS | -   |          | -   | FMC_D6 |      |
|     |      |     |          |     |     |     |     |     |     |           |     | BK2_IO2  |     |        | TOUT |
|     |      |     | TIM1_CH2 |     |     |     |     |     |     |           |     | QUADSPI_ |     |        | EVEN |
|     | PE10 | -   | N        | -   | -   | -   | -   | -   | -   | UART7_CTS | -   | BK2_IO3  | -   | FMC_D7 | TOUT |
Pinouts and pin description
EVEN
|     | PE11 | -   | TIM1_CH2 | -   | -   | -   | SPI4_NSS | -   | -   | -   | -   | SAI2_SD_B | -   | FMC_D8 |     |
| --- | ---- | --- | -------- | --- | --- | --- | -------- | --- | --- | --- | --- | --------- | --- | ------ | --- |
TOUT
|     |      |     | TIM1_CH3 |     |     |     |          |     |     |     |     | SAI2_SCK_ |     |        | EVEN |
| --- | ---- | --- | -------- | --- | --- | --- | -------- | --- | --- | --- | --- | --------- | --- | ------ | ---- |
|     | PE12 | -   |          | -   | -   | -   | SPI4_SCK | -   | -   | -   | -   |           | -   | FMC_D9 |      |
|     |      |     | N        |     |     |     |          |     |     |     |     | B         |     |        | TOUT |
PE13 - TIM1_CH3 - - - SPI4_MIS - - - - SAI2_FS_B - FMC_D10 EVEN
|     |      |     |          |     |     |     | O       |     |     |     |     |          |     |         | TOUT |
| --- | ---- | --- | -------- | --- | --- | --- | ------- | --- | --- | --- | --- | -------- | --- | ------- | ---- |
|     |      |     |          |     |     |     | SPI4_MO |     |     |     |     | SAI2_MCK |     |         | EVEN |
|     | PE14 | -   | TIM1_CH4 | -   | -   | -   |         | -   | -   | -   | -   |          | -   | FMC_D11 |      |
|     |      |     |          |     |     |     | SI      |     |     |     |     | _B       |     |         | TOUT |
Port E
| 91/229 |      |     | TIM1_BKI |     |     |     |     |     |     |     |     |     |     |         | EVEN |
| ------ | ---- | --- | -------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | ---- |
|        | PE15 | -   | N        | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_D12 | TOUT |

92/229 Table 12.  STM32F722xx and STM32F723xx alternate function mapping (continued) Pinouts and pin description
|     |      | AF0 | AF1 | AF2 | AF3         | AF4        | AF5        | AF6        | AF7         | AF8        | AF9        | AF10      | AF11 | AF12    | AF15 |
| --- | ---- | --- | --- | --- | ----------- | ---------- | ---------- | ---------- | ----------- | ---------- | ---------- | --------- | ---- | ------- | ---- |
|     |      |     |     |     |             |            | SPI1/I2S1/ | SPI2/I2S2/ | SPI2/I2S2/S |            | CAN1/TIM1  | SAI2/QUAD |      | UART7/F |      |
|     | Port |     |     |     |             |            |            | SPI3/I2S3/ |             | SAI2/USART | 2/13/14/QU | SPI/SDMM  |      |         |      |
|     |      |     |     |     | TIM8/9/10/1 | I2C1/2/3/U | SPI2/I2S2/ |            | PI3/I2S3/US |            |            |           |      | MC/SDM  |      |
SYS TIM1/2 TIM3/4/5 SPI3/I2S3/ 6/UART4/5/7/ ADSPI/ C2/OTG2_ SDMMC2 SYS
|     |     |     |     |     | 1/LPTIM1 | SART1 | SPI3/I2S3/ | SAI1/ | ART1/2/3/UA | 8/OTG1_FS | FMC/    | HS/OTG1_ |     | MC1/    |     |
| --- | --- | --- | --- | --- | -------- | ----- | ---------- | ----- | ----------- | --------- | ------- | -------- | --- | ------- | --- |
|     |     |     |     |     |          |       | SPI4/5     |       | RT5         |           |         |          |     | OTG2_FS |     |
|     |     |     |     |     |          |       |            | UART4 |             |           | OTG2_HS | FS       |     |         |     |
EVEN
|     | PF0 | -   | -   | -   | -   | I2C2_SDA | -   | -   | -   | -   | -   | -   | -   | FMC_A0 |     |
| --- | --- | --- | --- | --- | --- | -------- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
TOUT
EVEN
|     | PF1 | -   | -   | -   | -   | I2C2_SCL | -   | -   | -   | -   | -   | -   | -   | FMC_A1 |     |
| --- | --- | --- | --- | --- | --- | -------- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
TOUT
|     | PF2 | -   | -   | -   | -   | I2C2_SMB | -   | -   | -   | -   | -   | -   | -   | FMC_A2 | EVEN |
| --- | --- | --- | --- | --- | --- | -------- | --- | --- | --- | --- | --- | --- | --- | ------ | ---- |
|     |     |     |     |     |     | A        |     |     |     |     |     |     |     |        | TOUT |
EVEN
|     | PF3 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_A3 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
TOUT
EVEN
|     | PF4 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_A4 | TOUT |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | ---- |
DocID029808 Rev 3
EVEN
|     | PF5 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_A5 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
TOUT
|        |     |     |     |     | TIM10_CH |     |          | SAI1_SD_ |     |          | QUADSPI_ |     |     |     | EVEN |
| ------ | --- | --- | --- | --- | -------- | --- | -------- | -------- | --- | -------- | -------- | --- | --- | --- | ---- |
| Port F | PF6 | -   | -   | -   |          | -   | SPI5_NSS |          | -   | UART7_Rx |          | -   | -   | -   |      |
|        |     |     |     |     | 1        |     |          | B        |     |          | BK1_IO3  |     |     |     | TOUT |
PF7 - - - TIM11_CH1 - SPI5_SCK SAI1_MCL - UART7_Tx QUADSPI_ - - - EVEN
|     |     |     |     |     |     |     |          | K_B      |     |           | BK1_IO2   |          |     |     | TOUT |
| --- | --- | --- | --- | --- | --- | --- | -------- | -------- | --- | --------- | --------- | -------- | --- | --- | ---- |
|     |     |     |     |     |     |     | SPI5_MIS | SAI1_SCK |     |           |           | QUADSPI_ |     |     | EVEN |
|     | PF8 | -   | -   | -   | -   | -   |          |          | -   | UART7_RTS | TIM13_CH1 |          | -   | -   |      |
|     |     |     |     |     |     |     | O        | _B       |     |           |           | BK1_IO0  |     |     | TOUT |
|     |     |     |     |     |     |     | SPI5_MO  | SAI1_FS_ |     |           |           | QUADSPI_ |     |     | EVEN |
|     | PF9 | -   | -   | -   | -   | -   | SI       | B        | -   | UART7_CTS | TIM14_CH1 | BK1_IO1  | -   | -   | TOUT |
EVEN
|     | PF10 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
TOUT
STM32F722xx STM32F723xx
|     |      |     |     |     |     |     | SPI5_MO |     |     |     |     |           |     | FMC_SDN | EVEN |
| --- | ---- | --- | --- | --- | --- | --- | ------- | --- | --- | --- | --- | --------- | --- | ------- | ---- |
|     | PF11 | -   | -   | -   | -   | -   |         | -   | -   | -   | -   | SAI2_SD_B | -   |         |      |
|     |      |     |     |     |     |     | SI      |     |     |     |     |           |     | RAS     | TOUT |
|     | PF12 | -   | -   | -   | -   | -   | -       | -   | -   | -   | -   | -         | -   | FMC_A6  | EVEN |
TOUT
EVEN
|     | PF13 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_A7 |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
TOUT
EVEN
| Port F | PF14 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_A8 | TOUT |
| ------ | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | ---- |
EVEN
|     | PF15 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_A9 |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
TOUT

Table 12.  STM32F722xx and STM32F723xx alternate function mapping (continued) STM32F722xx STM32F723xx
|      | AF0 | AF1 | AF2 | AF3         | AF4        | AF5        | AF6        | AF7         | AF8        | AF9        | AF10      | AF11 | AF12    | AF15 |
| ---- | --- | --- | --- | ----------- | ---------- | ---------- | ---------- | ----------- | ---------- | ---------- | --------- | ---- | ------- | ---- |
|      |     |     |     |             |            | SPI1/I2S1/ | SPI2/I2S2/ | SPI2/I2S2/S |            | CAN1/TIM1  | SAI2/QUAD |      | UART7/F |      |
| Port |     |     |     |             |            |            | SPI3/I2S3/ |             | SAI2/USART | 2/13/14/QU | SPI/SDMM  |      |         |      |
|      |     |     |     | TIM8/9/10/1 | I2C1/2/3/U | SPI2/I2S2/ |            | PI3/I2S3/US |            |            |           |      | MC/SDM  |      |
SYS TIM1/2 TIM3/4/5 SPI3/I2S3/ 6/UART4/5/7/ ADSPI/ C2/OTG2_ SDMMC2 SYS
|     |     |     |     | 1/LPTIM1 | SART1 | SPI3/I2S3/ | SAI1/ | ART1/2/3/UA | 8/OTG1_FS | FMC/    | HS/OTG1_ |     | MC1/    |     |
| --- | --- | --- | --- | -------- | ----- | ---------- | ----- | ----------- | --------- | ------- | -------- | --- | ------- | --- |
|     |     |     |     |          |       | SPI4/5     |       | RT5         |           |         |          |     | OTG2_FS |     |
|     |     |     |     |          |       |            | UART4 |             |           | OTG2_HS | FS       |     |         |     |
EVEN
| PG0 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_A10 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- |
TOUT
EVEN
| PG1 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_A11 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- |
TOUT
| PG2 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_A12 | EVEN |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | ---- |
TOUT
EVEN
| PG3 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_A13 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- |
TOUT
|     |     |     |     |     |     |     |     |     |     |     |     |     | FMC_A14/ | EVEN |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | -------- | ---- |
| PG4 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_BA0  | TOUT |
DocID029808 Rev 3
|        |     |     |     |     |     |     |     |     |     |     |     |     | FMC_A15/ | EVEN |
| ------ | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | -------- | ---- |
| PG5    | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |          |      |
| Port G |     |     |     |     |     |     |     |     |     |     |     |     | FMC_BA1  | TOUT |
EVEN
| PG6 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
TOUT
| PG7 | -   | -   | -   | -   | -   | -   | -   | -   | USART6_CK | -   | -   | -   | FMC_INT | EVEN |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | ------- | ---- |
TOUT
|     |     |     |     |     |     |     |     |     | USART6_RT |     |     |     | FMC_SDC | EVEN |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | ------- | ---- |
| PG8 | -   | -   | -   | -   | -   | -   | -   | -   |           | -   | -   | -   |         |      |
|     |     |     |     |     |     |     |     |     | S         |     |     |     | LK      | TOUT |
FMC_NE2
PG9 - - - - - - - - USART6_RX QUADSPI_ SAI2_FS_B SDMMC2 /FMC_NC EVEN
|     |     |     |     |     |     |     |     |     |     | BK2_IO2 |     | _D0 |     | TOUT |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- | --- | --- | ---- |
E
|     |     |     |     |     |     |     |     |     |     |     |     | SDMMC2 |     | EVEN |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ | --- | ---- |
PG10 - - - - - - - - - - SAI2_SD_B FMC_NE3 Pinouts and pin description
|     |     |     |     |     |     |     |     |     |     |     |     | _D1 |     | TOUT |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
93/229

94/229 Table 12.  STM32F722xx and STM32F723xx alternate function mapping (continued) Pinouts and pin description
|      | AF0 | AF1 | AF2 | AF3         | AF4        | AF5        | AF6        | AF7         | AF8        | AF9        | AF10      | AF11 | AF12    | AF15 |
| ---- | --- | --- | --- | ----------- | ---------- | ---------- | ---------- | ----------- | ---------- | ---------- | --------- | ---- | ------- | ---- |
|      |     |     |     |             |            | SPI1/I2S1/ | SPI2/I2S2/ | SPI2/I2S2/S |            | CAN1/TIM1  | SAI2/QUAD |      | UART7/F |      |
| Port |     |     |     |             |            |            | SPI3/I2S3/ |             | SAI2/USART | 2/13/14/QU | SPI/SDMM  |      |         |      |
|      |     |     |     | TIM8/9/10/1 | I2C1/2/3/U | SPI2/I2S2/ |            | PI3/I2S3/US |            |            |           |      | MC/SDM  |      |
SYS TIM1/2 TIM3/4/5 SPI3/I2S3/ 6/UART4/5/7/ ADSPI/ C2/OTG2_ SDMMC2 SYS
|      |     |     |     | 1/LPTIM1  | SART1 | SPI3/I2S3/ | SAI1/ | ART1/2/3/UA | 8/OTG1_FS | FMC/    | HS/OTG1_ |        | MC1/    |      |
| ---- | --- | --- | --- | --------- | ----- | ---------- | ----- | ----------- | --------- | ------- | -------- | ------ | ------- | ---- |
|      |     |     |     |           |       | SPI4/5     |       | RT5         |           |         |          |        | OTG2_FS |      |
|      |     |     |     |           |       |            | UART4 |             |           | OTG2_HS | FS       |        |         |      |
|      |     |     |     |           |       |            |       |             |           |         | SDMMC2_  |        |         | EVEN |
| PG11 | -   | -   | -   | -         | -     | -          | -     | -           | -         | -       | D2       | -      | -       | TOUT |
|      |     |     |     | LPTIM1_IN |       |            |       |             | USART6_RT |         |          | SDMMC2 |         | EVEN |
| PG12 | -   | -   | -   | 1         | -     | -          | -     | -           | S         | -       | -        | _D3    | FMC_NE4 | TOUT |
Port G
PG13 TRACED0 - - LPTIM1_O - - - - USART6_CT - - - FMC_A24 EVEN
|      |         |     |     | UT        |     |     |     |     | S         |          |     |     |         | TOUT |
| ---- | ------- | --- | --- | --------- | --- | --- | --- | --- | --------- | -------- | --- | --- | ------- | ---- |
|      |         |     |     | LPTIM1_ET |     |     |     |     |           | QUADSPI_ |     |     |         | EVEN |
| PG14 | TRACED1 | -   | -   |           | -   | -   | -   | -   | USART6_TX |          | -   | -   | FMC_A25 |      |
|      |         |     |     | R         |     |     |     |     |           | BK2_IO3  |     |     |         | TOUT |
DocID029808 Rev 3
|      |     |     |     |     |     |     |     |     | USART6_CT |     |     |     | FMC_SDN | EVEN |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | --------- | --- | --- | --- | ------- | ---- |
| PG15 | -   | -   | -   | -   | -   | -   | -   | -   |           | -   | -   | -   |         |      |
|      |     |     |     |     |     |     |     |     | S         |     |     |     | CAS     | TOUT |
EVEN
| PH0 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | TOUT |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
EVEN
| PH1 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
TOUT
|     |     |     |     | LPTIM1_IN |     |     |     |     |     | QUADSPI_ | SAI2_SCK_ |     | FMC_SDC | EVEN |
| --- | --- | --- | --- | --------- | --- | --- | --- | --- | --- | -------- | --------- | --- | ------- | ---- |
| PH2 | -   | -   | -   |           | -   | -   | -   | -   | -   |          |           | -   |         |      |
|     |     |     |     | 2         |     |     |     |     |     | BK2_IO0  | B         |     | KE0     | TOUT |
| PH3 | -   | -   | -   | -         | -   | -   | -   | -   | -   | QUADSPI_ | SAI2_MCK  | -   | FMC_SDN | EVEN |
|     |     |     |     |           |     |     |     |     |     | BK2_IO1  | _B        |     | E0      | TOUT |
Port H
|     |     |     |     |     |          |     |     |     |     |     | OTG_HS_U |     |     | EVEN |
| --- | --- | --- | --- | --- | -------- | --- | --- | --- | --- | --- | -------- | --- | --- | ---- |
| PH4 | -   | -   | -   | -   | I2C2_SCL | -   | -   | -   | -   | -   |          | -   | -   |      |
|     |     |     |     |     |          |     |     |     |     |     | LPI_NXT  |     |     | TOUT |
STM32F722xx STM32F723xx
|     |     |     |     |     |          |          |     |     |     |           |     |     | FMC_SDN | EVEN |
| --- | --- | --- | --- | --- | -------- | -------- | --- | --- | --- | --------- | --- | --- | ------- | ---- |
| PH5 | -   | -   | -   | -   | I2C2_SDA | SPI5_NSS | -   | -   | -   | -         | -   | -   | WE      | TOUT |
|     |     |     |     |     | I2C2_SMB |          |     |     |     |           |     |     | FMC_SDN | EVEN |
| PH6 | -   | -   | -   | -   |          | SPI5_SCK | -   | -   | -   | TIM12_CH1 | -   | -   |         |      |
|     |     |     |     |     | A        |          |     |     |     |           |     |     | E1      | TOUT |
|     |     |     |     |     |          | SPI5_MIS |     |     |     |           |     |     | FMC_SDC | EVEN |
| PH7 | -   | -   | -   | -   | I2C3_SCL |          | -   | -   | -   | -         | -   | -   |         |      |
|     |     |     |     |     |          | O        |     |     |     |           |     |     | KE1     | TOUT |

Table 12.  STM32F722xx and STM32F723xx alternate function mapping (continued) STM32F722xx STM32F723xx
|      | AF0 | AF1 | AF2 | AF3         | AF4        | AF5        | AF6        | AF7         | AF8        | AF9        | AF10      | AF11 | AF12    | AF15 |
| ---- | --- | --- | --- | ----------- | ---------- | ---------- | ---------- | ----------- | ---------- | ---------- | --------- | ---- | ------- | ---- |
|      |     |     |     |             |            | SPI1/I2S1/ | SPI2/I2S2/ | SPI2/I2S2/S |            | CAN1/TIM1  | SAI2/QUAD |      | UART7/F |      |
| Port |     |     |     |             |            |            | SPI3/I2S3/ |             | SAI2/USART | 2/13/14/QU | SPI/SDMM  |      |         |      |
|      |     |     |     | TIM8/9/10/1 | I2C1/2/3/U | SPI2/I2S2/ |            | PI3/I2S3/US |            |            |           |      | MC/SDM  |      |
SYS TIM1/2 TIM3/4/5 SPI3/I2S3/ 6/UART4/5/7/ ADSPI/ C2/OTG2_ SDMMC2 SYS
|     |     |     |     | 1/LPTIM1 | SART1 | SPI3/I2S3/ | SAI1/ | ART1/2/3/UA | 8/OTG1_FS | FMC/    | HS/OTG1_ |     | MC1/    |     |
| --- | --- | --- | --- | -------- | ----- | ---------- | ----- | ----------- | --------- | ------- | -------- | --- | ------- | --- |
|     |     |     |     |          |       | SPI4/5     |       | RT5         |           |         |          |     | OTG2_FS |     |
|     |     |     |     |          |       |            | UART4 |             |           | OTG2_HS | FS       |     |         |     |
EVEN
| PH8 | -   | -   | -   | -   | I2C3_SDA | -   | -   | -   | -   | -   | -   | -   | FMC_D16 |     |
| --- | --- | --- | --- | --- | -------- | --- | --- | --- | --- | --- | --- | --- | ------- | --- |
TOUT
|      |     |     |          |     | I2C3_SMB |     |     |     |     |           |     |     |         | EVEN |
| ---- | --- | --- | -------- | --- | -------- | --- | --- | --- | --- | --------- | --- | --- | ------- | ---- |
| PH9  | -   | -   | -        | -   |          | -   | -   | -   | -   | TIM12_CH2 | -   | -   | FMC_D17 |      |
|      |     |     |          |     | A        |     |     |     |     |           |     |     |         | TOUT |
| PH10 | -   | -   | TIM5_CH1 | -   | -        | -   | -   | -   | -   | -         | -   | -   | FMC_D18 | EVEN |
TOUT
EVEN
| PH11 | -   | -   | TIM5_CH2 | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_D19 |     |
| ---- | --- | --- | -------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- |
TOUT
Port H
EVEN
| PH12 | -   | -   | TIM5_CH3 | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_D20 | TOUT |
| ---- | --- | --- | -------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | ---- |
DocID029808 Rev 3
|      |     |     |          | TIM8_CH1  |     |          |     |     |          |         |     |     |         | EVEN |
| ---- | --- | --- | -------- | --------- | --- | -------- | --- | --- | -------- | ------- | --- | --- | ------- | ---- |
| PH13 | -   | -   | -        |           | -   | -        | -   | -   | UART4_TX | CAN1_TX | -   | -   | FMC_D21 |      |
|      |     |     |          | N         |     |          |     |     |          |         |     |     |         | TOUT |
|      |     |     |          | TIM8_CH2  |     |          |     |     |          |         |     |     |         | EVEN |
| PH14 | -   | -   | -        |           | -   | -        | -   | -   | UART4_RX | CAN1_RX | -   | -   | FMC_D22 |      |
|      |     |     |          | N         |     |          |     |     |          |         |     |     |         | TOUT |
| PH15 | -   | -   | -        | TIM8_CH3  | -   | -        | -   | -   | -        | -       | -   | -   | FMC_D23 | EVEN |
|      |     |     |          | N         |     |          |     |     |          |         |     |     |         | TOUT |
|      |     |     |          |           |     | SPI2_NSS |     |     |          |         |     |     |         | EVEN |
| PI0  | -   | -   | TIM5_CH4 | -         | -   |          | -   | -   | -        | -       | -   | -   | FMC_D24 |      |
|      |     |     |          |           |     | /I2S2_WS |     |     |          |         |     |     |         | TOUT |
|      |     |     |          | TIM8_BKIN |     | SPI2_SCK |     |     |          |         |     |     |         | EVEN |
| PI1  | -   | -   | -        | 2         | -   | /I2S2_CK | -   | -   | -        | -       | -   | -   | FMC_D25 | TOUT |
|      |     |     |          |           |     | SPI2_MIS |     |     |          |         |     |     |         | EVEN |
| PI2  | -   | -   | -        | TIM8_CH4  | -   |          | -   | -   | -        | -       | -   | -   | FMC_D26 |      |
|      |     |     |          |           |     | O        |     |     |          |         |     |     |         | TOUT |
Pinouts and pin description
SPI2_MO
EVEN
Port I PI3 - - - TIM8_ETR - SI/I2S2_S - - - - - - FMC_D27 TOUT
D
|     |     |     |     |           |     |     |     |     |     |     | SAI2_MCK  |     | FMC_NBL | EVEN |
| --- | --- | --- | --- | --------- | --- | --- | --- | --- | --- | --- | --------- | --- | ------- | ---- |
| PI4 | -   | -   | -   | TIM8_BKIN | -   | -   | -   | -   | -   | -   |           | -   |         |      |
|     |     |     |     |           |     |     |     |     |     |     | _A        |     | 2       | TOUT |
|     |     |     |     |           |     |     |     |     |     |     | SAI2_SCK_ |     | FMC_NBL | EVEN |
| PI5 | -   | -   | -   | TIM8_CH1  | -   | -   | -   | -   | -   | -   | A         | -   | 3       | TOUT |
EVEN
| PI6 | -   | -   | -   | TIM8_CH2 | -   | -   | -   | -   | -   | -   | SAI2_SD_A | -   | FMC_D28 |     |
| --- | --- | --- | --- | -------- | --- | --- | --- | --- | --- | --- | --------- | --- | ------- | --- |
TOUT
95/229

96/229 Table 12.  STM32F722xx and STM32F723xx alternate function mapping (continued) Pinouts and pin description
|     |      | AF0 | AF1 | AF2 | AF3         | AF4        | AF5        | AF6        | AF7         | AF8        | AF9        | AF10      | AF11 | AF12    | AF15 |
| --- | ---- | --- | --- | --- | ----------- | ---------- | ---------- | ---------- | ----------- | ---------- | ---------- | --------- | ---- | ------- | ---- |
|     |      |     |     |     |             |            | SPI1/I2S1/ | SPI2/I2S2/ | SPI2/I2S2/S |            | CAN1/TIM1  | SAI2/QUAD |      | UART7/F |      |
|     | Port |     |     |     |             |            |            | SPI3/I2S3/ |             | SAI2/USART | 2/13/14/QU | SPI/SDMM  |      |         |      |
|     |      |     |     |     | TIM8/9/10/1 | I2C1/2/3/U | SPI2/I2S2/ |            | PI3/I2S3/US |            |            |           |      | MC/SDM  |      |
SYS TIM1/2 TIM3/4/5 SPI3/I2S3/ 6/UART4/5/7/ ADSPI/ C2/OTG2_ SDMMC2 SYS
|     |     |     |     |     | 1/LPTIM1 | SART1 | SPI3/I2S3/ | SAI1/ | ART1/2/3/UA | 8/OTG1_FS | FMC/    | HS/OTG1_ |     | MC1/    |     |
| --- | --- | --- | --- | --- | -------- | ----- | ---------- | ----- | ----------- | --------- | ------- | -------- | --- | ------- | --- |
|     |     |     |     |     |          |       | SPI4/5     |       | RT5         |           |         |          |     | OTG2_FS |     |
|     |     |     |     |     |          |       |            | UART4 |             |           | OTG2_HS | FS       |     |         |     |
EVEN
|     | PI7 | -   | -   | -   | TIM8_CH3 | -   | -   | -   | -   | -   | -   | SAI2_FS_A | -   | FMC_D29 |     |
| --- | --- | --- | --- | --- | -------- | --- | --- | --- | --- | --- | --- | --------- | --- | ------- | --- |
TOUT
EVEN
|     | PI8 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
TOUT
|     | PI9 | -   | -   | -   | -   | -   | -   | -   | -   | UART4_RX | CAN1_RX | -   | -   | FMC_D30 | EVEN |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | -------- | ------- | --- | --- | ------- | ---- |
TOUT
EVEN
|     | PI10 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | FMC_D31 |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- |
TOUT
|        |      |     |     |     |     |     |     |     |     |     |     | OTG_HS_U |     |     | EVEN |
| ------ | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | -------- | --- | --- | ---- |
| Port I | PI11 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | LPI_DIR  | -   | -   | TOUT |
DocID029808 Rev 3
EVEN
|     | PI12 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
TOUT
EVEN
|     | PI13 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
TOUT
|     | PI14 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | EVEN |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
TOUT
EVEN
|     | PI15 | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   | -   |     |
| --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
TOUT
STM32F722xx STM32F723xx

STM32F722xx STM32F723xx Memory mapping
4 Memory mapping
The memory map is shown in Figure 24.
Figure 24. Memory map
(cid:53)(cid:72)(cid:86)(cid:72)(cid:85)(cid:89)(cid:72)(cid:71) (cid:19)(cid:91)(cid:40)(cid:19)(cid:20)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:41)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:38)(cid:82)(cid:85)(cid:87)(cid:72)(cid:91)(cid:16)(cid:48)(cid:26)(cid:3)(cid:76)(cid:81)(cid:87)(cid:72)(cid:85)(cid:81)(cid:68)(cid:79)(cid:3)
(cid:19)(cid:91)(cid:40)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:40)(cid:19)(cid:19)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:83)(cid:72)(cid:85)(cid:76)(cid:83)(cid:75)(cid:72)(cid:85)(cid:68)(cid:79)(cid:86)
(cid:36)(cid:43)(cid:37)(cid:22) (cid:19)(cid:91)(cid:25)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:39)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:53)(cid:72)(cid:86)(cid:72)(cid:85)(cid:89)(cid:72)(cid:71) (cid:19)(cid:91)(cid:24)(cid:19)(cid:19)(cid:25)(cid:3)(cid:19)(cid:38)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:24)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:19)(cid:91)(cid:24)(cid:19)(cid:19)(cid:25)(cid:3)(cid:19)(cid:37)(cid:41)(cid:41)
(cid:19)(cid:91)(cid:41)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41) (cid:24)(cid:20)(cid:21)(cid:16)(cid:48)(cid:69)(cid:92)(cid:87)(cid:72) (cid:36)(cid:43)(cid:37)(cid:21)
(cid:37)(cid:79)(cid:82)(cid:70)(cid:78)(cid:3)(cid:26)
(cid:38)(cid:82)(cid:85)(cid:87)(cid:72)(cid:91)(cid:16)(cid:48)(cid:26) (cid:19)(cid:91)(cid:24)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)
(cid:44)(cid:81)(cid:87)(cid:72)(cid:85)(cid:81)(cid:68)(cid:79)(cid:3) (cid:53)(cid:72)(cid:86)(cid:72)(cid:85)(cid:89)(cid:72)(cid:71) (cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:27)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:23)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:19)(cid:91)(cid:40)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19) (cid:83)(cid:72)(cid:85)(cid:76)(cid:83)(cid:75)(cid:72)(cid:85)(cid:68)(cid:79)(cid:86) (cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:26)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:19)(cid:91)(cid:39)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:24)(cid:20)(cid:21)(cid:16)(cid:48)(cid:69)(cid:92)(cid:87)(cid:72)
(cid:37)(cid:79)(cid:82)(cid:70)(cid:78)(cid:3)(cid:25)
(cid:41)(cid:48)(cid:38)
(cid:19)(cid:91)(cid:39)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)
(cid:19)(cid:91)(cid:38)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41) (cid:36)(cid:43)(cid:37)(cid:20)
(cid:24)(cid:20)(cid:21)(cid:16)(cid:48)(cid:69)(cid:92)(cid:87)(cid:72)
(cid:37)(cid:79)(cid:82)(cid:70)(cid:78)(cid:3)(cid:24)
(cid:41)(cid:48)(cid:38)
(cid:19)(cid:91)(cid:38)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)
(cid:19)(cid:91)(cid:28)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:24)(cid:20)(cid:21)(cid:16)(cid:48)(cid:69)(cid:92)(cid:87)(cid:72)
(cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:21)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)
(cid:37)(cid:79)(cid:82)(cid:70)(cid:78)(cid:3)(cid:23)
(cid:52)(cid:88)(cid:68)(cid:71)(cid:16)(cid:54)(cid:51)(cid:44)(cid:3)(cid:68)(cid:81)(cid:71) (cid:53)(cid:72)(cid:86)(cid:72)(cid:85)(cid:89)(cid:72)(cid:71) (cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:20)(cid:3)(cid:25)(cid:38)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:20)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:3)(cid:41)(cid:48)(cid:38)(cid:3)(cid:69)(cid:68)(cid:81)(cid:78)(cid:3)(cid:22)(cid:3)(cid:3) (cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:20)(cid:3)(cid:25)(cid:37)(cid:41)(cid:41)
(cid:19)(cid:91)(cid:27)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)
(cid:19)(cid:91)(cid:26)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:24)(cid:20)(cid:21)(cid:16)(cid:48)(cid:69)(cid:92)(cid:87)(cid:72)
(cid:37)(cid:79)(cid:82)(cid:70)(cid:78)(cid:3)(cid:22)
(cid:41)(cid:48)(cid:38)(cid:3)(cid:69)(cid:68)(cid:81)(cid:78)(cid:3)(cid:20)(cid:3)(cid:87)(cid:82)(cid:3)
(cid:69)(cid:68)(cid:81)(cid:78)(cid:3)(cid:21)
(cid:19)(cid:91)(cid:25)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)
(cid:19)(cid:91)(cid:24)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:36)(cid:51)(cid:37)(cid:21)
(cid:24)(cid:20)(cid:21)(cid:16)(cid:48)(cid:69)(cid:92)(cid:87)(cid:72)
(cid:37)(cid:79)(cid:82)(cid:70)(cid:78)(cid:3)(cid:21)
(cid:51)(cid:72)(cid:85)(cid:76)(cid:83)(cid:75)(cid:72)(cid:85)(cid:68)(cid:79)(cid:86)
(cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)
(cid:19)(cid:91)(cid:22)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:24)(cid:20)(cid:21)(cid:16)(cid:48)(cid:69)(cid:92)(cid:87)(cid:72)
(cid:37)(cid:79)(cid:82)(cid:70)(cid:78)(cid:3)(cid:20)
(cid:54)(cid:53)(cid:36)(cid:48) (cid:53)(cid:72)(cid:86)(cid:72)(cid:85)(cid:89)(cid:72)(cid:71) (cid:19)(cid:91)(cid:21)(cid:19)(cid:19)(cid:23)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:22)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:20)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)
(cid:19) (cid:19) (cid:91) (cid:91) (cid:20) (cid:21) (cid:41) (cid:19) (cid:41) (cid:19) (cid:41) (cid:19) (cid:3) (cid:3) (cid:41) (cid:19) (cid:41) (cid:19) (cid:41) (cid:19) (cid:41) (cid:19) (cid:54)(cid:53)(cid:36)(cid:48)(cid:21)(cid:3)(cid:11)(cid:20)(cid:25)(cid:3)(cid:46)(cid:37)(cid:12) (cid:19)(cid:91)(cid:21)(cid:19)(cid:19)(cid:22)(cid:3)(cid:38)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:21)(cid:19)(cid:19)(cid:22)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41) (cid:53)(cid:72)(cid:86)(cid:72)(cid:85)(cid:89)(cid:72)(cid:71) (cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:19)(cid:3)(cid:27)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:19)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:19)(cid:3)(cid:26)(cid:41)(cid:41)(cid:41)
(cid:24)(cid:20)(cid:21)(cid:16)(cid:48)(cid:69)(cid:92)(cid:87)(cid:72) (cid:54)(cid:53)(cid:36)(cid:48)(cid:20)(cid:3)(cid:11)(cid:20)(cid:26)(cid:25)(cid:3)(cid:46)(cid:37)(cid:12) (cid:19)(cid:91)(cid:21)(cid:19)(cid:19)(cid:20)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:21)(cid:19)(cid:19)(cid:22)(cid:3)(cid:37)(cid:41)(cid:41)(cid:41)
(cid:37)(cid:79)(cid:82)(cid:70)(cid:78)(cid:3)(cid:19)
(cid:39)(cid:55)(cid:38)(cid:48)(cid:3)(cid:11)(cid:25)(cid:23)(cid:3)(cid:46)(cid:37)(cid:12) (cid:19)(cid:91)(cid:21)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:21)(cid:19)(cid:19)(cid:19)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:19)(cid:91)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)
(cid:53)(cid:72)(cid:86)(cid:72)(cid:85)(cid:89)(cid:72)(cid:71) (cid:19)(cid:91)(cid:20)(cid:41)(cid:41)(cid:41)(cid:3)(cid:19)(cid:19)(cid:21)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:20)(cid:41)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:50)(cid:83)(cid:87)(cid:76)(cid:82)(cid:81)(cid:3)(cid:37)(cid:92)(cid:87)(cid:72)(cid:86) (cid:19)(cid:91)(cid:20)(cid:41)(cid:41)(cid:41)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:20)(cid:41)(cid:41)(cid:41)(cid:3)(cid:19)(cid:19)(cid:20)(cid:41)
(cid:53)(cid:72)(cid:86)(cid:72)(cid:85)(cid:89)(cid:72)(cid:71) (cid:19)(cid:91)(cid:19)(cid:27)(cid:19)(cid:27)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:20)(cid:41)(cid:41)(cid:40)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:36)(cid:51)(cid:37)(cid:20)
(cid:41)(cid:79)(cid:68)(cid:86)(cid:75)(cid:3)(cid:80)(cid:72)(cid:80)(cid:82)(cid:85)(cid:92)(cid:3)(cid:82)(cid:81)(cid:3)(cid:36)(cid:59)(cid:44)(cid:48)(cid:3)
(cid:19)(cid:91)(cid:19)(cid:27)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:19)(cid:27)(cid:19)(cid:26)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)(cid:3)(cid:3)
(cid:76)(cid:81)(cid:87)(cid:72)(cid:85)(cid:73)(cid:68)(cid:70)(cid:72)
(cid:53)(cid:72)(cid:86)(cid:72)(cid:85)(cid:89)(cid:72)(cid:71) (cid:19)(cid:91)(cid:19)(cid:19)(cid:21)(cid:27)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:19)(cid:26)(cid:41)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:41)(cid:79)(cid:68)(cid:86)(cid:75)(cid:3)(cid:80)(cid:72)(cid:80)(cid:82)(cid:85)(cid:92)(cid:3)(cid:82)(cid:81)(cid:3)(cid:44)(cid:55)(cid:38)(cid:48)(cid:3)
(cid:19)(cid:91)(cid:19)(cid:19)(cid:21)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:19)(cid:19)(cid:21)(cid:26)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:76)(cid:81)(cid:87)(cid:72)(cid:85)(cid:73)(cid:68)(cid:70)(cid:72)
(cid:53)(cid:72)(cid:86)(cid:72)(cid:85)(cid:89)(cid:72)(cid:71) (cid:19)(cid:91)(cid:19)(cid:19)(cid:20)(cid:20)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:19)(cid:19)(cid:20)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:54)(cid:92)(cid:86)(cid:87)(cid:72)(cid:80)(cid:3)(cid:80)(cid:72)(cid:80)(cid:82)(cid:85)(cid:92) (cid:19)(cid:91)(cid:19)(cid:19)(cid:20)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:19)(cid:19)(cid:20)(cid:19)(cid:3)(cid:40)(cid:39)(cid:37)(cid:41)
(cid:19)(cid:91)(cid:23)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)
(cid:53)(cid:72)(cid:86)(cid:72)(cid:85)(cid:89)(cid:72)(cid:71) (cid:19)(cid:91)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:23)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:19)(cid:19)(cid:19)(cid:41)(cid:3)(cid:41)(cid:41)(cid:41)(cid:41)
(cid:44)(cid:55)(cid:38)(cid:48)(cid:3)(cid:53)(cid:36)(cid:48) (cid:19)(cid:91)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:16)(cid:3)(cid:19)(cid:91)(cid:19)(cid:19)(cid:19)(cid:19)(cid:3)(cid:22)(cid:41)(cid:41)(cid:41)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:20)(cid:19)(cid:19)(cid:25)(cid:57)(cid:20)
DocID029808 Rev 3 97/229
101

Memory mapping STM32F722xx STM32F723xx

Table 13. STM32F722xx and STM32F723xx register boundary
addresses(1)
| Bus | Boundary address          |          | Peripheral |
| --- | ------------------------- | -------- | ---------- |
|     | 0xE00F FFFF - 0xFFFF FFFF | Reserved |            |
Cortex-M7 0xE000 0000 - 0xE00F FFFF Cortex-M7 internal peripherals
|      | 0xD000 0000 - 0xDFFF FFFF | FMC bank 6                |     |
| ---- | ------------------------- | ------------------------- | --- |
|      | 0xC000 0000 - 0xCFFF FFFF | FMC bank 5                |     |
|      | 0xA000 2000 - 0xBFFF FFFF | Reserved                  |     |
|      | 0xA000 1000 - 0xA000 1FFF | Quad-SPI control register |     |
| AHB3 | 0xA000 0000- 0xA000 0FFF  | FMC control register      |     |
|      | 0x9000 0000 - 0x9FFF FFFF | Quad-SPI                  |     |
|      | 0x8000 0000 - 0x8FFF FFFF | FMC bank 3                |     |
|      | 0x7000 0000 - 0x7FFF FFFF | FMC bank 2                |     |
|      | 0x6000 0000 - 0x6FFF FFFF | FMC bank 1                |     |
|      | 0x5006 0C00- 0x5FFF FFFF  | Reserved                  |     |
|      | 0x5006 0800 - 0x5006 0BFF | RNG                       |     |
| AHB2 | 0x5004 0000 - 0x5006 07FF | Reserved                  |     |
|      | 0x5000 0000 - 0x5003 FFFF | USB OTG FS                |     |
98/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Memory mapping
Table 13. STM32F722xx and STM32F723xx register boundary
addresses(1) (continued)
Bus Boundary address Peripheral
0x4008 0000- 0x4FFF FFFF Reserved
0x4004 0000 - 0x4007 FFFF USB OTG HS
0x4002 6800- 0x4003 FFFF Reserved
0x4002 6400 - 0x4002 67FF DMA2
0x4002 6000 - 0x4002 63FF DMA1
0x4002 5000 - 0X4002 5FFF Reserved
0x4002 4000 - 0x4002 4FFF BKPSRAM
0x4002 3C00 - 0x4002 3FFF Flash interface register
0x4002 3800 - 0x4002 3BFF RCC
0X4002 3400 - 0X4002 37FF Reserved
0x4002 3000 - 0x4002 33FF CRC
AHB1
0x4002 2400 - 0x4002 2FFF Reserved
0x4002 2000 - 0x4002 23FF GPIOI
0x4002 1C00 - 0x4002 1FFF GPIOH
0x4002 1800 - 0x4002 1BFF GPIOG
0x4002 1400 - 0x4002 17FF GPIOF
0x4002 1000 - 0x4002 13FF GPIOE
0X4002 0C00 - 0x4002 0FFF GPIOD
0x4002 0800 - 0x4002 0BFF GPIOC
0x4002 0400 - 0x4002 07FF GPIOB
0x4002 0000 - 0x4002 03FF GPIOA
DocID029808 Rev 3 99/229
101

Memory mapping STM32F722xx STM32F723xx
Table 13. STM32F722xx and STM32F723xx register boundary
addresses(1) (continued)
Bus Boundary address Peripheral
0x4001 8000- 0x4001 FFFF Reserved
0x4001 7C00 - 0x4001 7FFF OTG PHY HS Controller(2)
0x4001 6000- 0x4001 7BFF Reserved
0x4001 5C00 - 0x4001 5FFF SAI2
0x4001 5800 - 0x4001 5BFF SAI1
0x4001 5400 - 0x4001 57FF Reserved
0x4001 5000 - 0x4001 53FF SPI5
0x4001 4C00 - 0x4001 4FFF Reserved
0x4001 4800 - 0x4001 4BFF TIM11
0x4001 4400 - 0x4001 47FF TIM10
0x4001 4000 - 0x4001 43FF TIM9
0x4001 3C00 - 0x4001 3FFF EXTI
0x4001 3800 - 0x4001 3BFF SYSCFG
APB2
0x4001 3400 - 0x4001 37FF SPI4
0x4001 3000 - 0x4001 33FF SPI1/I2S1
0x4001 2C00 - 0x4001 2FFF SDMMC1
0x4001 2400 - 0x4001 2BFF Reserved
0x4001 2000 - 0x4001 23FF ADC1 - ADC2 - ADC3
0x4001 1C00- 0x4001 1FFF SDMMC2
0x4001 1800 - 0x4001 1BFF Reserved
0x4001 1400 - 0x4001 17FF USART6
0x4001 1000 - 0x4001 13FF USART1
0x4001 0800 - 0x4001 0FFF Reserved
0x4001 0400 - 0x4001 07FF TIM8
0x4001 0000 - 0x4001 03FF TIM1
100/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Memory mapping
Table 13. STM32F722xx and STM32F723xx register boundary
addresses(1) (continued)
| Bus  | Boundary address          |                     | Peripheral |
| ---- | ------------------------- | ------------------- | ---------- |
|      | 0x4000 8000- 0x4000 FFFF  | Reserved            |            |
|      | 0x4000 7C00 - 0x4000 7FFF | UART8               |            |
|      | 0x4000 7800 - 0x4000 7BFF | UART7               |            |
|      | 0x4000 7400 - 0x4000 77FF | DAC                 |            |
|      | 0x4000 7000 - 0x4000 73FF | PWR                 |            |
|      | 0x4000 6800 - 0x4000 6FFF | Reserved            |            |
|      | 0x4000 6400 - 0x4000 67FF | CAN1                |            |
|      | 0x4000 6000 - 0x4000 63FF | Reserved            |            |
|      | 0x4000 5C00 - 0x4000 5FFF | I2C3                |            |
|      | 0x4000 5800 - 0x4000 5BFF | I2C2                |            |
|      | 0x4000 5400 - 0x4000 57FF | I2C1                |            |
|      | 0x4000 5000 - 0x4000 53FF | UART5               |            |
|      | 0x4000 4C00 - 0x4000 4FFF | UART4               |            |
|      | 0x4000 4800 - 0x4000 4BFF | USART3              |            |
|      | 0x4000 4400 - 0x4000 47FF | USART2              |            |
|      | 0x4000 4000 - 0x4000 43FF | Reserved            |            |
| APB1 | 0x4000 3C00 - 0x4000 3FFF | SPI3 / I2S3         |            |
|      | 0x4000 3800 - 0x4000 3BFF | SPI2 / I2S2         |            |
|      | 0x4000 3400 - 0x4000 37FF | Reserved            |            |
|      | 0x4000 3000 - 0x4000 33FF | IWDG                |            |
|      | 0x4000 2C00 - 0x4000 2FFF | WWDG                |            |
|      | 0x4000 2800 - 0x4000 2BFF | RTC & BKP Registers |            |
|      | 0x4000 2400 - 0x4000 27FF | LPTIM1              |            |
|      | 0x4000 2000 - 0x4000 23FF | TIM14               |            |
|      | 0x4000 1C00 - 0x4000 1FFF | TIM13               |            |
|      | 0x4000 1800 - 0x4000 1BFF | TIM12               |            |
|      | 0x4000 1400 - 0x4000 17FF | TIM7                |            |
|      | 0x4000 1000 - 0x4000 13FF | TIM6                |            |
|      | 0x4000 0C00 - 0x4000 0FFF | TIM5                |            |
|      | 0x4000 0800 - 0x4000 0BFF | TIM4                |            |
|      | 0x4000 0400 - 0x4000 07FF | TIM3                |            |
|      | 0x4000 0000 - 0x4000 03FF | TIM2                |            |
1. The gray color is used for reserved Flash memory addresses.
2. Only for the STM32F723xx devices.
DocID029808 Rev 3 101/229
101

Electrical characteristics STM32F722xx STM32F723xx
5 Electrical characteristics
5.1 Parameter conditions
Unless otherwise specified, all voltages are referenced to V .
SS
5.1.1 Minimum and maximum values
Unless otherwise specified the minimum and maximum values are guaranteed in the worst
conditions of ambient temperature, supply voltage and frequencies by tests in production on
100% of the devices with an ambient temperature at T = 25 °C and T = T max (given by
A A A
the selected temperature range).
Data based on characterization results, design simulation and/or technology characteristics
are indicated in the table footnotes. Based on characterization, the minimum and maximum
values refer to sample tests and represent the mean value plus or minus three times the
standard deviation (mean±3σ).
5.1.2 Typical values
Unless otherwise specified, typical data are based on T = 25 °C, V = 3.3 V (for the
A DD
1.7 V ≤ V ≤ 3.6 V voltage range). They are given only as design guidelines and are not
DD
tested.
Typical ADC accuracy values are determined by characterization of a batch of samples from
a standard diffusion lot over the full temperature range, where 95% of the devices have an
error less than or equal to the value indicated (mean±2σ).
5.1.3 Typical curves
Unless otherwise specified, all typical curves are given only as design guidelines and are
not tested.
5.1.4 Loading capacitor
The loading conditions used for pin parameter measurement are shown in Figure 25.
5.1.5 Pin input voltage
The input voltage measurement on a pin of the device is described in Figure 26.
Figure 25. Pin loading conditions Figure 26. Pin input voltage
(cid:45)(cid:35)(cid:53)(cid:0)(cid:80)(cid:73)(cid:78)
(cid:45)(cid:35)(cid:53)(cid:0)(cid:80)(cid:73)(cid:78)
(cid:35)(cid:0)(cid:29)(cid:0)(cid:21)(cid:16)(cid:0)(cid:80)(cid:38) (cid:54)(cid:41)(cid:46)
(cid:45)(cid:51)(cid:17)(cid:25)(cid:16)(cid:17)(cid:17)(cid:54)(cid:18) (cid:45)(cid:51)(cid:17)(cid:25)(cid:16)(cid:17)(cid:16)(cid:54)(cid:18)
102/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
5.1.6  Power supply scheme
Figure 27. STM32F722xx power supply scheme
(cid:57)(cid:37)(cid:36)(cid:55)
(cid:37)(cid:68)(cid:70)(cid:78)(cid:88)(cid:83)(cid:3)(cid:70)(cid:76)(cid:85)(cid:70)(cid:88)(cid:76)(cid:87)(cid:85)(cid:92)
|     | (cid:57)(cid:37)(cid:36)(cid:55)(cid:3)(cid:32) |     | (cid:51)(cid:82)(cid:90)(cid:72)(cid:85)(cid:3)(cid:86)(cid:90)(cid:76)(cid:87)(cid:70)(cid:75) | (cid:11)(cid:50)(cid:54)(cid:38)(cid:22)(cid:21)(cid:46)(cid:15)(cid:53)(cid:55)(cid:38)(cid:15) |
| --- | ----------------------------------------------- | --- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
(cid:58)(cid:68)(cid:78)(cid:72)(cid:88)(cid:83)(cid:3)(cid:79)(cid:82)(cid:74)(cid:76)(cid:70)
(cid:20)(cid:17)(cid:25)(cid:24)(cid:3)(cid:87)(cid:82)(cid:3)(cid:22)(cid:17)(cid:25)(cid:57)
(cid:37)(cid:68)(cid:70)(cid:78)(cid:88)(cid:83)(cid:3)(cid:85)(cid:72)(cid:74)(cid:76)(cid:86)(cid:87)(cid:72)(cid:85)(cid:86)(cid:15)
(cid:69)(cid:68)(cid:70)(cid:78)(cid:88)(cid:83)(cid:3)(cid:53)(cid:36)(cid:48)(cid:12)
|     |     |     | (cid:50)(cid:56)(cid:55) (cid:85)(cid:72)(cid:87)(cid:73)(cid:76)(cid:75)(cid:86)(cid:3)(cid:79)(cid:72)(cid:89)(cid:72)(cid:47) |     |
| --- | --- | --- | -------------------------------------------------------------------------------------------------------------------------------- | --- |
(cid:44)(cid:50)
(cid:42)(cid:51)(cid:44)(cid:18)(cid:50)(cid:86)
(cid:47)(cid:82)(cid:74)(cid:76)(cid:70)
|     | (cid:57) |     | (cid:44)(cid:49) |     |
| --- | -------- | --- | ---------------- | --- |
(cid:39)(cid:39)(cid:54)(cid:39)(cid:48)(cid:48)(cid:38)
(cid:57)
(cid:39)(cid:39)(cid:54)(cid:39)(cid:48)(cid:48)(cid:38)
(cid:20)(cid:19)(cid:19)(cid:3)(cid:81)(cid:41)
(cid:85)(cid:72)(cid:87)(cid:73)(cid:76)(cid:75)(cid:86)(cid:3)(cid:79)(cid:72)(cid:89)(cid:72)(cid:47)
|     | (cid:14)(cid:3)(cid:20)(cid:3)(cid:151)(cid:41) |     | (cid:50)(cid:56)(cid:55) |     |
| --- | ----------------------------------------------- | --- | ------------------------ | --- |
(cid:51)(cid:42)(cid:62)(cid:28)(cid:17)(cid:17)(cid:20)(cid:21)(cid:64)(cid:15)(cid:3)(cid:51)(cid:39)(cid:62)(cid:25)(cid:15)(cid:26)(cid:64)
(cid:44)(cid:50)
(cid:47)(cid:82)(cid:74)(cid:76)(cid:70)
|     |     |     | (cid:44)(cid:49) | (cid:46)(cid:72)(cid:85)(cid:81)(cid:72)(cid:79)(cid:3)(cid:79)(cid:82)(cid:74)(cid:76)(cid:70)(cid:3)(cid:3) |
| --- | --- | --- | ---------------- | ------------------------------------------------------------------------------------------------------------- |
(cid:57) (cid:11)(cid:38)(cid:51)(cid:56)(cid:15)(cid:3)(cid:3)
|     |     | (cid:38) (cid:36) (cid:51) (cid:66) (cid:20)          |     | (cid:71)(cid:76)(cid:74)(cid:76)(cid:87)(cid:68)(cid:79)(cid:3)(cid:3) |
| --- | --- | ----------------------------------------------------- | --- | ---------------------------------------------------------------------- |
|     |     | (cid:57) (cid:38) (cid:36) (cid:51) (cid:66) (cid:21) |     |                                                                        |
(cid:21)(cid:3)(cid:238)(cid:3)(cid:21)(cid:17)(cid:21)(cid:3)(cid:151)(cid:41) (cid:9)(cid:3)(cid:53)(cid:36)(cid:48)(cid:12)(cid:3)(cid:3)
(cid:57)(cid:39)(cid:39)
|     |                                                                                               | (cid:57)(cid:39)(cid:39)                                                                         | (cid:57)(cid:82)(cid:79)(cid:87)(cid:68)(cid:74)(cid:72)                 |     |
| --- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------ | --- |
|     |                                                                                               | (cid:20)(cid:18)(cid:21)(cid:18)(cid:17)(cid:17)(cid:17)(cid:20)(cid:20)(cid:18)(cid:20)(cid:21) | (cid:85)(cid:72)(cid:74)(cid:88)(cid:79)(cid:68)(cid:87)(cid:82)(cid:85) |     |
|     | (cid:20)(cid:21)(cid:3)(cid:238)(cid:3)(cid:20)(cid:3)(cid:19)(cid:19)(cid:3)(cid:81)(cid:41) | (cid:57)(cid:54)(cid:54)(cid:3)(cid:3)                                                           |                                                                          |     |
(cid:14)(cid:3)(cid:20)(cid:3)(cid:238)(cid:3)(cid:23)(cid:17)(cid:26)(cid:3)(cid:151)(cid:41)
(cid:20)(cid:18)(cid:21)(cid:18)(cid:17)(cid:17)(cid:17)(cid:20)(cid:20)(cid:18)(cid:20)(cid:21)
(cid:41)(cid:79)(cid:68)(cid:86)(cid:75)(cid:3)(cid:80)(cid:72)(cid:80)(cid:82)(cid:85)(cid:92)
(cid:37)(cid:60)(cid:51)(cid:36)(cid:54)(cid:54)(cid:66)(cid:53)(cid:40)(cid:42)
(cid:57)(cid:39)(cid:39)(cid:56)(cid:54)(cid:37)
(cid:57)(cid:39)(cid:39)(cid:56)(cid:54)(cid:37)
(cid:50)(cid:55)(cid:42)(cid:3)(cid:41)(cid:54)
(cid:3)(cid:51)(cid:43)(cid:60)
(cid:20)(cid:19)(cid:19)(cid:3)(cid:81)(cid:41)
(cid:14)(cid:3)(cid:20)(cid:3)(cid:151)(cid:41)
(cid:53)(cid:72)(cid:86)(cid:72)(cid:87)(cid:3)(cid:3)
|     |     | (cid:51)(cid:39)(cid:53)(cid:66)(cid:50)(cid:49) | (cid:70)(cid:82)(cid:81)(cid:87)(cid:85)(cid:82)(cid:79)(cid:79)(cid:72)(cid:85) |     |
| --- | --- | ------------------------------------------------ | -------------------------------------------------------------------------------- | --- |
(cid:57)(cid:39)(cid:39)
(cid:57)(cid:39)(cid:39)(cid:36)
(cid:57)(cid:53)(cid:40)(cid:41)
(cid:57)(cid:53)(cid:40)(cid:41)(cid:14)
|     | (cid:20)(cid:19)(cid:19)(cid:3)(cid:81)(cid:41)                                                 |                                          |                          | (cid:36)(cid:81)(cid:68)(cid:79)(cid:82)(cid:74)(cid:29)(cid:3)(cid:3)  |
| --- | ----------------------------------------------------------------------------------------------- | ---------------------------------------- | ------------------------ | ----------------------------------------------------------------------- |
|     | (cid:20)(cid:19)(cid:19)(cid:3)(cid:81)(cid:41)                                                 | (cid:57)(cid:53)(cid:40)(cid:41)(cid:16) | (cid:36)(cid:39)(cid:38) |                                                                         |
|     | (cid:14)(cid:3)(cid:20)(cid:3)(cid:151)(cid:41) (cid:14)(cid:3)(cid:20)(cid:3)(cid:151)(cid:41) |                                          |                          | (cid:53)(cid:38)(cid:86)(cid:15)(cid:3)(cid:51)(cid:47)(cid:47)(cid:15) |
(cid:17)(cid:17)(cid:17)
(cid:57)(cid:54)(cid:54)(cid:36)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:21)(cid:19)(cid:26)(cid:25)(cid:57)(cid:21)
1. The two 2.2 µF ceramic capacitors should be replaced by two 100 nF decoupling capacitors when the
voltage regulator is OFF.
| 2. The 4.7 µF ceramic capacitor must be connected to one of the V |           |      | DD  |  pin. |
| ----------------------------------------------------------------- | --------- | ---- | --- | ----- |
| 3. V                                                              | =V  and V | =V . |     |       |
| DDA                                                               | DD SSA    | SS   |     |       |
DocID029808 Rev 3 103/229
201

Electrical characteristics STM32F722xx STM32F723xx
Figure 28. STM32F723xx power supply scheme
(cid:57)(cid:37)(cid:36)(cid:55)
(cid:37)(cid:68)(cid:70)(cid:78)(cid:88)(cid:83)(cid:3)(cid:70)(cid:76)(cid:85)(cid:70)(cid:88)(cid:76)(cid:87)(cid:85)(cid:92)
(cid:57)(cid:37)(cid:36)(cid:55)(cid:3)(cid:32) (cid:11)(cid:50)(cid:54)(cid:38)(cid:22)(cid:21)(cid:46)(cid:15)(cid:53)(cid:55)(cid:38)(cid:15)
(cid:58)(cid:68)(cid:78)(cid:72)(cid:88)(cid:83)(cid:3)(cid:79)(cid:82)(cid:74)(cid:76)(cid:70)
(cid:20)(cid:17)(cid:25)(cid:24)(cid:3)(cid:87)(cid:82)(cid:3)(cid:22)(cid:17)(cid:25)(cid:57)
(cid:37)(cid:68)(cid:70)(cid:78)(cid:88)(cid:83)(cid:3)(cid:85)(cid:72)(cid:74)(cid:76)(cid:86)(cid:87)(cid:72)(cid:85)(cid:86)(cid:15)
(cid:69)(cid:68)(cid:70)(cid:78)(cid:88)(cid:83)(cid:3)(cid:53)(cid:36)(cid:48)(cid:12)
(cid:46)(cid:72)(cid:85)(cid:81)(cid:72)(cid:79)(cid:3)(cid:79)(cid:82)(cid:74)(cid:76)(cid:70)(cid:3)(cid:3)
(cid:11)(cid:38)(cid:51)(cid:56)(cid:15)(cid:3)(cid:3)
(cid:71)(cid:76)(cid:74)(cid:76)(cid:87)(cid:68)(cid:79)(cid:3)(cid:3)
(cid:9)(cid:3)(cid:53)(cid:36)(cid:48)(cid:12)(cid:3)(cid:3)
(cid:115)(cid:24)(cid:24) (cid:57)(cid:82)(cid:79)(cid:87)(cid:68)(cid:74)(cid:72)
(cid:1005)(cid:876)(cid:1006)(cid:876)(cid:856)(cid:856)(cid:856)(cid:1005)(cid:1005)(cid:876)(cid:1005)(cid:1006)
(cid:85)(cid:72)(cid:74)(cid:88)(cid:79)(cid:68)(cid:87)(cid:82)(cid:85)
(cid:20)(cid:21)(cid:3)(cid:238)(cid:3)(cid:20)(cid:3)(cid:19)(cid:19)(cid:3)(cid:81)(cid:41)
(cid:14)(cid:3)(cid:20)(cid:3)(cid:238)(cid:3)(cid:23)(cid:17)(cid:26)(cid:3)(cid:151)(cid:41)
(cid:115)(cid:54)(cid:54)(cid:3)(cid:3)
(cid:1005)(cid:876)(cid:1006)(cid:876)(cid:856)(cid:856)(cid:856)(cid:1005)(cid:1005)(cid:876)(cid:1005)(cid:1006)
(cid:50)(cid:55)(cid:42)(cid:3)(cid:43)(cid:54)(cid:3)(cid:51)(cid:43)(cid:60)
(cid:3)(cid:89)(cid:82)(cid:79)(cid:87)(cid:68)(cid:74)(cid:72)(cid:3)
(cid:85)(cid:72)(cid:74)(cid:88)(cid:79)(cid:68)(cid:87)(cid:82)(cid:85)
(cid:57)(cid:39)(cid:39)(cid:20)(cid:21)(cid:50)(cid:55)(cid:42)(cid:43)(cid:54)
(cid:50)(cid:55)(cid:42)(cid:3)(cid:43)(cid:54)(cid:3)(cid:51)(cid:43)(cid:60)
(cid:21)(cid:17)(cid:21)(cid:3)(cid:151)(cid:41)
(cid:50)(cid:55)(cid:42)(cid:66)(cid:43)(cid:54)(cid:66)(cid:53)(cid:40)(cid:59)(cid:55)
(cid:53)(cid:72)(cid:86)(cid:72)(cid:87)(cid:3)(cid:3)
(cid:51)(cid:39)(cid:53)(cid:66)(cid:50)(cid:49) (cid:70)(cid:82)(cid:81)(cid:87)(cid:85)(cid:82)(cid:79)(cid:79)(cid:72)(cid:85)
(cid:57)(cid:39)(cid:39)
(cid:57)(cid:39)(cid:39)(cid:36)
(cid:57)(cid:53)(cid:40)(cid:41)
(cid:57)(cid:53)(cid:40)(cid:41)(cid:14)
(cid:20)(cid:19)(cid:19)(cid:3)(cid:81)(cid:41) (cid:36)(cid:81)(cid:68)(cid:79)(cid:82)(cid:74)(cid:29)(cid:3)(cid:3)
(cid:20)(cid:19)(cid:19)(cid:3)(cid:81)(cid:41) (cid:14)(cid:3)(cid:20)(cid:3)(cid:151)(cid:41) (cid:57)(cid:53)(cid:40)(cid:41)(cid:16) (cid:36)(cid:39)(cid:38) (cid:53)(cid:38)(cid:86)(cid:15)(cid:3)(cid:51)(cid:47)(cid:47)(cid:15)
(cid:14)(cid:3)(cid:20)(cid:3)(cid:151)(cid:41)
(cid:17)(cid:17)(cid:17)
(cid:57)(cid:54)(cid:54)(cid:36)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:21)(cid:19)(cid:25)(cid:28)(cid:57)(cid:20)
1. The V allows supplying the PHY FS in PA11/PA12 and the PHY HS on PB14/PB15.
DDUSB
104/229 DocID029808 Rev 3
(cid:85)(cid:72)(cid:87)(cid:73)(cid:76)(cid:75)(cid:86)(cid:3)(cid:79)(cid:72)(cid:89)(cid:72)(cid:47)
(cid:50)(cid:56)(cid:55)
(cid:44)(cid:50)
(cid:42)(cid:51)(cid:44)(cid:18)(cid:50)(cid:86) (cid:47)(cid:82)(cid:74)(cid:76)(cid:70)
(cid:44)(cid:49)
(cid:39)(cid:39)(cid:54)(cid:39)(cid:48)(cid:48)(cid:38)
(cid:50)(cid:56)(cid:55)
(cid:51)(cid:42)(cid:62)(cid:28)(cid:17)(cid:17)(cid:20)(cid:21)(cid:64)(cid:15)(cid:3)(cid:51)(cid:39)(cid:62)(cid:25)(cid:15)(cid:26)(cid:64)
(cid:44)(cid:50)
(cid:47)(cid:82)(cid:74)(cid:76)(cid:70)
(cid:44)(cid:49)
(cid:57)(cid:39)(cid:39)(cid:56)(cid:54)(cid:37)
(cid:57)(cid:39)(cid:39)(cid:56)(cid:54)(cid:37)
(cid:20)(cid:19)(cid:19)(cid:3)(cid:81)(cid:41)
(cid:14)(cid:3)(cid:20)(cid:3)(cid:151)(cid:41)
(cid:50)(cid:55)(cid:42)(cid:3)(cid:41)(cid:54)
(cid:3)(cid:51)(cid:43)(cid:60)
(cid:115)(cid:18)(cid:4)(cid:87)(cid:890)(cid:1005)
(cid:21)(cid:3)(cid:238)(cid:3)(cid:21)(cid:17)(cid:21)(cid:3)(cid:151)(cid:41)
(cid:115)(cid:18)(cid:4)(cid:87)(cid:890)(cid:1006)
(cid:57)(cid:39)(cid:39)
(cid:41)(cid:79)(cid:68)(cid:86)(cid:75)(cid:3)(cid:80)(cid:72)(cid:80)(cid:82)(cid:85)(cid:92)
(cid:37)(cid:60)(cid:51)(cid:36)(cid:54)(cid:54)(cid:66)(cid:53)(cid:40)(cid:42)
(cid:85)(cid:72)(cid:87)(cid:73)(cid:76)(cid:75)(cid:86)(cid:3)(cid:79)(cid:72)(cid:89)(cid:72)(cid:47)
(cid:57)
(cid:85)(cid:72)(cid:87)(cid:73)(cid:76)(cid:75)(cid:86)(cid:3)(cid:79)(cid:72)(cid:89)(cid:72)(cid:47)
(cid:51)(cid:82)(cid:90)(cid:72)(cid:85)(cid:3)(cid:86)(cid:90)(cid:76)(cid:87)(cid:70)(cid:75)
(cid:57)
(cid:39)(cid:39)(cid:54)(cid:39)(cid:48)(cid:48)(cid:38)
(cid:20)(cid:19)(cid:19)(cid:3)(cid:81)(cid:41)
(cid:14)(cid:3)(cid:20)(cid:3)(cid:151)(cid:41)
(cid:50)(cid:56)(cid:55)
(cid:51)(cid:36)(cid:62)(cid:20)(cid:20)(cid:15)(cid:20)(cid:21)(cid:64)(cid:15)(cid:3)(cid:51)(cid:37)(cid:62)(cid:20)(cid:23)(cid:15)(cid:20)(cid:24)(cid:64)
(cid:44)(cid:50)
(cid:47)(cid:82)(cid:74)(cid:76)(cid:70)
(cid:44)(cid:49)
(cid:22)(cid:3)(cid:46)(cid:82)(cid:75)(cid:80)(cid:3)(cid:14)(cid:18)(cid:16)(cid:20)(cid:8)

STM32F722xx STM32F723xx Electrical characteristics
2. The two 2.2 µF ceramic capacitors should be replaced by two 100 nF decoupling capacitors when the
voltage regulator is OFF.
| 3. The 4.7 µF ceramic capacitor must be connected to one of the V |           |      |     | DD  pin. |     |     |
| ----------------------------------------------------------------- | --------- | ---- | --- | -------- | --- | --- |
| 4. V                                                              | =V  and V | =V . |     |          |     |     |
| DDA                                                               | DD SSA    | SS   |     |          |     |     |
Caution: Each power supply pair (V /V , V /V  ...) must be decoupled with filtering ceramic
|     |     | DD SS | DDA SSA |     |     |     |
| --- | --- | ----- | ------- | --- | --- | --- |
capacitors as shown above. These capacitors must be placed as close as possible to, or
below, the appropriate pins on the underside of the PCB to ensure good operation of the
device. It is not recommended to remove filtering capacitors to reduce PCB size or cost.
This might cause incorrect operation of the device.
5.1.7  Current consumption measurement
Figure 29. Current consumption measurement scheme
(cid:44)(cid:39)(cid:39)(cid:66)(cid:57)(cid:37)(cid:36)(cid:55)
(cid:57)(cid:37)(cid:36)(cid:55)
(cid:44)(cid:39)(cid:39)
(cid:57)(cid:39)(cid:39)
(cid:57)(cid:39)(cid:39)(cid:36)
(cid:68)(cid:76)(cid:20)(cid:23)(cid:20)(cid:21)(cid:25)
5.2  Absolute maximum ratings
Stresses above the absolute maximum ratings listed in Table 14: Voltage characteristics,
Table 15: Current characteristics, and Table 16: Thermal characteristics may cause
permanent damage to the device. These are stress ratings only and functional operation of
the device at these conditions is not implied. Exposure to maximum rating conditions for
extended periods may affect device reliability. The device mission profile (application
conditions) is compliant with JEDEC JESD47 Qualification Standard. Extended mission
profiles are available on demand.

Table 14. Voltage characteristics
| Symbol |                                           |        | Ratings |           | Min  | Max Unit |
| ------ | ----------------------------------------- | ------ | ------- | --------- | ---- | -------- |
|        | External main supply voltage (including V |        |         | ,V        |      |          |
| V –V   |                                           |        |         | DDA  DD,  | −0.3 | 4.0      |
| DD     | SS V , V                                  | and V  | ) (1)   |           |      |          |
|        | BAT                                       | DDUSB  | DDSDMMC |           |      |          |
Input voltage on FT pins(2)
|     |     |     |     |     | V SS −0.3 | V DD +4.0 |
| --- | --- | --- | --- | --- | --------- | --------- |
V
|     | Input voltage on TTa pins |     |     |     | V −0.3 | 4.0 |
| --- | ------------------------- | --- | --- | --- | ------ | --- |
SS
V
IN
|     | Input voltage on any other pin |     |     |     | V SS −0.3 | 4.0 |
| --- | ------------------------------ | --- | --- | --- | --------- | --- |
|     | Input voltage on BOOT pin      |     |     |     | V         | 9.0 |
SS
|     |     | DocID029808 Rev 3 |     |     |     | 105/229 |
| --- | --- | ----------------- | --- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     | STM32F722xx STM32F723xx |     |     |
| -------------------------- | --- | --- | --- | ----------------------- | --- | --- |
Table 14. Voltage characteristics (continued)
|     | Symbol |     |     | Ratings | Min Max | Unit |
| --- | ------ | --- | --- | ------- | ------- | ---- |
|ΔV
|     | DDx | | Variations between different V |     | DD  power pins | - 50 |     |
| --- | ----- | ------------------------------ | --- | -------------- | ---- | --- |
mV
|V −V | Variations between all the different ground pins(3) - 50
SSX  SS
see Section 5.3.18:
Absolute maximum
|     | V        | Electrostatic discharge voltage (human body model) |     |     |                      | -   |
| --- | -------- | -------------------------------------------------- | --- | --- | -------------------- | --- |
|     | ESD(HBM) |                                                    |     |     | ratings (electrical  |     |
sensitivity)
1. All main power (V DD , V DDA , V DDSDMMC,  V DDUSB ) and ground (V SS , V SSA ) pins must always be connected
to the external power supply, in the permitted range.
2. V  maximum value must always be respected. Refer to Table 15 for the values of the maximum allowed
IN
injected current.
3. Include VREF- pin.
|        |                                 | Table 15. Current characteristics  |       |                         |       |      |
| ------ | ------------------------------- | ---------------------------------- | ----- | ----------------------- | ----- | ---- |
| Symbol |                                 |                                    |       | Ratings                 |  Max. | Unit |
| ΣI     |                                 |                                    |       | power lines (source)(1) |       |      |
| VDD    | Total current into sum of all V |                                    | DD_x  |                         | 300   |      |
Σ I Total current out of sum of all V ground lines (sink)(1) −300
| VSS    |                      |       |                      | SS_x  |     |     |
| ------ | -------------------- | ----- | -------------------- | ----- | --- | --- |
| Σ I    | Total current into V |       |  power line (source) |       | 25  |     |
| VDDUSB |                      | DDUSB |                      |       |     |     |
Σ I
|          | Total current into V        |         |  power line (source) |                        | 60  |     |
| -------- | --------------------------- | ------- | -------------------- | ---------------------- | --- | --- |
| VDDSDMMC |                             | DDSDMMC |                      |                        |     |     |
| I        | Maximum current into each V |         |                      | power line (source)(1) | 100 |     |
| VDD      |                             |         |                      | DD_x                   |     |     |
I VDDSDMMC Maximum current into V DDSDMMC  power line (source): PG[12:9], PD[7:6] 100
| I   | Maximum current out of each V                  |     |     | ground line (sink)(1) | −100 |     |
| --- | ---------------------------------------------- | --- | --- | --------------------- | ---- | --- |
| VSS |                                                |     |     | SS_x                  |      |     |
|     | Output current sunk by any I/O and control pin |     |     |                       | 25   |     |
mA
I
IO
|     | Output current sourced by any I/Os and control pin |     |     |     | −25 |     |
| --- | -------------------------------------------------- | --- | --- | --- | --- | --- |
Total output current sunk by sum of all I/O and control pins (2) 120
ΣI
| IO  | Total output current sunk by sum of all USB I/Os |     |     |     | 25  |     |
| --- | ------------------------------------------------ | --- | --- | --- | --- | --- |
Total output current sourced by sum of all I/Os and control pins(2) −120
|     | Injected current on FT, FTf, RST and B pins (3) |     |     |     | −5/+0 |     |
| --- | ----------------------------------------------- | --- | --- | --- | ----- | --- |
I
INJ(PIN)
|          | Injected current on TTa pins(4)                                 |     |     |     | ±5  |     |
| -------- | --------------------------------------------------------------- | --- | --- | --- | --- | --- |
| ΣI       | (4) Total injected current (sum of all I/O and control pins)(5) |     |     |     |     |     |
| INJ(PIN) |                                                                 |     |     |     | ±25 |     |
1. All main power (V , V ) and ground (V , V ) pins must always be connected to the external power supply, in the
|     | DD DDA |     | SS SSA |     |     |     |
| --- | ------ | --- | ------ | --- | --- | --- |
permitted range.
2. This current consumption must be correctly distributed over all I/Os and control pins. The total output current must not be
sunk/sourced between two consecutive power supply pins referring to high pin count LQFP packages.
3. Positive injection is not possible on these I/Os and does not occur for input voltages lower than the specified maximum
value.
4. A positive injection is induced by V >V  while a negative injection is induced by V <V . I  must never be
|     |     | IN DDA |     | IN SS | INJ(PIN) |     |
| --- | --- | ------ | --- | ----- | -------- | --- |
exceeded. Refer to Table 14: Voltage characteristics for the values of the maximum allowed input voltage.
5. When several inputs are submitted to a current injection, the maximum ΣI INJ(PIN)  is the absolute sum of the positive and
negative injected currents (instantaneous values).
| 106/229 |     |     | DocID029808 Rev 3 |     |     |     |
| ------- | --- | --- | ----------------- | --- | --- | --- |

| STM32F722xx STM32F723xx |     |     |     |     |     |     | Electrical characteristics |     |
| ----------------------- | --- | --- | --- | --- | --- | --- | -------------------------- | --- |

Table 16. Thermal characteristics
|     |     | Symbol |                           | Ratings |     |     |  Value      | Unit |
| --- | --- | ------ | ------------------------- | ------- | --- | --- | ----------- | ---- |
|     |     | T      | Storage temperature range |         |     |     | −65 to +150 |      |
STG
°C
|     |     | T   | Maximum junction temperature |     |     |     | 125 |     |
| --- | --- | --- | ---------------------------- | --- | --- | --- | --- | --- |
J
| 5.3    | Operating conditions         |     |                                         |     |     |     |     |     |
| ------ | ---------------------------- | --- | --------------------------------------- | --- | --- | --- | --- | --- |
| 5.3.1  | General operating conditions |     |                                         |     |     |     |     |     |
|        |                              |     | Table 17. General operating conditions  |     |     |     |     |     |
 Conditions(1)
| Symbol |     | Parameter |     |     |     |     | Min Typ | Max Unit |
| ------ | --- | --------- | --- | --- | --- | --- | ------- | -------- |
Power Scale 3 (VOS[1:0] bits in
|     |     |     |     | PWR_CR register = 0x01), Regulator  |     |     | 0 - | 144 |
| --- | --- | --- | --- | ----------------------------------- | --- | --- | --- | --- |
ON, over-drive OFF
Over-
|     |     |     |     |     |     | drive  | -   | 168 |
| --- | --- | --- | --- | --- | --- | ------ | --- | --- |
Power Scale 2 (VOS[1:0] bits in
OFF
|     |     |     |     | PWR_CR register = 0x10),  |     |     | 0   |     |
| --- | --- | --- | --- | ------------------------- | --- | --- | --- | --- |
Over-
Regulator ON
| f   | Internal AHB clock frequency |     |     |     |     | drive  | -   | 180 |
| --- | ---------------------------- | --- | --- | --- | --- | ------ | --- | --- |
HCLK
ON
Over-
MHz
|     |     |     |     |                                  |     | drive  | -   | 180    |
| --- | --- | --- | --- | -------------------------------- | --- | ------ | --- | ------ |
|     |     |     |     | Power Scale 1 (VOS[1:0] bits in  |     | OFF    |     |        |
|     |     |     |     | PWR_CR register= 0x11),          |     |        | 0   |        |
|     |     |     |     | Regulator ON                     |     | Over-  |     |        |
|     |     |     |     |                                  |     | drive  | -   | 216(2) |
ON
|     |                               |     |     | Over-drive OFF |     |     | 0  - | 45  |
| --- | ----------------------------- | --- | --- | -------------- | --- | --- | ---- | --- |
| f   | Internal APB1 clock frequency |     |     |                |     |     |      |     |
PCLK1
|     |                               |     |     | Over-drive ON  |     |     | 0  - | 54  |
| --- | ----------------------------- | --- | --- | -------------- | --- | --- | ---- | --- |
|     |                               |     |     | Over-drive OFF |     |     | 0  - | 90  |
| f   | Internal APB2 clock frequency |     |     |                |     |     |      |     |
PCLK2
|     |                            |     |     | Over-drive ON |     |     | 0  -     | 108 |
| --- | -------------------------- | --- | --- | ------------- | --- | --- | -------- | --- |
| V   | Standard operating voltage |     |     |               | -   |     | 1.7(3) - | 3.6 |
DD
Analog operating voltage
|     |     |     |     |     |     |     | 1.7(3) - | 2.4 |
| --- | --- | --- | --- | --- | --- | --- | -------- | --- |
(ADC limited to 1.2 M samples)
| V (4)(5) |     |     |     | Must be the same potential as V |     | (6) |     |     |
| -------- | --- | --- | --- | ------------------------------- | --- | --- | --- | --- |
| DDA      |     |     |     |                                 |     | DD  |     |     |
Analog operating voltage
|     |     |     |     |     |     |     | 2.4 - | 3.6 |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- |
(ADC limited to 2.4 M samples)
|     | USB supply voltage (supply   |     |     | USB not used |     |     | 1.7 3.3 | 3.6 V |
| --- | ---------------------------- | --- | --- | ------------ | --- | --- | ------- | ----- |
| V   | voltage for PA11,PA12, PB14  |     |     |              |     |     |         |       |
DDUSB
|     | and PB15 pins)           |     |     | USB used |     |     | 3.0 -  | 3.6 |
| --- | ------------------------ | --- | --- | -------- | --- | --- | ------ | --- |
| V   | Backup operating voltage |     |     |          | -   |     | 1.65 - | 3.6 |
BAT
SDMMC2 supply voltage
V (supply voltage for PG[12:9]  It can be different from V 1.7 - 3.6
| DDSDMMC |     |     |     |     |     | DD  |     |     |
| ------- | --- | --- | --- | --- | --- | --- | --- | --- |
and PD6 pins)
|     |     |     |     | DocID029808 Rev 3 |     |     |     | 107/229 |
| --- | --- | --- | --- | ----------------- | --- | --- | --- | ------- |
201

| Electrical characteristics |     |     | STM32F722xx STM32F723xx |     |     |
| -------------------------- | --- | --- | ----------------------- | --- | --- |
Table 17. General operating conditions (continued)
 Conditions(1)
| Symbol | Parameter |     |     | Min Typ | Max Unit |
| ------ | --------- | --- | --- | ------- | -------- |
Power Scale 3 ((VOS[1:0] bits in
|     |     | PWR_CR register = 0x01), 144 MHz  |     | 1.08 1.14 | 1.20 |
| --- | --- | --------------------------------- | --- | --------- | ---- |
HCLK max frequency
Power Scale 2 ((VOS[1:0] bits in
PWR_CR register = 0x10), 168 MHz
| Regulator ON: 1.2 V internal  |     |     |     | 1.20 1.26 | 1.32 |
| ----------------------------- | --- | --- | --- | --------- | ---- |
HCLK max frequency with over-drive
| voltage on V | /V pins      |                                   |     |     |     |
| ------------ | ------------ | --------------------------------- | --- | --- | --- |
|              | CAP_1 CAP_2  | OFF or 180 MHz with over-drive ON |     |     |     |
| V            |              | Power Scale 1 ((VOS[1:0] bits in  |     |     |     |
12
PWR_CR register = 0x11), 180 MHz
|     |     |     |     | 1.26 1.32 | 1.40 |
| --- | --- | --- | --- | --------- | ---- |
HCLK max frequency with over-drive
OFF or 216 MHz with over-drive ON
V
|     |     | Max frequency 144 MHz |     | 1.10 1.14 | 1.20 |
| --- | --- | --------------------- | --- | --------- | ---- |
Regulator OFF: 1.2 V external
voltage must be supplied from
|     |     | Max frequency 168MHz |     | 1.20 1.26 | 1.32 |
| --- | --- | -------------------- | --- | --------- | ---- |
external regulator on
| V   | /V pins(7) | Max frequency 180 MHz |     | 1.26 1.32 | 1.38 |
| --- | ---------- | --------------------- | --- | --------- | ---- |
CAP_1 CAP_2
2 V ≤ V  ≤ 3.6 V
| Input voltage on RST and FT  |     | DD  |     | −0.3 - | 5.5 |
| ---------------------------- | --- | --- | --- | ------ | --- |
pins(8)
|     |     | V  ≤ 2 V |     | −0.3 - | 5.2 |
| --- | --- | -------- | --- | ------ | --- |
DD
| V                         |     |     |     |        | V + |
| ------------------------- | --- | --- | --- | ------ | --- |
| IN                        |     |     |     |        | DDA |
| Input voltage on TTa pins |     |     | -   | −0.3 - |     |
0.3
| Input voltage on BOOT pin  |     |          | -   | 0 - | 9    |
| -------------------------- | --- | -------- | --- | --- | ---- |
|                            |     | LQFP64   |     | - - | 881  |
|                            |     | LQFP100  |     | - - | 1117 |
|                            |     | WLCSP100 |     | - - | 558  |
Power dissipation at T A = 85 °C
| P D for suffix 6 or T | A  = 105 °C for  | LQFP144 |     | - - | 1587 mW |
| --------------------- | ---------------- | ------- | --- | --- | ------- |
suffix 7(9)
|     |     | LQFP176                   |     | - -    | 1869 |
| --- | --- | ------------------------- | --- | ------ | ---- |
|     |     | UFBGA144                  |     | - -    | 476  |
|     |     | UFBGA176                  |     | - -    | 485  |
|     |     | Maximum power dissipation |     | −40  - | 85   |
Ambient temperature for 6
°C
suffix version Low power dissipation(10)
|     |     |     |     | −40  - | 105 |
| --- | --- | --- | --- | ------ | --- |
TA
|     |     | Maximum power dissipation  |     | −40  - | 105 |
| --- | --- | -------------------------- | --- | ------ | --- |
Ambient temperature for 7
°C
| suffix version                 |     | Low power dissipation(10) |     | −40  - | 125 |
| ------------------------------ | --- | ------------------------- | --- | ------ | --- |
|                                |     | 6 suffix version          |     | −40  - | 105 |
| TJ  Junction temperature range |     |                           |     |        | °C  |
|                                |     | 7 suffix version          |     | −40  - | 125 |
1. The over-drive mode is not supported at the voltage ranges from 1.7 to 2.1 V.
2. 216 MHz maximum frequency for 6 suffix version (200 MHz maximum frequency for 7 suffix version).
3. V /V  minimum value of 1.7 V is obtained with the use of an external power supply supervisor (refer to Section 2.17.2:
DD DDA
Internal reset OFF).
4. When the ADC is used, refer to Table 68: ADC characteristics.
| 5. If V  pin is present, it must respect the following condition: V |     |     | -V  < 1.2 V. |     |     |
| ------------------------------------------------------------------- | --- | --- | ------------ | --- | --- |
| REF+                                                                |     | DDA | REF+         |     |     |
6. It is recommended to power V and V from the same source. A maximum difference of 300 mV between V and V
|     | DD  DDA  |     |     |     | DD  DDA  |
| --- | -------- | --- | --- | --- | -------- |
can be tolerated during power-up and power-down operation.
| 108/229 |     | DocID029808 Rev 3 |     |     |     |
| ------- | --- | ----------------- | --- | --- | --- |

STM32F722xx STM32F723xx Electrical characteristics
7. The over-drive mode is not supported when the internal regulator is OFF.
8. To sustain a voltage higher than VDD+0.3, the internal Pull-up and Pull-Down resistors must be disabled
| 9. If T  is lower, higher P |  values are allowed as long as T |     |  does not exceed T | .    |     |
| --------------------------- | -------------------------------- | --- | ------------------ | ---- | --- |
| A                           | D                                |     | J                  | Jmax |     |
10. In low power dissipation state, T A  can be extended to this range as long as T J  does not exceed T Jmax .
          Table 18. Limitations depending on the operating power supply range
Maximum Flash
Maximum HCLK
| Operating  |     | memory access  |     |     | Possible Flash  |
| ---------- | --- | -------------- | --- | --- | --------------- |
frequency vs Flash
power supply  ADC operation frequency with  I/O operation memory
memory wait states
| range |     | no wait states  | (1)(2) |     | operations |
| ----- | --- | --------------- | ------ | --- | ---------- |
|       |     | (f              | )      |     |            |
Flashmax
|                 |                  |        | 180 MHz with 8 wait    |                   | 8-bit erase and   |
| --------------- | ---------------- | ------ | ---------------------- | ----------------- | ----------------- |
| V  =1.7 to      | Conversion time  |        |                        | No I/O            |                   |
| DD              |                  | 20 MHz | states and over-drive  |                   | program           |
| 2.1 V(3)        | up to 1.2 Msps   |        |                        | compensation      |                   |
|                 |                  |        | OFF                    |                   | operations only   |
|                 |                  |        | 216 MHz with 9 wait    |                   | 16-bit erase and  |
| V DD  = 2.1 to  | Conversion time  |        |                        | No I/O            |                   |
|                 |                  | 22 MHz | states and over-drive  |                   | program           |
| 2.4 V           | up to 1.2 Msps   |        |                        | compensation      |                   |
|                 |                  |        | ON                     |                   | operations        |
|                 |                  |        | 216 MHz with 8 wait    |                   | 16-bit erase and  |
|  = 2.4 to       | Conversion time  |        |                        | I/O compensation  |                   |
V DD
|              |                  | 24 MHz  | states and over-drive  |                   | program           |
| ------------ | ---------------- | ------- | ---------------------- | ----------------- | ----------------- |
| 2.7 V        | up to 2.4 Msps   |         |                        | works             |                   |
|              |                  |         | ON                     |                   | operations        |
|              |                  |         | 216 MHz with 7 wait    |                   | 32-bit erase and  |
| V  = 2.7 to  | Conversion time  |         |                        | I/O compensation  |                   |
| DD           |                  | 30 MHz  | states and over-drive  |                   | program           |
3.6 V(4)
|     | up to 2.4 Msps  |     |     | works |            |
| --- | --------------- | --- | --- | ----- | ---------- |
|     |                 |     | ON  |       | operations |
1. Applicable only when the code is executed from Flash memory. When the code is executed from RAM, no wait state is
required.
2. Thanks to the ART accelerator on ITCM interface and L1-cache on AXI interface, the number of wait states given here
does not impact the execution speed from Flash memory since the ART accelerator or L1-cache allows to achieve a
performance equivalent to 0-wait state program execution.
3. V /V  minimum value of 1.7 V is obtained with the use of an external power supply supervisor (refer to Section 2.17.2:
DD DDA
Internal reset OFF).
4. The voltage range for USB full speed  PHYs can drop down to 2.7 V. However the electrical characteristics of D- and D+
pins will be degraded between 2.7 and 3 V.
| 5.3.2  | VCAP1/VCAP2 external capacitor |     |     |     |     |
| ------ | ------------------------------ | --- | --- | --- | --- |
Stabilization for the main regulator is achieved by connecting an external capacitor C  to
EXT
|       | the VCAP1/VCAP2 pins. C                               | EXT |  is specified in Table 19.  |     |     |
| ----- | ----------------------------------------------------- | --- | --------------------------- | --- | --- |
| Note: | The VCAP2 pin is not available on the LQFP64 package. |     |                             |     |     |
Figure 30. External capacitor C
EXT
(cid:38)
(cid:40)(cid:54)(cid:53)
(cid:53)(cid:3)(cid:47)(cid:72)(cid:68)(cid:78)
(cid:48)(cid:54)(cid:20)(cid:28)(cid:19)(cid:23)(cid:23)(cid:57)(cid:21)
1. Legend: ESR is the equivalent series resistance.
|     |     |     | DocID029808 Rev 3 |     | 109/229 |
| --- | --- | --- | ----------------- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
|            |     | Table 19. VCAP1/VCAP2 operating conditions(1)  |           |     |     |     |            |     |
| ---------- | --- | ---------------------------------------------- | --------- | --- | --- | --- | ---------- | --- |
| Symbol     |     |                                                | Parameter |     |     |     | Conditions |     |
| CEXT       |     | Capacitance of external capacitor              |           |     |     |     | 2.2 µF     |     |
| ESR        |     | ESR of external capacitor                      |           |     |     |     | < 2 Ω      |     |
1. When bypassing the voltage regulator, the two 2.2 µF V  capacitors are not required and should be
CAP
replaced by two 100 nF decoupling capacitors.
           Table 20. VCAP1 operating conditions in the LQFP64 package(1)
| Symbol |     |                                   | Parameter |     |     |                         | Conditions |     |
| ------ | --- | --------------------------------- | --------- | --- | --- | ----------------------- | ---------- | --- |
| CEXT   |     | Capacitance of external capacitor |           |     |     |                         | 4.7 µF     |     |
| ESR    |     | ESR of external capacitor         |           |     |     | between 0.1 Ω and 0.2 Ω |            |     |
1. When bypassing the voltage regulator, the 4.7 µF V CAP  capacitor is not required and should be replaced
by two 100 nF decoupling capacitors.
5.3.3  Operating conditions at power-up / power-down (regulator ON)
| Subject to general operating conditions for T |     |     |     | .   |     |     |     |     |
| --------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
A
Table 21. Operating conditions at power-up / power-down (regulator ON)
| Symbol |     |                 | Parameter |     | Min |     | Max | Unit |
| ------ | --- | --------------- | --------- | --- | --- | --- | --- | ---- |
|        | V   |  rise time rate |           |     | 20  |     | ∞   |      |
DD
| t VDD |     |                 |     |     |     |     |     | µs/V |
| ----- | --- | --------------- | --- | --- | --- | --- | --- | ---- |
|       | V   |  fall time rate |     |     | 20  |     | ∞   |      |
DD
5.3.4  Operating conditions at power-up / power-down (regulator OFF)
| Subject to general operating conditions for T |     |     |     | .   |     |     |     |     |
| --------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
A
Table 22. Operating conditions at power-up / power-down (regulator OFF)(1)

| Symbol |     |                 | Parameter |           | Conditions |     | Min | Max Unit |
| ------ | --- | --------------- | --------- | --------- | ---------- | --- | --- | -------- |
|        | V   |  rise time rate |           | Power-up  |            |     | 20  | ∞        |
DD
t
| VDD |      |                 |     |             |     |     |     | ∞   |
| --- | ---- | --------------- | --- | ----------- | --- | --- | --- | --- |
|     | V DD |  fall time rate |     | Power-down  |     |     | 20  |     |
µs/V
|     | V     |  and V | rise time rate | Power-up |     |     | 20  | ∞   |
| --- | ----- | ------ | -------------- | -------- | --- | --- | --- | --- |
|     | CAP_1 |        | CAP_2          |          |     |     |     |     |
t VCAP
|     | V     |  and V |  fall time rate | Power-down |     |     | 20  | ∞   |
| --- | ----- | ------ | --------------- | ---------- | --- | --- | --- | --- |
|     | CAP_1 |        | CAP_2           |            |     |     |     |     |
1. To reset the internal logic at power-down, a reset must be applied on pin PA0 when V  reach below
| 1.08 V. |     |     |     |     |     |     | DD  |     |
| ------- | --- | --- | --- | --- | --- | --- | --- | --- |
5.3.5  Reset and power control block characteristics
The parameters given in Table 23 are derived from tests performed under ambient
| temperature and V |     | DD  supply voltage conditions summarized in Table 17. |     |     |     |     |     |     |
| ----------------- | --- | ----------------------------------------------------- | --- | --- | --- | --- | --- | --- |
110/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics

Table 23.  reset and power control block characteristics
| Symbol | Parameter | Conditions                  |     | Min Typ   | Max Unit |
| ------ | --------- | --------------------------- | --- | --------- | -------- |
|        |           | PLS[2:0]=000 (rising edge)  |     | 2.09 2.14 | 2.19 V   |
|        |           | PLS[2:0]=000 (falling edge) |     | 1.98 2.04 | 2.08 V   |
|        |           | PLS[2:0]=001 (rising edge)  |     | 2.23 2.30 | 2.37 V   |
|        |           | PLS[2:0]=001 (falling edge) |     | 2.13 2.19 | 2.25 V   |
|        |           | PLS[2:0]=010 (rising edge)  |     | 2.39 2.45 | 2.51 V   |
|        |           | PLS[2:0]=010 (falling edge) |     | 2.29 2.35 | 2.39 V   |
|        |           | PLS[2:0]=011 (rising edge)  |     | 2.54 2.60 | 2.65 V   |
Programmable voltage  PLS[2:0]=011 (falling edge) 2.44 2.51 2.56 V
V PVD
detector level selection PLS[2:0]=100 (rising edge) 2.70 2.76 2.82 V
|     |                    | PLS[2:0]=100 (falling edge) |     | 2.59 2.66 | 2.71 V |
| --- | ------------------ | --------------------------- | --- | --------- | ------ |
|     |                    | PLS[2:0]=101 (rising edge)  |     | 2.86 2.93 | 2.99 V |
|     |                    | PLS[2:0]=101 (falling edge) |     | 2.65 2.84 | 2.92 V |
|     |                    | PLS[2:0]=110 (rising edge)  |     | 2.96 3.03 | 3.10 V |
|     |                    | PLS[2:0]=110 (falling edge) |     | 2.85 2.93 | 2.99 V |
|     |                    | PLS[2:0]=111 (rising edge)  |     | 3.07 3.14 | 3.21 V |
|     |                    | PLS[2:0]=111 (falling edge) |     | 2.95 3.03 | 3.09 V |
| V   | (1) PVD hysteresis |                             | -   | - 100     | - mV   |
PVDhyst
|     | Power-on/power-down  | Falling edge |     | 1.60 1.68 | 1.76 V |
| --- | -------------------- | ------------ | --- | --------- | ------ |
V POR/PDR
|     | reset threshold | Rising edge |     | 1.64 1.72 | 1.80 V |
| --- | --------------- | ----------- | --- | --------- | ------ |
(1)
| V PDRhyst | PDR hysteresis |              | -   | - 40      | - mV   |
| --------- | -------------- | ------------ | --- | --------- | ------ |
|           |                | Falling edge |     | 2.13 2.19 | 2.24 V |
Brownout level 1
V
| BOR1 | threshold         | Rising edge  |     | 2.23 2.29 | 2.33 V |
| ---- | ----------------- | ------------ | --- | --------- | ------ |
|      | Brownout level 2  | Falling edge |     | 2.44 2.50 | 2.56 V |
V BOR2
|     | threshold         | Rising edge  |     | 2.53 2.59 | 2.63 V |
| --- | ----------------- | ------------ | --- | --------- | ------ |
|     | Brownout level 3  | Falling edge |     | 2.75 2.83 | 2.88 V |
V
| BOR3 | threshold          |             |     |           |        |
| ---- | ------------------ | ----------- | --- | --------- | ------ |
|      |                    | Rising edge |     | 2.85 2.92 | 2.97 V |
| V    | (1) BOR hysteresis |             | -   | - 100     | - mV   |
BORhyst
T
| RSTTEMPO | POR reset temporization |     | -   | 0.5 1.5 | 3.0 ms |
| -------- | ----------------------- | --- | --- | ------- | ------ |
(1)(2)
InRush current on
| (1)  | voltage regulator power- |     |     |       |        |
| ---- | ------------------------ | --- | --- | ----- | ------ |
| I    |                          |     | -   | - 160 | 250 mA |
| RUSH | on (POR or wakeup        |     |     |       |        |
from Standby)
InRush energy on
|      |                          | V  = 1.7 V, T        |  = 105 °C,  |     |        |
| ---- | ------------------------ | -------------------- | ----------- | --- | ------ |
| (1)  | voltage regulator power- | DD                   | A           |     |        |
| E    |                          |                      |             | - - | 5.4 µC |
| RUSH | on (POR or wakeup        | I = 171 mA for 31 µs |             |     |        |
RUSH
from Standby)
|     | DocID029808 Rev 3 |     |     |     | 111/229 |
| --- | ----------------- | --- | --- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
1. Guaranteed by design.
2. The reset temporization is measured from the power-on (POR reset or wakeup from V ) to the instant
BAT
when first instruction is read by the user application code.
5.3.6  Over-drive switching characteristics
When the over-drive mode switches from enabled to disabled or disabled to enabled, the
system clock is stalled during the internal voltage set-up.
The over-drive switching characteristics are given in Table 24. They are sbject to general
operating conditions for T .
A
Table 24. Over-drive switching characteristics(1)

| Symbol | Parameter | Conditions | Min Typ | Max Unit |
| ------ | --------- | ---------- | ------- | -------- |
|        |           | HSI        | - 45    | -        |
HSE max for 4 MHz
|          | Over_drive switch  |                    | 45 - | 100 |
| -------- | ------------------ | ------------------ | ---- | --- |
| Tod_swen |                    | and min for 26 MHz |      |     |
enable time
External HSE
|     |     |     | - 40 | -   |
| --- | --- | --- | ---- | --- |
50 MHz
µs
|     |     | HSI  | - 20 | -   |
| --- | --- | ---- | ---- | --- |
HSE max for 4 MHz
|           | Over_drive switch  |                     | 20 - | 80  |
| --------- | ------------------ | ------------------- | ---- | --- |
| Tod_swdis |                    | and min for 26 MHz. |      |     |
disable time
External HSE
|     |     |     | - 15 | -   |
| --- | --- | --- | ---- | --- |
50 MHz
1. Guaranteed by design.
5.3.7  Supply current characteristics
The current consumption is a function of several parameters and factors such as the
operating voltage, ambient temperature, I/O pin loading, device software configuration,
operating frequencies, I/O pin switching rate, program location in memory and executed
binary code.
The current consumption is measured as described in Figure 29: Current consumption
measurement scheme.
All the run-mode current consumption measurements given in this section are performed
with a reduced code that gives a consumption equivalent to CoreMark code.
112/229 DocID029808 Rev 3

| STM32F722xx STM32F723xx |     |     |     |     | Electrical characteristics |     |     |
| ----------------------- | --- | --- | --- | --- | -------------------------- | --- | --- |
Typical and maximum current consumption
The MCU is placed under the following conditions:
• All I/O pins are in input mode with a static value at V  or V  (no load).
DD SS
• All peripherals are disabled except if it is explicitly mentioned.
• The Flash memory access time is adjusted both to f  frequency and V range
|     |     |     |     |     | HCLK | DD  |     |
| --- | --- | --- | --- | --- | ---- | --- | --- |
(see Table 18: Limitations depending on the operating power supply range).
•
When the regulator is ON, the voltage scaling and over-drive mode are adjusted to
|     | f   |  frequency as follows: |     |     |     |     |     |
| --- | --- | ---------------------- | --- | --- | --- | --- | --- |
HCLK
 ≤
|     | –   | Scale 3 for f |  144 MHz |     |     |     |     |
| --- | --- | ------------- | -------- | --- | --- | --- | --- |
HCLK
|     | –   | Scale 2 for 144 MHz < f |     | ≤  168 MHz |     |     |     |
| --- | --- | ----------------------- | --- | ---------- | --- | --- | --- |
HCLK
– Scale 1 for 168 MHz < f  ≤  216 MHz. The over-drive is only ON at 216 MHz.
HCLK
• When the regulator is OFF, the V12 is provided externally as described in Table 17:
General operating conditions:
|     | • The system clock is HCLK, f |     |        | = f /4, and f |  = f /2.  |     |     |
| --- | ----------------------------- | --- | ------ | ------------- | --------- | --- | --- |
|     |                               |     | PCLK1  | HCLK PCLK2    | HCLK      |     |     |
• External clock frequency is 25 MHz and PLL is ON when f  is higher than 25 MHz.
HCLK
• The typical current consumption values are obtained for 1.7 V ≤   V  ≤   3.6 V voltage
DD
|     | range and for T | = 25 °C unless otherwise specified. |     |     |     |     |     |
| --- | --------------- | ----------------------------------- | --- | --- | --- | --- | --- |
A
|     | • The maximum values are obtained for 1.7 V ≤  |     |     |  ≤  |     |     |     |
| --- | ---------------------------------------------- | --- | --- | --- | --- | --- | --- |
 V  3.6 V voltage range and a
DD
|     | maximum ambient temperature (T |     |     | ) unless otherwise specified. |     |     |     |
| --- | ------------------------------ | --- | --- | ----------------------------- | --- | --- | --- |
A
• For the voltage range 1.7 V ≤   V  ≤   3.6 V, the maximum frequency is 180 MHz.
DD
Table 25. T   y       pical and maximum current consumption in Run mode, code with data processing
 running from ITCM RAM, regulator ON
Max(1)
| Symbol | Parameter | Conditions | f (MHz) | Typ |     |     | Unit |
| ------ | --------- | ---------- | ------- | --- | --- | --- | ---- |
HCLK
|     |     |     |     | T  = 25 °C | T  = 85 °C | T  = 105 °C |     |
| --- | --- | --- | --- | ---------- | ---------- | ----------- | --- |
|     |     |     |     | A          | A          | A           |     |
|     |     |     | 216 | 156 170(4) | 180(4)     | 200         |     |
|     |     |     | 200 | 144 154    | 164.6      | 183         |     |
|     |     |     |     | 134(4)     | 143(4)     | 158(4)      |     |
|     |     |     | 180 | 127        |            |             |     |
All peripherals
|     |     |     | 168 | 113 119 | 127.4 | 141 |     |
| --- | --- | --- | --- | ------- | ----- | --- | --- |
enabled(2)(3)
|     |              |     | 144 | 86 96  | 112.6    | 126    |     |
| --- | ------------ | --- | --- | ------ | -------- | ------ | --- |
|     |              |     | 60  | 41 44  | 52.8     | 65     |     |
|     | Supply cur-  |     | 25  | 22 24  | 33.5     | 45     |     |
| I   | rent in RUN  |     |     |        |          |        | mA  |
| DD  |              |     |     | 110(4) | 119.6(4) |        |     |
|     | mode         |     | 216 | 99     |          | 138.5  |     |
|     |              |     | 200 | 92 102 | 113.1    | 132    |     |
|     |              |     |     | 90(4)  | 96.7(4)  | 125(4) |     |
|     |              |     | 180 | 81     |          |        |     |
All peripherals
|     |     |     | 168 | 72 78 | 86.5 | 100.1 |     |
| --- | --- | --- | --- | ----- | ---- | ----- | --- |
disabled(3)
|     |     |     | 144 | 55 61 | 77.1 | 90.8 |     |
| --- | --- | --- | --- | ----- | ---- | ---- | --- |
|     |     |     | 60  | 24 25 | 38.5 | 50.3 |     |
|     |     |     | 25  | 12 13 | 26.3 | 38.1 |     |
1. Guaranteed by characterization results.
|     |     |     | DocID029808 Rev 3 |     |     |     | 113/229 |
| --- | --- | --- | ----------------- | --- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     |     | STM32F722xx STM32F723xx |     |     |
| -------------------------- | --- | --- | --- | --- | ----------------------- | --- | --- |
2. When analog peripheral blocks such as ADCs, DACs, HSE, LSE, HSI, or LSI are ON, an additional power consumption
should be considered.
3. When the ADC is ON (ADON bit set in the ADC_CR2 register), add an additional power consumption of 1.73 mA per ADC
for the analog part.
4. Guaranteed by test in production.
Table 26. T   y       pical and maximum current consumption in Run mode, code with data processing
 running from Flash memory (ART ON except prefetch / L1-cache ON)
or SRAM on AXI (L1-cache ON), regulator ON
Max(1)
| Symbol Parameter | Conditions | f HCLK  (MHz) | Typ   |              |              |               | Unit |
| ---------------- | ---------- | ------------- | ----- | ------------ | ------------ | ------------- | ---- |
|                  |            |               |       | T A  = 25 °C | T A  = 85 °C | T A  = 105 °C |      |
|                  |            | 216           | 155.3 | 164          | 175.8        | 185           |      |
|                  |            | 200           | 144.7 | 153.6        | 165.2        | 176           |      |
|                  |            | 180           | 127.3 | 135          | 143.5        | 154           |      |
All peripherals
|     | enabled(2)(3) | 168 | 113.1 | 119.1 | 127.8 | 138 |     |
| --- | ------------- | --- | ----- | ----- | ----- | --- | --- |
|     |               | 144 | 86.9  | 91.6  | 99.5  | 110 |     |
|     |               | 60  | 41.2  | 43.6  | 53.1  | 64  |     |
Supply cur-
|                   |     | 25  | 21.7 | 24  | 33.6  | 43.8 |     |
| ----------------- | --- | --- | ---- | --- | ----- | ---- | --- |
| I DD rent in RUN  |     |     |      |     |       |      | mA  |
|                   |     | 216 | 90   | 106 | 120.4 | 130  |     |
mode
|     |     | 200 | 84  | 99   | 113.8 | 124 |     |
| --- | --- | --- | --- | ---- | ----- | --- | --- |
|     |     | 180 | 74  | 86.6 | 97.3  | 107 |     |
All peripherals
|     |     | 168 | 66  | 76  | 87  | 97  |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
disabled(3)
|     |     | 144 | 51  | 59   | 68.2 | 78   |     |
| --- | --- | --- | --- | ---- | ---- | ---- | --- |
|     |     | 60  | 23  | 27   | 38.8 | 49   |     |
|     |     | 25  | 11  | 13.6 | 26.4 | 36.8 |     |
1. Guaranteed by characterization results.
2. When analog peripheral blocks such as ADCs, DACs, HSE, LSE, HSI, or LSI are ON, an additional power consumption
should be considered.
3. When the ADC is ON (ADON bit set in the ADC_CR2 register), add an additional power consumption of 1.73 mA per ADC
for the analog part.
| 114/229 |     | DocID029808 Rev 3 |     |     |     |     |     |
| ------- | --- | ----------------- | --- | --- | --- | --- | --- |

STM32F722xx STM32F723xx Electrical characteristics
Table 27. T   y       pical and maximum current consumption in Run mode, code with data processing
 running from Flash memory or SRAM on AXI (L1-cache disabled), regulator ON
Max(1)
| Symbol | Parameter | Conditions | f  (MHz) | Typ |     | Unit |
| ------ | --------- | ---------- | -------- | --- | --- | ---- |
HCLK
|     |     |     |     |       | TA= 25 °C TA=85 °C | TA=105 °C |
| --- | --- | --- | --- | ----- | ------------------ | --------- |
|     |     |     | 216 | 129.3 | 137.6 162.8        | 173       |
|     |     |     | 200 | 122   | 128 153.2          | 163.3     |
|     |     |     | 180 | 108   | 117 136.4          | 146       |
All peripherals
|     |     |     | 168 | 99  | 104.5 122.3 | 132 |
| --- | --- | --- | --- | --- | ----------- | --- |
enabled(2)(3)
|     |              |     | 144 | 80  | 84.7 99.3 | 109.2 |
| --- | ------------ | --- | --- | --- | --------- | ----- |
|     |              |     | 60  | 42  | 45 59.5   | 70    |
|     | Supply cur-  |     | 25  | 23  | 23.4 37.8 | 48    |
| I   | rent in RUN  |     |     |     |           | mA    |
DD
|     | mode |     | 216 | 73.3 | 82.3 107.4 | 119   |
| --- | ---- | --- | --- | ---- | ---------- | ----- |
|     |      |     | 200 | 70   | 77 101.8   | 113.5 |
|     |      |     | 180 | 62   | 71 90.2    | 101   |
All peripherals
|     |     | disabled(3) | 168 | 59  | 63.6 81.4 | 92.1 |
| --- | --- | ----------- | --- | --- | --------- | ---- |
|     |     |             | 144 | 49  | 53.3 67.9 | 79   |
|     |     |             | 60  | 26  | 31 45.1   | 56   |
|     |     |             | 25  | 14  | 16 30.6   | 41.2 |
1. Guaranteed by characterization results.
2. When analog peripheral blocks such as ADCs, DACs, HSE, LSE, HSI, or LSI are ON, an additional power consumption
should be considered.
3. When the ADC is ON (ADON bit set in the ADC_CR2 register), add an additional power consumption of 1.73 mA per ADC
for the analog part.
|     |     |     | DocID029808 Rev 3 |     |     | 115/229 |
| --- | --- | --- | ----------------- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     | STM32F722xx STM32F723xx |     |
| -------------------------- | --- | --- | --- | ----------------------- | --- |
Table 28. T   y       pical and maximum current consumption in Run mode, code with data processing
 running from Flash memory on ITCM interface (ART disabled), regulator ON
Max(1)
| Symbol Parameter | Conditions | f  (MHz) | Typ |     | Unit |
| ---------------- | ---------- | -------- | --- | --- | ---- |
HCLK
|     |     |     |     | TA= 25 °C TA=85 °C | TA=105 °C |
| --- | --- | --- | --- | ------------------ | --------- |
|     |     | 216 | 138 | 151 174.7          | 184       |
|     |     | 200 | 133 | 141 164.3          | 174       |
|     |     | 180 | 110 | 131 149.2          | 159       |
All peripherals
|     |     | 168 | 99  | 117 134 | 144 |
| --- | --- | --- | --- | ------- | --- |
enabled(2)(3)
|             |     | 144 | 79  | 98 111.7 | 121 |
| ----------- | --- | --- | --- | -------- | --- |
|             |     | 60  | 49  | 53 64    | 75  |
| Supply cur- |     | 25  | 27  | 30 38.3  | 48  |
| I rent in   |     |     |     |          | mA  |
DD
| RUN mode |     | 216 | 82  | 96 119.5 | 131 |
| -------- | --- | --- | --- | -------- | --- |
|          |     | 200 | 81  | 89 113.1 | 124 |
|          |     | 180 | 65  | 85 103.1 | 114 |
All peripherals
|     | disabled(3) | 168 | 58  | 76 93.2 | 104 |
| --- | ----------- | --- | --- | ------- | --- |
|     |             | 144 | 48  | 67 80.4 | 91  |
|     |             | 60  | 33  | 36 49.7 | 60  |
|     |             | 25  | 18  | 21 31.1 | 41  |
1. Guaranteed by characterization results.
2. When analog peripheral blocks such as ADCs, DACs, HSE, LSE, HSI, or LSI are ON, an additional power consumption
should be considered.
3. When the ADC is ON (ADON bit set in the ADC_CR2 register), add an additional power consumption of 1.73 mA per ADC
for the analog part.
| 116/229 |     | DocID029808 Rev 3 |     |     |     |
| ------- | --- | ----------------- | --- | --- | --- |

| STM32F722xx STM32F723xx |     |     |     |     | Electrical characteristics |     |
| ----------------------- | --- | --- | --- | --- | -------------------------- | --- |
Table 29. Typical and maximum current consumption in Run mode, code with data processing
 running from Flash memory (ART ON except prefetch / L1-cache ON)
or SRAM on AXI (L1-cache ON), regulator OFF
Max(1)
Typ
|     |     | f   |     |     |     | Unit |
| --- | --- | --- | --- | --- | --- | ---- |
Symbol Parameter Conditions HCLK TA= 25 °C TA= 85 °C TA= 105 °C
(MHz)
|     |     | IDD12   | IDD IDD12 | IDD IDD12 | IDD IDD12 | IDD |
| --- | --- | ------- | --------- | --------- | --------- | --- |
|     |     | 180 112 | 1.4 120   | 2 132.7   | 2 142     | 2   |
|     |     | 168 110 | 1.4 106.4 | 2 118.7   | 2 130     | 2   |
All Peripher-
|     | als  | 144 78 | 1.3 82.5 | 2 93.6 | 2 103 | 2   |
| --- | ---- | ------ | -------- | ------ | ----- | --- |
Enabled(2)(3)
| Supply cur-  |     | 60 37 | 1.1 37.6 | 2 49.3 | 2 60 | 2   |
| ------------ | --- | ----- | -------- | ------ | ---- | --- |
| rent in RUN  |     | 25 19 | 1.1 18.5 | 2 30.4 | 2 40 | 2   |
IDD12/
mode from  mA
| IDD |     | 180 74 | 1.4 78 | 2 89.3 | 2 99 | 2   |
| --- | --- | ------ | ------ | ------ | ---- | --- |
V12 and
VDD supply
|     |     | 168 64 | 1.4 68 | 2 80.1 | 2 90 | 2   |
| --- | --- | ------ | ------ | ------ | ---- | --- |
All Peripher-
|     | als Dis- | 144 51 | 1.3 54 | 2 63.5 | 2 74 | 2   |
| --- | -------- | ------ | ------ | ------ | ---- | --- |
abled(3)
|     |     | 60 22 | 1.1 24 | 2 35.2 | 2 45 | 2   |
| --- | --- | ----- | ------ | ------ | ---- | --- |
|     |     | 25 10 | 1.2 12 | 2 23.2 | 2 35 | 2   |
1. Guaranteed by characterization results.
2. When analog peripheral blocks such as ADCs, DACs, HSE, LSE, HSI, or LSI are ON, an additional power consumption
should be considered.
3. When the ADC is ON (ADON bit set in the ADC_CR2 register), add an additional power consumption of 1.73 mA per ADC
for the analog part.
|     |     | DocID029808 Rev 3 |     |     |     | 117/229 |
| --- | --- | ----------------- | --- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     |     |     |     |     | STM32F722xx STM32F723xx |     |     |     |     |
| -------------------------- | --- | --- | --- | --- | --- | --- | --- | ----------------------- | --- | --- | --- | --- |
Table           30. Typical and maximum current consumption in Sleep mode, regulator ON
Max(1)
| Symbol | Parameter | Conditions |     | f  (MHz) |     | Typ |     |     |     |     |     | Unit |
| ------ | --------- | ---------- | --- | -------- | --- | --- | --- | --- | --- | --- | --- | ---- |
HCLK
|     |     |     |     |     |     |     | TA= 25 °C |        | TA=85 °C  |     | TA=105 °C |     |
| --- | --- | --- | --- | --- | --- | --- | --------- | ------ | --------- | --- | --------- | --- |
|     |     |     |     | 216 |     | 82  |           | 96(3)  | 109.3(3)  |     | 128.3     |     |
|     |     |     |     | 200 |     | 77  |           | 84     | 103.4     |     | 122.6     |     |
|     |     |     |     | 180 |     | 67  |           | 72(3)  | 88.3(3)   |     | 120(3)    |     |
All peripherals
|     |     | enabled(2) |     | 168 |     | 60  |     | 64  | 78.9 |     | 92.7 |     |
| --- | --- | ---------- | --- | --- | --- | --- | --- | --- | ---- | --- | ---- | --- |
|     |     |            |     | 144 |     | 46  |     | 49  | 61.8 |     | 73.6 |     |
|     |     |            |     | 60  |     | 24  |     | 26  | 37.2 |     | 49   |     |
Supply cur-
|      | rent in  |     |     | 25  |     | 14  |     | 16     | 27       |     | 38.8 |     |
| ---- | -------- | --- | --- | --- | --- | --- | --- | ------ | -------- | --- | ---- | --- |
| I DD |          |     |     |     |     |     |     |        |          |     |      | mA  |
|      | SLEEP    |     |     | 216 |     | 24  |     | 28(3)  | 42.9(3)  |     | 62.2 |     |
mode
|     |     |     |     | 200 |     | 22  |     | 26     | 41.9     |     | 61.2   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ | -------- | --- | ------ | --- |
|     |     |     |     | 180 |     | 19  |     | 21(3)  | 33.2(3)  |     | 48(3)  |     |
All peripherals
|     |     |     |     | 168 |     | 17  |     | 19  | 30.1 |     | 43.9 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- | --- | ---- | --- |
disabled
|     |     |     |     | 144 |     | 13  |     | 15  | 24.6 |     | 36.3 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- | --- | ---- | --- |
|     |     |     |     | 60  |     | 7   |     | 9   | 20.5 |     | 32.3 |     |
|     |     |     |     | 25  |     | 5   |     | 7   | 18.8 |     | 30.6 |     |
1. Guaranteed by characterization results.
2. When analog peripheral blocks such as ADCs, DACs, HSE, LSE, HSI, or LSI are ON, an additional power consumption
should be considered.
3. Guaranteed by test in production.
Table        3    1. Typical and maximum current consumption in Sleep mode, regulator OFF
Max(1)
|     |     |     |     |     | Typ |     |     |     |     |     |     | Unit |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
f HCLK
| Symbol | Parameter | Conditions |     |     |     | TA= 25 °C |     | TA= 85 °C |     | TA= 105 °C |     |     |
| ------ | --------- | ---------- | --- | --- | --- | --------- | --- | --------- | --- | ---------- | --- | --- |
(MHz)
|     |     |     |     | IDD12 | IDD | IDD12 | IDD | IDD12 | IDD | IDD12 | IDD  |     |
| --- | --- | --- | --- | ----- | --- | ----- | --- | ----- | --- | ----- | ---- | --- |
|     |     |     | 180 | 62    | 1.3 | 67.5  | 2   | 84.4  | 2   |       | 95 2 |     |
|     |     |     | 168 | 55    | 1.3 | 59.8  | 2   | 75.4  | 2   |       | 86 2 |     |
All Periph-
|     |     | erals  | 144 | 43  | 1.3 | 46.3 | 2   | 59.6 | 2   |     | 70 2 |     |
| --- | --- | ------ | --- | --- | --- | ---- | --- | ---- | --- | --- | ---- | --- |
Enabled(2)
|     |     |     | 60  | 22  | 1   | 24  | 2   | 35.8 | 2   |     | 46 2 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ---- | --- | --- | ---- | --- |
Supply cur-
|     | rent in RUN  |     | 25  | 13  | 1   | 15  | 2   | 25.8 | 2   |     | 36 2 |     |
| --- | ------------ | --- | --- | --- | --- | --- | --- | ---- | --- | --- | ---- | --- |
IDD12/
|     | mode from  |     |     |     |     |     |     |     |     |     |     | mA  |
| --- | ---------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
IDD
|     | V12 and V |     | 180 | 17  | 1.3 | 19  | 2   | 31.4 | 2   |     | 42 2 |     |
| --- | --------- | --- | --- | --- | --- | --- | --- | ---- | --- | --- | ---- | --- |
DD
supply
|     |     |     | 168 | 15  | 1.3 | 17  | 2   | 28.4 | 2   |     | 40 2 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ---- | --- | --- | ---- | --- |
All Periph-
|     |     | erals Dis- | 144 | 12  | 1.2 | 14  | 2   | 23.2 | 2   |     | 33 2 |     |
| --- | --- | ---------- | --- | --- | --- | --- | --- | ---- | --- | --- | ---- | --- |
abled
|         |     |     | 60  | 5                 | 1   | 6   | 2   | 19.3 | 2   |     | 29 2 |     |
| ------- | --- | --- | --- | ----------------- | --- | --- | --- | ---- | --- | --- | ---- | --- |
|         |     |     | 25  | 3                 | 1   | 4   | 2   | 17.6 | 2   |     | 28 2 |     |
| 118/229 |     |     |     | DocID029808 Rev 3 |     |     |     |      |     |     |      |     |

| STM32F722xx STM32F723xx |     |     | Electrical characteristics |     |     |
| ----------------------- | --- | --- | -------------------------- | --- | --- |
1. Guaranteed by characterization results.
2. When analog peripheral blocks such as ADCs, DACs, HSE, LSE, HSI, or LSI are ON, an additional power consumption
should be considered.
           Table 32. Typical and maximum current consumptions in Stop mode
Max(1)
Typ
| Symbol | Parameter | Conditions |             | V DD  = 3.6 V       | Unit |
| ------ | --------- | ---------- | ----------- | ------------------- | ---- |
|        |           |            | T A  =      | T A  =  T A  =  T A |  =   |
|        |           |            | 25 °C 25 °C | 85 °C 105 °C        |      |
Flash memory in Stop mode,
| Supply current in Stop  |     |     | 0.45 | 2 12 22 |     |
| ----------------------- | --- | --- | ---- | ------- | --- |
all oscillators OFF, no IWDG
mode, main regulator in
Flash memory in Deep power
| Run mode |     |     | 0.4 | 2 12 22 |     |
| -------- | --- | --- | --- | ------- | --- |
down mode, all oscillators OFF
I
DD_STOP_NM
(normal mode) Flash memory in Stop mode, all
|     |     |     | 0.32 | 1.5 10 18 |     |
| --- | --- | --- | ---- | --------- | --- |
Supply current in Stop  oscillators OFF, no IWDG
mode, main regulator in Flash memory in Deep power
Low-power mode down mode, all oscillators OFF, no  0.27 1.5 10 18
IWDG mA
Regulator in Run mode, Flash
memory in Deep power down
|     |     |     | 0.15 | 0.8 5 7 |     |
| --- | --- | --- | ---- | ------- | --- |
mode, all oscillators OFF, no
| I Supply current in Stop                 |     |     |     |     |     |
| ---------------------------------------- | --- | --- | --- | --- | --- |
| DD_STOP_UDM mode, main regulator in IWDG |     |     |     |     |     |
(under-drive
Low voltage and under-Regulator in Low-power mode,
mode)
drive modes
Flash memory in Deep power
|     |     |     | 0.1 | 0.7 4 7 |     |
| --- | --- | --- | --- | ------- | --- |
down mode, all oscillators OFF, no
IWDG
1. Data based on characterization, tested in production.

|     |     | DocID029808 Rev 3 |     |     | 119/229 |
| --- | --- | ----------------- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     |     | STM32F722xx STM32F723xx |     |
| -------------------------- | --- | --- | --- | --- | ----------------------- | --- |
     T     able 33. Typical and maximum current consumptions in Standby mode
|                  |     |            | Typ(1)      |          | Max(2)      |             |
| ---------------- | --- | ---------- | ----------- | -------- | ----------- | ----------- |
|                  |     |            |             |          | T  =  T  =  | T  =        |
|                  |     |            | T  = 25 °C  |          | A A         | A           |
| Symbol Parameter |     | Conditions | A           |          | 25 °C 85 °C | 105 °C Unit |
|                  |     |            | V  =  V     | =  V  =  |             |             |
|                  |     |            | DD DD       | DD       | V  = 3.3 V  |             |
|                  |     |            | 1.7 V 2.4 V | 3.3 V    | DD          |             |
Backup SRAM OFF, RTC and
|     |     |     | 1.09 1.13 | 1.4 | 4 27 | 55  |
| --- | --- | --- | --------- | --- | ---- | --- |
LSE OFF
Backup SRAM ON, RTC and
|     |     |     | 1.85 1.88 | 2.17 | 5 30 | 60  |
| --- | --- | --- | --------- | ---- | ---- | --- |
LSE OFF
Backup SRAM OFF, RTC ON
|     |     |     | 1.65 1.86 | 2.43 | 7 47 | 95.5 |
| --- | --- | --- | --------- | ---- | ---- | ---- |
and LSE in low drive mode
Backup SRAM OFF, RTC ON
|     | and LSE in medium low drive  |     | 1.67 1.88 | 2.46 | 7 47.5 | 97  |
| --- | ---------------------------- | --- | --------- | ---- | ------ | --- |
mode
Backup SRAM OFF, RTC ON
|                 | and LSE in medium high drive  |     | 1.8 2.01 | 2.61 | 7.5 50.5 | 102.5 |
| --------------- | ----------------------------- | --- | -------- | ---- | -------- | ----- |
| Supply current  | mode                          |     |          |      |          |       |
I DD_STBY in Standby  µA
Backup SRAM OFF, RTC ON
mode
|     |     |     | 1.92 2.13 | 2.73 | 8 53 | 107 |
| --- | --- | --- | --------- | ---- | ---- | --- |
and LSE in high drive mode
Backup SRAM ON, RTC ON
|     |     |     | 2.39 2.6 | 3.23 | 9 62 | 127 |
| --- | --- | --- | -------- | ---- | ---- | --- |
and LSE in low drive mode
Backup SRAM ON, RTC ON
|     | and LSE in Medium low drive  |     | 2.41 2.64 | 3.25 | 9 63 | 128 |
| --- | ---------------------------- | --- | --------- | ---- | ---- | --- |
mode
Backup SRAM ON, RTC ON
|     | and LSE in Medium high drive  |     | 2.67 2.89 | 2.53 | 10 68 | 139 |
| --- | ----------------------------- | --- | --------- | ---- | ----- | --- |
mode
Backup SRAM ON, RTC ON
|     |     |     | 2.68 2.9 | 3.51 | 10 68 | 138 |
| --- | --- | --- | -------- | ---- | ----- | --- |
and LSE in High drive mode
1. PDR is OFF for V =1.7V. When the PDR is OFF (internal reset OFF), the typical current consumption is reduced by
DD
additional 1.2 µA.
2. Guaranteed by characterization results.
120/229 DocID029808 Rev 3

| STM32F722xx STM32F723xx |     |     |     | Electrical characteristics |     |     |
| ----------------------- | --- | --- | --- | -------------------------- | --- | --- |

| Table 34. Typical and maximum current consumptions in V |     |               |             |         | BAT  mode  |            |
| ------------------------------------------------------- | --- | ------------- | ----------- | ------- | ---------- | ---------- |
|                                                         |     |               | Typ         |         | Max(2)     |            |
|                                                         |     |               | T  =25 °C   | T       |  =85 °C    | T  =105 °C |
| Symbol Parameter                                        |     | Conditions(1) | A           |         | A          | A Unit     |
|                                                         |     |               | V  =  V     | =  V =  |            |            |
|                                                         |     |               | BAT BAT     | BAT     | V  = 3.6 V |            |
|                                                         |     |               | 1.7 V 2.4 V | 3.3 V   | BAT        |            |
Backup SRAM OFF, RTC and
|     |     |     | 0.035 0.037 | 0.043 | 4   | 10  |
| --- | --- | --- | ----------- | ----- | --- | --- |
LSE OFF
Backup SRAM ON, RTC and
|     |     |     | 0.69 0.71 | 0.73 | 9   | 20  |
| --- | --- | --- | --------- | ---- | --- | --- |
LSE OFF
Backup SRAM OFF, RTC ON
|     |     |     | 0.57 0.74 | 1.05 | 98  | 244 |
| --- | --- | --- | --------- | ---- | --- | --- |
and LSE in low drive mode
Backup SRAM OFF, RTC ON
|     | and LSE in medium low drive  |     | 0.59 0.76 | 1.08 | 101 | 251 |
| --- | ---------------------------- | --- | --------- | ---- | --- | --- |
mode
Backup SRAM OFF, RTC ON
Supply current and LSE in medium high drive  0.69 0.86 1.19 111 277
| I           |      |     |     |     |     | µA  |
| ----------- | ---- | --- | --- | --- | --- | --- |
| DD_VBATin V | mode |     |     |     |     |     |
BAT  mode
Backup SRAM OFF, RTC ON
|     |     |     | 0.8 0.98 | 1.31 | 122 | 305 |
| --- | --- | --- | -------- | ---- | --- | --- |
and LSE in high drive mode
Backup SRAM ON, RTC ON and
|     |     |     | 1.22 1.41 | 1.74 | 162 | 405 |
| --- | --- | --- | --------- | ---- | --- | --- |
LSE in low drive mode
Backup SRAM ON, RTC ON and
|     |     |     | 1.25 1.43 | 1.78 | 166 | 414 |
| --- | --- | --- | --------- | ---- | --- | --- |
LSE in Medium low drive mode
Backup SRAM ON, RTC ON and
|     |     |     | 1.46 1.65 | 2.01 | 187 | 468 |
| --- | --- | --- | --------- | ---- | --- | --- |
LSE in Medium high drive mode
Backup SRAM ON, RTC ON and
|     |     |     | 1.46 1.65 | 2.01 | 187 | 468 |
| --- | --- | --- | --------- | ---- | --- | --- |
LSE in High drive mode
| 1. Crystal used: Abracon ABS07-120-32.768 kHz-T with a C |     | L   |  of 6 pF for typical values. |     |     |     |
| -------------------------------------------------------- | --- | --- | ---------------------------- | --- | --- | --- |
2. Guaranteed by characterization results.
DocID029808 Rev 3 121/229
201

Electrical characteristics STM32F722xx STM32F723xx
Figure 31. Typical V current consumption (RTC ON/BKP SRAM OFF and
BAT
LSE in low drive mode)
(cid:1008)
(cid:1007)(cid:856)(cid:1009)
(cid:1007)
(cid:1005)(cid:856)(cid:1010)(cid:1009)(cid:3)(cid:115)
(cid:1006)(cid:856)(cid:1009) (cid:1005)(cid:856)(cid:1011)(cid:3)(cid:115)
(cid:1005)(cid:856)(cid:1012)(cid:3)(cid:115)
(cid:1006) (cid:1006)(cid:3)(cid:115)
(cid:1006)(cid:856)(cid:1008)(cid:3)(cid:115)
(cid:1005)(cid:856)(cid:1009)
(cid:1006)(cid:856)(cid:1011)(cid:3)(cid:115)
(cid:1007)(cid:3)(cid:115)
(cid:1005)
(cid:1007)(cid:856)(cid:1007)(cid:3)(cid:115)
(cid:1004)(cid:856)(cid:1009) (cid:1007)(cid:856)(cid:1010)(cid:3)(cid:115)
(cid:1004)
(cid:1004) (cid:1006)(cid:1004) (cid:1008)(cid:1004) (cid:1010)(cid:1004) (cid:1012)(cid:1004) (cid:1005)(cid:1004)(cid:1004) (cid:1005)(cid:1006)(cid:1004)
(cid:100)(cid:286)(cid:373)(cid:393)(cid:286)(cid:396)(cid:258)(cid:410)(cid:437)(cid:396)(cid:286)(cid:3)(cid:931)(cid:18)
(cid:48)(cid:54)(cid:22)(cid:26)(cid:24)(cid:27)(cid:24)(cid:57)(cid:20)
Figure 32. Typical V current consumption (RTC ON/BKP SRAM OFF and
BAT
LSE in medium low drive mode)
122/229 DocID029808 Rev 3
(cid:12)(cid:36)(cid:88)(cid:11)(cid:3)(cid:55)(cid:36)(cid:37)(cid:57)(cid:66)(cid:39)(cid:39)(cid:44)
(cid:48)(cid:54)(cid:22)(cid:26)(cid:24)(cid:27)(cid:25)(cid:57)(cid:20)
(cid:12)(cid:36)(cid:88)(cid:11)(cid:3)(cid:55)(cid:36)(cid:37)(cid:57)(cid:66)(cid:39)(cid:39)(cid:44)
(cid:1008)(cid:856)(cid:1009)
(cid:1008)
(cid:1007)(cid:856)(cid:1009)
(cid:1005)(cid:856)(cid:1010)(cid:1009)(cid:3)(cid:115) (cid:1007)
(cid:1005)(cid:856)(cid:1011)(cid:3)(cid:115)
(cid:1006)(cid:856)(cid:1009) (cid:1005)(cid:856)(cid:1012)(cid:3)(cid:115)
(cid:1006)(cid:3)(cid:115)
(cid:1006)
(cid:1006)(cid:856)(cid:1008)(cid:3)(cid:115)
(cid:1005)(cid:856)(cid:1009) (cid:1006)(cid:856)(cid:1011)(cid:3)(cid:115)
(cid:1007)(cid:3)(cid:115)
(cid:1005)
(cid:1007)(cid:856)(cid:1007)(cid:3)(cid:115)
(cid:1007)(cid:856)(cid:1010)(cid:3)(cid:115)
(cid:1004)(cid:856)(cid:1009)
(cid:1004)
(cid:1004) (cid:1006)(cid:1004) (cid:1008)(cid:1004) (cid:1010)(cid:1004) (cid:1012)(cid:1004) (cid:1005)(cid:1004)(cid:1004) (cid:1005)(cid:1006)(cid:1004)
(cid:100)(cid:286)(cid:373)(cid:393)(cid:286)(cid:396)(cid:258)(cid:410)(cid:437)(cid:396)(cid:286)(cid:3)(cid:931)(cid:18)

STM32F722xx STM32F723xx Electrical characteristics
Figure 33. Typical V current consumption (RTC ON/BKP SRAM OFF and
BAT
LSE in medium high drive mode)
(cid:1008)(cid:856)(cid:1009)
(cid:1008)
(cid:1007)(cid:856)(cid:1009)
(cid:1005)(cid:856)(cid:1010)(cid:1009)(cid:3)(cid:115)
(cid:1007)
(cid:1005)(cid:856)(cid:1011)(cid:3)(cid:115)
(cid:3)(cid:1006)(cid:856)(cid:1009) (cid:1005)(cid:856)(cid:1012)(cid:3)(cid:115)
(cid:1006)(cid:3)(cid:115)
(cid:1006)
(cid:1006)(cid:856)(cid:1008)(cid:3)(cid:115)
(cid:1005)(cid:856)(cid:1009) (cid:1006)(cid:856)(cid:1011)(cid:3)(cid:115)
(cid:1007)(cid:3)(cid:115)
(cid:1005)
(cid:1007)(cid:856)(cid:1007)(cid:3)(cid:115)
(cid:1004)(cid:856)(cid:1009) (cid:1007)(cid:856)(cid:1010)(cid:3)(cid:115)
(cid:1004)
(cid:1004) (cid:1006)(cid:1004) (cid:1008)(cid:1004) (cid:1010)(cid:1004) (cid:1012)(cid:1004) (cid:1005)(cid:1004)(cid:1004) (cid:1005)(cid:1006)(cid:1004)
(cid:100)(cid:286)(cid:373)(cid:393)(cid:286)(cid:396)(cid:258)(cid:410)(cid:437)(cid:396)(cid:286)(cid:3)(cid:931)(cid:18)
Figure 34. Typical V current consumption (RTC ON/BKP SRAM OFF and
BAT
LSE in high drive mode)
DocID029808 Rev 3 123/229
201
(cid:12)(cid:36)(cid:88)(cid:11)(cid:3)(cid:55)(cid:36)(cid:37)(cid:57)(cid:66)(cid:39)(cid:39)(cid:44)
(cid:48)(cid:54)(cid:22)(cid:26)(cid:24)(cid:27)(cid:26)(cid:57)(cid:20)
(cid:1008)(cid:856)(cid:1009)
(cid:1008)
(cid:1007)(cid:856)(cid:1009)
(cid:1007) (cid:1005)(cid:856)(cid:1010)(cid:1009)(cid:3)(cid:115)
(cid:1005)(cid:856)(cid:1011)(cid:3)(cid:115)
(cid:3) (cid:1006)(cid:856)(cid:1009)
(cid:1005)(cid:856)(cid:1012)(cid:3)(cid:115)
(cid:1006)(cid:3)(cid:115)
(cid:1006)
(cid:1006)(cid:856)(cid:1008)(cid:3)(cid:115)
(cid:1005)(cid:856)(cid:1009) (cid:1006)(cid:856)(cid:1011)(cid:3)(cid:115)
(cid:1007)(cid:3)(cid:115)
(cid:1005)
(cid:1007)(cid:856)(cid:1007)(cid:3)(cid:115)
(cid:1007)(cid:856)(cid:1010)(cid:3)(cid:115)
(cid:1004)(cid:856)(cid:1009)
(cid:1004)
(cid:1004) (cid:1006)(cid:1004) (cid:1008)(cid:1004) (cid:1010)(cid:1004) (cid:1012)(cid:1004) (cid:1005)(cid:1004)(cid:1004) (cid:1005)(cid:1006)(cid:1004)
(cid:100)(cid:286)(cid:373)(cid:393)(cid:286)(cid:396)(cid:258)(cid:410)(cid:437)(cid:396)(cid:286)(cid:3)(cid:931)(cid:18)
(cid:48)(cid:54)(cid:22)(cid:26)(cid:24)(cid:27)(cid:27)(cid:57)(cid:20)
(cid:12)(cid:36)(cid:88)(cid:11)(cid:3)(cid:55)(cid:36)(cid:37)(cid:57)(cid:66)(cid:39)(cid:39)(cid:44)

Electrical characteristics STM32F722xx STM32F723xx
Figure 35. Typical V current consumption (RTC ON/BKP SRAM OFF and
BAT
LSE in high medium drive mode)
(cid:1013)
(cid:1012)
(cid:1011)
(cid:1010) (cid:1005)(cid:856)(cid:1010)(cid:1009)(cid:3)(cid:115)
(cid:1005)(cid:856)(cid:1011)(cid:3)(cid:115)
(cid:1009) (cid:1005)(cid:856)(cid:1012)(cid:3)(cid:115)
(cid:1006)(cid:3)(cid:115)
(cid:1008)
(cid:1006)(cid:856)(cid:1008)(cid:3)(cid:115)
(cid:1006)(cid:856)(cid:1011)(cid:3)(cid:115)
(cid:1007)
(cid:1007)(cid:3)(cid:115)
(cid:1007)(cid:856)(cid:1007)(cid:3)(cid:115)
(cid:1006)
(cid:1007)(cid:856)(cid:1010)(cid:3)(cid:115)
(cid:1005)
(cid:1004)
(cid:1004) (cid:1006)(cid:1004) (cid:1008)(cid:1004) (cid:1010)(cid:1004) (cid:1012)(cid:1004) (cid:1005)(cid:1004)(cid:1004) (cid:1005)(cid:1006)(cid:1004)
(cid:100)(cid:286)(cid:373)(cid:393)(cid:286)(cid:396)(cid:258)(cid:410)(cid:437)(cid:396)(cid:286)(cid:894)(cid:3)(cid:931)(cid:18)(cid:895)
I/O system current consumption
The current consumption of the I/O system has two components: static and dynamic.
I/O static current consumption
All the I/Os used as inputs with pull-up generate current consumption when the pin is
externally held low. The value of this current consumption can be simply computed by using
the pull-up/pull-down resistors values given in Table 62: I/O static characteristics.
For the output pins, any external pull-down or external load must also be considered to
estimate the current consumption.
Additional I/O current consumption is due to I/Os configured as inputs if an intermediate
voltage level is externally applied. This current consumption is caused by the input Schmitt
trigger circuits used to discriminate the input value. Unless this specific configuration is
required by the application, this supply current consumption can be avoided by configuring
these I/Os in analog mode. This is notably the case of ADC input pins which should be
configured as analog inputs.
Caution: Any floating input pin can also settle to an intermediate voltage level or switch inadvertently,
as a result of external electromagnetic noise. To avoid current consumption related to
floating pins, they must either be configured in analog mode, or forced internally to a definite
digital value. This can be done either by using pull-up/down resistors or by configuring the
pins in output mode.
I/O dynamic current consumption
In addition to the internal peripheral current consumption (see Table 36: Peripheral current
consumption), the I/Os used by an application also contribute to the current consumption.
When an I/O pin switches, it uses the current from the MCU supply voltage to supply the I/O
124/229 DocID029808 Rev 3
(cid:12)(cid:36)(cid:88)(cid:11)(cid:3)(cid:55)(cid:36)(cid:37)(cid:57)(cid:66)(cid:39)(cid:39)(cid:44)
(cid:48)(cid:54)(cid:22)(cid:26)(cid:24)(cid:27)(cid:28)(cid:57)(cid:20)

| STM32F722xx STM32F723xx |     |     |     |     | Electrical characteristics |     |
| ----------------------- | --- | --- | --- | --- | -------------------------- | --- |
pin circuitry and to charge/discharge the capacitive load (internal or external) connected to
the pin:
|     |     |     | I = V | × f × C |     |     |
| --- | --- | --- | ----- | ------- | --- | --- |
|     |     |     | SW    | DD SW   |     |     |
Where
I  is the current sunk by a switching I/O to charge/discharge the capacitive load
SW
V  is the MCU supply voltage
DD
f  is the I/O switching frequency
SW
|     | C is the total capacitance seen by the I/O pin: C = C |     |     |     | + C |     |
| --- | ----------------------------------------------------- | --- | --- | --- | --- | --- |
INT EXT
The test pin is configured in push-pull output mode and is toggled by software at a fixed
frequency.
Table 35. Switching output I/O current consumption(1)

I/O toggling
|        |           |            |                   |     | Typ        | Typ        |
| ------ | --------- | ---------- | ----------------- | --- | ---------- | ---------- |
| Symbol | Parameter | Conditions |  frequency (fsw)  |     |            | Unit       |
|        |           |            |                   |     | V  = 3.3 V | V  = 1.8 V |
|        |           |            |                   |     | DD         | DD         |
MHz
|     |     |     |     | 2   | 0.1 | 0.1 |
| --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     | 8   | 0.4 | 0.2 |
|     |     |     |     | 25  | 1.1 | 0.7 |
|     |     |     |     | 50  | 2.4 | 1.3 |
C EXT  = 0 pF
|     |                |       |          | 60  | 3.1 | 1.6 |
| --- | -------------- | ----- | -------- | --- | --- | --- |
|     |                | C = C |  + C +C  |     |     |     |
|     |                | INT   | S    EXT |     |     |     |
|     |                |       |          | 84  | 4.3 | 2.4 |
|     |                |       |          | 90  | 4.9 | 2.6 |
|     |                |       |          | 100 | 5.4 | 2.8 |
|     | I/O switching  |       |          | 108 | 5.6 | -   |
I mA
DDIO
|     | Current |     |     | 2   | 0.2 | 0.1 |
| --- | ------- | --- | --- | --- | --- | --- |
|     |         |     |     | 8   | 0.6 | 0.3 |
|     |         |     |     | 25  | 1.8 | 1.1 |
|     |         |     |     | 50  | 3.1 | 2.3 |
C  = 10 pF
EXT
|     |     | C = C INT |  + C S  +C   EXT  | 60  | 4.6   | 3.4     |
| --- | --- | --------- | ----------------- | --- | ----- | ------- |
|     |     |           |                   | 84  | 9.7   | 3.6     |
|     |     |           |                   | 90  | 10.12 | 5.2     |
|     |     |           |                   | 100 | 14.92 | 5.4     |
|     |     |           |                   | 108 | 18.11 | -       |
|     |     |           | DocID029808 Rev 3 |     |       | 125/229 |
201

| Electrical characteristics |     |     |     | STM32F722xx STM32F723xx |     |
| -------------------------- | --- | --- | --- | ----------------------- | --- |
Table 35. Switching output I/O current consumption(1) (continued)
I/O toggling
|        |           |            |     | Typ  | Typ  |
| ------ | --------- | ---------- | --- | ---- | ---- |
| Symbol | Parameter | Conditions |     |      | Unit |
 frequency (fsw)
|     |     |     |     | V DD  = 3.3 V | V DD  = 1.8 V |
| --- | --- | --- | --- | ------------- | ------------- |
MHz
|     |     |     | 2   | 0.3 | 0.1 |
| --- | --- | --- | --- | --- | --- |
|     |     |     | 8   | 1.0 | 0.5 |
|     |     |     | 25  | 3.5 | 1.6 |
C EXT  = 22 pF
|     |     |     | 50  | 5.9 | 4.2 |
| --- | --- | --- | --- | --- | --- |
C = C  + C +C
|     |                | INT S  |   EXT |       |     |
| --- | -------------- | ------ | ----- | ----- | --- |
|     |                |        | 60    | 10.0  | 4.4 |
|     | I/O switching  |        | 84    | 19.12 | 5.8 |
I mA
DDIO
|     | Current |     | 90  | 19.6 | -   |
| --- | ------- | --- | --- | ---- | --- |
|     |         |     | 2   | 0.3  | 0.2 |
|     |         |     | 8   | 1.3  | 0.7 |
C  = 33 pF
|     |     | EXT                  | 25    | 3.5   | 2.3  |
| --- | --- | -------------------- | ----- | ----- | ---- |
|     |     | C = C INT  + C S  +C |   EXT |       |      |
|     |     |                      | 50    | 10.26 | 5.19 |
|     |     |                      | 60    | 16.53 | -    |
1. CINT + C S,  PCB board capacitance including the pad pin is estimated to15 pF.
On-chip peripheral current consumption
The MCU is placed under the following conditions:
| •   | At startup, all I/O pins are in analog input configuration.   |       |                |          |     |
| --- | ------------------------------------------------------------- | ----- | -------------- | -------- | --- |
| •   | All peripherals are disabled unless otherwise mentioned.      |       |                |          |     |
| •   | I/O compensation cell enabled.                                |       |                |          |     |
| •   | The ART/L1-cache is ON.                                       |       |                |          |     |
| •   | Scale 1 mode selected, internal digital voltage V12 = 1.32 V. |       |                |          |     |
| •   | HCLK is the system clock. f                                   |       |  = f /4, and f |  = f /2. |     |
|     |                                                               | PCLK1 | HCLK PCLK2     | HCLK     |     |
The given value is calculated by measuring the difference of current consumption
– with all peripherals clocked off
– with only one peripheral clocked on
– f  = 216 MHz (Scale 1 + over-drive ON), f  = 168 MHz (Scale 2),
|     | HCLK |     | HCLK |     |     |
| --- | ---- | --- | ---- | --- | --- |
f HCLK  = 144 MHz (Scale 3)
•
|         | Ambient operating temperature is 25 °C and V |                   | DD =3.3 V. |     |     |
| ------- | -------------------------------------------- | ----------------- | ---------- | --- | --- |
| 126/229 |                                              | DocID029808 Rev 3 |            |     |     |

STM32F722xx STM32F723xx Electrical characteristics

Table 36. Peripheral current consumption
I (Typ)(1)
DD
| Peripheral |     |         |          |           | Unit |
| ---------- | --- | ------- | -------- | --------- | ---- |
|            |     | Scale 1 |  Scale 2 |  Scale 3  |      |
AHB1
| (up to  | GPIOA | 3.6 | 3.4 | 2.9 | µA/MHz |
| ------- | ----- | --- | --- | --- | ------ |
216 MHz)
|     | GPIOB | 3.7 | 3.6 | 3.1 |     |
| --- | ----- | --- | --- | --- | --- |
|     | GPIOC | 3.7 | 3.4 | 3.0 |     |
|     | GPIOD | 3.7 | 3.6 | 3.0 |     |
|     | GPIOE | 3.6 | 3.4 | 2.9 |     |
|     | GPIOF | 3.5 | 3.4 | 2.9 |     |
|     | GPIOG | 3.5 | 3.3 | 2.8 |     |
|     | GPIOH | 3.5 | 3.4 | 2.9 |     |
|     | GPIOI | 3.5 | 3.3 | 2.9 |     |
AHB2
| (up to  | CRC | 1.2 | 1.1 | 0.9 | µA/MHz |
| ------- | --- | --- | --- | --- | ------ |
216 MHz)
|     | BKPSRAM     | 0.8             | 0.7             | 0.6             |     |
| --- | ----------- | --------------- | --------------- | --------------- | --- |
|     | DMA1        | 3.07 x N + 8.7  | 2.98 x N + 8.4  | 2.52 x N + 7.02 |     |
|     | DMA2        | 3.01 x N + 7.98 | 2.95 x N + 7.95 | 2.48 x N + 6.69 |     |
|     | OTG_HS+ULPI | 54.4            | 53.2            | 44.6            |     |
|     | RNG         | 1.9             | 1.8             | 1.6             |     |
|     | USB_OTG_FS  | 28.7            | 27.9            | 23.5            |     |
|     |             | 16.2            | 15.8            | 13.3            |     |
FMC
AHB3
| (up to  |     |      |      |      | µA/MHz |
| ------- | --- | ---- | ---- | ---- | ------ |
|         |     | 16.9 | 16.3 | 13.8 |        |
216 MHz)
QSPI
|  Bus matrix(2) |     | 15.8              | 12.8 | 8.5 | µA/MHz  |
| -------------- | --- | ----------------- | ---- | --- | ------- |
|                |     | DocID029808 Rev 3 |      |     | 127/229 |
201

Electrical characteristics STM32F722xx STM32F723xx
Table 36. Peripheral current consumption (continued)
(Typ)(1)
I
DD
| Peripheral |              |         |          |           | Unit |
| ---------- | ------------ | ------- | -------- | --------- | ---- |
|            |              | Scale 1 |  Scale 2 |  Scale 3  |      |
|            | TIM2         | 19.3    | 18.2     | 15.6      |      |
|            | TIM3         | 15      | 14       | 12.2      |      |
|            | TIM4         | 15.7    | 15.1     | 12.8      |      |
|            | TIM5         | 18      | 16.9     | 14.4      |      |
|            | TIM6         | 3.7     | 3.1      | 2.8       |      |
|            | TIM7         | 3.5     | 2.9      | 2.5       |      |
|            | TIM12        | 8.1     | 7.8      | 6.4       |      |
|            | TIM13        | 6.1     | 5.1      | 4.7       |      |
|            | TIM14        | 6.3     | 5.6      | 4.7       |      |
|            | LPTIM1       | 9.4     | 9.8      | 8.3       |      |
|            | WWDG         | 2.4     | 1.3      | 1.4       |      |
|            | SPI2/I2S2(3) | 6.7     | 6        | 5.3       |      |
APB1
SPI3/I2S3(3)
| (up to  |     | 4.8 | 3.8 | 3.3 | µA/MHz |
| ------- | --- | --- | --- | --- | ------ |
54 MHz)
|     | USART2 | 13.3 | 12   | 10.6 |     |
| --- | ------ | ---- | ---- | ---- | --- |
|     | USART3 | 12.8 | 12   | 10.3 |     |
|     | UART4  | 11.7 | 10.7 | 9.2  |     |
|     | UART5  | 11.7 | 10.2 | 8.9  |     |
|     | I2C1   | 10.6 | 9.6  | 8.3  |     |
|     | I2C2   | 10.6 | 9.6  | 8.3  |     |
|     | I2C3   | 10.7 | 9.8  | 8.3  |     |
|     | CAN1   | 8.9  | 8    | 6.9  |     |
|     | PWR    | 11.3 | 11.3 | 8.9  |     |
DAC(4)
|     |       | 6.1  | 5.1  | 4.4  |     |
| --- | ----- | ---- | ---- | ---- | --- |
|     | UART7 | 13.3 | 12   | 10.3 |     |
|     | UART8 | 12.6 | 11.6 | 9.7  |     |
128/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
Table 36. Peripheral current consumption (continued)
(Typ)(1)
I
DD
Peripheral Unit
|     |         | Scale 1 |  Scale 2 |  Scale 3  |
| --- | ------- | ------- | -------- | --------- |
|     | TIM1    | 24.9    | 23.8     | 20        |
|     | TIM8    | 24.5    | 23.7     | 20        |
|     | USART1  | 12.4    | 11.6     | 10        |
|     | USART6  | 12.3    | 11.7     | 10        |
|     | ADC1(5) | 6.3     | 5.8      | 4.9       |
ADC2(5)
|     |         | 6.3 | 5.6 | 4.9 |
| --- | ------- | --- | --- | --- |
|     | ADC3(5) | 6.4 | 5.8 | 5   |
|     | SDMMC1  | 9.1 | 8.3 | 7.1 |
|     | SDMMC2  | 7   | 7.2 | 6   |
APB2
|     | SPI1/I2S1(3) | 3.2 | 3.2 | 2.6 |
| --- | ------------ | --- | --- | --- |
(up to  µA/MHz
| 108 MHz) | SPI4   | 2.9 | 2.9 | 2.2 |
| -------- | ------ | --- | --- | --- |
|          | SYSCFG | 1   | 1   | 0.7 |
|          | TIM9   | 9.9 | 9.1 | 7.8 |
|          | TIM10  | 7   | 6.4 | 5.6 |
|          | TIM11  | 7.2 | 6.8 | 5.7 |
|          | SPI5   | 4.8 | 4.1 | 3.6 |
|          | SAI1   | 5.6 | 4.9 | 4.2 |
|          | SAI2   | 5.4 | 4.7 | 4   |
USB PHY HS
|     |     | 8.3 | 7.9 | 6.7 |
| --- | --- | --- | --- | --- |
Controller
| 1. When the I/O compensation cell  is ON, I |     | DD  typical value increases by 0.22 mA. |     |     |
| ------------------------------------------- | --- | --------------------------------------- | --- | --- |
2. The BusMatrix is automatically active when at least one master is ON.
3. To enable an I2S peripheral, first set the I2SMOD bit and then the I2SE bit in the SPI_I2SCFGR register.
4. When the DAC is ON and EN1/2 bits are set in DAC_CR register, add an additional power consumption of
0.75 mA per DAC channel for the analog part.
5. When the ADC is ON (ADON bit set in the ADC_CR2 register), add an additional power consumption of
1.73 mA per ADC for the analog part.
DocID029808 Rev 3 129/229
201

| Electrical characteristics |     |     |     | STM32F722xx STM32F723xx |     |     |
| -------------------------- | --- | --- | --- | ----------------------- | --- | --- |
USB OTG HS and USB OTG HS PHY current consumption (on STM32F723xx
devices)
The MCU is placed under the following conditions:
•
STM32 MCU is enumerated as a HID device.
|     | •   |     |     |  = 168 MHz (Scale 2),  |     |     |
| --- | --- | --- | --- | ---------------------- | --- | --- |
f  = 216 MHz (Scale 1 + over-drive ON), f
|     | HCLK |     | HCLK |     |     |     |
| --- | ---- | --- | ---- | --- | --- | --- |
f  = 144 MHz (Scale 3)
HCLK
The given value is calculated by measuring the difference of current consumption in
case:
– USB is configured but no transfer is done.
– USB is configured and there is a transmission on going.
•
|     | Ambient operating temperature is 25 °C, V |     | DD  = V | DDUSB  = 3.3 V. |     |     |
| --- | ----------------------------------------- | --- | ------- | --------------- | --- | --- |
           Table 37. USB OTG HS and USB OTG PHY HS current consumption
I  (Typ)
DD
Unit
|     |     |     | Scale 1 | Scale 2 | Scale 3 |     |
| --- | --- | --- | ------- | ------- | ------- | --- |
USB OTG HS and USB OTG HS PHY
|     |     |     | 50.16 | 44.92 | 38.98 | mA  |
| --- | --- | --- | ----- | ----- | ----- | --- |
current consumption
| 5.3.8  | Wakeup time from low-power modes |     |     |     |     |     |
| ------ | -------------------------------- | --- | --- | --- | --- | --- |
The wakeup times given in Table 38 are measured starting from the wakeup event trigger up
to the first instruction executed by the CPU:
• For Stop or Sleep modes: the wakeup event is WFE.
• WKUP (PA0) pin is used to wakeup from Standby, Stop and Sleep modes.
All timings are derived from tests performed under ambient temperature and V =3.3 V.
DD

Table 38. Low-power mode wakeup timings
Typ(1) Max(1)
| Symbol | Parameter |     | Conditions |     |     | Unit |
| ------ | --------- | --- | ---------- | --- | --- | ---- |
CPU
(2)
| t WUSLEEP | Wakeup from Sleep |     | -   |     | 13 13 | clock  |
| --------- | ----------------- | --- | --- | --- | ----- | ------ |
cycles
|     |     | Main regulator is ON |     |     | 14 14.9 |     |
| --- | --- | -------------------- | --- | --- | ------- | --- |
Main regulator is ON and Flash
104.1 107.6
memory in Deep power down mode
Wakeup from Stop mode
| t (2) | with MR/LP regulator in  |     |     |     |     | µs  |
| ----- | ------------------------ | --- | --- | --- | --- | --- |
WUSTOP
|     | normal mode | Low power regulator is ON |     |     | 21.4 24.2 |     |
| --- | ----------- | ------------------------- | --- | --- | --------- | --- |
Low power regulator is ON and Flash
111.5 116.5
memory in Deep power down mode
| 130/229 |     | DocID029808 Rev 3 |     |     |     |     |
| ------- | --- | ----------------- | --- | --- | --- | --- |

| STM32F722xx STM32F723xx |     |     |     |     | Electrical characteristics |     |
| ----------------------- | --- | --- | --- | --- | -------------------------- | --- |
Table 38. Low-power mode wakeup timings (continued)
| Symbol | Parameter |     | Conditions |     | Typ(1) | Max(1) Unit |
| ------ | --------- | --- | ---------- | --- | ------ | ----------- |
Main regulator in under-drive mode
|     |                        | (Flash memory in Deep power-down  |     |     | 107.4 | 113.2 |
| --- | ---------------------- | --------------------------------- | --- | --- | ----- | ----- |
|     | Wakeup from Stop mode  | mode)                             |     |     |       |       |
(2)
t WUSTOP with MR/LP regulator in  Low power regulator in under-drive  µs
|     | Under-drive mode | mode  |     |     |       |     |
| --- | ---------------- | ----- | --- | --- | ----- | --- |
|     |                  |       |     |     | 112.7 | 120 |
(Flash memory in Deep power-down
mode)
|     |     | Exit Standby mode on rising edge |     |     | 308 | 313 |
| --- | --- | -------------------------------- | --- | --- | --- | --- |
Wakeup from Standby
| tWUSTDBY(2) |     |     |     |     |     | µs  |
| ----------- | --- | --- | --- | --- | --- | --- |
mode
|     |     | Exit Standby mode on falling edge |     |     | 307 | 313 |
| --- | --- | --------------------------------- | --- | --- | --- | --- |
1. Guaranteed by characterization results.
2. The wakeup times are measured from the wakeup event to the point in which the application code reads the first
5.3.9  External clock source characteristics
High-speed external user clock generated from an external source
In bypass mode the HSE oscillator is switched off and the input pin is a standard I/O. The
external clock signal has to respect the Table 62: I/O static characteristics. However, the
recommended clock input waveform is shown in Figure 36.
The characteristics given in Table 39 result from tests performed using an high-speed
external clock source, and under ambient temperature and supply voltage conditions
summarized in Table 17.
           Table 39. High-speed external user clock characteristics
|     | Symbol | Parameter | Conditions |     | Min Typ | Max Unit |
| --- | ------ | --------- | ---------- | --- | ------- | -------- |
External user clock source
|     | f HSE_ext frequency(1)                |     |     |     | 1 -    | 50 MHz |
| --- | ------------------------------------- | --- | --- | --- | ------ | ------ |
|     | V OSC_IN input pin high level voltage |     |     |     | 0.7V - | V      |
|     | HSEH                                  |     |     |     | DD     | DD     |
V
|     | V HSEL OSC_IN input pin low level voltage |     |     |     | V SS - | 0.3V DD |
| --- | ----------------------------------------- | --- | --- | --- | ------ | ------- |
-
t
|     | w(HSE) OSC_IN high or low time(1) |     |     |     | 5 - | -   |
| --- | --------------------------------- | --- | --- | --- | --- | --- |
t
w(HSE)
ns
t r(HSE) OSC_IN rise or fall time(1)
|     |     |     |     |     | - - | 10  |
| --- | --- | --- | --- | --- | --- | --- |
t
f(HSE)
|     | C OSC_IN input capacitance(1) |     |     | -   | - 5 | - pF |
| --- | ----------------------------- | --- | --- | --- | --- | ---- |
in(HSE)
|     | DuCy (HSE) Duty cycle           |     |     | -       | 45 - | 55 %  |
| --- | ------------------------------- | --- | --- | ------- | ---- | ----- |
|     | I OSC_IN Input leakage current  |     | V   | ≤ V ≤ V | - -  | ±1 µA |
|     | L                               |     | SS  | IN  DD  |      |       |
1. Guaranteed by design.
|     |     | DocID029808 Rev 3 |     |     |     | 131/229 |
| --- | --- | ----------------- | --- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     | STM32F722xx STM32F723xx |     |     |
| -------------------------- | --- | --- | --- | ----------------------- | --- | --- |
Low-speed external user clock generated from an external source
In bypass mode the LSE oscillator is switched off and the input pin is a standard I/O. The
external clock signal has to respect the Table 62: I/O static characteristics. However, the
recommended clock input waveform is shown in Figure 37.
The characteristics given in Table 40 result from tests performed using an low-speed
external clock source, and under ambient temperature and supply voltage conditions
summarized in Table 17.
           Table 40. Low-speed external user clock characteristics
| Symbol |     | Parameter | Conditions | Min | Typ | Max Unit |
| ------ | --- | --------- | ---------- | --- | --- | -------- |
User External clock source
| f   | frequency(1) |     |     | -   | 32.768 | 1000 kHz |
| --- | ------------ | --- | --- | --- | ------ | -------- |
LSE_ext
OSC32_IN input pin high level
| V    |         |     |     | 0.7V | -   | V   |
| ---- | ------- | --- | --- | ---- | --- | --- |
| LSEH | voltage |     |     | DD   |     | DD  |
V
| V    | OSC32_IN input pin low level voltage |     | -   | V   | -   | 0.3V |
| ---- | ------------------------------------ | --- | --- | --- | --- | ---- |
| LSEL |                                      |     |     | SS  |     | DD   |
t
| w(LSE) | OSC32_IN high or low time(1) |     |     | 450 | -   | -   |
| ------ | ---------------------------- | --- | --- | --- | --- | --- |
t
f(LSE)
ns
t
| r(LSE) | OSC32_IN rise or fall time(1) |     |     | -   | -   | 50  |
| ------ | ----------------------------- | --- | --- | --- | --- | --- |
t
f(LSE)
| C   | OSC32_IN input capacitance(1) |     | -   | -   | 5   | - pF |
| --- | ----------------------------- | --- | --- | --- | --- | ---- |
in(LSE)
| DuCy | Duty cycle |     | -   | 30  | -   | 70 % |
| ---- | ---------- | --- | --- | --- | --- | ---- |
(LSE)
| I   | OSC32_IN Input leakage current  |     | V ≤ V ≤ V  | -   | -   | ±1 µA |
| --- | ------------------------------- | --- | ---------- | --- | --- | ----- |
| L   |                                 |     | SS  IN  DD |     |     |       |
1. Guaranteed by design.
Figure 36. High-speed external clock source AC timing diagram
(cid:54)(cid:40)(cid:51)(cid:37)(cid:40)
(cid:25)(cid:16)(cid:5)
(cid:17)(cid:16)(cid:5)
(cid:54)(cid:40)(cid:51)(cid:37)(cid:44)
|     |     | (cid:84)(cid:82)(cid:8)(cid:40)(cid:51)(cid:37)(cid:9) |                                                        |                                                        |     | (cid:84)(cid:55)(cid:8)(cid:40)(cid:51)(cid:37)(cid:9) (cid:84) |
| --- | --- | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | --- | --------------------------------------------------------------- |
|     |     |                                                        | (cid:84)(cid:70)(cid:8)(cid:40)(cid:51)(cid:37)(cid:9) | (cid:84)(cid:55)(cid:8)(cid:40)(cid:51)(cid:37)(cid:9) |     |                                                                 |
(cid:52)(cid:40)(cid:51)(cid:37)
(cid:37)(cid:88)(cid:84)(cid:69)(cid:82)(cid:78)(cid:65)(cid:76) (cid:70)(cid:40)(cid:51)(cid:37)(cid:63)(cid:69)(cid:88)(cid:84)
(cid:41)(cid:44)
|     |     | (cid:67)(cid:76)(cid:79)(cid:67)(cid:75)(cid:0)(cid:83)(cid:79)(cid:85)(cid:82)(cid:67)(cid:69) | (cid:47)(cid:51)(cid:35)(cid:63)(cid:41)(cid:46) |     |     |     |
| --- | --- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------ | --- | --- | --- |
(cid:51)(cid:52)(cid:45)(cid:19)(cid:18)(cid:38)
(cid:65)(cid:73)(cid:17)(cid:23)(cid:21)(cid:18)(cid:24)
| 132/229 |     | DocID029808 Rev 3 |     |     |     |     |
| ------- | --- | ----------------- | --- | --- | --- | --- |

STM32F722xx STM32F723xx Electrical characteristics
Figure 37. Low-speed external clock source AC timing diagram
(cid:57)(cid:47)(cid:54)(cid:40)(cid:43)
(cid:28)(cid:19)(cid:8)
(cid:20)(cid:19)(cid:8)
(cid:57)(cid:47)(cid:54)(cid:40)(cid:47)
|     | (cid:87)(cid:85)(cid:11)(cid:47)(cid:54)(cid:40)(cid:12) |                                                          |     | (cid:87)(cid:58)(cid:11)(cid:47)(cid:54)(cid:40)(cid:12) (cid:87) |
| --- | -------------------------------------------------------- | -------------------------------------------------------- | --- | ----------------------------------------------------------------- |
|     | (cid:87)(cid:73)(cid:11)(cid:47)(cid:54)(cid:40)(cid:12) | (cid:87)(cid:58)(cid:11)(cid:47)(cid:54)(cid:40)(cid:12) |     |                                                                   |
(cid:55)(cid:47)(cid:54)(cid:40)
(cid:40)(cid:91)(cid:87)(cid:72)(cid:85)(cid:81)(cid:68)(cid:79) (cid:73)(cid:47)(cid:54)(cid:40)(cid:66)(cid:72)(cid:91)(cid:87)
|     | (cid:50)(cid:54)(cid:38)(cid:22)(cid:21)(cid:66)(cid:44)(cid:49) | (cid:44)(cid:47) |     |     |
| --- | ---------------------------------------------------------------- | ---------------- | --- | --- |
(cid:70)(cid:79)(cid:82)(cid:70)(cid:78)(cid:3)(cid:86)(cid:82)(cid:88)(cid:85)(cid:70)(cid:72)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)
(cid:68)(cid:76)(cid:20)(cid:26)(cid:24)(cid:21)(cid:28)
High-speed external clock generated from a crystal/ceramic resonator
The high-speed external (HSE) clock can be supplied with a 4 to 26 MHz crystal/ceramic
resonator oscillator. All the information given in this paragraph are based on
characterization results obtained with typical external components specified in Table 41. In
the application, the resonator and the load capacitors have to be placed as close as
possible to the oscillator pins in order to minimize output distortion and startup stabilization
time. Refer to the crystal resonator manufacturer for more details on the resonator
characteristics (frequency, package, accuracy).
|            | Table 41. HSE 4-26 MHz oscillator characteristics(1)  |            |         |          |
| ---------- | ----------------------------------------------------- | ---------- | ------- | -------- |
| Symbol     | Parameter                                             | Conditions | Min Typ | Max Unit |
| f OSC_IN   | Oscillator frequency                                  | -          | 4 -     | 26 MHz   |
| R          | Feedback resistor                                     | -          | - 200   | - kΩ     |
F
V =3.3 V,
DD
|     |     | ESR= 30 Ω,  | - 450 | -   |
| --- | --- | ----------- | ----- | --- |
C =5 pF@25 MHz
L
| I DD | HSE current consumption |     |     | µA  |
| ---- | ----------------------- | --- | --- | --- |
V =3.3 V,
DD
|     |     | ESR= 30 Ω,  | - 530 | -   |
| --- | --- | ----------- | ----- | --- |
C L =10 pF@25 MHz
| ACC (2) | HSE accuracy | -   | −500 - | 500 ppm |
| ------- | ------------ | --- | ------ | ------- |
HSE
| G _crit_max | Maximum critical crystal g | Startup | - - | 1 mA/V |
| ----------- | -------------------------- | ------- | --- | ------ |
| m           | m                          |         |     |        |
(3)
| t      | Startup time  |  V  is stabilized | - 2 | - ms |
| ------ | ------------- | ----------------- | --- | ---- |
| SU(HSE |               | DD                |     |      |
1. Guaranteed by design.
2. This parameter depends on the crystal used in the application. The minimum and maximum values must
be respected to comply with USB standard specifications.
3. t SU(HSE)  is the startup time measured from the moment it is enabled (by software) to a stabilized 8 MHz
oscillation is reached. This value is based on characterization results. It is measured for a standard crystal
resonator and it can vary significantly with the crystal manufacturer.
DocID029808 Rev 3 133/229
201

Electrical characteristics STM32F722xx STM32F723xx
For C and C , it is recommended to use high-quality external ceramic capacitors in the
L1 L2
5 pF to 25 pF range (typ.), designed for high-frequency applications, and selected to match
the requirements of the crystal or resonator (see Figure 38). C and C are usually the
L1 L2
same size. The crystal manufacturer typically specifies a load capacitance which is the
series combination of C and C . PCB and MCU pin capacitance must be included (10 pF
L1 L2
can be used as a rough estimate of the combined pin and board capacitance) when sizing
C and C .
L1 L2
Note: For information on selecting the crystal, refer to the application note AN2867 “Oscillator
design guide for ST microcontrollers” available from the ST website www.st.com.
Figure 38. Typical application with an 8 MHz crystal
(cid:53)(cid:72)(cid:86)(cid:82)(cid:81)(cid:68)(cid:87)(cid:82)(cid:85)(cid:3)(cid:90)(cid:76)(cid:87)(cid:75)
(cid:76)(cid:81)(cid:87)(cid:72)(cid:74)(cid:85)(cid:68)(cid:87)(cid:72)(cid:71)(cid:3)(cid:70)(cid:68)(cid:83)(cid:68)(cid:70)(cid:76)(cid:87)(cid:82)(cid:85)(cid:86)
(cid:38)(cid:47)(cid:20)
(cid:50)(cid:54)(cid:38)(cid:66)(cid:44)(cid:49) (cid:73)(cid:43)(cid:54)(cid:40)
(cid:37)(cid:76)(cid:68)(cid:86)(cid:3)
(cid:27)(cid:3)(cid:48)(cid:43)(cid:93)
(cid:53)(cid:41) (cid:70)(cid:82)(cid:81)(cid:87)(cid:85)(cid:82)(cid:79)(cid:79)(cid:72)(cid:71)
(cid:85)(cid:72)(cid:86)(cid:82)(cid:81)(cid:68)(cid:87)(cid:82)(cid:85)
(cid:74)(cid:68)(cid:76)(cid:81)
(cid:38)(cid:47)(cid:21) (cid:53)(cid:40)(cid:59)(cid:55) (cid:11)(cid:20)(cid:12)(cid:3) (cid:50)(cid:54)(cid:38)(cid:66)(cid:50)(cid:56)(cid:55) (cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)
(cid:68)(cid:76)(cid:20)(cid:26)(cid:24)(cid:22)(cid:19)
1. R value depends on the crystal characteristics.
EXT
Low-speed external clock generated from a crystal/ceramic resonator
The low-speed external (LSE) clock can be supplied with a 32.768 kHz crystal/ceramic
resonator oscillator. All the information given in this paragraph are based on
characterization results obtained with typical external components specified in Table 42. In
the application, the resonator and the load capacitors have to be placed as close as
possible to the oscillator pins in order to minimize output distortion and startup stabilization
time. Refer to the crystal resonator manufacturer for more details on the resonator
characteristics (frequency, package, accuracy).
Table 42. LSE oscillator characteristics (f = 32.768 kHz) (1)
LSE
Symbol Parameter Conditions Min Typ Max Unit
LSEDRV[1:0]=00
- 250 -
Low drive capability
LSEDRV[1:0]=10
- 300 -
Medium low drive capability
I LSE current consumption nA
DD
LSEDRV[1:0]=01
- 370 -
Medium high drive capability
LSEDRV[1:0]=11
- 480 -
High drive capability
134/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
Table 42. LSE oscillator characteristics (f  = 32.768 kHz) (1) (continued)
LSE
| Symbol | Parameter | Conditions | Min Typ | Max Unit |
| ------ | --------- | ---------- | ------- | -------- |
LSEDRV[1:0]=00
|     |     |     | -   | - 0.48 |
| --- | --- | --- | --- | ------ |
Low drive capability
LSEDRV[1:0]=10
|     |     |     | -   | - 0.75 |
| --- | --- | --- | --- | ------ |
Medium low drive capability
| G _crit_max | Maximum critical crystal g |     |     | µA/V |
| ----------- | -------------------------- | --- | --- | ---- |
| m           | m                          |     |     |      |
LSEDRV[1:0]=01
|     |     |     | -   | - 1.7 |
| --- | --- | --- | --- | ----- |
Medium high drive capability
LSEDRV[1:0]=11
|     |     |     | -   | - 2.7 |
| --- | --- | --- | --- | ----- |
High drive capability
(2)
| t SU | start-up time  |  V DD  is stabilized | - 2 | - s |
| ---- | -------------- | -------------------- | --- | --- |
1. Guaranteed by design.
2. Guaranteed by characterization results. t  is the start-up time measured from the moment it is enabled
SU
(by software) to a stabilized 32.768 kHz oscillation is reached. This value is measured for a standard
crystal resonator and it can vary significantly with the crystal manufacturer.
Note: For information on selecting the crystal, refer to the application note AN2867 “Oscillator
design guide for ST microcontrollers” available from the ST Microelectronics website
www.st.com.
Figure 39. Typical application with a 32.768 kHz crystal
(cid:53)(cid:72)(cid:86)(cid:82)(cid:81)(cid:68)(cid:87)(cid:82)(cid:85)(cid:3)(cid:90)(cid:76)(cid:87)(cid:75)
(cid:76)(cid:81)(cid:87)(cid:72)(cid:74)(cid:85)(cid:68)(cid:87)(cid:72)(cid:71)(cid:3)(cid:70)(cid:68)(cid:83)(cid:68)(cid:70)(cid:76)(cid:87)(cid:82)(cid:85)(cid:86)
(cid:38)(cid:47)(cid:20)
|     | (cid:50)(cid:54)(cid:38)(cid:22)(cid:21)(cid:66) | (cid:44)(cid:49) | (cid:73)(cid:47)(cid:54)(cid:40) |     |
| --- | ------------------------------------------------ | ---------------- | -------------------------------- | --- |
(cid:37)(cid:76)(cid:68)(cid:86)(cid:3)(cid:3)
(cid:22)(cid:21)(cid:17)(cid:26)(cid:25)(cid:27)(cid:3)(cid:78)(cid:43)(cid:93)
(cid:53)(cid:41) (cid:70)(cid:82)(cid:81)(cid:87)(cid:85)(cid:82)(cid:79)(cid:79)(cid:72)(cid:71)
(cid:85)(cid:72)(cid:86)(cid:82)(cid:81)(cid:68)(cid:87)(cid:82)(cid:85)
(cid:74)(cid:68)(cid:76)(cid:81)
|     | (cid:50)(cid:54)(cid:38)(cid:22)(cid:21)(cid:66) | (cid:50)(cid:56)(cid:55) | (cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41) |     |
| --- | ------------------------------------------------ | ------------------------ | ------------------------------------------------ | --- |
(cid:38)(cid:47)(cid:21)
(cid:68)(cid:76)(cid:20)(cid:26)(cid:24)(cid:22)(cid:20)(cid:68)
DocID029808 Rev 3 135/229
201

Electrical characteristics STM32F722xx STM32F723xx
5.3.10  Internal clock source characteristics
The parameters given in Table 43 and Table 44 are derived from tests performed under
ambient temperature and V  supply voltage conditions summarized in Table 17.
DD
High-speed internal (HSI) RC oscillator
|            |                           | Table 43. HSI oscillator characteristics (1)  |     |                       |     |         |          |
| ---------- | ------------------------- | --------------------------------------------- | --- | --------------------- | --- | ------- | -------- |
| Symbol     |                           | Parameter                                     |     | Conditions            |     | Min Typ | Max Unit |
| f HSI      | Frequency                 |                                               |     |                       | -   | - 16    | - MHz    |
|            | HSI user trimming step(2) |                                               |     |                       | -   | -       | - 1 %    |
|            |                           |                                               |     | T  = –40 to 105 °C(3) |     | −8      | - 4.5 %  |
A
ACC
| HSI |                                |     |     |  = –10 to 85 °C(3) |     |     |       |
| --- | ------------------------------ | --- | --- | ------------------ | --- | --- | ----- |
|     | Accuracy of the HSI oscillator |     |     | T                  |     | −4  | - 4 % |
A
|     |     |     |     | T  = 25 °C(4) |     | −1  | - 1 % |
| --- | --- | --- | --- | ------------- | --- | --- | ----- |
A
(2)
| t su(HSI) | HSI oscillator startup time          |     |     |     | -   | - 2.2 | 4 µs  |
| --------- | ------------------------------------ | --- | --- | --- | --- | ----- | ----- |
| I         | (2) HSI oscillator power consumption |     |     |     | -   | - 60  | 80 µA |
DD(HSI)
| 1. V DD  = 3.3 V, T | A  = –40 to 105 °C unless otherwise specified. |     |     |     |     |     |     |
| ------------------- | ---------------------------------------------- | --- | --- | --- | --- | --- | --- |
2. Guaranteed by design.
3. Guaranteed by characterization results.
4. Factory calibrated, parts not soldered.
Figure 40. ACCHSI versus temperature
(cid:1010)
(cid:1008)
(cid:1006)
(cid:895)(cid:1081)(cid:894)(cid:47)(cid:94)(cid:44)(cid:18)(cid:18)(cid:4) (cid:1004)
|     | (cid:882)(cid:1008)(cid:1004) | (cid:1004) | (cid:1006)(cid:1009) | (cid:1009)(cid:1009) | (cid:1012)(cid:1009) | (cid:1005)(cid:1004)(cid:1009) | (cid:1005)(cid:1006)(cid:1009) |
| --- | ----------------------------- | ---------- | -------------------- | -------------------- | -------------------- | ------------------------------ | ------------------------------ |
(cid:100)(cid:4)(cid:3)(cid:894)(cid:931)(cid:18)(cid:895)
(cid:882)(cid:1006)
(cid:882)(cid:1008)
|     |     |     | (cid:68)(cid:349)(cid:374) | (cid:68)(cid:258)(cid:454) | (cid:100)(cid:455)(cid:393)(cid:349)(cid:272)(cid:258)(cid:367) |     |     |
| --- | --- | --- | -------------------------- | -------------------------- | --------------------------------------------------------------- | --- | --- |
(cid:882)(cid:1010)
(cid:882)(cid:1012)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:20)(cid:19)(cid:24)(cid:24)(cid:57)(cid:20)
1. Guaranteed by characterization results.
136/229 DocID029808 Rev 3

| STM32F722xx STM32F723xx |     |     |     |     |     | Electrical characteristics |     |
| ----------------------- | --- | --- | --- | --- | --- | -------------------------- | --- |
Low-speed internal (LSI) RC oscillator
|     |            | Table 44. LSI oscillator characteristics (1)  |           |     |     |     |          |
| --- | ---------- | --------------------------------------------- | --------- | --- | --- | --- | -------- |
|     | Symbol     |                                               | Parameter |     | Min | Typ | Max Unit |
(2)
|     | f LSI | Frequency                       |     |     | 17  | 32  | 47 kHz  |
| --- | ----- | ------------------------------- | --- | --- | --- | --- | ------- |
|     | t     | (3) LSI oscillator startup time |     |     | -   | 15  | 40 µs   |
su(LSI)
|     | I   | (3) LSI oscillator power consumption |     |     | -   | 0.4 | 0.6 µA |
| --- | --- | ------------------------------------ | --- | --- | --- | --- | ------ |
DD(LSI)
|     | 1. V  = 3 V, T |  = –40 to 105 °C unless otherwise specified. |     |     |     |     |     |
| --- | -------------- | -------------------------------------------- | --- | --- | --- | --- | --- |
|     | DD             | A                                            |     |     |     |     |     |
2. Guaranteed by characterization results.
3. Guaranteed by design.
Figure 41. LSI deviation versus temperature
(cid:1012)(cid:856)(cid:1004)(cid:1081)
(cid:1010)(cid:856)(cid:1004)(cid:1081)
(cid:1008)(cid:856)(cid:1004)(cid:1081)
(cid:12)(cid:8)(cid:11)(cid:3)(cid:81)(cid:82)(cid:76)(cid:87)(cid:68)(cid:76)(cid:89)(cid:72)(cid:71)(cid:3)(cid:71)(cid:72)(cid:93)(cid:76)(cid:79)(cid:68)(cid:80)(cid:85)(cid:82)(cid:49)
(cid:1006)(cid:856)(cid:1004)(cid:1081)
(cid:68)(cid:349)(cid:374)
(cid:1004)(cid:856)(cid:1004)(cid:1081) (cid:68)(cid:258)(cid:454)
(cid:3)(cid:882)(cid:1008)(cid:1004)(cid:931)(cid:18) (cid:3)(cid:1004)(cid:931)(cid:18) (cid:1006)(cid:1009)(cid:931)(cid:18) (cid:3)(cid:1012)(cid:1009)(cid:931)(cid:18) (cid:3)(cid:1005)(cid:1004)(cid:1009)(cid:931)(cid:18) (cid:1005)(cid:1006)(cid:1009)(cid:931)(cid:18) (cid:100)(cid:455)(cid:393)(cid:349)(cid:272)(cid:258)(cid:367)
(cid:882)(cid:1006)(cid:856)(cid:1004)(cid:1081)
(cid:882)(cid:1008)(cid:856)(cid:1004)(cid:1081)
(cid:882)(cid:1010)(cid:856)(cid:1004)(cid:1081)
(cid:882)(cid:1012)(cid:856)(cid:1004)(cid:1081)
(cid:55)(cid:72)(cid:80)(cid:83)(cid:72)(cid:85)(cid:68)(cid:87)(cid:88)(cid:85)(cid:72)(cid:3)(cid:11)(cid:131)(cid:38)(cid:12)
(cid:48)(cid:54)(cid:22)(cid:26)(cid:24)(cid:24)(cid:23)(cid:57)(cid:20)
| 5.3.11  | PLL characteristics |     |     |     |     |     |     |
| ------- | ------------------- | --- | --- | --- | --- | --- | --- |
The parameters given in Table 45 and Table 46 are derived from tests performed under
|        | temperature and V  | DD  supply voltage conditions summarized in Table 17. |            |     |         |     |          |
| ------ | ------------------ | ----------------------------------------------------- | ---------- | --- | ------- | --- | -------- |
|        |                    | Table 45. Main PLL characteristics                    |            |     |         |     |          |
| Symbol |                    | Parameter                                             | Conditions |     | Min     | Typ | Max Unit |
|        | PLL input clock(1) |                                                       |            |     | 0.95(2) |     |          |
| f      |                    |                                                       |            | -   |         | 1   | 2.10     |
PLL_IN
| f   | PLL multiplier output clock |     |     | -   | 24  | -   | 216 |
| --- | --------------------------- | --- | --- | --- | --- | --- | --- |
PLL_OUT
MHz
48 MHz PLL multiplier output
| f         |                |     |     | -   | -   | 48  | 75  |
| --------- | -------------- | --- | --- | --- | --- | --- | --- |
| PLL48_OUT | clock          |     |     |     |     |     |     |
| f         | PLL VCO output |     |     | -   | 100 | -   | 432 |
VCO_OUT
|     |     |     | DocID029808 Rev 3 |     |     |     | 137/229 |
| --- | --- | --- | ----------------- | --- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     |     |     | STM32F722xx STM32F723xx |     |     |     |
| -------------------------- | --- | --- | --- | --- | --- | ----------------------- | --- | --- | --- |
Table 45. Main PLL characteristics (continued)
| Symbol |               | Parameter |                    | Conditions |     | Min | Typ | Max | Unit |
| ------ | ------------- | --------- | ------------------ | ---------- | --- | --- | --- | --- | ---- |
|        |               |           | VCO freq = 100 MHz |            |     | 75  | -   | 200 |      |
| t      | PLL lock time |           |                    |            |     |     |     |     | µs   |
LOCK
|     |                       |     | VCO freq = 432 MHz |     |       | 100 | -    | 300 |     |
| --- | --------------------- | --- | ------------------ | --- | ----- | --- | ---- | --- | --- |
|     |                       |     |                    |     | RMS   | -   | 25   | -   |     |
|     | Cycle-to-cycle jitter |     |                    |     | peak  |     |      |     |     |
|     |                       |     |                    |     | to    | -   | ±150 | -   |     |
peak
System clock
216 MHz
|     |     |     |     |     | RMS | -   | 15  | -   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
peak
Period Jitter
|           |     |     |     |     | to  | -   | ±200 | -   |     |
| --------- | --- | --- | --- | --- | --- | --- | ---- | --- | --- |
| Jitter(3) |     |     |     |     |     |     |      |     | ps  |
peak
|     | Main clock output (MCO) for      |     | Cycle to cycle at 50 MHz  |     |     |     |     |     |     |
| --- | -------------------------------- | --- | ------------------------- | --- | --- | --- | --- | --- | --- |
|     |                                  |     |                           |     |     | -   | 32  | -   |     |
|     | RMII Ethernet                    |     | on 1000 samples           |     |     |     |     |     |     |
|     | Main clock output (MCO) for MII  |     | Cycle to cycle at 25 MHz  |     |     |     |     |     |     |
|     |                                  |     |                           |     |     | -   | 40  | -   |     |
|     | Ethernet                         |     | on 1000 samples           |     |     |     |     |     |     |
Cycle to cycle at 1 MHz
|     | Bit Time CAN jitter |     |     |     |     | -   | 330 | -   |     |
| --- | ------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
on 1000 samples
|          |                            |     | VCO freq = 100 MHz     |     |     | 0.15 |     | 0.40 |     |
| -------- | -------------------------- | --- | ---------------------- | --- | --- | ---- | --- | ---- | --- |
| I (4)    | PLL power consumption on V |     |                        |     |     |      | -   |      | mA  |
| DD(PLL)  |                            |     | DD VCO freq = 432 MHz  |     |     | 0.45 |     | 0.75 |     |
|          |                            |     | VCO freq = 100 MHz     |     |     | 0.30 |     | 0.40 |     |
| I (4)    | PLL power consumption on V |     |                        |     |     |      | -   |      | mA  |
| DDA(PLL) |                            |     | DDA VCO freq = 432 MHz |     |     | 0.55 |     | 0.85 |     |
1. Take care of using the appropriate division factor M to obtain the specified PLL input clock values. The M factor is shared
between PLL and PLLI2S.
2. Guaranteed by design.
3. The use of 2 PLLs in parallel could degraded the Jitter up to +30%.
4. Guaranteed by characterization results.

Table 46. PLLI2S characteristics
| Symbol |                       | Parameter |     | Conditions |     | Min     | Typ | Max  | Unit |
| ------ | --------------------- | --------- | --- | ---------- | --- | ------- | --- | ---- | ---- |
| f      | PLLI2S input clock(1) |           |     | -          |     | 0.95(2) | 1   | 2.10 |      |
PLLI2S_IN
PLLI2S multiplier output clock for
| f PLLI2SQ_OUT |     |     |     | -   |     | -   | -   | 216 |     |
| ------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
SAI
MHz
PLLI2S multiplier output clock for
| f           |                   |     |                    | -   |     | -   | -   | 216 |     |
| ----------- | ----------------- | --- | ------------------ | --- | --- | --- | --- | --- | --- |
| PLLI2SR_OUT | I2S               |     |                    |     |     |     |     |     |     |
| f VCO_OUT   | PLLI2S VCO output |     |                    | -   |     | 100 | -   | 432 |     |
|             |                   |     | VCO freq = 100 MHz |     |     | 75  | -   | 200 |     |
| t LOCK      | PLLI2S lock time  |     |                    |     |     |     |     |     | µs  |
|             |                   |     | VCO freq = 432 MHz |     |     | 100 | -   | 300 |     |
| 138/229     |                   |     | DocID029808 Rev 3  |     |     |     |     |     |     |

| STM32F722xx STM32F723xx |     |     |     |     |     |     | Electrical characteristics |     |     |
| ----------------------- | --- | --- | --- | --- | --- | --- | -------------------------- | --- | --- |
Table 46. PLLI2S characteristics (continued)
| Symbol |     | Parameter | Conditions         |     |     | Min | Typ | Max | Unit |
| ------ | --- | --------- | ------------------ | --- | --- | --- | --- | --- | ---- |
|        |     |           | Cycle to cycle at  |     | RMS | -   | 90  | -   |      |
12.288 MHz on
 peak
|     |     |     | 48KHz period,  |     | to   | -   |  ±280 | -   | ps  |
| --- | --- | --- | -------------- | --- | ---- | --- | ----- | --- | --- |
|     |     |     | N=432, R=5     |     | peak |     |       |     |     |
Master I2S clock jitter
Average frequency of
Jitter(3)
12.288 MHz
|     |     |     |     |     |     | -   | 90  | -   | ps  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
N = 432, R = 5
on 1000 samples
Cycle to cycle at 48 KHz
|     | WS I2S clock jitter |     |     |     |     | -   | 400 | -   | ps  |
| --- | ------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
on 1000 samples
|            | PLLI2S power consumption on  |     | VCO freq = 100 MHz |     |     | 0.15 |     | 0.40 |     |
| ---------- | ---------------------------- | --- | ------------------ | --- | --- | ---- | --- | ---- | --- |
| I (4)      |                              |     |                    |     |     |      | -   |      | mA  |
| DD(PLLI2S) | V                            |     | VCO freq = 432 MHz |     |     | 0.45 |     | 0.75 |     |
DD
|             | PLLI2S power consumption on  |     | VCO freq = 100 MHz |     |     | 0.30 |     | 0.40 |     |
| ----------- | ---------------------------- | --- | ------------------ | --- | --- | ---- | --- | ---- | --- |
| I           | (4)                          |     |                    |     |     |      | -   |      | mA  |
| DDA(PLLI2S) | V                            |     | VCO freq = 432 MHz |     |     | 0.55 |     | 0.85 |     |
DDA
1. Take care of using the appropriate division factor M to have the specified PLL input clock values.
2. Guaranteed by design.
3. Value given with main PLL running.
4. Guaranteed by characterization results.
           Table 47. PLLISAI characteristics
| Symbol |                       | Parameter | Conditions |     |     | Min     | Typ | Max  | Unit |
| ------ | --------------------- | --------- | ---------- | --- | --- | ------- | --- | ---- | ---- |
| f      | PLLSAI input clock(1) |           |            | -   |     | 0.95(2) | 1   | 2.10 |      |
PLLSAI_IN
PLLSAI multiplier output clock
| f           |            |     |     | -   |     | -   | 48  | 75  |     |
| ----------- | ---------- | --- | --- | --- | --- | --- | --- | --- | --- |
| PLLSAIP_OUT | for 48 MHz |     |     |     |     |     |     |     |     |
MHz
PLLSAI multiplier output clock
| f PLLSAIQ_OUT |     |     |     | -   |     | -   | -   | 216 |     |
| ------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
for SAI
| f   | PLLSAI VCO output |     |     | -   |     | 100 | -   | 432 |     |
| --- | ----------------- | --- | --- | --- | --- | --- | --- | --- | --- |
VCO_OUT
|     |                  |     | VCO freq = 100 MHz |     |     | 75  | -   | 200 |     |
| --- | ---------------- | --- | ------------------ | --- | --- | --- | --- | --- | --- |
| t   | PLLSAI lock time |     |                    |     |     |     |     |     | µs  |
LOCK
|     |     |     | VCO freq = 432 MHz |     |     | 100 | -   | 300 |     |
| --- | --- | --- | ------------------ | --- | --- | --- | --- | --- | --- |
|     |     |     |                    |     | RMS | -   | 90  | -   |     |
Cycle to cycle at
12.288 MHz on
 peak
|     |     |     | 48KHz period,  |     |     |     |  ± 280 |     |     |
| --- | --- | --- | -------------- | --- | --- | --- | ------ | --- | --- |
|     |     |     |                |     | to  | -   |        | -   | ps  |
N=432, R=5
peak
Master SAI clock jitter
Average frequency of
Jitter(3)
12.288 MHz
|     |     |     |     |     |     | -   | 90  | -   | ps  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
N = 432, R = 5
on 1000 samples
Cycle to cycle at 48 KHz
|     | FS clock jitter |     |     |     |     | -   | 400 | -   | ps  |
| --- | --------------- | --- | --- | --- | --- | --- | --- | --- | --- |
on 1000 samples
|     |     |     | DocID029808 Rev 3 |     |     |     |     |     | 139/229 |
| --- | --- | --- | ----------------- | --- | --- | --- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     |     |     |     |     | STM32F722xx STM32F723xx |     |     |     |
| -------------------------- | --- | --- | --- | --- | --- | --- | --- | ----------------------- | --- | --- | --- |
Table 47. PLLISAI characteristics (continued)
| Symbol     |                              | Parameter |     |     |     | Conditions         |     | Min  | Typ | Max  | Unit |
| ---------- | ---------------------------- | --------- | --- | --- | --- | ------------------ | --- | ---- | --- | ---- | ---- |
|            | PLLSAI power consumption on  |           |     |     |     | VCO freq = 100 MHz |     | 0.15 |     | 0.40 |      |
| I          | (4)                          |           |     |     |     |                    |     |      | -   |      | mA   |
| DD(PLLSAI) | V                            |           |     |     |     | VCO freq = 432 MHz |     | 0.45 |     | 0.75 |      |
DD
|             | PLLSAI power consumption on  |     |     |     |     | VCO freq = 100 MHz |     | 0.30 |     | 0.40 |     |
| ----------- | ---------------------------- | --- | --- | --- | --- | ------------------ | --- | ---- | --- | ---- | --- |
| I           | (4)                          |     |     |     |     |                    |     |      | -   |      | mA  |
| DDA(PLLSAI) | V                            |     |     |     |     | VCO freq = 432 MHz |     | 0.55 |     | 0.85 |     |
DDA
1. Take care of using the appropriate division factor M to have the specified PLL input clock values.
2. Guaranteed by design.
3. Value given with main PLL running.
4. Guaranteed by characterization results.
5.3.12  PLL spread spectrum clock generation (SSCG) characteristics
The spread spectrum clock generation (SSCG) feature allows to reduce electromagnetic
interferences (see Table 58: EMI characteristics). It is available only on the main PLL.
|     |            |     | Table 48. SSCG parameters constraint  |     |     |     |     |     |     |     |     |
| --- | ---------- | --- | ------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Max(1)
|     | Symbol |     |     |                      | Parameter |     |     | Min | Typ |     | Unit |
| --- | ------ | --- | --- | -------------------- | --------- | --- | --- | --- | --- | --- | ---- |
|     | f      |     |     | Modulation frequency |           |     |     | -   | -   | 10  | KHz  |
Mod
|                   | md  |     |     | Peak modulation depth |     |     |     | 0.25 | -   | 2     | %   |
| ----------------- | --- | --- | --- | --------------------- | --- | --- | --- | ---- | --- | ----- | --- |
| MODEPER * INCSTEP |     |     |     |                       |     | -   |     | -    | -   | 215−1 | -   |
1. Guaranteed by design.
Equation 1
The frequency modulation period (MODEPER) is given by the equation below:
|     |     |     |     | MODEPER |     | = round[f | ⁄   | (4× f )] |     |     |     |
| --- | --- | --- | --- | ------- | --- | --------- | --- | -------- | --- | --- | --- |
PLL_IN Mod
|     | f       | and f | must be expressed in Hz. |     |     |     |     |     |     |     |     |
| --- | ------- | ----- | ------------------------ | --- | --- | --- | --- | --- | --- | --- | --- |
|     | PLL_IN  | Mod   |                          |     |     |     |     |     |     |     |     |
As an example:
If f = 1 MHz, and f = 1 kHz, the modulation depth (MODEPER) is given by
|     | PLL_IN  |     |     | MOD  |     |     |     |     |     |     |     |
| --- | ------- | --- | --- | ---- | --- | --- | --- | --- | --- | --- | --- |
equation 1:
|     |     |     |     |         |     | round[10 | 6⁄ (4× | 3)]      |     |     |     |
| --- | --- | --- | --- | ------- | --- | -------- | ------ | -------- | --- | --- | --- |
|     |     |     |     | MODEPER |     | =        |        | 10 = 250 |     |     |     |
Equation 2
Equation 2 allows to calculate the increment step (INCSTEP):
|     |     | INCSTEP                   |     | = round[((2 |     | 15 –1)× md× | PLLN)⁄ | (100× 5× | MODEPER)] |     |     |
| --- | --- | ------------------------- | --- | ----------- | --- | ----------- | ------ | -------- | --------- | --- | --- |
|     | f   | must be expressed in MHz. |     |             |     |             |        |          |           |     |     |
VCO_OUT
With a modulation depth (md) = ±2 % (4 % peak to peak), and PLLN = 240 (in MHz):
|         |         |     | round[((2 |     | 15 –1)×           | 2× 240)⁄ (100× | 5×  | 250)]                 |     |     |     |
| ------- | ------- | --- | --------- | --- | ----------------- | -------------- | --- | --------------------- | --- | --- | --- |
|         | INCSTEP |     | =         |     |                   |                |     | = 126md(quantitazed)% |     |     |     |
| 140/229 |         |     |           |     | DocID029808 Rev 3 |                |     |                       |     |     |     |

STM32F722xx STM32F723xx Electrical characteristics
An amplitude quantization error may be generated because the linear modulation profile is
obtained by taking the quantized values (rounded to the nearest integer) of MODPER and
INCSTEP. As a result, the achieved modulation depth is quantized. The percentage
quantized modulation depth is given by the following formula:
md % = (MODEPER× INCSTEP× 100× 5)⁄ ((2 15 –1)× PLLN)
quantized
As a result:
md % = (250× 126× 100× 5)⁄ ((2 15 –1)× 240) = 2.002%(peak)
quantized
Figure 42 and Figure 43 show the main PLL output clock waveforms in center spread and
down spread modes, where:
F0 is f nominal.
PLL_OUT
T is the modulation period.
mode
md is the modulation depth.
Figure 42. PLL output clock waveforms in center spread mode
(cid:38)(cid:82)(cid:69)(cid:81)(cid:85)(cid:69)(cid:78)(cid:67)(cid:89)(cid:0)(cid:8)(cid:48)(cid:44)(cid:44)(cid:63)(cid:47)(cid:53)(cid:52)(cid:9)
(cid:77)(cid:68)
(cid:38)(cid:16)
(cid:77)(cid:68)
(cid:52)(cid:73)(cid:77)(cid:69)
(cid:84)(cid:77)(cid:79)(cid:68)(cid:69) (cid:18)(cid:88)(cid:84)(cid:77)(cid:79)(cid:68)(cid:69)
(cid:65)(cid:73)(cid:17)(cid:23)(cid:18)(cid:25)(cid:17)
Figure 43. PLL output clock waveforms in down spread mode
(cid:41)(cid:85)(cid:72)(cid:84)(cid:88)(cid:72)(cid:81)(cid:70)(cid:92)(cid:3)(cid:11)(cid:51)(cid:47)(cid:47)(cid:66)(cid:50)(cid:56)(cid:55)(cid:12)
(cid:41)(cid:19)
(cid:21)(cid:91)(cid:80)(cid:71)
(cid:55)(cid:76)(cid:80)(cid:72)
(cid:87)(cid:80)(cid:82)(cid:71)(cid:72) (cid:21)(cid:91)(cid:87)(cid:80)(cid:82)(cid:71)(cid:72)
(cid:68)(cid:76)(cid:20)(cid:26)(cid:21)(cid:28)(cid:21)(cid:69)
DocID029808 Rev 3 141/229
201

Electrical characteristics STM32F722xx STM32F723xx
5.3.13  USB OTG HS PHY PLLs characteristics (on STM32F723xx devices)
The parameters given in Table 49 are derived from tests performed under temperature and
V  supply voltage conditions summarized in Table 17.
DD
|                    | Table 49. USB OTG HS PLL1 characteristics(1)  |     |            |     |                      |     |     |      |
| ------------------ | --------------------------------------------- | --- | ---------- | --- | -------------------- | --- | --- | ---- |
| Symbol             | Parameter                                     |     | Conditions |     |  Min                 | Typ | Max | Unit |
| f PLL1 input clock |                                               |     | -          |     | 12, 12.5, 16, 24, 25 |     |     |      |
PLL1_IN
| f PLL1 output clock(2) |     |     | -   |     | -   | 60  | -   | MHz |
| ---------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
PLL1_OUT
| f PLL1 VCO output |     |     | -   |     | 600 | -   | 720 |     |
| ----------------- | --- | --- | --- | --- | --- | --- | --- | --- |
VCO_OUT
| t PLL1 lock time(2) |     |     | -   |     | -   | -   | 22  | µs  |
| ------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
LOCK
| I DD(PLL1) PLL1 digital power consumption |     |     | -   |     | -   | -   | 1.8 |     |
| ----------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
mA
| I PLL1 analog power consumption |     |     | -   |     | -   | -   | 2.75 |     |
| ------------------------------- | --- | --- | --- | --- | --- | --- | ---- | --- |
DDA(PLL1)
1. Guaranteed by design.
2. Based on test during characterization.
Table 50. USB OTG HS PLL2 characteristics(1)

| Symbol             | Parameter |     | Conditions |     |  Min | Typ | Max | Unit |
| ------------------ | --------- | --- | ---------- | --- | ---- | --- | --- | ---- |
| f PLL2 input clock |           |     | -          |     | -    | 60  | -   |      |
PLL2_IN
PLL2 output clock(2)
| f PLL2_OUT        |     |     | -   |     | -   | 480 | -   | MHz |
| ----------------- | --- | --- | --- | --- | --- | --- | --- | --- |
| f PLL2 VCO output |     |     | -   |     | -   | 480 | -   |     |
VCO_OUT
PLL2 lock time(2)
| t LOCK                           |     |     | -   |     | -   | -   | 91  | µs  |
| -------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
| I PLL2 digital power consumption |     |     | -   |     | -   | -   | 2.1 |     |
DD(PLL2)
mA
| I PLL2 analog power consumption |     |     | -   |     | -   | -   | 1.5 |     |
| ------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
DDA(PLL2)
1. Guaranteed by design.
2. Based on test during characterization.
5.3.14  USB OTG HS PHY regulator characteristics (on
STM32F723xx devices)
The parameters given in Table 51 are derived from tests performed under temperature and
V DD  supply voltage conditions summarized in Table 17.
           Table 51. USB OTG HS PHY regulator characteristics(1)
| Symbol    |                             | Parameter | Conditions |     | Min  | Typ | Max  | Unit |
| --------- | --------------------------- | --------- | ---------- | --- | ---- | --- | ---- | ---- |
| V         | 1.2 V internal voltage on V |           |            | -   | 1.18 | 1.2 | 1.24 | V    |
| DD12OTGHS |                             | DD12OTGHS |            |     |      |     |      |      |
| CEXT      | External capacitor on V     |           |            | -   | 1.1  | 2.2 | 3.3  | µF   |
DD12OTGHS
| I DDPHYHSREG | Regulator power consumption |     |     | -   | 100 | 120 | 125 | µA  |
| ------------ | --------------------------- | --- | --- | --- | --- | --- | --- | --- |
1. Based on test during characterization.
142/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
5.3.15  USB HS PHY external resistor characteristics (on
STM32F723xx devices)
          Table 52. USB HS PHY external resistor characteristics (on STM32F723xx devices)
| Symbol |     | Parameter |     | Conditions | Min | Typ | Max Unit |
| ------ | --- | --------- | --- | ---------- | --- | --- | -------- |
External calibration resistor connected  Required if using  kΩ
| REXT |                           |     |     |            | 2.97 | 3.00 | 3.03 |
| ---- | ------------------------- | --- | --- | ---------- | ---- | ---- | ---- |
|      | (to GND) from OTG_HS_REXT |     |     | USB HS PHY |      |      |      |
5.3.16  Memory characteristics
Flash memory
The characteristics are given at TA = –40 to 105 °C unless otherwise specified.
The devices are shipped to customers with the Flash memory erased.
|            |           | Table 53. Flash memory characteristics  |            |          |     |     |          |
| ---------- | --------- | --------------------------------------- | ---------- | -------- | --- | --- | -------- |
| Symbol     | Parameter |                                         | Conditions |          | Min | Typ | Max Unit |
|            |           | Write / Erase 8-bit mode, V             |            |  = 1.7 V | -   | 6.7 | -        |
DD
I Supply current Write / Erase 16-bit mode, V  = 2.1 V - 9.2 - mA
| DD         |     |                                     |             | DD          |        |      |        |
| ---------- | --- | ----------------------------------- | ----------- | ----------- | ------ | ---- | ------ |
|            |     | Write / Erase 32-bit mode, V        |             | DD  = 3.3 V | -      | 12.6 | -      |
|            |     | Table 54. Flash memory programming  |             |             |        |      |        |
|            |     |                                     |             |             | Min(1) |      | Max(1) |
| Symbol     |     | Parameter                           |  Conditions |             |        | Typ  | Unit   |
Program/erase parallelism
100(2)
| t prog | Word programming time |     |     |     | -   | 16  | µs  |
| ------ | --------------------- | --- | --- | --- | --- | --- | --- |
(PSIZE) = x 8/16/32
Program/erase parallelism
|     |     |     |     |     | -   | 346 | 418 |
| --- | --- | --- | --- | --- | --- | --- | --- |
(PSIZE) = x 8
Program/erase parallelism
| t         | Sector (16 KB) erase time |     |                |     | -   | 252 | 312 ms |
| --------- | ------------------------- | --- | -------------- | --- | --- | --- | ------ |
| ERASE16KB |                           |     | (PSIZE) = x 16 |     |     |     |        |
Program/erase parallelism
|     |     |     |     |     | -   | 208 | 265 |
| --- | --- | --- | --- | --- | --- | --- | --- |
(PSIZE) = x 32
Program/erase parallelism
|     |     |     |     |     | -   | 1953 | 2500 |
| --- | --- | --- | --- | --- | --- | ---- | ---- |
(PSIZE) = x 8
Program/erase parallelism
| t ERASE128KB | Sector (128 KB) erase time |     |     |     | -   | 1252 | 1639 ms |
| ------------ | -------------------------- | --- | --- | --- | --- | ---- | ------- |
(PSIZE) = x 16
Program/erase parallelism
|     |     |     |     |     | -   | 927 | 1322 |
| --- | --- | --- | --- | --- | --- | --- | ---- |
(PSIZE) = x 32
Program/erase parallelism
|     |     |     |     |     | -   | 1027 | 1298 |
| --- | --- | --- | --- | --- | --- | ---- | ---- |
(PSIZE) = x 8
Program/erase parallelism
| t         | Sector (64 KB) erase time |     |                |     | -   | 675 | 840 ms |
| --------- | ------------------------- | --- | -------------- | --- | --- | --- | ------ |
| ERASE64KB |                           |     | (PSIZE) = x 16 |     |     |     |        |
Program/erase parallelism
|     |     |     |     |     | -   | 505 | 682 |
| --- | --- | --- | --- | --- | --- | --- | --- |
(PSIZE) = x 32
|     |     | DocID029808 Rev 3 |     |     |     |     | 143/229 |
| --- | --- | ----------------- | --- | --- | --- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
Table 54. Flash memory programming (continued)
|        |     |           |     |             | Min(1) |     | Max(1) |      |
| ------ | --- | --------- | --- | ----------- | ------ | --- | ------ | ---- |
| Symbol |     | Parameter |     |  Conditions |        | Typ |        | Unit |
Program/erase parallelism
|     |     |     |     |     |     | - 7718 | 9883 |     |
| --- | --- | --- | --- | --- | --- | ------ | ---- | --- |
(PSIZE) = x 8
Program/erase parallelism
| t   | Mass erase time |     |                |     |     | - 4869 | 6379 | ms  |
| --- | --------------- | --- | -------------- | --- | --- | ------ | ---- | --- |
| ME  |                 |     | (PSIZE) = x 16 |     |     |        |      |     |
Program/erase parallelism
|     |     |     |     |     |     | - 3503 | 5180 |     |
| --- | --- | --- | --- | --- | --- | ------ | ---- | --- |
(PSIZE) = x 32
|     |                     |     | 32-bit program operation |     | 2.7 |     | -   | 3 V   |
| --- | ------------------- | --- | ------------------------ | --- | --- | --- | --- | ----- |
| V   | Programming voltage |     | 16-bit program operation |     | 2.1 |     | -   | 3.6 V |
prog
|     |     |     | 8-bit program operation |     | 1.7 |     | -   | 3.6 V |
| --- | --- | --- | ----------------------- | --- | --- | --- | --- | ----- |
1. Guaranteed by characterization results.
2. The maximum programming time is measured after 10 K erase operations.

|        |     | Table 55. Flash memory programming with V |     |             |        | PP   |        |      |
| ------ | --- | ----------------------------------------- | --- | ----------- | ------ | ---- | ------ | ---- |
| Symbol |     | Parameter                                 |     |  Conditions | Min(1) | Typ  | Max(1) | Unit |
100(2)
| t   | Double word programming |     |     |     | -   | 16  |     | µs  |
| --- | ----------------------- | --- | --- | --- | --- | --- | --- | --- |
prog
| t         | Sector (16 KB) erase time |     |     |                  | -   | 180 |     | -   |
| --------- | ------------------------- | --- | --- | ---------------- | --- | --- | --- | --- |
| ERASE16KB |                           |     |     | T  = 0 to +40 °C |     |     |     |     |
A
t ERASE128KB Sector (128 KB) erase time V DD  = 3.3 V - 900 - ms
V  = 8.5 V
| t   | Sector (64 KB) erase time |     |     | PP  | -   | 450 |     | -   |
| --- | ------------------------- | --- | --- | --- | --- | --- | --- | --- |
ERASE64KB
| t ME | Mass erase time     |     |     |     | -   | 6.9 |     | - s   |
| ---- | ------------------- | --- | --- | --- | --- | --- | --- | ----- |
| V    | Programming voltage |     |     | -   | 2.7 | -   |     | 3.6 V |
prog
| V   | V   |  voltage range |     | -   | 7   | -   |     | 9 V |
| --- | --- | -------------- | --- | --- | --- | --- | --- | --- |
| PP  | PP  |                |     |     |     |     |     |     |
Minimum current sunk on
| I   |       |      |     | -   | 10  | -   |     | - mA |
| --- | ----- | ---- | --- | --- | --- | --- | --- | ---- |
| PP  | the V |  pin |     |     |     |     |     |      |
PP
Cumulative time during
| t (3) |     |     |     | -   | -   | -   |     | 1 hour |
| ----- | --- | --- | --- | --- | --- | --- | --- | ------ |
VPP
|     | which V | PP  is applied |     |     |     |     |     |     |
| --- | ------- | -------------- | --- | --- | --- | --- | --- | --- |
1. Guaranteed by design.
2. The maximum programming time is measured after 10 K erase operations.
3. V PP  should only be connected during programming/erasing.
           Table 56. Flash memory endurance and data retention
Value
 Conditions(1)
| Symbol | Parameter |     |     |     |     |     |     | Unit |
| ------ | --------- | --- | --- | --- | --- | --- | --- | ---- |
Min(2)
T A  = –40 to +85 °C (6 suffix versions)
| N   | Endurance |                                         |     |     |     | 10  |     | kcycles |
| --- | --------- | --------------------------------------- | --- | --- | --- | --- | --- | ------- |
| END |           | T  = –40 to +105 °C (7 suffix versions) |     |     |     |     |     |         |
A
1 kcycle(3) at T
|     |                |                  | A  = 85 °C |     |     | 30  |     |       |
| --- | -------------- | ---------------- | ---------- | --- | --- | --- | --- | ----- |
| t   | Data retention | 1 kcycle(3) at T |  = 105 °C  |     |     | 10  |     | Years |
| RET |                |                  | A          |     |     |     |     |       |
10 kcycles(3) at T
|     |     |     |     | A  = 55 °C |     | 20  |     |     |
| --- | --- | --- | --- | ---------- | --- | --- | --- | --- |
144/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
1. Tj can not go above 125°C (current consumption limitation).
2. Guaranteed by characterization results.
3. Cycling performed over the whole temperature range.
5.3.17 EMC characteristics
Susceptibility tests are performed on a sample basis during device characterization.
Functional EMS (electromagnetic susceptibility)
While a simple application is executed on the device (toggling 2 LEDs through I/O ports).
the device is stressed by two electromagnetic events until a failure occurs. The failure is
indicated by the LEDs:
• Electrostatic discharge (ESD) (positive and negative) is applied to all device pins until
a functional disturbance occurs. This test is compliant with the IEC 61000-4-2 standard.
• FTB: A burst of fast transient voltage (positive and negative) is applied to V and V
DD SS
through a 100 pF capacitor, until a functional disturbance occurs. This test is compliant
with the IEC 61000-4-4 standard.
A device reset allows normal operations to be resumed.
The test results are given in Table 57. They are based on the EMS levels and classes
defined in application note AN1709.
Table 57. EMS characteristics
Level/
Symbol Parameter Conditions
Class
V = 3.3 V, LQFP176, T =
Voltage limits to be applied on any I/O pin to DD A
V +25 °C, f = 216 MHz, conforms 2B
FESD induce a functional disturbance HCLK
to IEC 61000-4-2
Fast transient voltage burst limits to be V = 3.3 V, TFBGA216, T
DD A
V applied through 100 pF on V and V =+25 °C, f = 216 MHz, 5A
EFTB DD SS HCLK
pins to induce a functional disturbance conforms to IEC 61000-4-2
As a consequence, it is recommended to add a serial resistor (1 kΏ) located as close as
possible to the MCU to the pins exposed to noise (connected to tracks longer than 50 mm
on PCB).
Designing hardened software to avoid noise problems
EMC characterization and optimization are performed at component level with a typical
application environment and simplified MCU software. It should be noted that good EMC
performance is highly dependent on the user application and the software in particular.
Therefore it is recommended that the user applies EMC software optimization and
prequalification tests in relation with the EMC level requested for his application.
Software recommendations
The software flowchart must include the management of runaway conditions such as:
• Corrupted program counter
• Unexpected reset
DocID029808 Rev 3 145/229
201

| Electrical characteristics |     |     |     | STM32F722xx STM32F723xx |     |     |
| -------------------------- | --- | --- | --- | ----------------------- | --- | --- |
• Critical Data corruption (control registers...)
Prequalification trials
Most of the common failures (unexpected reset and program counter corruption) can be
reproduced by manually forcing a low state on the NRST pin or the Oscillator pins for 1
second.
To complete these trials, ESD stress can be applied directly on the device, over the range of
specification values. When unexpected behavior is detected, the software can be hardened
to prevent unrecoverable errors occurring (see application note AN1015).
Electromagnetic Interference (EMI)
The electromagnetic field emitted by the device are monitored while a simple application,
executing EEMBC code, is running. This emission test is compliant with SAE IEC61967-2
standard which specifies the test board and the pin loading.

Table 58. EMI characteristics
Max vs.
|                  |     |            |     | Monitored  | [f /f   | ]    |
| ---------------- | --- | ---------- | --- | ---------- | ------- | ---- |
| Symbol Parameter |     | Conditions |     |            | HSE CPU | Unit |
frequency band
25/200 MHz
|                                                           |                                                |                            |     | 0.1 MHz to 30 MHz | 23  |      |
| --------------------------------------------------------- | ---------------------------------------------- | -------------------------- | --- | ----------------- | --- | ---- |
|                                                           | V = 3.6 V, T                                   | = 25 °C, LQFP176 package,  |     | 30 MHz to 130 MHz | 20  |      |
|                                                           | DD                                             | A                          |     |                   |     |      |
|                                                           | conforming to IEC61967-2 ART/L1-cache OFF,     |                            |     |                   |     | dBµV |
| S Peak level                                              |                                                |                            |     | 130 MHz to 1 GHz  | 34  |      |
| EMI                                                       | over-drive ON, all peripheral clocks enabled,  |                            |     |                   |     |      |
|                                                           | clock dithering disabled.                      |                            |     | 1 GHz to  2 GHz   | 24  |      |
|                                                           |                                                |                            |     | EMI Level         | 4   | -    |
| 5.3.18  Absolute maximum ratings (electrical sensitivity) |                                                |                            |     |                   |     |      |
Based on three different tests (ESD, LU) using specific measurement methods, the device is
stressed in order to determine its performance in terms of electrical sensitivity.
Electrostatic discharge (ESD)
Electrostatic discharges (a positive then a negative pulse separated by 1 second) are
applied to the pins of each sample according to each pin combination. The sample size
depends on the number of supply pins in the device (3 parts × (n+1) supply pins). This test
conforms to the ANSI/ESDA/JEDEC JS-001-2012 and ANSI/ESD S5.3.1-2009 standards.
            Table 59. ESD absolute maximum ratings
Maximum
| Symbol | Ratings |     | Conditions |     | Class | Unit |
| ------ | ------- | --- | ---------- | --- | ----- | ---- |
value(1)
Electrostatic discharge  T = +25 °C conforming to
| V                                   |     | A                                |     |     | 2 2000 |     |
| ----------------------------------- | --- | -------------------------------- | --- | --- | ------ | --- |
| ESD(HBM) voltage (human body model) |     | ANSI/ESDA/JEDEC JS-001-2012      |     |     |        |     |
|                                     |     | = +25 °C conforming to ANSI/ESD  |     |     |        | V   |
T A
Electrostatic discharge
| V   |     | STM5.3.1-2009, all the packages  |     |     | 3 250 |     |
| --- | --- | -------------------------------- | --- | --- | ----- | --- |
ESD(CDM) voltage (charge device model)
excepted WLCSP100
1. Guaranteed by characterization results.
| 146/229 |     | DocID029808 Rev 3 |     |     |     |     |
| ------- | --- | ----------------- | --- | --- | --- | --- |

| STM32F722xx STM32F723xx |     |     |     | Electrical characteristics |     |
| ----------------------- | --- | --- | --- | -------------------------- | --- |
Static latchup
Two complementary static tests are required on six parts to assess the latchup
performance:
•
A supply overvoltage is applied to each power supply pin
•
A current injection is applied to each input, output and configurable I/O pin
These tests are compliant with EIA/JESD 78A IC latchup standard.
|            |           | Table 60. Electrical sensitivities |            |     |       |
| ---------- | --------- | ---------------------------------- | ---------- | --- | ----- |
| Symbol     | Parameter |                                    | Conditions |     | Class |
LU Static latch-up class T = +105 °C conforming to JESD78A II level A
A
| 5.3.19  I/O current injection characteristics |     |     |     |     |     |
| --------------------------------------------- | --- | --- | --- | --- | --- |
As a general rule, current injection to the I/O pins, due to external voltage below V  or
SS
above V  (for standard, 3 V-capable I/O pins) should be avoided during normal product
DD
operation. However, in order to give an indication of the robustness of the microcontroller in
cases when abnormal injection accidentally happens, susceptibility tests are performed on a
sample basis during device characterization.
Functional susceptibilty to I/O current injection
While a simple application is executed on the device, the device is stressed by injecting
current into the I/O pins programmed in floating input mode. While current is injected into
the I/O pin, one at a time, the device is checked for functional failures.
The failure is indicated by an out of range parameter: ADC error above a certain limit (>5
LSB TUE), out of conventional limits of induced leakage current on adjacent pins (out of –
5 µA/+0 µA range), or other functional failure (for example reset, oscillator frequency
deviation).
Negative induced leakage current is caused by negative injection and positive induced
leakage current by positive injection.
The test results are given in Table 61.
           Table 61. I/O current injection susceptibility
Functional susceptibility
| Symbol |     | Description |     |           | Unit      |
| ------ | --- | ----------- | --- | --------- | --------- |
|        |     |             |     | Negative  | Positive  |
|        |     |             |     | injection | injection |
Injected current on BOOT0, PDR_ON, BYPASS_REG,
|     |     |     |     | -0  | 0   |
| --- | --- | --- | --- | --- | --- |
OTG_HS_REXT
NA(1)
|     | Injected current on NRST  |     |     | -0  |     |
| --- | ------------------------- | --- | --- | --- | --- |
I Injected current on PF9, PF10, PH0_OSCIN, PH1_OSCOUT, PC0,  mA
| INJ |     |     |     | -0  | NA(1) |
| --- | --- | --- | --- | --- | ----- |
PC1, PC2, PC3, PB14(2), PB15(2)
NA(1)
|     | Injected current on any other FT or FTf pins  |     |     | -5  |     |
| --- | --------------------------------------------- | --- | --- | --- | --- |
|     | Injected current on any other pins            |     |     | -5  | +5  |
1. Injection is not possible.
|     |     | DocID029808 Rev 3 |     |     | 147/229 |
| --- | --- | ----------------- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     |     |     | STM32F722xx STM32F723xx |     |     |
| -------------------------- | --- | --- | --- | --- | --- | ----------------------- | --- | --- |
2. PB14 and PB15 in the STM32F723xx devices.
Note: It is recommended to add a Schottky diode (pin to ground) to analog pins which may
potentially inject negative currents.
| 5.3.20  | I/O port characteristics |     |     |     |     |     |     |     |
| ------- | ------------------------ | --- | --- | --- | --- | --- | --- | --- |
General input/output characteristics
Unless otherwise specified, the parameters given in Table 62: I/O static characteristics are
derived from tests performed under the conditions summarized in Table 17. All I/Os are
CMOS and TTL compliant.
|        |                             | Table 62. I/O static characteristics  |                  |     |     |       |          |      |
| ------ | --------------------------- | ------------------------------------- | ---------------- | --- | --- | ----- | -------- | ---- |
| Symbol |                             | Parameter                             | Conditions       |     | Min | Typ   | Max      | Unit |
|        |                             |                                       |                  |     |     | 0.35V | −0.04(1) |      |
|        | FT, TTa and NRST I/O input  |                                       |                  |     |     |       | DD       |      |
|        |                             |                                       | 1.7 V≤ V ≤ 3.6 V |     | -   | -     |          |      |
|        | low level voltage           |                                       | DD               |     |     |       | (2)      |      |
0.3V
DD
1.75 V≤ V ≤ 3.6 V, –
| V IL |     |     | DD  |     | -   | -   |     | V   |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- |
40 °C≤ T ≤ 105 °C
|     | BOOT I/O input low level  |     | A   |     |     |     |              |     |
| --- | ------------------------- | --- | --- | --- | --- | --- | ------------ | --- |
|     |                           |     |     |     |     |     | 0.1V +0.1(1) |     |
|     | voltage                   |     |     |     |     |     | DD           |     |
1.7 V≤ V ≤ 3.6 V,
|     |     |     | DD  |     | -   | -   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
0 °C≤ T ≤ 105 °C
A
0.45V +0.3(1)
|     | FT, TTa and NRST I/O input  |     |                  |     | DD  |     |     |     |
| --- | --------------------------- | --- | ---------------- | --- | --- | --- | --- | --- |
|     |                             |     | 1.7 V≤ V ≤ 3.6 V |     |     | -   | -   |     |
|     | high level voltage(5)       |     | DD               |     | (2) |     |     |     |
0.7V
DD
1.75 V≤ V ≤ 3.6 V, –
| V IH |     |     | DD  |     |     |     |     | V   |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- |
40 °C≤ T ≤ 105 °C
|     | BOOT I/O input high level  |     | A   |       |         |     |     |     |
| --- | -------------------------- | --- | --- | ----- | ------- | --- | --- | --- |
|     |                            |     |     | 0.17V | +0.7(1) | -   | -   |     |
|     | voltage                    |     |     |       | DD      |     |     |     |
1.7 V≤ V ≤ 3.6 V,
DD
0 °C≤ T ≤ 105 °C
A
FT, TTa and NRST I/O input
|     |     |     | 1.7 V≤ V ≤ 3.6 V |      | (3) |     |     |     |
| --- | --- | --- | ---------------- | ---- | --- | --- | --- | --- |
|     |     |     | DD               | 10%V | DD  | -   | -   |     |
hysteresis
1.75 V≤ V ≤ 3.6 V, –
| V   |     |     | DD                |     |     |     |     | V   |
| --- | --- | --- | ----------------- | --- | --- | --- | --- | --- |
| HYS |     |     | 40 °C≤ T ≤ 105 °C |     |     |     |     |     |
A
|     | BOOT I/O input hysteresis |     |     |     | 0.1 | -   | -   |     |
| --- | ------------------------- | --- | --- | --- | --- | --- | --- | --- |
1.7 V≤ V ≤ 3.6 V,
DD
0 °C≤ T ≤ 105 °C
A
|         | I/O input leakage current (4)    |     | V ≤ V ≤ V         |     | -   | -   | ±1  |     |
| ------- | -------------------------------- | --- | ----------------- | --- | --- | --- | --- | --- |
|         |                                  |     | SS  IN  DD        |     |     |     |     |     |
| I       |                                  |     |                   |     |     |     |     | µA  |
| lkg     | I/O FT input leakage current (5) |     | = 5 V             |     |     |     |     |     |
|         |                                  |     | V IN              |     | -   | -   | 3   |     |
| 148/229 |                                  |     | DocID029808 Rev 3 |     |     |     |     |     |

| STM32F722xx STM32F723xx |     |     |     | Electrical characteristics |     |
| ----------------------- | --- | --- | --- | -------------------------- | --- |
Table 62. I/O static characteristics (continued)
| Symbol | Parameter | Conditions | Min | Typ  | Max Unit |
| ------ | --------- | ---------- | --- | ---- | -------- |
All pins
except for
PA10/PB12
|     |     |     | 30  | 40  | 50  |
| --- | --- | --- | --- | --- | --- |
(OTG_FS_ID
| Weak pull-up  | ,OTG_HS_ID |        |     |     |     |
| ------------- | ---------- | ------ | --- | --- | --- |
| R equivalent  |            | V = V  |     |     |     |
| PU            | )          | IN  SS |     |     |     |
resistor(6)
PA10/PB12
(OTG_FS_ID
|     |     |     | 7   | 10  | 14  |
| --- | --- | --- | --- | --- | --- |
,OTG_HS_ID
)
kΩ
All pins
except for
PA10/PB12
|            |            |     | 30  | 40  | 50  |
| ---------- | ---------- | --- | --- | --- | --- |
| Weak pull- | (OTG_FS_ID |     |     |     |     |
| down       | ,OTG_HS_ID |     |     |     |     |
= V
| R PD | )   | V IN  DD |     |     |     |
| ---- | --- | -------- | --- | --- | --- |
equivalent
resistor(7)
 PA10/PB12
(OTG_FS_ID
|     |     |     | 7   | 10  | 14  |
| --- | --- | --- | --- | --- | --- |
,OTG_HS_ID
)
| C (8) I/O pin capacitance |     | -   | -   | 5   | - pF |
| ------------------------- | --- | --- | --- | --- | ---- |
IO
1. Guaranteed by design.
2. Tested in production.
3. With a minimum of 200 mV.
4. Leakage could be higher than the maximum value, if negative current is injected on adjacent pins, Refer to Table 61: I/O
current injection susceptibility
5. To sustain a voltage higher than VDD +0.3 V, the internal pull-up/pull-down resistors must be disabled. Leakage could be
higher than the maximum value, if negative current is injected on adjacent pins.Refer to Table 61: I/O current injection
susceptibility
6. Pull-up resistors are designed with a true resistance in series with a switchable PMOS. This PMOS contribution to the
series resistance is minimum (~10% order).
7. Pull-down resistors are designed with a true resistance in series with a switchable NMOS. This NMOS contribution to the
series resistance is minimum (~10% order).
8.  Hysteresis voltage between Schmitt trigger switching levels. Guaranteed by characterization results.
All I/Os are CMOS and TTL compliant (no software configuration required). Their
characteristics cover more than the strict CMOS-technology or TTL parameters. The
coverage of these requirements for FT I/Os is shown in Figure 44.
|     |     | DocID029808 Rev 3 |     |     | 149/229 |
| --- | --- | ----------------- | --- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
Figure 44. FT I/O input characteristics
(cid:57)(cid:44)(cid:47)(cid:18)(cid:57)(cid:44)(cid:43)(cid:3)(cid:11)(cid:57)(cid:12)
(cid:21)(cid:17)(cid:24)(cid:21) (cid:39)
(cid:39)
(cid:57)
(cid:81)(cid:3)(cid:32)(cid:3)(cid:19)(cid:17)(cid:26)
(cid:80)(cid:76)
(cid:43)
(cid:57)(cid:44)
(cid:81)(cid:87)(cid:3)
(cid:80)(cid:72)
(cid:84)
(cid:88)(cid:76)(cid:85)(cid:72)
(cid:55)(cid:55)(cid:47)(cid:3)(cid:85)(cid:72)(cid:84)(cid:88)(cid:76)(cid:85)(cid:72)(cid:80)(cid:72)(cid:81)(cid:87)(cid:3)
(cid:54)(cid:3)(cid:85)(cid:72)
(cid:57)(cid:44)(cid:43)(cid:80)(cid:76)(cid:81)(cid:3)(cid:32)(cid:3)(cid:21)(cid:57)
(cid:20)
(cid:20)
(cid:21) (cid:17)(cid:28)
(cid:17)
(cid:17)
(cid:26)
(cid:19) (cid:21)
(cid:55)(cid:72)(cid:86)(cid:87)(cid:72)
(cid:71)(cid:3)(cid:76)
(cid:81)(cid:3)
(cid:83)(cid:85) (cid:82)
(cid:71)
(cid:88)(cid:70)(cid:87)(cid:76)
(cid:80)
(cid:82)
(cid:81)
(cid:88)
(cid:3)
(cid:79)
(cid:3)
(cid:68)
(cid:16)(cid:3)
(cid:87)
(cid:38)
(cid:76)(cid:82)
(cid:48)
(cid:81)
(cid:50)
(cid:86)(cid:15)(cid:3)(cid:57)(cid:44)(cid:43)
(cid:80)(cid:76)(cid:81)(cid:32)(cid:3)(cid:19)(cid:17)(cid:23)(cid:24)(cid:57)(cid:39)(cid:39)(cid:14)(cid:19)(cid:17)(cid:22)
(cid:20)(cid:17)
(cid:20)
(cid:20)
(cid:19)
(cid:19)
(cid:17)
(cid:17)
(cid:25)
(cid:20)
(cid:17)
(cid:21)
(cid:27)
(cid:24)
(cid:28)
(cid:21)
(cid:37)(cid:68)(cid:86)(cid:72)(cid:71)(cid:3)(cid:82)(cid:81)(cid:3)(cid:39)
(cid:37)
(cid:72)
(cid:68)
(cid:86)
(cid:86)
(cid:76)(cid:74)
(cid:72)
(cid:81)
(cid:71)
(cid:36)
(cid:3)
(cid:3)
(cid:86)
(cid:82)
(cid:85)
(cid:76)
(cid:81)
(cid:72)
(cid:3)
(cid:68)
(cid:39)
(cid:3)(cid:81)
(cid:72)
(cid:82)
(cid:86)(cid:76)
(cid:87)
(cid:74)
(cid:3)(cid:71)
(cid:81)
(cid:72)
(cid:3)(cid:86)
(cid:87)(cid:72)
(cid:76)(cid:80)
(cid:85)(cid:80)
(cid:88)(cid:79)
(cid:76)
(cid:68)
(cid:81)
(cid:87)
(cid:72)
(cid:76)(cid:82)
(cid:71)
(cid:81) (cid:55) (cid:86) (cid:55)
(cid:15)(cid:3)(cid:57)
(cid:47)(cid:3)
(cid:44)
(cid:85)
(cid:47)
(cid:72)
(cid:80)
(cid:84)
(cid:68)
(cid:88)
(cid:91)
(cid:76)(cid:85)
(cid:32)
(cid:72)
(cid:3)
(cid:80)
(cid:19)(cid:17)
(cid:72)
(cid:22)
(cid:81)
(cid:24)
(cid:87)
(cid:57)
(cid:3)
(cid:39)(cid:39)(cid:16)(cid:19)(cid:17)(cid:19)(cid:23)
(cid:19)(cid:17)(cid:24)(cid:24) (cid:57)(cid:44)(cid:47)(cid:80)(cid:68)(cid:91)(cid:3)(cid:32)(cid:3)(cid:19)(cid:17)(cid:27)(cid:57)
(cid:19)(cid:17)(cid:24)(cid:20)
(cid:55)(cid:72)(cid:86)(cid:87)(cid:72)(cid:71)(cid:3)(cid:76)(cid:81)(cid:3)(cid:83)(cid:85)(cid:82)(cid:71)(cid:88)(cid:70)(cid:87)(cid:76)(cid:82)(cid:81)(cid:3)(cid:3)(cid:16)(cid:3)(cid:38)(cid:48)(cid:50)(cid:54)(cid:3)(cid:85)(cid:72)(cid:84)(cid:88)(cid:76)(cid:85)(cid:72)(cid:80)(cid:72)(cid:81)(cid:87)(cid:3)(cid:57)(cid:44)(cid:47)(cid:80)(cid:68)(cid:91)(cid:3)(cid:32)(cid:3)(cid:19)(cid:17)(cid:22)(cid:57)(cid:39)(cid:39)
(cid:57)(cid:39)(cid:39)(cid:3)(cid:11)(cid:57)(cid:12)
(cid:20)(cid:17)(cid:26) (cid:21)(cid:17)(cid:19) (cid:21)(cid:17)(cid:23) (cid:21)(cid:17)(cid:26) (cid:22)(cid:17)(cid:22) (cid:22)(cid:17)(cid:25)
(cid:48)(cid:54)(cid:22)(cid:22)(cid:26)(cid:23)(cid:25)(cid:57)(cid:21)
Output driving current
The GPIOs (general purpose input/outputs) can sink or source up to ±8 mA, and sink or
source up to ±20 mA (with a relaxed V /V ) except PC13, PC14, PC15 and PI8 which
OL OH
can sink or source up to ±3mA. When using the PC13 to PC15 and PI8 GPIOs in output
mode, the speed should not exceed 2 MHz with a maximum load of 30 pF.
In the user application, the number of I/O pins which can drive current must be limited to
respect the absolute maximum rating specified in Section 5.2. In particular:
• The sum of the currents sourced by all the I/Os on V plus the maximum Run
DD,
consumption of the MCU sourced on V cannot exceed the absolute maximum rating
DD,
ΣI (see Table 15).
VDD
• The sum of the currents sunk by all the I/Os on V plus the maximum Run
SS
consumption of the MCU sunk on V cannot exceed the absolute maximum rating
SS
ΣI (see Table 15).
VSS
Output voltage levels
Unless otherwise specified, the parameters given in Table 63 are derived from tests
performed under ambient temperature and V supply voltage conditions summarized in
DD
Table 17. All I/Os are CMOS and TTL compliant.
150/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics

Table 63. Output voltage characteristics
| Symbol |     | Parameter | Conditions |     | Min | Max Unit |
| ------ | --- | --------- | ---------- | --- | --- | -------- |
CMOS port(2)
(1)
V OL Output low level voltage for an I/O pin  I IO  = +8 mA - 0.4
|     |     |     | 2.7 V ≤ V |  ≤ 3.6 V |     |     |
| --- | --- | --- | --------- | -------- | --- | --- |
DD
CMOS port(2)
| (3) Output high level voltage for an I/O pin  |     |     |              |          |           |     |
| --------------------------------------------- | --- | --- | ------------ | -------- | --------- | --- |
| V OH                                          |     |     | I = -8 mA    |          | V DD −0.4 | - V |
| except PC14                                   |     |     | IO           |          |           |     |
|                                               |     |     | 2.7 V ≤ V DD |  ≤ 3.6 V |           |     |
CMOS port(2)
| V (3) Output high level voltage for PC14 |     |     |               |          | V −0.4 | -   |
| ---------------------------------------- | --- | --- | ------------- | -------- | ------ | --- |
| OH                                       |     |     | I IO  = -2 mA |          | DD     |     |
|                                          |     |     | 2.7 V ≤ V     |  ≤ 3.6 V |        |     |
DD
TTL port(2)
| V (1) Output low level voltage for an I/O pin  |     |     | I =+8mA   |          | -   | 0.4 |
| ---------------------------------------------- | --- | --- | --------- | -------- | --- | --- |
| OL                                             |     |     | IO        |          |     |     |
|                                                |     |     | 2.7 V ≤ V |  ≤ 3.6 V |     |     |
DD
V
TTL port(2)
| (3) Output high level voltage for an I/O pin  |     |     |           |          |     |     |
| --------------------------------------------- | --- | --- | --------- | -------- | --- | --- |
| V                                             |     |     | I =-8mA   |          | 2.4 | -   |
| OH  except PC14                               |     |     | IO        |          |     |     |
|                                               |     |     | 2.7 V ≤ V |  ≤ 3.6 V |     |     |
DD
I = +20 mA
| V (1) Output low level voltage for an I/O pin  |     |     | IO        |          | -   | 1.3(4) |
| ---------------------------------------------- | --- | --- | --------- | -------- | --- | ------ |
| OL                                             |     |     | 2.7 V ≤ V |  ≤ 3.6 V |     |        |
DD
V
| Output high level voltage for an I/O pin  |     |     | I = -20 mA |          |           |     |
| ----------------------------------------- | --- | --- | ---------- | -------- | --------- | --- |
| V (3)                                     |     |     | IO         |          | V −1.3(4) | -   |
| OH except PC14                            |     |     | 2.7 V ≤ V  |  ≤ 3.6 V | DD        |     |
DD
I = +6 mA
| V (1) Output low level voltage for an I/O pin  |     |     | IO        |          | -   | 0.4(4) |
| ---------------------------------------------- | --- | --- | --------- | -------- | --- | ------ |
| OL                                             |     |     | 1.8 V ≤ V |  ≤ 3.6 V |     |        |
DD
V
| Output high level voltage for an I/O pin  |     |     | I = -6 mA |          |           |     |
| ----------------------------------------- | --- | --- | --------- | -------- | --------- | --- |
| V (3)                                     |     |     | IO        |          | V −0.4(4) | -   |
| OH except PC14                            |     |     | 1.8 V ≤ V |  ≤ 3.6 V | DD        |     |
DD
I = +4 mA
| V (1) Output low level voltage for an I/O pin  |     |     | IO        |         | -   | 0.4(5) |
| ---------------------------------------------- | --- | --- | --------- | ------- | --- | ------ |
| OL                                             |     |     | 1.7 V ≤ V |  ≤ 3.6V |     |        |
DD
| Output high level voltage for an I/O pin  |     |     | I = -4 mA |         |           |     |
| ----------------------------------------- | --- | --- | --------- | ------- | --------- | --- |
| V (3)                                     |     |     | IO        |         | V −0.4(5) | - V |
| OH except PC14                            |     |     | 1.7 V ≤ V |  ≤ 3.6V | DD        |     |
DD
I = -1 mA
| V (3) Output high level voltage for PC14 |     |     | IO        |         | V −0.4(5) | -   |
| ---------------------------------------- | --- | --- | --------- | ------- | --------- | --- |
| OH                                       |     |     | 1.7 V ≤ V |  ≤ 3.6V | DD        |     |
DD
1. The I  current sunk by the device must always respect the absolute maximum rating specified in Table 15.
IO
| and the sum of I | IO  (I/O ports and control pins) must not exceed I |     | VSS | .   |     |     |
| ---------------- | -------------------------------------------------- | --- | --- | --- | --- | --- |
2. TTL and CMOS outputs are compatible with JEDEC standards JESD36 and JESD52.
3. The I  current sourced by the device must always respect the absolute maximum rating specified in
IO
| Table 15 and the sum of I |     | IO  (I/O ports and control pins) must not exceed I |     | VDD . |     |     |
| ------------------------- | --- | -------------------------------------------------- | --- | ----- | --- | --- |
4. Based on characterization data.
5. Guaranteed by design.
Input/output AC characteristics
The definition and values of input/output AC characteristics are given in Figure 45 and
Table 64, respectively.
|     |     | DocID029808 Rev 3 |     |     |     | 151/229 |
| --- | --- | ----------------- | --- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     |     |     |     | STM32F722xx STM32F723xx |     |     |     |
| -------------------------- | --- | --- | --- | --- | --- | --- | ----------------------- | --- | --- | --- |
Unless otherwise specified, the parameters given in Table 64 are derived from tests
performed under the ambient temperature and V DD  supply voltage conditions summarized
in Table 17.
Table 64. I/O AC characteristics(1)(2)

OSPEEDRy
| [1:0] bit  | Symbol |     | Parameter |     |     | Conditions |     | Min Typ | Max | Unit |
| ---------- | ------ | --- | --------- | --- | --- | ---------- | --- | ------- | --- | ---- |
value(1)

|     |            |                      |     |     | C L |  = 50 pF, V | DD  ≥ 2.7 V | - - | 4   |     |
| --- | ---------- | -------------------- | --- | --- | --- | ----------- | ----------- | --- | --- | --- |
|     |            |                      |     |     | C   |  = 50 pF, V |  ≥ 1.7 V    | - - | 2   |     |
|     |            |                      |     |     | L   |             | DD          |     |     |     |
|     | f          | Maximum frequency(3) |     |     | C   |  = 10 pF, V |  ≥ 2.7 V    | - - | 8   | MHz |
|     | max(IO)out |                      |     |     | L   |             | DD          |     |     |     |
| 00  |            |                      |     |     | C   |  = 10 pF, V |  ≥ 1.8 V    | - - | 4   |     |
|     |            |                      |     |     | L   |             | DD          |     |     |     |
|     |            |                      |     |     | C   |  = 10 pF, V |  ≥ 1.7 V    | - - | 3   |     |
|     |            |                      |     |     | L   |             | DD          |     |     |     |
Output high to low level fall
|     | t        | /                            |     |     | C     |  = 50 pF, V |  = 1.7 V to  |     |      |     |
| --- | -------- | ---------------------------- | --- | --- | ----- | ----------- | ------------ | --- | ---- | --- |
|     | f(IO)out | time and output low to high  |     |     | L     |             | DD           | - - | 100  | ns  |
|     | t        |                              |     |     | 3.6 V |             |              |     |      |     |
|     | r(IO)out | level rise time              |     |     |       |             |              |     |      |     |
|     |          |                              |     |     | C     | = 50 pF, V  | ≥ 2.7 V      | - - | 25   |     |
|     |          |                              |     |     | L     |             | DD           |     |      |     |
|     |          |                              |     |     | C     | = 50 pF, V  | ≥ 1.8 V      | - - | 12.5 |     |
|     |          |                              |     |     | L     |             | DD           |     |      |     |
|     |          |                              |     |     | C     | = 50 pF, V  | ≥ 1.7 V      | - - | 10   |     |
|     |          |                              |     |     | L     |             | DD           |     |      |     |
|     | f        | Maximum frequency(3)         |     |     |       |             |              |     |      | MHz |
max(IO)out
|     |     |     |     |     | C L  | = 10 pF, V | DD  ≥ 2.7 V | - - | 50  |     |
| --- | --- | --- | --- | --- | ---- | ---------- | ----------- | --- | --- | --- |
|     |     |     |     |     | C    | = 10 pF, V | ≥ 1.8 V     | - - | 20  |     |
|     |     |     |     |     | L    |            | DD          |     |     |     |
01
|     |          |         |               |                    | C              | = 10 pF, V | ≥ 1.7 V  | - - | 12.5 |     |
| --- | -------- | ------- | ------------- | ------------------ | -------------- | ---------- | -------- | --- | ---- | --- |
|     |          |         |               |                    | L              |            | DD       |     |      |     |
|     |          |         |               |                    | C              | = 50 pF, V |  ≥ 2.7 V | - - | 10   |     |
|     |          |         |               |                    | L              |            | DD       |     |      |     |
|     |          | O ut p  | u t h i g h   | t o  l o w  le v   | e l  f a ll  C | = 10 pF, V |  ≥ 2.7 V | - - | 6    |     |
|     | t        | /       |               |                    | L              |            | DD       |     |      |     |
|     | f(IO)out | tim e   | an d   o u    | t p u t  l ow  t o |  h i g h       |            |          |     |      | ns  |
t
|     | r(IO)out | level rise time |     |     | C L  | = 50 pF, V | DD  ≥ 1.7 V | - - | 20    |     |
| --- | -------- | --------------- | --- | --- | ---- | ---------- | ----------- | --- | ----- | --- |
|     |          |                 |     |     | C    | = 10 pF, V |  ≥ 1.7 V    | - - | 10    |     |
|     |          |                 |     |     | L    |            | DD          |     |       |     |
|     |          |                 |     |     | C    | = 40 pF, V | ≥ 2.7 V     | - - | 50(4) |     |
|     |          |                 |     |     | L    |            | DD          |     |       |     |
100(4)
|         |            |                      |               |                    | C            | = 10 pF, V |  ≥ 2.7 V    | - - |      |     |
| ------- | ---------- | -------------------- | ------------- | ------------------ | ------------ | ---------- | ----------- | --- | ---- | --- |
|         |            |                      |               |                    | L            |            | DD          |     |      |     |
|         | f          | Maximum frequency(3) |               |                    | C            | = 40 pF, V |  ≥ 1.7 V    | - - | 25   | MHz |
|         | max(IO)out |                      |               |                    | L            |            | DD          |     |      |     |
|         |            |                      |               |                    | C L          | = 10 pF, V | DD  ≥ 1.8 V | - - | 50   |     |
| 10      |            |                      |               |                    | C            | = 10 pF, V | ≥ 1.7 V     | - - | 42.5 |     |
|         |            |                      |               |                    | L            |            | DD          |     |      |     |
|         |            |                      |               |                    | C            | = 40 pF, V | ≥2.7 V      | - - | 6    |     |
|         |            |                      |               |                    | L            |            | DD          |     |      |     |
|         |            | O ut p               | u t h i g h   | t o  l o w  le v   | e l  f a ll  |            |             |     |      |     |
|         | t          | /                    |               |                    | C            | = 10 pF, V |  ≥ 2.7 V    | - - | 4    |     |
|         | f(IO)out   |                      |               |                    | L            |            | DD          |     |      |     |
|         |            | tim e                | an d   o u    | t p u t  l ow  t o |  h i g h     |            |             |     |      | ns  |
|         | t r(IO)out |                      |               |                    | C            | = 40 pF, V |  ≥ 1.7 V    | - - | 10   |     |
|         |            | level rise time      |               |                    | L            |            | DD          |     |      |     |
|         |            |                      |               |                    | C L          | = 10 pF, V | DD  ≥ 1.7 V | - - | 6    |     |
| 152/229 |            |                      |               | DocID029808 Rev 3  |              |            |             |     |      |     |

| STM32F722xx STM32F723xx |     |     |     |     |     |     |     | Electrical characteristics |     |     |
| ----------------------- | --- | --- | --- | --- | --- | --- | --- | -------------------------- | --- | --- |
Table 64. I/O AC characteristics(1)(2) (continued)
OSPEEDRy
| [1:0] bit  | Symbol |     | Parameter |     |     | Conditions |     | Min Typ | Max | Unit |
| ---------- | ------ | --- | --------- | --- | --- | ---------- | --- | ------- | --- | ---- |
value(1)
|     |              |                      |     |     | C    | = 30 pF, V |  ≥ 2.7 V    | - - | 100(4) |     |
| --- | ------------ | -------------------- | --- | --- | ---- | ---------- | ----------- | --- | ------ | --- |
|     |              |                      |     |     | L    |            | DD          |     |        |     |
|     |              |                      |     |     | C    | = 30 pF, V |  ≥ 1.8 V    | - - | 50     |     |
|     |              |                      |     |     | L    |            | DD          |     |        |     |
|     |              |                      |     |     | C    | = 30 pF, V |  ≥ 1.7 V    | - - | 42.5   |     |
|     |              | Maximum frequency(3) |     |     | L    |            | DD          |     |        |     |
|     | f max(IO)out |                      |     |     |      |            |             |     |        | MHz |
|     |              |                      |     |     | C    | = 10 pF, V | ≥ 2.7 V     | - - | 180(4) |     |
|     |              |                      |     |     | L    |            | DD          |     |        |     |
|     |              |                      |     |     | C L  | = 10 pF, V | DD  ≥ 1.8 V | - - | 100    |     |
|     |              |                      |     |     | C    | = 10 pF, V | ≥ 1.7 V     | - - | 72.5   |     |
|     |              |                      |     |     | L    |            | DD          |     |        |     |
11
|     |          |       |                 |                    | C              | = 30 pF, V | ≥ 2.7 V | - - | 4   |     |
| --- | -------- | ----- | --------------- | ------------------ | -------------- | ---------- | ------- | --- | --- | --- |
|     |          |       |                 |                    | L              |            | DD      |     |     |     |
|     |          |       |                 |                    | C              | = 30 pF, V |  ≥1.8 V | - - | 6   |     |
|     |          |       |                 |                    | L              |            | DD      |     |     |     |
|     |          | O ut  | p u t h i g h   | t o  l o w  le v   | e l  f a ll  C | = 30 pF, V |  ≥1.7 V | - - | 7   |     |
|     | t        | /     |                 |                    | L              |            | DD      |     |     |     |
|     | f(IO)out | tim e |   an d   o u    | t p u t  l ow  t o |  h i g h       |            |         |     |     | ns  |
t
|     | r(IO)out | level rise time |     |     | C L  | = 10 pF, V | DD  ≥ 2.7 V | - - | 2.5 |     |
| --- | -------- | --------------- | --- | --- | ---- | ---------- | ----------- | --- | --- | --- |
|     |          |                 |     |     | C    | = 10 pF, V | ≥1.8 V      | - - | 3.5 |     |
|     |          |                 |     |     | L    |            | DD          |     |     |     |
|     |          |                 |     |     | C    | = 10 pF, V | ≥1.7 V      | - - | 4   |     |
|     |          |                 |     |     | L    |            | DD          |     |     |     |
Pulse width of external signals
| -   | tEXTIpw | detected by the EXTI  |     |     |     |     | -   | 10 - | -   | ns  |
| --- | ------- | --------------------- | --- | --- | --- | --- | --- | ---- | --- | --- |
controller
1. Guaranteed by design.
2. The I/O speed is configured using the OSPEEDRy[1:0] bits. Refer to the STM32F72xxx and STM32F73xxx reference
manual for a description of the GPIOx_SPEEDR GPIO port output speed register.
3. The maximum frequency is defined in Figure 45.
For maximum frequencies above 50 MHz and V  > 2.4 V, the compensation cell should be used.
| 4.  |     |     |     | DD  |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure 45. I/O AC characteristics definition
|     |     |     |     |     | (cid:28)(cid:19)(cid:8) |     | (cid:20)(cid:19)(cid:8) |     |     |     |
| --- | --- | --- | --- | --- | ----------------------- | --- | ----------------------- | --- | --- | --- |
(cid:24)(cid:19)(cid:8)
(cid:24)(cid:19)(cid:8)
(cid:28)(cid:19)(cid:8)
(cid:20)(cid:19)(cid:8)
|     | (cid:40)(cid:59)(cid:55)(cid:40)(cid:53)(cid:49)(cid:36)(cid:47) |     | (cid:87) (cid:85)(cid:11)(cid:44)(cid:50)(cid:12)(cid:82)(cid:88)(cid:87) |     |     |     |     | (cid:87) |     |     |
| --- | ---------------------------------------------------------------- | --- | ------------------------------------------------------------------------- | --- | --- | --- | --- | -------- | --- | --- |
(cid:73)(cid:11)(cid:44)(cid:50)(cid:12)(cid:82)(cid:88)(cid:87)
(cid:50)(cid:56)(cid:55)(cid:51)(cid:56)(cid:55)
(cid:55)
(cid:50)(cid:49)(cid:3)(cid:38)(cid:47)
|     |     |     | (cid:48)(cid:68)(cid:91)(cid:76)(cid:80)(cid:88)(cid:80)(cid:3)(cid:73)(cid:85)(cid:72)(cid:84)(cid:88)(cid:72)(cid:81)(cid:70)(cid:92)(cid:3)(cid:76)(cid:86)(cid:3)(cid:68)(cid:70)(cid:75)(cid:76)(cid:72)(cid:89)(cid:72)(cid:71)(cid:3)(cid:76)(cid:73)(cid:3)(cid:11)(cid:87) |     |     | (cid:14)(cid:3)(cid:87)(cid:12)(cid:3)(cid:148)(cid:3)(cid:11)(cid:21)(cid:18)(cid:22)(cid:12)(cid:55)(cid:3)(cid:68)(cid:81)(cid:71)(cid:3)(cid:76)(cid:73)(cid:3)(cid:87)(cid:75)(cid:72)(cid:3)(cid:71)(cid:88)(cid:87)(cid:92)(cid:3)(cid:70)(cid:92)(cid:70)(cid:79)(cid:72)(cid:3)(cid:76)(cid:86)(cid:3)(cid:11)(cid:23)(cid:24)(cid:16)(cid:24)(cid:24)(cid:8)(cid:12)(cid:3) |     |     |     |     |
| --- | --- | --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
(cid:85)(cid:3) (cid:73)
(cid:90)(cid:75)(cid:72)(cid:81)(cid:3)(cid:79)(cid:82)(cid:68)(cid:71)(cid:72)(cid:71)(cid:3)(cid:69)(cid:92)(cid:3)(cid:38)(cid:47)(cid:3)(cid:86)(cid:83)(cid:72)(cid:70)(cid:76)(cid:73)(cid:76)(cid:72)(cid:71)(cid:3)(cid:76)(cid:81)(cid:3)(cid:87)(cid:75)(cid:72)(cid:3)(cid:87)(cid:68)(cid:69)(cid:79)(cid:72)(cid:3)(cid:179)(cid:3)(cid:44)(cid:18)(cid:50)(cid:3)(cid:36)(cid:38)(cid:3)(cid:70)(cid:75)(cid:68)(cid:85)(cid:68)(cid:70)(cid:87)(cid:72)(cid:85)(cid:76)(cid:86)(cid:87)(cid:76)(cid:70)(cid:86)(cid:180)(cid:17)(cid:3)
(cid:3)
(cid:68)(cid:76)(cid:20)(cid:23)(cid:20)(cid:22)(cid:20)(cid:71)
|     |     |     |     | DocID029808 Rev 3 |     |     |     |     |     | 153/229 |
| --- | --- | --- | --- | ----------------- | --- | --- | --- | --- | --- | ------- |
201

| Electrical characteristics |                          |     |     | STM32F722xx STM32F723xx |     |
| -------------------------- | ------------------------ | --- | --- | ----------------------- | --- |
| 5.3.21                     | NRST pin characteristics |     |     |                         |     |
The NRST pin input driver uses CMOS technology. It is connected to a permanent pull-up
resistor, R  (see Table 62: I/O static characteristics).
PU
Unless otherwise specified, the parameters given in Table 65 are derived from tests
performed under the ambient temperature and V  supply voltage conditions summarized
DD
in Table 17.
|        |            Table 65. NRST pin characteristics   |     |            |         |          |
| ------ | ----------------------------------------------- | --- | ---------- | ------- | -------- |
| Symbol | Parameter                                       |     | Conditions | Min Typ | Max Unit |
| R      | Weak pull-up equivalent resistor(1)             |     | V = V      | 30 40   | 50 kΩ    |
| PU     |                                                 |     | IN  SS     |         |          |
(2)
| V   | NRST Input filtered pulse |     | -   | - - | 100 ns |
| --- | ------------------------- | --- | --- | --- | ------ |
F(NRST)
| V        | (2) NRST Input not filtered pulse |     | V  > 2.7 V | 300 - | - ns |
| -------- | --------------------------------- | --- | ---------- | ----- | ---- |
| NF(NRST) |                                   |     | DD         |       |      |
T NRST_OUT Generated reset pulse duration Internal Reset source 20 - - µs
1. The pull-up is designed with a true resistance in series with a switchable PMOS. This PMOS contribution to the series
resistance must be minimum (~10% order).
2. Guaranteed by design.
Figure 46. Recommended NRST pin protection
(cid:57)(cid:39)(cid:39)
(cid:40)(cid:91)(cid:87)(cid:72)(cid:85)(cid:81)(cid:68)(cid:79)
(cid:85)(cid:72)(cid:86)(cid:72)(cid:87)(cid:3)(cid:70)(cid:76)(cid:85)(cid:70)(cid:88)(cid:76)(cid:87)(cid:11)(cid:20)(cid:12)
|     |     | (cid:49)(cid:53)(cid:54)(cid:55)(cid:11)(cid:21)(cid:12) | (cid:53)(cid:51)(cid:56) | (cid:44)(cid:81)(cid:87)(cid:72)(cid:85)(cid:81)(cid:68)(cid:79)(cid:3)(cid:53)(cid:72)(cid:86)(cid:72)(cid:87) |     |
| --- | --- | -------------------------------------------------------- | ------------------------ | --------------------------------------------------------------------------------------------------------------- | --- |
(cid:41)(cid:76)(cid:79)(cid:87)(cid:72)(cid:85)
(cid:19)(cid:17)(cid:20)(cid:3)(cid:151)(cid:41)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)
(cid:68)(cid:76)(cid:20)(cid:23)(cid:20)(cid:22)(cid:21)(cid:70)
1. The reset network protects the device against parasitic resets. 0.1 uF capacitor must be placed as close as
possible to the chip.
2. The user must ensure that the level on the NRST pin can go below the V IL(NRST)  max level specified in
Table 65. Otherwise the reset is not taken into account by the device.
| 154/229 |     | DocID029808 Rev 3 |     |     |     |
| ------- | --- | ----------------- | --- | --- | --- |

| STM32F722xx STM32F723xx |                           |     |     |     |     |     |     | Electrical characteristics |     |     |
| ----------------------- | ------------------------- | --- | --- | --- | --- | --- | --- | -------------------------- | --- | --- |
| 5.3.22                  | TIM timer characteristics |     |     |     |     |     |     |                            |     |     |
The parameters given in Table 66 are guaranteed by design.
Refer to Section 5.3.20: I/O port characteristics for details on the input/output alternate
function characteristics (output compare, input capture, external clock, PWM output).
|     |             |        |           | Table 66. TIMx characteristics(1)(2)  |               |     |     |     |     |      |
| --- | ----------- | ------ | --------- | ------------------------------------- | ------------- | --- | --- | --- | --- | ---- |
|     |             | Symbol | Parameter |                                       | Conditions(3) |     |     | Min | Max | Unit |
AHB/APBx prescaler=1
|     |     |     |     |     | or 2 or 4, f |         |  =  |     |     | t       |
| --- | --- | --- | --- | --- | ------------ | ------- | --- | --- | --- | ------- |
|     |     |     |     |     |              | TIMxCLK |     | 1   | -   | TIMxCLK |
216 MHz
t
|     |     | res(TIM) | Timer resolution time |     |     |     |     |     |     |     |
| --- | --- | -------- | --------------------- | --- | --- | --- | --- | --- | --- | --- |
AHB/APBx
|     |     |     |     |     | prescaler>4, f |     |  =      |     |     | t       |
| --- | --- | --- | --- | --- | -------------- | --- | ------- | --- | --- | ------- |
|     |     |     |     |     |                |     | TIMxCLK | 1   | -   | TIMxCLK |
108 MHz
Timer external clock
|     |     | f   |                         |     |     |            |     |     | f /2    |     |
| --- | --- | --- | ----------------------- | --- | --- | ---------- | --- | --- | ------- | --- |
|     |     | EXT |                         |     |     |            |     | 0   | TIMxCLK | MHz |
|     |     |     | frequency on CH1 to CH4 |     |  f  |  = 216 MHz |     |     |         |     |
TIMxCLK
|     |     | Res | Timer resolution |     |     |     |     | -   | 16/32 | bit |
| --- | --- | --- | ---------------- | --- | --- | --- | --- | --- | ----- | --- |
TIM
|     |             |     | Maximum possible count  |     |     |     |     |     | 65536 ×  |           |
| --- | ----------- | --- | ----------------------- | --- | --- | --- | --- | --- | -------- | --------- |
|     | t MAX_COUNT |     |                         |     |     | -   |     | -   |          | t TIMxCLK |
|     |             |     | with 32-bit counter     |     |     |     |     |     | 65536    |           |
1. TIMx is used as a general term to refer to the TIM1 to TIM12 timers.
2. Guaranteed by design.
3. The maximum timer frequency on APB1 or APB2 is up to 216 MHz, by setting the TIMPRE bit in the
RCC_DCKCFGR register, if APBx prescaler is 1 or 2 or 4, then TIMxCLK = HCLK, otherwise TIMxCLK =
4x PCLKx.
| 5.3.23  | RTC characteristics |     |           |     |                                |     |            |     |     |     |
| ------- | ------------------- | --- | --------- | --- | ------------------------------ | --- | ---------- | --- | --- | --- |
|         |                     |     |           |     | Table 67. RTC characteristics  |     |            |     |     |     |
|         | Symbol              |     | Parameter |     |                                |     | Conditions |     | Min | Max |
Any read/write operation
|     |     | - f   | /RTCCLKfrequency ratio |     |     |     |     |     | 4   | -   |
| --- | --- | ----- | ---------------------- | --- | --- | --- | --- | --- | --- | --- |
|     |     | PCLK1 |                        |     |     |     |     |     |     |     |
from/to an RTC register
| 5.3.24  | 12-bit ADC characteristics |     |     |     |     |     |     |     |     |     |
| ------- | -------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Unless otherwise specified, the parameters given in Table 68 are derived from tests
performed under the ambient temperature, f PCLK2  frequency and V DDA  supply voltage
conditions summarized in Table 17.
Table 68. ADC characteristics
| Symbol |                            | Parameter |     |  Conditions       |           |     | Min    |     | Typ  Max | Unit    |
| ------ | -------------------------- | --------- | --- | ----------------- | --------- | --- | ------ | --- | -------- | ------- |
| V      | Power supply               |           |     |                   |           |     | 1.7(1) |     | - 3.6    | V       |
| DDA    |                            |           |     |                   |  − V      |     |        |     |          |         |
|        |                            |           |     |  V                |  < 1.2 V  |     |        |     |          |         |
| V      | Positive reference voltage |           |     | DDA               | REF+      |     | 1.7(1) |     | - V      | V       |
| REF+   |                            |           |     |                   |           |     |        |     | DDA      |         |
| V REF- | Negative reference voltage |           |     |                   | -         |     | -      |     | 0        | - V     |
|        |                            |           |     | DocID029808 Rev 3 |           |     |        |     |          | 155/229 |
201

| Electrical characteristics |     |     |     |     |     | STM32F722xx STM32F723xx |     |     |
| -------------------------- | --- | --- | --- | --- | --- | ----------------------- | --- | --- |
Table 68. ADC characteristics (continued)
Typ
| Symbol |     | Parameter |  Conditions |                    | Min |     | Max | Unit |
| ------ | --- | --------- | ----------- | ------------------ | --- | --- | --- | ---- |
|        |     |           | V           |  = 1.7(1) to 2.4 V | 0.6 | 15  | 18  | MHz  |
DDA
| f   | ADC clock frequency |     |     |     |     |     |     |     |
| --- | ------------------- | --- | --- | --- | --- | --- | --- | --- |
ADC
|     |     |     | V DDA |  = 2.4 to 3.6 V | 0.6 | 30  | 36  | MHz |
| --- | --- | --- | ----- | --------------- | --- | --- | --- | --- |
f  = 30 MHz,
|     |                            |     | ADC               |     | -   | -   | 1764 | kHz |
| --- | -------------------------- | --- | ----------------- | --- | --- | --- | ---- | --- |
| (2) |                            |     | 12-bit resolution |     |     |     |      |     |
| f   | External trigger frequency |     |                   |     |     |     |      |     |
TRIG
|     |     |     |     | -   | -   | -   | 17  | 1/f ADC |
| --- | --- | --- | --- | --- | --- | --- | --- | ------- |
0
| V   | Conversion voltage range(3) |     |     | -   | (V or V |   -  | V    | V   |
| --- | --------------------------- | --- | --- | --- | ------- | ---- | ---- | --- |
| AIN |                             |     |     |     | SSA     | REF- | REF+ |     |
tied to ground)
See Equation 1 for
| R (2)    | External input impedance   |     |     |         | -   | -   | 50  | kΩ  |
| -------- | -------------------------- | --- | --- | ------- | --- | --- | --- | --- |
| AIN      |                            |     |     | details |     |     |     |     |
| R (2)(4) | Sampling switch resistance |     |     | -       | 1.5 | -   | 6   | kΩ  |
ADC
|     | (2) Internal sample and hold  |     |     |           |     |     |       |     |
| --- | ----------------------------- | --- | --- | --------- | --- | --- | ----- | --- |
| C   |                               |     |     |  -        | -   | 4   | 7     | pF  |
| ADC | capacitor                     |     |     |           |     |     |       |     |
|     |                               |     | f   |  = 30 MHz | -   | -   | 0.100 | µs  |
| (2) | Injection trigger conversion  |     | ADC |           |     |     |       |     |
t
| lat | latency                     |     |     |           |     |     | 3(5)  |         |
| --- | --------------------------- | --- | --- | --------- | --- | --- | ----- | ------- |
|     |                             |     |     |           | -   | -   |       | 1/f ADC |
|     | Regular trigger conversion  |     | f   |  = 30 MHz | -   | -   | 0.067 | µs      |
| (2) |                             |     | ADC |           |     |     |       |         |
t latr
|     | latency |     |     |     | -   | -   | 2(5) | 1/f |
| --- | ------- | --- | --- | --- | --- | --- | ---- | --- |
ADC
|     |     |     | f   |  = 30 MHz | 0.100 | -   | 16  | µs  |
| --- | --- | --- | --- | --------- | ----- | --- | --- | --- |
ADC
| t (2) | Sampling time  |     |     |     |     |     |     |     |
| ----- | -------------- | --- | --- | --- | --- | --- | --- | --- |
S
|     |                   |     |     | -   | 3   | -   | 480 | 1/f ADC |
| --- | ----------------- | --- | --- | --- | --- | --- | --- | ------- |
| t   | (2) Power-up time |     | -   |     | -   | 2   | 3   | µs      |
STAB
f  = 30 MHz
ADC
|     |     |     |     |     | 0.50 | -   | 16.40 | µs  |
| --- | --- | --- | --- | --- | ---- | --- | ----- | --- |
12-bit resolution
f  = 30 MHz
ADC
|     |     |     |     |     | 0.43 | -   | 16.34 | µs  |
| --- | --- | --- | --- | --- | ---- | --- | ----- | --- |
10-bit resolution
|      | Total conversion time (including  |     | f   |  = 30 MHz |      |     |       |     |
| ---- | --------------------------------- | --- | --- | --------- | ---- | --- | ----- | --- |
| t    | (2)                               |     | A   | D C       | 0.37 | -   | 16.27 | µs  |
| CONV | sampling time)                    |     |     |           |      |     |       |     |
8 - b it resolution
f  = 30 MHz
|     |     |     | ADC |     | 0.30 | -   | 16.20 | µs  |
| --- | --- | --- | --- | --- | ---- | --- | ----- | --- |
6-bit resolution
|     |     |     | 9 to 492 (t    |  for sampling +n-bit resolution for successive  |     |     |     |     |
| --- | --- | --- | -------------- | ----------------------------------------------- | --- | --- | --- | --- |
|     |     |     |                | S                                               |     |     |     | 1/f |
|     |     |     | approximation) |                                                 |     |     |     | ADC |
12-bit resolution
|     |     |     |     |     | -   | -   | 2.4 | Msps |
| --- | --- | --- | --- | --- | --- | --- | --- | ---- |
Single ADC
12-bit resolution
Sampling rate
| (2) |     |                  | Interleave Dual ADC  |      | -   | -   | 4.5 | Msps |
| --- | --- | ---------------- | -------------------- | ---- | --- | --- | --- | ---- |
| f   | (f  |  = 36 MHz, and   |                      |      |     |     |     |      |
| S   | ADC |                  |                      | mode |     |     |     |      |
t  = 3 ADC cycles)
S
12-bit resolution
|     |     |     | Interleave Triple ADC  |     | -   | -   | 7.2 | Msps |
| --- | --- | --- | ---------------------- | --- | --- | --- | --- | ---- |
mode
| 156/229 |     |     | DocID029808 Rev 3 |     |     |     |     |     |
| ------- | --- | --- | ----------------- | --- | --- | --- | --- | --- |

| STM32F722xx STM32F723xx |     |     |     |     |     |     |     | Electrical characteristics |     |     |
| ----------------------- | --- | --- | --- | --- | --- | --- | --- | -------------------------- | --- | --- |
Table 68. ADC characteristics (continued)
Typ
| Symbol |     | Parameter |     |  Conditions |     |     |     | Min | Max | Unit |
| ------ | --- | --------- | --- | ----------- | --- | --- | --- | --- | --- | ---- |
ADC V  DC current
REF
(2)
| I VREF+ | consumption in conversion  |     |     |     | -   |     |     | - 300 | 500 | µA  |
| ------- | -------------------------- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
mode
ADC V  DC current
DDA
| I (2) | consumption in conversion  |     |     |     | -   |     |     | - 1.6 | 1.8 | mA  |
| ----- | -------------------------- | --- | --- | --- | --- | --- | --- | ----- | --- | --- |
VDDA
mode
1. V  minimum value of 1.7 V is obtained with the use of an external power supply supervisor (refer to Section 2.17.2:
DDA
Internal reset OFF).
2. Guaranteed by characterization results.
| 3. V  is internally connected to V |     |     |  and V                          |  is internally connected to V |     |         | .   |     |     |     |
| ---------------------------------- | --- | --- | ------------------------------- | ----------------------------- | --- | ------- | --- | --- | --- | --- |
| REF+                               |     |     | DDA REF-                        |                               |     |         | SSA |     |     |     |
| 4. R  maximum value is given for V |     |     | =1.7 V, and minimum value for V |                               |     | =3.3 V. |     |     |     |     |
| ADC                                |     |     | DD                              |                               |     | DD      |     |     |     |     |
5. For external triggers, a delay of 1/f PCLK2  must be added to the latency specified in Table 68.
|     | Equation 1: R |     |  max formula |     |     |     |     |     |     |     |
| --- | ------------- | --- | ------------ | --- | --- | --- | --- | --- | --- | --- |
AIN
(k–0.5)
=
|     |     |     | R   | ----------------------------------------------------------------–R |     |        |     |     |     |     |
| --- | --- | --- | --- | ------------------------------------------------------------------ | --- | ------ | --- | --- | --- | --- |
|     |     |     | AIN |                                                                    |     |        | N+2 | ADC |     |     |
|     |     |     |     | f                                                                  | × C | × ln(2 |     | )   |     |     |
|     |     |     |     | ADC                                                                |     | ADC    |     |     |     |     |
The formula above (Equation 1) is used to determine the maximum external impedance
allowed for an error below 1/4 of LSB. N = 12 (from 12-bit resolution) and k is the number of
sampling periods defined in the ADC_SMPR1 register.
|     |            |     | Table 69. ADC static accuracy at f |     |     |     |     |  = 18 MHz  |     |     |
| --- | ---------- | --- | ---------------------------------- | --- | --- | --- | --- | ---------- | --- | --- |
ADC
Max(1)
|     | Symbol |                           | Parameter |     | Test conditions |          |     | Typ |     | Unit |
| --- | ------ | ------------------------- | --------- | --- | --------------- | -------- | --- | --- | --- | ---- |
|     |        | ET Total unadjusted error |           |     |                 |          |     | ±3  | ±4  |      |
|     |        |                           |           |     | f               |  =18 MHz |     |     |     |      |
ADC
|     |     | EO Offset error |     |     |       |                 |     | ±2  | ±3  |     |
| --- | --- | --------------- | --- | --- | ----- | --------------- | --- | --- | --- | --- |
|     |     |                 |     |     | V DDA |  = 1.7 to 3.6 V |     |     |     |     |
LSB
|     |     | EG Gain error |     |     | V   |  = 1.7 to 3.6 V |     | ±1  | ±3  |     |
| --- | --- | ------------- | --- | --- | --- | --------------- | --- | --- | --- | --- |
REF
|     |     | ED Differential linearity error |     |     | V    | − V < 1.2 V |     | ±1  | ±2  |     |
| --- | --- | ------------------------------- | --- | --- | ---- | ----------- | --- | --- | --- | --- |
|     |     |                                 |     |     | DDA  | REF         |     |     |     |     |
|     |     | EL Integral linearity error     |     |     |      |             |     | ±2  | ±3  |     |
1. Guaranteed by characterization results.
|     |            |     | Table 70. ADC static accuracy at f |     |     |     |     |  = 30 MHz  |     |     |
| --- | ---------- | --- | ---------------------------------- | --- | --- | --- | --- | ---------- | --- | --- |
ADC
|     | Symbol |                           | Parameter |     | Test conditions |     |     | Typ | Max(1) | Unit |
| --- | ------ | ------------------------- | --------- | --- | --------------- | --- | --- | --- | ------ | ---- |
|     |        | ET Total unadjusted error |           |     |                 |     |     | ±2  | ±5     |      |
 = 30 MHz,
f ADC
|     |     | EO Offset error |     |     |  < 10 kΩ,   |     |     | ±1.5 | ±2.5 |     |
| --- | --- | --------------- | --- | --- | ----------- | --- | --- | ---- | ---- | --- |
R
AIN
|     |     | EG Gain error |     |     | V  = 2.4 to 3.6 V,   |     |     | ±1.5 | ±4  | LSB |
| --- | --- | ------------- | --- | --- | -------------------- | --- | --- | ---- | --- | --- |
DDA
V  = 1.7 to 3.6 V,
|     |     | ED Differential linearity error |     |     | REF   |         |     | ±1   | ±2  |     |
| --- | --- | ------------------------------- | --- | --- | ----- | ------- | --- | ---- | --- | --- |
|     |     |                                 |     |     | V − V | < 1.2 V |     |      |     |     |
|     |     |                                 |     |     | DDA   | REF     |     |      |     |     |
|     |     | EL Integral linearity error     |     |     |       |         |     | ±1.5 | ±3  |     |
1. Guaranteed by characterization results.
|     |     |     |     | DocID029808 Rev 3 |     |     |     |     |     | 157/229 |
| --- | --- | --- | --- | ----------------- | --- | --- | --- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     |     | STM32F722xx STM32F723xx |     |
| -------------------------- | --- | --- | --- | --- | ----------------------- | --- |

|     |        | Table 71. ADC static accuracy at f |                 | ADC |  = 36 MHz  |             |
| --- | ------ | ---------------------------------- | --------------- | --- | ---------- | ----------- |
|     | Symbol | Parameter                          | Test conditions |     | Typ        | Max(1) Unit |
|     | ET     | Total unadjusted error             |                 |     | ±4         | ±7          |
f  =36 MHz,
|     | EO  | Offset error | ADC |     | ±2  | ±3  |
| --- | --- | ------------ | --- | --- | --- | --- |
V  = 2.4 to 3.6 V,
|     |     |            | DDA |     |     | LSB |
| --- | --- | ---------- | --- | --- | --- | --- |
|     | EG  | Gain error |     |     | ±3  | ±6  |
V REF  = 1.7 to 3.6 V
|     | ED  | Differential linearity error | V − V | < 1.2 V | ±2  | ±3  |
| --- | --- | ---------------------------- | ----- | ------- | --- | --- |
DDA  REF
|     | EL  | Integral linearity error |     |     | ±3  | ±6  |
| --- | --- | ------------------------ | --- | --- | --- | --- |
1. Guaranteed by characterization results.
Ta     b     le 72. ADC dynamic accuracy at f  = 18 MHz - limited test conditions(1)
ADC
| Symbol |                          | Parameter | Test conditions |     | Min Typ   | Max Unit |
| ------ | ------------------------ | --------- | --------------- | --- | --------- | -------- |
| ENOB   | Effective number of bits |           |                 |     | 10.3 10.4 | - bits   |
f  =18 MHz
ADC
| SINAD | Signal-to-noise and distortion ratio |     |        |         | 64 64.2 | -   |
| ----- | ------------------------------------ | --- | ------ | ------- | ------- | --- |
|       |                                      |     | V  = V | = 1.7 V |         |     |
DDA REF+
Input Frequency = 20 KHz
| SNR |     | Signal-to-noise ratio |     |     | 64 65 | - dB |
| --- | --- | --------------------- | --- | --- | ----- | ---- |
Temperature = 25 °C
| THD | Total harmonic distortion |     |     |     | −67 −72 | -   |
| --- | ------------------------- | --- | --- | --- | ------- | --- |
1. Guaranteed by characterization results.
 = 36 MHz - limited test conditions(1)
Ta     b     le 73. ADC dynamic accuracy at f
ADC
| Symbol |                          | Parameter | Test conditions |     | Min Typ   | Max Unit |
| ------ | ------------------------ | --------- | --------------- | --- | --------- | -------- |
| ENOB   | Effective number of bits |           |                 |     | 10.6 10.8 | - bits   |
f  =36 MHz
ADC
SINAD Signal-to noise and distortion ratio V  = V = 3.3 V 66 67 -
DDA REF+
SNR Signal-to noise ratio Input Frequency = 20 KHz 64 68 - dB
Temperature = 25 °C
| THD | Total harmonic distortion |     |     |     | −70 −72 | -   |
| --- | ------------------------- | --- | --- | --- | ------- | --- |
1. Guaranteed by characterization results.
Note: ADC accuracy vs. negative injection current: injecting a negative current on any analog
input pins should be avoided as this significantly reduces the accuracy of the conversion
being performed on another analog input. It is recommended to add a Schottky diode (pin to
ground) to analog pins which may potentially inject negative currents.
 and ΣI
Any positive injection current within the limits specified for I  in
|     |     |     |     | INJ(PIN) | INJ(PIN) |     |
| --- | --- | --- | --- | -------- | -------- | --- |
Section 5.3.20 does not affect the ADC accuracy.
158/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
Figure 47. ADC accuracy characteristics
(cid:54)(cid:50)(cid:37)(cid:38)(cid:11) (cid:54)(cid:36)(cid:36)(cid:33)
(cid:59)(cid:17)(cid:44)(cid:51)(cid:34) (cid:41)(cid:36)(cid:37)(cid:33)(cid:44)(cid:0)(cid:29)(cid:0) (cid:8)(cid:79)(cid:82)(cid:0)(cid:0)(cid:0)(cid:0)(cid:0)(cid:0)(cid:0)(cid:0)(cid:0)(cid:0)(cid:0)(cid:0)(cid:0)(cid:0)(cid:68)(cid:69)(cid:80)(cid:69)(cid:78)(cid:68)(cid:73)(cid:78)(cid:71)(cid:0)(cid:79)(cid:78)(cid:0)(cid:80)(cid:65)(cid:67)(cid:75)(cid:65)(cid:71)(cid:69)(cid:9)(cid:61)
(cid:20)(cid:16)(cid:25)(cid:22) (cid:20)(cid:16)(cid:25)(cid:22)
(cid:37)(cid:39)
(cid:20)(cid:16)(cid:25)(cid:21)
(cid:20)(cid:16)(cid:25)(cid:20)
(cid:20)(cid:16)(cid:25)(cid:19)
(cid:8)(cid:18)(cid:9)
(cid:37)(cid:52)
(cid:8)(cid:19)(cid:9)
(cid:23)
(cid:8)(cid:17)(cid:9)
(cid:22)
(cid:21)
(cid:37)(cid:47) (cid:37)(cid:44)
(cid:20)
(cid:19)
(cid:37)(cid:36)
(cid:18)
(cid:17)
(cid:17)(cid:44)(cid:51)(cid:34)(cid:41)(cid:36)(cid:37)(cid:33)(cid:44)
(cid:16)
(cid:17) (cid:18) (cid:19) (cid:20)(cid:21)(cid:22) (cid:23) (cid:20)(cid:16)(cid:25)(cid:19) (cid:20)(cid:16)(cid:25)(cid:20) (cid:20)(cid:16)(cid:25)(cid:21) (cid:20)(cid:16)(cid:25)(cid:22)
(cid:54)(cid:51)(cid:51)(cid:33) (cid:54)(cid:36)(cid:36)(cid:33)
(cid:65)(cid:73)(cid:17)(cid:20)(cid:19)(cid:25)(cid:21)(cid:67)
1. See also Table 70.
2. Example of an actual transfer curve.
3. Ideal transfer curve.
4. End point correlation line.
5. E = Total Unadjusted Error: maximum deviation between the actual and the ideal transfer curves.
T
EO = Offset Error: deviation between the first actual transition and the first ideal one.
EG = Gain Error: deviation between the last ideal transition and the last actual one.
ED = Differential Linearity Error: maximum deviation between actual steps and the ideal one.
EL = Integral Linearity Error: maximum deviation between any actual transition and the end point
correlation line.
Figure 48. Typical connection diagram using the ADC
(cid:57)(cid:39)(cid:39) (cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)
(cid:54)(cid:68)(cid:80)(cid:83)(cid:79)(cid:72)(cid:3)(cid:68)(cid:81)(cid:71)(cid:3)(cid:75)(cid:82)(cid:79)(cid:71)(cid:3)(cid:36)(cid:39)(cid:38)(cid:3)
(cid:57)(cid:55) (cid:70)(cid:82)(cid:81)(cid:89)(cid:72)(cid:85)(cid:87)(cid:72)(cid:85)
(cid:19)(cid:17)(cid:25)(cid:3)(cid:57)
(cid:53)(cid:36)(cid:44)(cid:49) (cid:11)(cid:20)(cid:12)
(cid:36)(cid:44)(cid:49)(cid:91)
(cid:53)(cid:36)(cid:39)(cid:38) (cid:11)(cid:20)(cid:12)
(cid:20)(cid:21)(cid:16)(cid:69)(cid:76)(cid:87)
(cid:70)(cid:82)(cid:81)(cid:89)(cid:72)(cid:85)(cid:87)(cid:72)(cid:85)
(cid:57)(cid:55)
(cid:57)(cid:36)(cid:44)(cid:49) (cid:38)(cid:83)(cid:68)(cid:85)(cid:68)(cid:86)(cid:76)(cid:87)(cid:76)(cid:70) (cid:19)(cid:17)(cid:25)(cid:3)(cid:57) (cid:38) (cid:36)(cid:39)(cid:38)(cid:11)(cid:20)(cid:12)
(cid:44)(cid:47)(cid:147)(cid:20)(cid:3)(cid:151)(cid:36)
(cid:68)(cid:76)(cid:20)(cid:26)(cid:24)(cid:22)(cid:23)
1. Refer to Table 68 for the values of R , R and C .
AIN ADC ADC
2. C represents the capacitance of the PCB (dependent on soldering and PCB layout quality) plus the
parasitic
pad capacitance (roughly 5 pF). A high C value downgrades conversion accuracy. To remedy this,
parasitic
f should be reduced.
ADC
DocID029808 Rev 3 159/229
201

Electrical characteristics STM32F722xx STM32F723xx
General PCB design guidelines
Power supply decoupling should be performed as shown in Figure 49 or Figure 50,
depending on whether V is connected to V or not. The 10 nF capacitors should be
REF+ DDA
ceramic (good quality). They should be placed them as close as possible to the chip.
Figure 49. Power supply and reference decoupling (V not connected to V )
REF+ DDA
(cid:94)(cid:100)(cid:68)(cid:1007)(cid:1006)(cid:38)
(cid:115)(cid:90)(cid:28)(cid:38)(cid:1085) (cid:894)(cid:1005)(cid:895)
(cid:1005)(cid:3)(cid:1106)(cid:38)(cid:3)(cid:876)(cid:876)(cid:3)(cid:1005)(cid:1004)(cid:3)(cid:374)(cid:38)
(cid:115)(cid:24)(cid:24)(cid:4)
(cid:1005)(cid:3)(cid:1106)(cid:38)(cid:3)(cid:876)(cid:876)(cid:3)(cid:1005)(cid:1004)(cid:3)(cid:374)(cid:38)
(cid:894)(cid:1005)(cid:895)
(cid:115)(cid:94)(cid:94)(cid:4) (cid:876)(cid:3)(cid:115)(cid:90)(cid:28)(cid:38)(cid:882)
(cid:258)(cid:349)(cid:1005)(cid:1011)(cid:1009)(cid:1007)(cid:1009)(cid:272)
1. V input is available on all the packages except LQFP64, whereas the V is available only on
REF+ REF–
UFBGA176 and UFBGA144. When V is not available, it is internally connected to V .
REF- SSA
Figure 50. Power supply and reference decoupling (V connected to V )
REF+ DDA
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)
(cid:57)(cid:53)(cid:40)(cid:41)(cid:14)(cid:18)(cid:57)(cid:39)(cid:39)(cid:36) (cid:11)(cid:20)(cid:12)
(cid:20)(cid:3)(cid:151)(cid:41)(cid:3)(cid:18)(cid:18)(cid:3)(cid:20)(cid:19)(cid:3)(cid:81)(cid:41)
(cid:57)(cid:53)(cid:40)(cid:41)(cid:16)(cid:18)(cid:57)(cid:54)(cid:54)(cid:36) (cid:11)(cid:20)(cid:12)
(cid:68)(cid:76)(cid:20)(cid:26)(cid:24)(cid:22)(cid:25)(cid:70)
1. V input is available on all the packages except LQFP64, whereas the V is available only on
REF+ REF–
UFBGA176 and UFBGA144. When V is not available, it is internally connected to V .
REF- SSA
160/229 DocID029808 Rev 3

| STM32F722xx STM32F723xx |        |                                    |                             |                                               |           |     |     |     | Electrical characteristics |         |       |
| ----------------------- | ------ | ---------------------------------- | --------------------------- | --------------------------------------------- | --------- | --- | --- | --- | -------------------------- | ------- | ----- |
| 5.3.25                  |        | Temperature sensor characteristics |                             |                                               |           |     |     |     |                            |         |       |
|                         |        |                                    |                             | Table 74. Temperature sensor characteristics  |           |     |     |     |                            |         |       |
|                         | Symbol |                                    |                             |                                               | Parameter |     |     |     | Min                        | Typ Max | Unit  |
|                         | (1)    |                                    |                             |                                               |           |     |     |     |                            | ±1 ±2   |       |
|                         | T      | V                                  |  linearity with temperature |                                               |           |     |     |     | -                          |         | °C    |
|                         | L      | SENSE                              |                             |                                               |           |     |     |     |                            |         |       |
| Avg_Slope(1)            |        | Average slope                      |                             |                                               |           |     |     |     | -                          | 2.5 -   | mV/°C |
(1)
|     | V 25  | Voltage at 25 °C |     |     |     |     |     |     | -   | 0.76 - | V   |
| --- | ----- | ---------------- | --- | --- | --- | --- | --- | --- | --- | ------ | --- |
|     | t (2) | Startup time     |     |     |     |     |     |     | -   | 6 10   | µs  |
START
T (2) ADC sampling time when reading the temperature (1 °C accuracy) 10 - - µs
S_temp
1. Guaranteed by characterization results.
2. Guaranteed by design.
|     |        |            |     | Table 75. Temperature sensor calibration values  |           |     |     |     |                |     |     |
| --- | ------ | ---------- | --- | ------------------------------------------------ | --------- | --- | --- | --- | -------------- | --- | --- |
|     | Symbol |            |     |                                                  | Parameter |     |     |     | Memory address |     |     |
TS_CAL1 TS ADC raw data acquired at temperature of 30 °C, V = 3.3 V 0x1FF0 7A2C - 0x1FF0 7A2D
DDA
TS_CAL2 TS ADC raw data acquired at temperature of 110 °C, V DDA = 3.3 V 0x1FF0 7A2E - 0x1FF0 7A2F
| 5.3.26  |     | V   |  monitoring characteristics |     |     |     |     |     |     |     |     |
| ------- | --- | --- | --------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
BAT

|     |        |     |                       | Table 76. V | BAT  monitoring characteristics  |     |     |     |     |     |      |
| --- | ------ | --- | --------------------- | ----------- | -------------------------------- | --- | --- | --- | --- | --- | ---- |
|     | Symbol |     |                       |             | Parameter                        |     |     | Min | Typ | Max | Unit |
|     | R      |     | Resistor bridge for V |             |                                  |     |     | -   | 50  | -   | KΩ   |
BAT
|     | Q   |     | Ratio on V |  measurement |     |     |     | -   | 4   | -   | -   |
| --- | --- | --- | ---------- | ------------ | --- | --- | --- | --- | --- | --- | --- |
BAT
|     | Er(1) |     | Error on Q |     |     |     |     | –1  | -   | +1  | %   |
| --- | ----- | --- | ---------- | --- | --- | --- | --- | --- | --- | --- | --- |
ADC sampling time when reading the V
|     | T (2)(2) |     |     |     |     | BAT   |     | 5   | -   | -   | µs  |
| --- | -------- | --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- |
S_vbat
1 mV accuracy
1. Guaranteed by design.
2. Shortest sampling time can be determined in the application by multiple iterations.
| 5.3.27  |     | Reference voltage |     |     |     |     |     |     |     |     |     |
| ------- | --- | ----------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
The parameters given in Table 77 are derived from tests performed under ambient
|     |     | temperature and V |     |     |  supply voltage conditions summarized in Table 17. |     |     |     |     |     |     |
| --- | --- | ----------------- | --- | --- | -------------------------------------------------- | --- | --- | --- | --- | --- | --- |
DD
|     |     |             |     |     | Table 77.  internal reference voltage  |     |     |     |     |     |     |
| --- | --- | ----------- | --- | --- | -------------------------------------- | --- | --- | --- | --- | --- | --- |
Typ
| Symbol |     |     |     | Parameter |     | Conditions |     |     | Min | Max | Unit |
| ------ | --- | --- | --- | --------- | --- | ---------- | --- | --- | --- | --- | ---- |
V REFINT Internal reference voltage –40 °C < T A  < +105 °C 1.18 1.21 1.24 V
ADC sampling time when reading the
| T        |           | (1)                                             |     |     |                   |     | -            |     | 10  | - - | µs      |
| -------- | --------- | ----------------------------------------------- | --- | --- | ----------------- | --- | ------------ | --- | --- | --- | ------- |
|          | S_vrefint | internal reference voltage                      |     |     |                   |     |              |     |     |     |         |
|          |           | (2) Internal reference voltage spread over the  |     |     |                   |     |  = 3V ± 10mV |     |     |     |         |
| V        |           |                                                 |     |     |                   | V   |              |     | -   | 3 5 | mV      |
| RERINT_s |           | temperature range                               |     |     |                   | DD  |              |     |     |     |         |
|          |           |                                                 |     |     | DocID029808 Rev 3 |     |              |     |     |     | 161/229 |
201

| Electrical characteristics |     |     |     |     |     |     | STM32F722xx STM32F723xx |     |     |
| -------------------------- | --- | --- | --- | --- | --- | --- | ----------------------- | --- | --- |
Table 77.  internal reference voltage (continued)
| Symbol                        |     | Parameter |     |     | Conditions |     | Min | Typ  | Max Unit  |
| ----------------------------- | --- | --------- | --- | --- | ---------- | --- | --- | ---- | --------- |
| T (2) Temperature coefficient |     |           |     |     |            | -   | -   | 30   | 50 ppm/°C |
Coeff
(2)
| t START Startup time |     |     |     |     |     | -   | -   | 6   | 10 µs |
| -------------------- | --- | --- | --- | --- | --- | --- | --- | --- | ----- |
1. Shortest sampling time can be determined in the application by multiple iterations.
2. Guaranteed by design.
           Table 78. Internal reference voltage calibration values
| Symbol |     |     | Parameter |     |     |     | Memory address |     |     |
| ------ | --- | --- | --------- | --- | --- | --- | -------------- | --- | --- |
V Raw data acquired at temperature of 30 °C V  = 3.3 V 0x1FF0 7A2A - 0x1FF0 7A2B
| REFIN_CAL                              |           |     |                                |     | DDA |      |          |     |     |
| -------------------------------------- | --------- | --- | ------------------------------ | --- | --- | ---- | -------- | --- | --- |
| 5.3.28  DAC electrical characteristics |           |     |                                |     |     |      |          |     |     |
|                                        |           |     | Table 79. DAC characteristics  |     |     |      |          |     |     |
| Symbol                                 | Parameter |     | Min                            | Typ | Max | Unit | Comments |     |     |
1.7(1)
| V Analog supply voltage |     |     |     | -   | 3.6  | V   |     | -   |     |
| ----------------------- | --- | --- | --- | --- | ---- | --- | --- | --- | --- |
DDA
|                            |     |     | 1.7(1) |     |     |      |  ≤ V |     |     |
| -------------------------- | --- | --- | ------ | --- | --- | ---- | ---- | --- | --- |
| V Reference supply voltage |     |     |        | -   | 3.6 | V V  |      |     |     |
| REF+                       |     |     |        |     |     | REF+ | DDA  |     |     |
| V Ground                   |     |     | 0      | -   | 0   | V    |      | -   |     |
SSA
|     |     | Connected to  |     |     |     | kΩ  |     |     |     |
| --- | --- | ------------- | --- | --- | --- | --- | --- | --- | --- |
|     |     |               | 5   | -   | -   |     |     | -   |     |
Resistive load V
| R (2) |     | SSA |     |     |     |     |     |     |     |
| ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
LOAD
with buffer ONConnected to
|     |     |     | 25  | -   | -   | kΩ  |     | -   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
V
DDA
When the buffer is OFF, the Minimum
Impedance output with buffer
| R (2) |     |     | -   | -   | 15  | kΩ resistive load between DAC_OUT and  |     |     |     |
| ----- | --- | --- | --- | --- | --- | -------------------------------------- | --- | --- | --- |
| O OFF |     |     |     |     |     |                                        |     |     |     |
V  to have a 1% accuracy is 1.5 MΩ
SS
| (2)                    |     |     |     |     |     | Maximum capacitive load at DAC_OUT  |     |     |     |
| ---------------------- | --- | --- | --- | --- | --- | ----------------------------------- | --- | --- | --- |
| C LOAD Capacitive load |     |     | -   | -   | 50  | pF                                  |     |     |     |
pin (when the buffer is ON).
It gives the maximum output excursion of
DAC_OUT Lower DAC_OUT voltage
|                       |     |     | 0.2  | -   | -   | V the DAC. |     |     |     |
| --------------------- | --- | --- | ---- | --- | --- | ---------- | --- | --- | --- |
| min(2) with buffer ON |     |     |      |     |     |            |     |     |     |
It corresponds to 12-bit input code
|                                 |     |     |     |     |        | (0x0E0) to (0xF1C) at V   |     |     |  = 3.6 V and  |
| ------------------------------- | --- | --- | --- | --- | ------ | ------------------------- | --- | --- | ------------- |
| DAC_OUT Higher DAC_OUT voltage  |     |     |     |     | V  −   |                           |     |     | REF+          |
|                                 |     |     | -   | -   | D D A  | V (0x1C7) to (0xE38) at V |     |     |  = 1.7 V      |
| max(2) with buffer ON           |     |     |     |     | 0 .2   |                           |     |     | REF+          |
DAC_OUT Lower DAC_OUT voltage
| min(2)                          |     |     | -                 | 0.5 | -     | mV                                        |     |     |     |
| ------------------------------- | --- | --- | ----------------- | --- | ----- | ----------------------------------------- | --- | --- | --- |
| with buffer OFF                 |     |     |                   |     |       | It gives the maximum output excursion of  |     |     |     |
| DAC_OUT Higher DAC_OUT voltage  |     |     |                   |     | V  −  | the DAC.                                  |     |     |     |
|                                 |     |     | -                 | -   | REF+  | V                                         |     |     |     |
| max(2) with buffer OFF          |     |     |                   |     | 1LSB  |                                           |     |     |     |
| 162/229                         |     |     | DocID029808 Rev 3 |     |       |                                           |     |     |     |

| STM32F722xx STM32F723xx |     |     |     |     |     | Electrical characteristics |     |
| ----------------------- | --- | --- | --- | --- | --- | -------------------------- | --- |
Table 79. DAC characteristics (continued)
| Symbol | Parameter |     | Min Typ | Max Unit |     | Comments |     |
| ------ | --------- | --- | ------- | -------- | --- | -------- | --- |
With no load, worst code (0x800) at
|     |     |     | - 170 | 240 | V  = 3.6 V in terms of DC  |     |     |
| --- | --- | --- | ----- | --- | -------------------------- | --- | --- |
REF+
|     | DAC DC V | REF  current  |     |     | consumption on the inputs |     |     |
| --- | -------- | ------------- | --- | --- | ------------------------- | --- | --- |
(4)
| I VREF+ | consumption in quiescent  |     |     | µA  |     |     |     |
| ------- | ------------------------- | --- | --- | --- | --- | --- | --- |
With no load, worst code (0xF1C) at
mode (Standby mode)
|     |     |     | - 50 | 75  | V REF+  = 3.6 V in terms of DC  |     |     |
| --- | --- | --- | ---- | --- | ------------------------------- | --- | --- |
consumption on the inputs
With no load, middle code (0x800) on the
|     |     |     | - 280 | 380 µA |     |     |     |
| --- | --- | --- | ----- | ------ | --- | --- | --- |
inputs
|     | DAC DC V |  current  |     |     |     |     |     |
| --- | -------- | --------- | --- | --- | --- | --- | --- |
DDA
| I (4) | consumption in quiescent  |     |     |     |                                      |     |     |
| ----- | ------------------------- | --- | --- | --- | ------------------------------------ | --- | --- |
| DDA   |                           |     |     |     | With no load, worst code (0xF1C) at  |     |     |
mode(3)
|     |     |     | - 475 | 625 µA | V  = 3.6 V in terms of DC  |     |     |
| --- | --- | --- | ----- | ------ | -------------------------- | --- | --- |
REF+
consumption on the inputs
Differential non linearity
|        |                         |     | - - | ±0.5  LSB | Given for the DAC in 10-bit configuration. |     |     |
| ------ | ----------------------- | --- | --- | --------- | ------------------------------------------ | --- | --- |
| DNL(4) | Difference between two  |     |     |           |                                            |     |     |
consecutive code-1LSB)
|     |     |     | - - | ±2  LSB | Given for the DAC in 12-bit configuration. |     |     |
| --- | --- | --- | --- | ------- | ------------------------------------------ | --- | --- |
Integral non linearity  - - ±1 LSB Given for the DAC in 10-bit configuration.
(difference between
| INL(4) | measured value at Code i  |     |     |     |     |     |     |
| ------ | ------------------------- | --- | --- | --- | --- | --- | --- |
and the value at Code i on a  - - ±4 LSB Given for the DAC in 12-bit configuration.
line drawn between Code 0
and last Code 1023)
|     |     |     | - - | ±10 mV | Given for the DAC in 12-bit configuration  |     |     |
| --- | --- | --- | --- | ------ | ------------------------------------------ | --- | --- |
Offset error
|           | (difference between     |     |     |        | Given for the DAC in 10-bit at V |     |  =   |
| --------- | ----------------------- | --- | --- | ------ | -------------------------------- | --- | ---- |
|           |                         |     | - - | ±3 LSB |                                  |     | REF+ |
| Offset(4) | measured value at Code  |     |     |        | 3.6 V                            |     |      |
(0x800) and the ideal value =
|     |            |     |     |         | Given for the DAC in 12-bit at V |     | REF+  =  |
| --- | ---------- | --- | --- | ------- | -------------------------------- | --- | -------- |
|     | V REF+ /2) |     | - - | ±12 LSB |                                  |     |          |
3.6 V
Gain
Gain error - - ±0.5 % Given for the DAC in 12-bit configuration
error(4)
Settling time (full scale: for a
10-bit input code transition
|          | between the lowest and the  |     |     |     | C  ≤  50 pF,  |     |     |
| -------- | --------------------------- | --- | --- | --- | ------------- | --- | --- |
| t        | (4)                         |     | - 3 | 6   | µs LOAD       |     |     |
| SETTLING | highest input codes when    |     |     |     | R  ≥ 5 kΩ     |     |     |
LOAD
DAC_OUT reaches final
value ±4LSB
|        | Total Harmonic Distortion |     |     |      | C  ≤  50 pF,  |     |     |
| ------ | ------------------------- | --- | --- | ---- | ------------- | --- | --- |
| THD(4) |                           |     | - - | - dB | LOAD          |     |     |
 ≥ 5 kΩ
|     | Buffer ON |     |     |     | R LOAD |     |     |
| --- | --------- | --- | --- | --- | ------ | --- | --- |
Max frequency for a correct
| Update  | DAC_OUT change when           |     |     |        | C  ≤  50 pF,  |     |     |
| ------- | ----------------------------- | --- | --- | ------ | ------------- | --- | --- |
|         |                               |     | - - | 1 MS/s | LOAD          |     |     |
| rate(2) |                               |     |     |        |  ≥ 5 kΩ       |     |     |
|         | small variation in the input  |     |     |        | R LOAD        |     |     |
code (from code i to i+1LSB)
|     |     |     | DocID029808 Rev 3 |     |     |     | 163/229 |
| --- | --- | --- | ----------------- | --- | --- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
Table 79. DAC characteristics (continued)
Symbol Parameter Min Typ Max Unit Comments
Wakeup time from off state C LOAD ≤ 50 pF, R LOAD ≥ 5 kΩ
t WAKEUP (4) (Setting the ENx bit in the - 6.5 10 µs input code between lowest and highest
DAC Control register) possible ones.
Power supply rejection ratio
PSRR+ (2) (to V ) (static DC - –67 –40 dB No R , C = 50 pF
DDA LOAD LOAD
measurement)
1. V minimum value of 1.7 V is obtained with the use of an external power supply supervisor (refer to Section 2.17.2:
DDA
Internal reset OFF).
2. Guaranteed by design.
3. The quiescent mode corresponds to a state where the DAC maintains a stable output level to ensure that no dynamic
consumption occurs.
4. Guaranteed by characterization results.
Figure 51. 12-bit buffered /non-buffered DAC
(cid:37)(cid:88)(cid:73)(cid:73)(cid:72)(cid:85)(cid:72)(cid:71)(cid:18)(cid:49)(cid:82)(cid:81)(cid:16)(cid:69)(cid:88)(cid:73)(cid:73)(cid:72)(cid:85)(cid:72)(cid:71)(cid:3)(cid:39)(cid:36)(cid:38)
(cid:37)(cid:88)(cid:73)(cid:73)(cid:72)(cid:85)(cid:11)(cid:20)(cid:12)
(cid:53)(cid:47)
(cid:20)(cid:21)(cid:16)(cid:69)(cid:76)(cid:87)(cid:3) (cid:39)(cid:36)(cid:38)(cid:66)(cid:50)(cid:56)(cid:55)(cid:91)
(cid:71)(cid:76)(cid:74)(cid:76)(cid:87)(cid:68)(cid:79)(cid:3)(cid:87)(cid:82)(cid:3)
(cid:68)(cid:81)(cid:68)(cid:79)(cid:82)(cid:74)(cid:3)
(cid:70)(cid:82)(cid:81)(cid:89)(cid:72)(cid:85)(cid:87)(cid:72)(cid:85)(cid:3)
(cid:38)
(cid:47)
(cid:65)(cid:73)(cid:17)(cid:23)(cid:17)(cid:21)(cid:23)(cid:54)(cid:19)
1. The DAC integrates an output buffer that can be used to reduce the output impedance and to drive external
loads directly without the use of an external operational amplifier. The buffer can be bypassed by
configuring the BOFFx bit in the DAC_CR register.
5.3.29 Communications interfaces
I
2
C interface characteristics
2 2
The I C interface meets the timings requirements of the I C-bus specification and user
manual rev. 03 for:
• Standard-mode (Sm): with a bit rate up to 100 kbit/s
• Fast-mode (Fm): with a bit rate up to 400 kbit/s.
• Fast-mode Plus (Fm+): with a bit rate up to 1Mbit/s.
2
The I C timings requirements are guaranteed by design when the I2C peripheral is properly
configured (refer to RM0385 reference manual) and when the I2CCLK frequency is greater
than the minimum shown in the table below:
164/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
Table 80. Minimum I2CCLK frequency in all I2C modes
| Symbol Parameter |               | Condition |     | Min | Unit |
| ---------------- | ------------- | --------- | --- | --- | ---- |
|                  | Standard-mode |           |     | 2   |      |
Analog Filtre ON
10
DNF=0
Fast-mode
Analog Filtre OFF
I2CCLK  9
| f(I2CCLK) |     |     | DNF=1 |     | MHz |
| --------- | --- | --- | ----- | --- | --- |
frequency
Analog Filtre ON
22.5
DNF=0
Fast-mode Plus
Analog Filtre OFF
16
DNF=1
The SDA and SCL I/O requirements are met with the following restrictions: the SDA and
SCL I/O pins are not “true” open-drain. When configured as open-drain, the PMOS
| connected between the I/O pin and V |     |  is disabled, but is still present.  |     |     |     |
| ----------------------------------- | --- | ------------------------------------ | --- | --- | --- |
DD
The 20mA output drive requirement in Fast-mode Plus is not supported. This limits the
maximum load Cload supported in Fm+, which is given by these formulas:
•
| Tr(SDA/SCL)=0.8473xR | xC  |     |     |     |     |
| -------------------- | --- | --- | --- | --- | --- |
p load
•
| R (min)= (VDD-V | (max))/I | (max) |     |     |     |
| --------------- | -------- | ----- | --- | --- | --- |
| p               | OL OL    |       |     |     |     |
Where Rp is the I2C lines pull-up. Refer to Section 5.3.20: I/O port characteristics for the
I2C I/Os characteristics.
All I 2 C SDA and SCL I/Os embed an analog filter. Refer to the table below for the analog
filter characteristics:
|            | Table 81. I2C analog filter characteristics(1) |     |     |     |      |
| ---------- | ---------------------------------------------- | --- | --- | --- | ---- |
| Symbol     | Parameter                                      |     | Min | Max | Unit |
Maximum pulse width of spikes
| t that are suppressed by the analog  |     |     | 50(2) | 260(3) | ns  |
| ------------------------------------ | --- | --- | ----- | ------ | --- |
AF
filter
1. Guaranteed by characterization results.
| 2. Spikes with widths below t | AF(min)  are filtered. |     |     |     |     |
| ----------------------------- | ---------------------- | --- | --- | --- | --- |
| 3. Spikes with widths above t |  are not filtered      |     |     |     |     |
AF(max)
|     | DocID029808 Rev 3 |     |     |     | 165/229 |
| --- | ----------------- | --- | --- | --- | ------- |
201

| Electrical characteristics |     |     | STM32F722xx STM32F723xx |     |
| -------------------------- | --- | --- | ----------------------- | --- |
SPI interface characteristics
Unless otherwise specified, the parameters given in Table 82 for the SPI interface are
derived from tests performed under the ambient temperature, f PCLKx  frequency and V DD
supply voltage conditions summarized in Table 17, with the following configuration:
• Output speed is set to OSPEEDRy[1:0] = 11
• Capacitive load C = 30 pF
• Measurement points are done at CMOS levels: 0.5V
DD
Refer to Section 5.3.20: I/O port characteristics for more details on the input/output alternate
function characteristics (NSS, SCK, MOSI, MISO for SPI).
Table 82. SPI dynamic characteristics(1)

| Symbol  | Parameter |  Conditions | Min | Typ Max Unit |
| ------- | --------- | ----------- | --- | ------------ |
Master mode
54(2)
|     |     | SPI1,4,5 | -   | -   |
| --- | --- | -------- | --- | --- |
2.7≤VDD≤3.6
Master mode
|     |     | SPI1,4,5  | -   | - 27 |
| --- | --- | --------- | --- | ---- |
1.71≤VDD≤3.6
Master transmitter mode
|     |     | SPI1,4,5  | -   | - 54 |
| --- | --- | --------- | --- | ---- |
1.71≤VDD≤3.6
Slave receiver mode
f
SCK
|     | SPI clock frequency | SPI1,4,5 | -   | - 54 MHz |
| --- | ------------------- | -------- | --- | -------- |
1/t
| c(SCK) |     | 1.71≤VDD≤3.6 |     |     |
| ------ | --- | ------------ | --- | --- |
Slave mode transmitter/full duplex
|     |     | SPI1,4,5  | -   | - 50(3) |
| --- | --- | --------- | --- | ------- |
2.7≤VDD≤3.6
Slave mode transmitter/full duplex
37(3)
|     |     | SPI1,4,5 | -   | -   |
| --- | --- | -------- | --- | --- |
1.71≤VDD≤3.6
Master & Slave mode
|     |     | SPI2,3  | -   | - 27 |
| --- | --- | ------- | --- | ---- |
 1.71≤VDD≤3.6
tsu(NSS) NSS setup time Slave mode, SPI presc = 2 4xTpclk - -
| th(NSS) | NSS hold time | Slave mode, SPI presc = 2 | 2xTpclk | - - |
| ------- | ------------- | ------------------------- | ------- | --- |
ns
tw(SCKH)
|     | SCK high and low time | Master mode  | Tpclk-1 | Tpclk Tpclk+1 |
| --- | --------------------- | ------------ | ------- | ------------- |
tw(SCKL)
| 166/229 |     | DocID029808 Rev 3 |     |     |
| ------- | --- | ----------------- | --- | --- |

| STM32F722xx STM32F723xx |     |     | Electrical characteristics |     |
| ----------------------- | --- | --- | -------------------------- | --- |
Table 82. SPI dynamic characteristics(1) (continued)
| Symbol  | Parameter |  Conditions | Min Typ | Max Unit |
| ------- | --------- | ----------- | ------- | -------- |
| tsu(MI) |           | Master mode | 4 -     | -        |
Data input setup time
| tsu(SI) |     | Slave mode  | 3.5 - | -   |
| ------- | --- | ----------- | ----- | --- |
| th(MI)  |     | Master mode | 3 -   | -   |
Data input hold time
| th(SI)                            |     | Slave mode | 1 - | -   |
| --------------------------------- | --- | ---------- | --- | --- |
| ta(SO) Data output access time    |     | Slave mode | 7 9 | 21  |
| tdis(SO) Data output disable time |     | Slave mode | 5 7 | 12  |
ns
|     |     | Slave mode 2.7≤VDD≤3.6V  | - 6.5 | 10  |
| --- | --- | ------------------------ | ----- | --- |
tv(SO)
| Data output valid time |     | Slave mode 1.71≤VDD≤3.6V | - 6.5 | 13.5 |
| ---------------------- | --- | ------------------------ | ----- | ---- |
| tv(MO)                 |     | Master mode              | - 2   | 3    |
Slave mode
|                              |     |               | 4.5 - | -   |
| ---------------------------- | --- | ------------- | ----- | --- |
| th(SO) Data output hold time |     | 1.71≤VDD≤3.6V |       |     |
| th(MO)                       |     | Master mode   | 0 -   | -   |
1. Guaranteed by characterization results.
2. Excepting SPI1 with SCK IO=PA5. In this configuration, the maximum achievable frequency is 40 MHz.
3. Maximum frequency of the slave transmitter is determined by sum of Tv(SO) and Tsu(MI) intervals which has to fit into SCK
level phase preceding the SCK sampling edge.This value can be achieved when it communicates with a Master having
Tsu(MI)=0 while signal Duty(SCK)=50%.
Figure 52. SPI timing diagram - slave mode and CPHA = 0
(cid:49)(cid:54)(cid:54)(cid:3)(cid:76)(cid:81)(cid:83)(cid:88)(cid:87)
|     |                                                                                                                   | (cid:87) (cid:70)(cid:11)(cid:54)(cid:38)(cid:46)(cid:12) | (cid:87) (cid:75)(cid:11)(cid:49)(cid:54)(cid:54)(cid:12) |     |
| --- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --- |
|     | (cid:87) (cid:87)                                                                                                 |                                                           | (cid:87)                                                  |     |
|     | (cid:86)(cid:88)(cid:11)(cid:49)(cid:54)(cid:54)(cid:12) (cid:90)(cid:11)(cid:54)(cid:38)(cid:46)(cid:43)(cid:12) |                                                           | (cid:85)(cid:11)(cid:54)(cid:38)(cid:46)(cid:12)          |     |
(cid:38)(cid:51)(cid:43)(cid:36)(cid:32)(cid:19)
(cid:87)(cid:88)(cid:83)(cid:81)(cid:76)(cid:3)(cid:46)(cid:38)(cid:54)
(cid:38)(cid:51)(cid:50)(cid:47)(cid:32)(cid:19)
(cid:38)(cid:51)(cid:43)(cid:36)(cid:32)(cid:19)
(cid:38)(cid:51)(cid:50)(cid:47)(cid:32)(cid:20)
(cid:87) (cid:68)(cid:11)(cid:54)(cid:50)(cid:12) (cid:87) (cid:90)(cid:11)(cid:54)(cid:38)(cid:46)(cid:47)(cid:12) (cid:87) (cid:89)(cid:11)(cid:54)(cid:50)(cid:12) (cid:87) (cid:75)(cid:11)(cid:54)(cid:50)(cid:12) (cid:87) (cid:73)(cid:11)(cid:54)(cid:38)(cid:46)(cid:12) (cid:87) (cid:71)(cid:76)(cid:86)(cid:11)(cid:54)(cid:50)(cid:12)
(cid:48)(cid:44)(cid:54)(cid:50)(cid:3)(cid:82)(cid:88)(cid:87)(cid:83)(cid:88)(cid:87) (cid:41)(cid:76)(cid:85)(cid:86)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:3)(cid:50)(cid:56)(cid:55) (cid:49)(cid:72)(cid:91)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:86)(cid:3)(cid:50)(cid:56)(cid:55) (cid:47)(cid:68)(cid:86)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:3)(cid:50)(cid:56)(cid:55)
(cid:87) (cid:75)(cid:11)(cid:54)(cid:44)(cid:12)
(cid:87)
(cid:86)(cid:88)(cid:11)(cid:54)(cid:44)(cid:12)
(cid:48)(cid:50)(cid:54)(cid:44)(cid:3)(cid:76)(cid:81)(cid:83)(cid:88)(cid:87) (cid:41)(cid:76)(cid:85)(cid:86)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:3)(cid:44)(cid:49) (cid:49)(cid:72)(cid:91)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:86)(cid:3)(cid:44)(cid:49) (cid:47)(cid:68)(cid:86)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:3)(cid:44)(cid:49)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:20)(cid:25)(cid:24)(cid:27)(cid:57)(cid:20)
|     |     | DocID029808 Rev 3 |     | 167/229 |
| --- | --- | ----------------- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
Figure 53. SPI timing diagram - slave mode and CPHA = 1
(cid:49)(cid:54)(cid:54)(cid:3)(cid:76)(cid:81)(cid:83)(cid:88)(cid:87)
(cid:38)(cid:51)(cid:43)(cid:36)(cid:32)(cid:20)
(cid:38)(cid:51)(cid:50)(cid:47)(cid:32)(cid:19)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:20)(cid:25)(cid:24)(cid:28)(cid:57)(cid:20)
Figure 54. SPI timing diagram - master mode
168/229 DocID029808 Rev 3
(cid:87)(cid:88)(cid:83)(cid:81)(cid:76)(cid:3)(cid:46)(cid:38)(cid:54)
(cid:87)
(cid:70)(cid:11)(cid:54)(cid:38)(cid:46)(cid:12)
(cid:87) (cid:87) (cid:87) (cid:87)
(cid:86)(cid:88)(cid:11)(cid:49)(cid:54)(cid:54)(cid:12) (cid:90)(cid:11)(cid:54)(cid:38)(cid:46)(cid:43)(cid:12) (cid:73)(cid:11)(cid:54)(cid:38)(cid:46)(cid:12) (cid:75)(cid:11)(cid:49)(cid:54)(cid:54)(cid:12)
(cid:38)(cid:51)(cid:43)(cid:36)(cid:32)(cid:20)
(cid:38)(cid:51)(cid:50)(cid:47)(cid:32)(cid:20)
(cid:87) (cid:87) (cid:87) (cid:87) (cid:87) (cid:87)
(cid:68)(cid:11)(cid:54)(cid:50)(cid:12) (cid:90)(cid:11)(cid:54)(cid:38)(cid:46)(cid:47)(cid:12) (cid:89)(cid:11)(cid:54)(cid:50)(cid:12) (cid:75)(cid:11)(cid:54)(cid:50)(cid:12) (cid:85)(cid:11)(cid:54)(cid:38)(cid:46)(cid:12) (cid:71)(cid:76)(cid:86)(cid:11)(cid:54)(cid:50)(cid:12)
(cid:48)(cid:44)(cid:54)(cid:50)(cid:3)(cid:82)(cid:88)(cid:87)(cid:83)(cid:88)(cid:87) (cid:41)(cid:76)(cid:85)(cid:86)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:3)(cid:50)(cid:56)(cid:55) (cid:49)(cid:72)(cid:91)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:86)(cid:3)(cid:50)(cid:56)(cid:55) (cid:47)(cid:68)(cid:86)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:3)(cid:50)(cid:56)(cid:55)
(cid:87) (cid:87)
(cid:86)(cid:88)(cid:11)(cid:54)(cid:44)(cid:12) (cid:75)(cid:11)(cid:54)(cid:44)(cid:12)
(cid:48)(cid:50)(cid:54)(cid:44)(cid:3)(cid:76)(cid:81)(cid:83)(cid:88)(cid:87) (cid:41)(cid:76)(cid:85)(cid:86)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:3)(cid:44)(cid:49) (cid:49)(cid:72)(cid:91)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:86)(cid:3)(cid:44)(cid:49) (cid:47)(cid:68)(cid:86)(cid:87)(cid:3)(cid:69)(cid:76)(cid:87)(cid:3)(cid:44)(cid:49)
(cid:68)(cid:76)(cid:20)(cid:23)(cid:20)(cid:22)(cid:25)(cid:70)
(cid:87)(cid:88)(cid:83)(cid:87)(cid:88)(cid:50)(cid:3)(cid:46)(cid:38)(cid:54)
(cid:43)(cid:76)(cid:74)(cid:75)
(cid:49)(cid:54)(cid:54)(cid:3)(cid:76)(cid:81)(cid:83)(cid:88)(cid:87)
(cid:87)(cid:70)(cid:11)(cid:54)(cid:38)(cid:46)(cid:12)
(cid:38)(cid:51)(cid:43)(cid:36)(cid:32)(cid:19)
(cid:38)(cid:51)(cid:50)(cid:47)(cid:32)(cid:19)
(cid:38)(cid:51)(cid:43)(cid:36)(cid:32)(cid:19)
(cid:38)(cid:51)(cid:50)(cid:47)(cid:32)(cid:20)
(cid:87)(cid:90)(cid:11)(cid:54)(cid:38)(cid:46)(cid:43)(cid:12) (cid:87)(cid:85)(cid:11)(cid:54)(cid:38)(cid:46)(cid:12)
(cid:87)(cid:90)(cid:11)(cid:54)(cid:38)(cid:46)(cid:47)(cid:12) (cid:87)(cid:73)(cid:11)(cid:54)(cid:38)(cid:46)(cid:12)
(cid:48)(cid:44)(cid:54)(cid:50)
(cid:47)(cid:54)(cid:37)(cid:3)(cid:44)(cid:49)
(cid:44)(cid:49)(cid:51)(cid:56)(cid:55)
(cid:87)(cid:75)(cid:11)(cid:48)(cid:44)(cid:12)
(cid:48)(cid:50)(cid:54)(cid:44)
(cid:37)(cid:44)(cid:55)(cid:20)(cid:3)(cid:50)(cid:56)(cid:55) (cid:47)(cid:54)(cid:37)(cid:3)(cid:50)(cid:56)(cid:55)
(cid:50)(cid:56)(cid:55)(cid:51)(cid:56)(cid:55)
(cid:87)(cid:88)(cid:83)(cid:87)(cid:88)(cid:50)(cid:3)(cid:46)(cid:38)(cid:54)
(cid:38)(cid:51)(cid:43)(cid:36)(cid:32)(cid:20)
(cid:38)(cid:51)(cid:50)(cid:47)(cid:32)(cid:19)
(cid:38)(cid:51)(cid:43)(cid:36)(cid:32)(cid:20)
(cid:38)(cid:51)(cid:50)(cid:47)(cid:32)(cid:20)
(cid:87)(cid:86)(cid:88)(cid:11)(cid:48)(cid:44)(cid:12)
(cid:48)(cid:54)(cid:37)(cid:3)(cid:44)(cid:49) (cid:37)(cid:44)(cid:55)(cid:25)(cid:3)(cid:44)(cid:49)
(cid:48)(cid:54)(cid:37)(cid:3)(cid:50)(cid:56)(cid:55)
(cid:87)(cid:89)(cid:11)(cid:48)(cid:50)(cid:12) (cid:87)(cid:75)(cid:11)(cid:48)(cid:50)(cid:12)

| STM32F722xx STM32F723xx |     |     |     | Electrical characteristics |     |
| ----------------------- | --- | --- | --- | -------------------------- | --- |
I2S interface characteristics
Unless otherwise specified, the parameters given in Table 83 for the I2S interface are
derived from tests performed under the ambient temperature, f PCLKx  frequency and V DD
supply voltage conditions summarized in Table 17, with the following configuration:
• Output speed is set to OSPEEDRy[1:0] = 10
• Capacitive load C = 30 pF
• Measurement points are done at CMOS levels: 0.5V
DD
Refer to Section 5.3.20: I/O port characteristics for more details on the input/output alternate
function characteristics (CK, SD, WS).
Table 83. I2S dynamic characteristics(1)

| Symbol | Parameter              |     | Conditions | Min      | Max Unit      |
| ------ | ---------------------- | --- | ---------- | -------- | ------------- |
| f      | I2S Main clock output  |     | -          | 256 x 8K | 256xFs(2) MHz |
MCK
|     |                      | Master data: 32 bits |     | -   | 64xFs |
| --- | -------------------- | -------------------- | --- | --- | ----- |
| f   | I2S clock frequency  |                      |     |     | MHz   |
CK
|     |                                 | Slave data: 32 bits |     | -   | 64xFs |
| --- | ------------------------------- | ------------------- | --- | --- | ----- |
| D   | I2S clock frequency duty cycle  | Slave receiver      |     | 30  | 70 %  |
CK
| t   | WS valid time  | Master mode  |     | -   | 3   |
| --- | -------------- | ------------ | --- | --- | --- |
v(WS)
| t   | WS hold time  | Master mode  |     | 0   | -   |
| --- | ------------- | ------------ | --- | --- | --- |
h(WS)
| t su(WS) | WS setup time  | Slave mode |     | 5   | -   |
| -------- | -------------- | ---------- | --- | --- | --- |
| t        | WS hold time   | Slave mode |     | 2   | -   |
h(WS)
| t   |     | Master receiver  |     | 2.5 | -   |
| --- | --- | ---------------- | --- | --- | --- |
su(SD_MR)
Data input setup time
| t   |     | Slave receiver  |     | 2.5 | -   |
| --- | --- | --------------- | --- | --- | --- |
su(SD_SR)
ns
| t   |     | Master receiver  |     | 3.5 | -   |
| --- | --- | ---------------- | --- | --- | --- |
h(SD_MR)
Data input hold time
| t h(SD_SR) |     | Slave receiver                         |     | 2   | -   |
| ---------- | --- | -------------------------------------- | --- | --- | --- |
| t          |     | Slave transmitter (after enable edge)  |     | -   | 12  |
v(SD_ST)
Data output valid time
| t   |     | Master transmitter (after enable edge)  |     | -   | 3   |
| --- | --- | --------------------------------------- | --- | --- | --- |
v(SD_MT)
| t   |     | Slave transmitter (after enable edge)  |     | 5   | -   |
| --- | --- | -------------------------------------- | --- | --- | --- |
h(SD_ST)
Data output hold time
| t   |     | Master transmitter (after enable edge)  |     | 0   | -   |
| --- | --- | --------------------------------------- | --- | --- | --- |
h(SD_MT)
1. Guaranteed by characterization results.
2. 256xFs maximum is 49.152 MHz (APB1 Maximum frequency).
Note: Refer to RM0385 reference manual I2S section for more details on the sampling frequency
(F S ).
f , f , and D  values reflect only the digital peripheral behavior. The values of these
MCK CK CK
parameters might be slightly impacted by the source clock precision. D  depends mainly
CK
on the value of ODD bit. The digital contribution leads to a minimum value of
(I2SDIV/(2*I2SDIV+ODD) and a maximum value of (I2SDIV+ODD)/(2*I2SDIV+ODD). F
S
maximum value is supported for each mode/condition.
|     |     | DocID029808 Rev 3 |     |     | 169/229 |
| --- | --- | ----------------- | --- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
| Figure 55. I2S slave timing diagram (Philips protocol)(1) |     |     |     |     |
| --------------------------------------------------------- | --- | --- | --- | --- |
(cid:87)(cid:70)(cid:11)(cid:38)(cid:46)(cid:12)
(cid:38)(cid:51)(cid:50)(cid:47)(cid:3)(cid:32)(cid:3)(cid:19)
(cid:87)(cid:88)(cid:83)(cid:81)(cid:44)(cid:3)(cid:46)(cid:38)
(cid:38)(cid:51)(cid:50)(cid:47)(cid:3)(cid:32)(cid:3)(cid:20)
(cid:87)(cid:75)(cid:11)(cid:58)(cid:54)(cid:12)
| (cid:87)(cid:90)(cid:11)(cid:38)(cid:46)(cid:43)(cid:12) |     | (cid:87)(cid:90)(cid:11)(cid:38)(cid:46)(cid:47)(cid:12) |     |     |
| -------------------------------------------------------- | --- | -------------------------------------------------------- | --- | --- |
(cid:58)(cid:54)(cid:3)(cid:76)(cid:81)(cid:83)(cid:88)(cid:87)
| (cid:87)(cid:86)(cid:88)(cid:11)(cid:58)(cid:54)(cid:12) |     |     | (cid:87)(cid:89)(cid:11)(cid:54)(cid:39)(cid:66)(cid:54)(cid:55)(cid:12) | (cid:87)(cid:75)(cid:11)(cid:54)(cid:39)(cid:66)(cid:54)(cid:55)(cid:12) |
| -------------------------------------------------------- | --- | --- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
(cid:54)(cid:39)(cid:87)(cid:85)(cid:68)(cid:81)(cid:86)(cid:80)(cid:76)(cid:87)
|     | (cid:47)(cid:54)(cid:37)(cid:3)(cid:87)(cid:85)(cid:68)(cid:81)(cid:86)(cid:80)(cid:76)(cid:87)(cid:11)(cid:20)(cid:12) | (cid:48)(cid:54)(cid:37)(cid:3)(cid:87)(cid:85)(cid:68)(cid:81)(cid:86)(cid:80)(cid:76)(cid:87) | (cid:37)(cid:76)(cid:87)(cid:81)(cid:3)(cid:87)(cid:85)(cid:68)(cid:81)(cid:86)(cid:80)(cid:76)(cid:87) | (cid:47)(cid:54)(cid:37)(cid:3)(cid:87)(cid:85)(cid:68)(cid:81)(cid:86)(cid:80)(cid:76)(cid:87) |
| --- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
|     | (cid:87)(cid:86)(cid:88)(cid:11)(cid:54)(cid:39)(cid:66)(cid:54)(cid:53)(cid:12)                                        |                                                                                                 | (cid:87)(cid:75)(cid:11)(cid:54)(cid:39)(cid:66)(cid:54)(cid:53)(cid:12)                                |                                                                                                 |
|     | (cid:47)(cid:54)(cid:37)(cid:3)(cid:85)(cid:72)(cid:70)(cid:72)(cid:76)(cid:89)(cid:72)(cid:11)(cid:20)(cid:12)         | (cid:48)(cid:54)(cid:37)(cid:3)(cid:85)(cid:72)(cid:70)(cid:72)(cid:76)(cid:89)(cid:72)         | (cid:37)(cid:76)(cid:87)(cid:81)(cid:3)(cid:85)(cid:72)(cid:70)(cid:72)(cid:76)(cid:89)(cid:72)         | (cid:47)(cid:54)(cid:37)(cid:3)(cid:85)(cid:72)(cid:70)(cid:72)(cid:76)(cid:89)(cid:72)         |
(cid:54)(cid:39)(cid:85)(cid:72)(cid:70)(cid:72)(cid:76)(cid:89)(cid:72)
(cid:48)(cid:54)(cid:23)(cid:25)(cid:24)(cid:21)(cid:27)(cid:57)(cid:20)
1. LSB transmit/receive of the previously transmitted byte. No LSB transmit/receive is sent before the first
byte.
Figure 56. I2S master timing diagram (Philips protocol)(1)
(cid:87)(cid:73)(cid:11)(cid:38)(cid:46)(cid:12) (cid:87)(cid:85)(cid:11)(cid:38)(cid:46)(cid:12)
(cid:87)(cid:70)(cid:11)(cid:38)(cid:46)(cid:12)
(cid:87)(cid:88)(cid:83)(cid:87)(cid:88)(cid:82)(cid:3)(cid:46)(cid:38) (cid:38)(cid:51)(cid:50)(cid:47)(cid:3)(cid:32)(cid:3)(cid:19)
(cid:87)(cid:90)(cid:11)(cid:38)(cid:46)(cid:43)(cid:12)
(cid:38)(cid:51)(cid:50)(cid:47)(cid:3)(cid:32)(cid:3)(cid:20)
| (cid:87)(cid:89)(cid:11)(cid:58)(cid:54)(cid:12) |     |     |     | (cid:87)(cid:75)(cid:11)(cid:58)(cid:54)(cid:12) |
| ------------------------------------------------ | --- | --- | --- | ------------------------------------------------ |
(cid:87)(cid:90)(cid:11)(cid:38)(cid:46)(cid:47)(cid:12)
(cid:58)(cid:54)(cid:3)(cid:82)(cid:88)(cid:87)(cid:83)(cid:88)(cid:87)
|     |     |     | (cid:87)(cid:89)(cid:11)(cid:54)(cid:39)(cid:66)(cid:48)(cid:55)(cid:12) | (cid:87)(cid:75)(cid:11)(cid:54)(cid:39)(cid:66)(cid:48)(cid:55)(cid:12) |
| --- | --- | --- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
(cid:54)(cid:39)(cid:87)(cid:85)(cid:68)(cid:81)(cid:86)(cid:80)(cid:76)(cid:87) (cid:47)(cid:54)(cid:37)(cid:3)(cid:87)(cid:85)(cid:68)(cid:81)(cid:86)(cid:80)(cid:76)(cid:87)(cid:11)(cid:20)(cid:12) (cid:48)(cid:54)(cid:37)(cid:3)(cid:87)(cid:85)(cid:68)(cid:81)(cid:86)(cid:80)(cid:76)(cid:87) (cid:37)(cid:76)(cid:87)(cid:81)(cid:3)(cid:87)(cid:85)(cid:68)(cid:81)(cid:86)(cid:80)(cid:76)(cid:87) (cid:47)(cid:54)(cid:37)(cid:3)(cid:87)(cid:85)(cid:68)(cid:81)(cid:86)(cid:80)(cid:76)(cid:87)
|     | (cid:87)(cid:86)(cid:88)(cid:11)(cid:54)(cid:39)(cid:66)(cid:48)(cid:53)(cid:12) |     | (cid:87)(cid:75)(cid:11)(cid:54)(cid:39)(cid:66)(cid:48)(cid:53)(cid:12) |     |
| --- | -------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------ | --- |
(cid:54)(cid:39)(cid:85)(cid:72)(cid:70)(cid:72)(cid:76)(cid:89)(cid:72) (cid:47)(cid:54)(cid:37)(cid:3)(cid:85)(cid:72)(cid:70)(cid:72)(cid:76)(cid:89)(cid:72)(cid:11)(cid:20)(cid:12) (cid:48)(cid:54)(cid:37)(cid:3)(cid:85)(cid:72)(cid:70)(cid:72)(cid:76)(cid:89)(cid:72) (cid:37)(cid:76)(cid:87)(cid:81)(cid:3)(cid:85)(cid:72)(cid:70)(cid:72)(cid:76)(cid:89)(cid:72) (cid:47)(cid:54)(cid:37)(cid:3)(cid:85)(cid:72)(cid:70)(cid:72)(cid:76)(cid:89)(cid:72)
(cid:48)(cid:54)(cid:23)(cid:25)(cid:24)(cid:21)(cid:28)(cid:57)(cid:20)
1. LSB transmit/receive of the previously transmitted byte. No LSB transmit/receive is sent before the first
byte.
170/229 DocID029808 Rev 3

| STM32F722xx STM32F723xx |     |     | Electrical characteristics |     |     |
| ----------------------- | --- | --- | -------------------------- | --- | --- |
SAI characteristics
Unless otherwise specified, the parameters given in Table 84 for SAI are derived from tests
performed under the ambient temperature, f PCLKx  frequency and VDD supply voltage
conditions summarized in Table 17, with the following configuration:
• Output speed is set to OSPEEDRy[1:0] = 10
• Capacitive load C=30 pF
• Measurement points are performed at CMOS levels: 0.5V
DD
Refer to Section 5.3.20: I/O port characteristics for more details on the input/output alternate
function characteristics (SCK,SD,WS).
Table 84. SAI characteristics(1)

| Symbol  | Parameter              | Conditions  | Min    | Max    | Unit  |
| ------- | ---------------------- | ----------- | ------ | ------ | ----- |
| f       | SAI Main clock output  |   -         | 256x8K | 256xFs |       |
MCKL
128xFs(3)
|     |                         | Master data: 32 bits | -   |     | MHz |
| --- | ----------------------- | -------------------- | --- | --- | --- |
| F   | SAI clock frequency(2)  |                      |     |     |     |
CK
|     |     | Slave data: 32 bits | -   | 128xFs(3) |     |
| --- | --- | ------------------- | --- | --------- | --- |
Master mode
|     |     |     | -   | 18  |     |
| --- | --- | --- | --- | --- | --- |
2.7≤VDD≤3.6V
| t     | FS valid time  |             |     |     |     |
| ----- | -------------- | ----------- | --- | --- | --- |
| v(FS) |                | Master mode |     |     |     |
|       |                |             | -   | 20  |     |
1.71≤VDD≤3.6V
| t   | FS setup time  | Slave mode  | 1   | -   |     |
| --- | -------------- | ----------- | --- | --- | --- |
su(FS)
|               |               | Master mode      | 7   | -   |     |
| ------------- | ------------- | ---------------- | --- | --- | --- |
| t h(FS)       | FS hold time  |                  |     |     |     |
|               |               | Slave mode       | 0.5 | -   |     |
| t su(SD_A_MR) |               | Master receiver  | 1   | -   |     |
Data input setup time
| t   |     | Slave receiver  | 2.5 | -   |     |
| --- | --- | --------------- | --- | --- | --- |
su(SD_B_SR)
| t   |     | Master receiver  | 3.5 | -   |     |
| --- | --- | ---------------- | --- | --- | --- |
h(SD_A_MR)
Data input hold time
ns
| t   |     | Slave receiver  | 0.5 |     |     |
| --- | --- | --------------- | --- | --- | --- |
h(SD_B_SR)
Slave transmitter (after enable edge)
|     |     |     | -   | 11  |     |
| --- | --- | --- | --- | --- | --- |
2.7≤VDD≤3.6V
| t   | Data output valid time  |     |     |     |     |
| --- | ----------------------- | --- | --- | --- | --- |
v(SD_B_MT)
Slave transmitter (after enable edge)
|     |     |     | -   | 18  |     |
| --- | --- | --- | --- | --- | --- |
1.71≤VDD≤3.6V
t h(SD_B_ST) Data output hold time  Slave transmitter (after enable edge) 5 -
Master transmitter (after enable edge)
|     |     |     | -   | 16  |     |
| --- | --- | --- | --- | --- | --- |
2.7≤VDD≤3.6V
| t   | Data output valid time  |     |     |     |     |
| --- | ----------------------- | --- | --- | --- | --- |
v(SD_A_MT)
Master transmitter (after enable edge)
|     |     |     | -   | 18.5 |     |
| --- | --- | --- | --- | ---- | --- |
1.71≤VDD≤3.6V
t Data output hold time  Master transmitter (after enable edge)  7.5 -
h(SD_A_MT)
1. Guaranteed by characterization results.
2. APB clock frequency must be at least twice SAI clock frequency.
3. With Fs = 192 KHz.
|     |     | DocID029808 Rev 3 |     |     | 171/229 |
| --- | --- | ----------------- | --- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
Figure 57. SAI master timing waveforms
(cid:17)(cid:15)(cid:70)(cid:51)(cid:35)(cid:43)
(cid:51)(cid:33)(cid:41)(cid:63)(cid:51)(cid:35)(cid:43)(cid:63)(cid:56)
(cid:84)(cid:72)(cid:8)(cid:38)(cid:51)(cid:9)
(cid:51)(cid:33)(cid:41)(cid:63)(cid:38)(cid:51)(cid:63)(cid:56)
(cid:8)(cid:79)(cid:85)(cid:84)(cid:80)(cid:85)(cid:84)(cid:9) (cid:84)(cid:86)(cid:8)(cid:38)(cid:51)(cid:9) (cid:84)(cid:86)(cid:8)(cid:51)(cid:36)(cid:63)(cid:45)(cid:52)(cid:9) (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:63)(cid:45)(cid:52)(cid:9)
(cid:51)(cid:33)(cid:41)(cid:63)(cid:51)(cid:36)(cid:63)(cid:56)
(cid:51)(cid:76)(cid:79)(cid:84)(cid:0)(cid:78) (cid:51)(cid:76)(cid:79)(cid:84)(cid:0)(cid:78)(cid:11)(cid:18)
(cid:8)(cid:84)(cid:82)(cid:65)(cid:78)(cid:83)(cid:77)(cid:73)(cid:84)(cid:9)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:51)(cid:36)(cid:63)(cid:45)(cid:50)(cid:9) (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:63)(cid:45)(cid:50)(cid:9)
(cid:51)(cid:33)(cid:41)(cid:63)(cid:51)(cid:36)(cid:63)(cid:56) (cid:51)(cid:76)(cid:79)(cid:84)(cid:0)(cid:78)
(cid:8)(cid:82)(cid:69)(cid:67)(cid:69)(cid:73)(cid:86)(cid:69)(cid:9)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:23)(cid:17)(cid:54)(cid:17)
Figure 58. SAI slave timing waveforms
(cid:17)(cid:15)(cid:70)(cid:51)(cid:35)(cid:43)
(cid:51)(cid:33)(cid:41)(cid:63)(cid:51)(cid:35)(cid:43)(cid:63)(cid:56)
(cid:84)(cid:87)(cid:8)(cid:35)(cid:43)(cid:40)(cid:63)(cid:56)(cid:9) (cid:84)(cid:87)(cid:8)(cid:35)(cid:43)(cid:44)(cid:63)(cid:56)(cid:9) (cid:84)(cid:72)(cid:8)(cid:38)(cid:51)(cid:9)
(cid:51)(cid:33)(cid:41)(cid:63)(cid:38)(cid:51)(cid:63)(cid:56)
(cid:8)(cid:73)(cid:78)(cid:80)(cid:85)(cid:84)(cid:9) (cid:84)(cid:83)(cid:85)(cid:8)(cid:38)(cid:51)(cid:9) (cid:84)(cid:86)(cid:8)(cid:51)(cid:36)(cid:63)(cid:51)(cid:52)(cid:9) (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:63)(cid:51)(cid:52)(cid:9)
(cid:51)(cid:33)(cid:41)(cid:63)(cid:51)(cid:36)(cid:63)(cid:56)
(cid:51)(cid:76)(cid:79)(cid:84)(cid:0)(cid:78) (cid:51)(cid:76)(cid:79)(cid:84)(cid:0)(cid:78)(cid:11)(cid:18)
(cid:8)(cid:84)(cid:82)(cid:65)(cid:78)(cid:83)(cid:77)(cid:73)(cid:84)(cid:9)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:51)(cid:36)(cid:63)(cid:51)(cid:50)(cid:9) (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:63)(cid:51)(cid:50)(cid:9)
(cid:51)(cid:33)(cid:41)(cid:63)(cid:51)(cid:36)(cid:63)(cid:56) (cid:51)(cid:76)(cid:79)(cid:84)(cid:0)(cid:78)
(cid:8)(cid:82)(cid:69)(cid:67)(cid:69)(cid:73)(cid:86)(cid:69)(cid:9)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:23)(cid:18)(cid:54)(cid:17)
172/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
USB OTG full speed (FS) characteristics
This interface is present in both the USB OTG HS and USB OTG FS controllers.
|            |        |                                             | Table 85. USB OTG full speed startup time |           |     |     |     |      |     |       |     |
| ---------- | ------ | ------------------------------------------- | ----------------------------------------- | --------- | --- | --- | --- | ---- | --- | ----- | --- |
|            | Symbol |                                             |                                           | Parameter |     |     |     |  Max |     |  Unit |     |
| t          | (1)    | USB OTG full speed transceiver startup time |                                           |           |     |     |     | 1    |     |       | µs  |
STARTUP
1. Guaranteed by design.

Table 86. USB OTG full speed DC electrical characteristics
|     |        |     |           |     |     |            |     | Min. |      | Max.( |      |
| --- | ------ | --- | --------- | --- | --- | ---------- | --- | ---- | ---- | ----- | ---- |
|     | Symbol |     | Parameter |     |     | Conditions |     |      | Typ. |       | Unit |
|     |        |     |           |     |     |            |     | (1)  |      | 1)    |      |
USB OTG full speed
|     | V   | transceiver operating  |     |     |     |     | -   | 3.0(2) |     | - 3.6 | V   |
| --- | --- | ---------------------- | --- | --- | --- | --- | --- | ------ | --- | ----- | --- |
DDUSB
voltage
I(USB_FS_DP/DM,
|        | V   | (3) Differential input sensitivity |     |     |     |                |     | 0.2 |     | -   | -   |
| ------ | --- | ---------------------------------- | --- | --- | --- | -------------- | --- | --- | --- | --- | --- |
| Input  | DI  |                                    |     |     |     | USB_HS_DP/DM)  |     |     |     |     |     |
levels
(3) Differential common mode
|     | V CM |     |     |     |     | Includes V | DI  range | 0.8 |     | - 2.5 | V   |
| --- | ---- | --- | --- | --- | --- | ---------- | --------- | --- | --- | ----- | --- |
range
Single ended receiver
|     | V   | (3) |     |     |     |     | -   | 1.3 |     | - 2.0 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- |
SE threshold
 of 1.5 kΩ to 3.6 V(4)
| Output  | V   | Static output level low |     |     | R   |     |     | -   |     | - 0.3 |     |
| ------- | --- | ----------------------- | --- | --- | --- | --- | --- | --- | --- | ----- | --- |
|         | OL  |                         |     |     |     | L   |     |     |     |       |     |
V
levels V Static output level high R  of 15 kΩ to V (4) 2.8 - 3.6
|     | OH  |     |     |     |     | L   | SS  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
PA11, PA12
|     |     |     |     |     |     | V IN  = V | DD  | 14.25 |     | - 24.8 |     |
| --- | --- | --- | --- | --- | --- | --------- | --- | ----- | --- | ------ | --- |
(USB_FS_DP/DM)
|     | R   | PA9, PB13 |     |     |     |     |     |     |     |     |     |
| --- | --- | --------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
PD
|     |     |               |     |     |     | V IN  = V | DD  |     |     |     |     |
| --- | --- | ------------- | --- | --- | --- | --------- | --- | --- | --- | --- | --- |
|     |     | (OTG_FS_VBUS, |     |     |     |           |     | 2.4 | 5.2 | 8   |     |
OTG_HS_VBUS)
kΩ
|     |     | PA12 (USB_FS_DP) |     |     | V   |  = V | , during idle | 0.9 | 1.25 | 1.575 |     |
| --- | --- | ---------------- | --- | --- | --- | ---- | ------------- | --- | ---- | ----- | --- |
IN SS
PA9, PB13
R
|     | PU  |               |     |     |     | V IN  = V | SS , during  |      |      |      |     |
| --- | --- | ------------- | --- | --- | --- | --------- | ------------ | ---- | ---- | ---- | --- |
|     |     | (OTG_FS_VBUS, |     |     |     |           |              | 0.55 | 0.95 | 1.35 |     |
reception
OTG_HS_VBUS)
1. All the voltages are measured from the local ground potential.
2. The USB OTG full speed transceiver functionality is ensured down to 2.7 V but not the full USB full speed
| electrical characteristics which are degraded in the 2.7-to-3.0 V V |     |     |     |     |     |     |  voltage range. |     |     |     |     |
| ------------------------------------------------------------------- | --- | --- | --- | --- | --- | --- | --------------- | --- | --- | --- | --- |
DDUSB
3. Guaranteed by design.
4. R L  is the load connected on the USB OTG full speed drivers.
When VBUS sensing feature is enabled, PA9 and PB13 should be left at their default state
Note:
(floating input), not as alternate function. A typical 200 µA current consumption of the
sensing block (current to voltage conversion to determine the different sessions) can be
observed on PA9 and PB13 when the feature is enabled.
|     |     |     | DocID029808 Rev 3 |     |     |     |     |     |     |     | 173/229 |
| --- | --- | --- | ----------------- | --- | --- | --- | --- | --- | --- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
Figure 59. USB OTG full speed timings: definition of data signal rise and fall time
(cid:38)(cid:85)(cid:82)(cid:86)(cid:86)(cid:3)(cid:82)(cid:89)(cid:72)(cid:85)
(cid:83)(cid:82)(cid:76)(cid:81)(cid:87)(cid:86)
(cid:39)(cid:76)(cid:73)(cid:73)(cid:72)(cid:85)(cid:72)(cid:81)(cid:87)(cid:76)(cid:68)(cid:79)
(cid:71)(cid:68)(cid:87)(cid:68)(cid:3)(cid:79)(cid:76)(cid:81)(cid:72)(cid:86)
(cid:57)(cid:38)(cid:53)(cid:54)
(cid:57)(cid:54)(cid:54)
|     | (cid:87)(cid:73) | (cid:87)(cid:85) |     |     |     |
| --- | ---------------- | ---------------- | --- | --- | --- |
(cid:68)(cid:76)(cid:20)(cid:23)(cid:20)(cid:22)(cid:26)(cid:69)
           Table 87. USB OTG full speed electrical characteristics(1)
Driver characteristics
| Symbol                            | Parameter |     | Conditions | Min Max | Unit |
| --------------------------------- | --------- | --- | ---------- | ------- | ---- |
| t Rise time(2)                    |           |     | C = 50 pF  | 4 20    | ns   |
| r                                 |           |     | L          |         |      |
| t Fall time(2)                    |           |     | C = 50 pF  | 4 20    | ns   |
| f                                 |           |     | L          |         |      |
| t rfm Rise/ fall time matching    |           |     | t/t r f    | 90 111  | %    |
| V Output signal crossover voltage |           |     | -          | 1.3 2.0 | V    |
CRS
Driving high or
| Z Output driver impedance(3) |     |     |      | 28 44 | Ω   |
| ---------------------------- | --- | --- | ---- | ----- | --- |
| DRV                          |     |     | low  |       |     |
1. Guaranteed by design.
2. Measured from 10% to 90% of the data signal. For more detailed informations, please refer to USB
Specification - Chapter 7 (version 2.0).
3. No external termination series resistors are required on DP (D+) and DM (D-) pins since the matching
impedance is included in the embedded driver.
USB high speed (HS) characteristics (through ULPI in STM32F722xx devices)
Unless otherwise specified, the parameters given in Table 90 for ULPI are derived from
tests performed under the ambient temperature, f  frequency summarized in Table 89
HCLK
and V DD  supply voltage conditions summarized in Table 88, with the following configuration:
•
Output speed is set to OSPEEDRy[1:0] = 11, unless otherwise specified
•
Capacitive load C = 20 pF, unless otherwise specified
•
| Measurement points are done at CMOS levels: 0.5V |     |     | DD  | .   |     |
| ------------------------------------------------ | --- | --- | --- | --- | --- |
Refer to Section 5.3.20: I/O port characteristics for more details on the input/output
characteristics.
|             | Table 88. USB HS DC electrical characteristics  |           |     |                 |      |
| ----------- | ----------------------------------------------- | --------- | --- | --------------- | ---- |
| Symbol      |                                                 | Parameter |     | Min.(1) Max.(1) | Unit |
| Input level | V USB OTG HS operating voltage                  |           |     | 1.7 3.6         | V    |
DD
1. All the voltages are measured from the local ground potential.
174/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
|            | Table 89. USB HS clock timing parameters(1) |     |     |     |     |     |     |
| ---------- | ------------------------------------------- | --- | --- | --- | --- | --- | --- |

| Symbol |     | Parameter |     | Min | Typ | Max | Unit |
| ------ | --- | --------- | --- | --- | --- | --- | ---- |
f  value to guarantee proper operation of
| -   | HCLK |     |     | 30  | -   | -   | MHz |
| --- | ---- | --- | --- | --- | --- | --- | --- |
USB HS interface
F START_8BIT Frequency (first transition) 8-bit ±10% 54 60 66 MHz
| F   | Frequency (steady state) ±500 ppm |     |     | 59.97 | 60  | 60.03 | MHz |
| --- | --------------------------------- | --- | --- | ----- | --- | ----- | --- |
STEADY
| D   | Duty cycle (first transition) |     | 8-bit ±10% | 40  | 50  | 60  | %   |
| --- | ----------------------------- | --- | ---------- | --- | --- | --- | --- |
START_8BIT
| D   | Duty cycle (steady state) ±500 ppm |     |     | 49.975 | 50  | 50.025 | %   |
| --- | ---------------------------------- | --- | --- | ------ | --- | ------ | --- |
STEADY
Time to reach the steady state frequency and
| t      |                                       |     |            | -   | -   | 1.4 | ms  |
| ------ | ------------------------------------- | --- | ---------- | --- | --- | --- | --- |
| STEADY | duty cycle after the first transition |     |            |     |     |     |     |
| t      | Clock startup time after the          |     | Peripheral | -   | -   | 5.6 |     |
START_DEV
ms
| t   | de-assertion of SuspendM |     | Host | -   | -   | -   |     |
| --- | ------------------------ | --- | ---- | --- | --- | --- | --- |
START_HOST
PHY preparation time after the first transition
| t PREP |     |     |     | -   | -   | -   | µs  |
| ------ | --- | --- | --- | --- | --- | --- | --- |
of the input clock
1. Guaranteed by design.
Figure 60. ULPI timing diagram
(cid:35)(cid:76)(cid:79)(cid:67)(cid:75)
|     | (cid:84) (cid:51)(cid:35) | (cid:84)(cid:40)(cid:35) |     |     |     |     |     |
| --- | ------------------------- | ------------------------ | --- | --- | --- | --- | --- |
(cid:35)(cid:79)(cid:78)(cid:84)(cid:82)(cid:79)(cid:76)(cid:0)(cid:41)(cid:78)
(cid:8)(cid:53)(cid:44)(cid:48)(cid:41)(cid:63)(cid:36)(cid:41)(cid:50)(cid:12)
| (cid:53)(cid:44)(cid:48)(cid:41)(cid:63)(cid:46)(cid:56)(cid:52)(cid:9) | (cid:84)(cid:51)(cid:36) | (cid:84)(cid:40)(cid:36) |     |     |     |     |     |
| ----------------------------------------------------------------------- | ------------------------ | ------------------------ | --- | --- | --- | --- | --- |
(cid:68)(cid:65)(cid:84)(cid:65)(cid:0)(cid:41)(cid:78)
(cid:8)(cid:24)(cid:13)(cid:66)(cid:73)(cid:84)(cid:9)
(cid:84)
|     |     |     |     | (cid:84) (cid:36)(cid:35) | (cid:36)(cid:35) |     |     |
| --- | --- | --- | --- | ------------------------- | ---------------- | --- | --- |
(cid:35)(cid:79)(cid:78)(cid:84)(cid:82)(cid:79)(cid:76)(cid:0)(cid:79)(cid:85)(cid:84)
(cid:8)(cid:53)(cid:44)(cid:48)(cid:41)(cid:63)(cid:51)(cid:52)(cid:48)(cid:9)
(cid:84)(cid:36)(cid:36)
(cid:68)(cid:65)(cid:84)(cid:65)(cid:0)(cid:79)(cid:85)(cid:84)
(cid:8)(cid:24)(cid:13)(cid:66)(cid:73)(cid:84)(cid:9)
(cid:65)(cid:73)(cid:17)(cid:23)(cid:19)(cid:22)(cid:17)(cid:67)
|     |     | DocID029808 Rev 3 |     |     |     |     | 175/229 |
| --- | --- | ----------------- | --- | --- | --- | --- | ------- |
201

| Electrical characteristics |     |     |     |     | STM32F722xx STM32F723xx |     |     |
| -------------------------- | --- | --- | --- | --- | ----------------------- | --- | --- |
           Table 90. Dynamic characteristics: USB ULPI(1)
| Symbol                                       | Parameter | Conditions |     |     | Min. | Typ. Max. | Unit |
| -------------------------------------------- | --------- | ---------- | --- | --- | ---- | --------- | ---- |
| t Control in (ULPI_DIR, ULPI_NXT) setup time |           |            | -   |     | 1.5  | -         | -    |
SC
| t Control in (ULPI_DIR, ULPI_NXT) hold time |     |     | -   |     | 1   | -   | -   |
| ------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
HC
| t Data in setup time |     |     | -   |     | 1.5 | -   | -   |
| -------------------- | --- | --- | --- | --- | --- | --- | --- |
SD
| t Data in hold time |     |     | -   |     | 1   | -   | -   |
| ------------------- | --- | --- | --- | --- | --- | --- | --- |
HD
|     |     | 2.7 V < V | DD  | < 3.6 V,  |     |     |     |
| --- | --- | --------- | --- | --------- | --- | --- | --- |
ns
|     |     | C   |  = 20 pF and  |     | -   | 6 7.5 |     |
| --- | --- | --- | ------------- | --- | --- | ----- | --- |
L
OSPEEDRy[1:0] = 11
|     |     |     | -   |     | -   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
t DC /t DD Data/control output delay
1.7 V < V < 3.6 V,
|     |     |                 | DD  |     |     | 9.5 11 |     |
| --- | --- | --------------- | --- | --- | --- | ------ | --- |
|     |     | C  = 15 pF and  |     |     | -   |        |     |
L
OSPEEDRy[1:0] = 11
1. Guaranteed by characterization results.
USB high speed (HS) characteristics (Embedded PHY High speed in
STM32F723xx devices)
           Table 91. USB OTG high speed DC electrical characteristics
| Symbol                                    | Parameter  |     | Conditions |     | Min  | Typ  Max  | Unit  |
| ----------------------------------------- | ---------- | --- | ---------- | --- | ---- | --------- | ----- |
| V High speed squelch detection threshold  |            |     |            | -   | 100  |  - 150    | mV    |
hssq
V   High speed disconnect detection threshold  - 525 -  625 mV
hsdsc
V hsdif  High speed differential detection threshold -  100 -  -  mV
High speed data signalling common mode voltage
| V   |     |     |     | -   | -50 |  - 500 | mV  |
| --- | --- | --- | --- | --- | --- | ------ | --- |
hscm range
| V hsoi   High speed idle level      |     |     |     | -   | -10 |  - 10  | mV  |
| ----------------------------------- | --- | --- | --- | --- | --- | ------ | --- |
| V   High speed data signaling high  |     |     |     |  -  | 360 |  - 440 | mV  |
hsoh
| V High speed data signaling low  |     |     |     |  -  | -10 |  - 10 | mV  |
| -------------------------------- | --- | --- | --- | --- | --- | ----- | --- |
hsol
| V Chirp J level  |     |     |     |  -  | 700 | -  1100 | mV  |
| ---------------- | --- | --- | --- | --- | --- | ------- | --- |
chirpj
| V   Chirp K level  |     |     |     |  -  | -900 | -  -500 | mV  |
| ------------------ | --- | --- | --- | --- | ---- | ------- | --- |
chirpk
           Table 92. USB OTG high speed electrical characteristics
| Parameter      | Comments  |     | Conditions  |     | Min  | Typ  Max  | Unit  |
| -------------- | --------- | --- | ----------- | --- | ---- | --------- | ----- |
| t   Rise time  |           |     |             |  -  | 0.5  |  - -      | ns    |
lr
| t Fall time  |     |     |     |  -  | 0.5 |  -  - | ns  |
| ------------ | --- | --- | --- | --- | --- | ----- | --- |
lf
Setup time from INHSDRIVERENABLE=1 to the
| t   |     |     |     |  -  | 10  |  - -  | ns  |
| --- | --- | --- | --- | --- | --- | ----- | --- |
lrfm transition on INHSDATAP/INHSDATAN
Ω
| Z   Driver output impedance  |     |     |     |  -  | 40.5 | - 49.5 |     |
| ---------------------------- | --- | --- | --- | --- | ---- | ------ | --- |
drv
176/229 DocID029808 Rev 3

| STM32F722xx STM32F723xx |     |     | Electrical characteristics |     |     |
| ----------------------- | --- | --- | -------------------------- | --- | --- |

Table 93. USB FS PHY BCD electrical characteristics
| Symbol  |                                      | Parameter  | Conditions | Min  Typ  Max  | Unit  |
| ------- | ------------------------------------ | ---------- | ---------- | -------------- | ----- |
|         | Primary detection mode consumption   |            | -          | - - 300        |       |
| I       |                                      |            |            |                | µA    |
| DDUSB   | Secondary detection mode consumption |            | -          | - - 300        |       |
kΩ
| R   | Data line leakage resistance |     | -   | 300 - - |     |
| --- | ---------------------------- | --- | --- | ------- | --- |
DAT_LKG
| V   | Data line leakage voltage |     | -   | 0.0 - 3.6 | V   |
| --- | ------------------------- | --- | --- | --------- | --- |
DAT_LKG
Ω
R DCP_DAT   Dedicated charging port resistance across D+/D- -  - - 200
| V   |   Logic high |     |  -  | 2.0 - 3.6 |     |
| --- | ------------ | --- | --- | --------- | --- |
LGC_HI
| V   | Logic low |     |  -  | - - 0.8 |     |
| --- | --------- | --- | --- | ------- | --- |
LGC_LOW
| VL  | Logic threshold |     |  -  | 0.8 - 2.0 |     |
| --- | --------------- | --- | --- | --------- | --- |
GC
V
| V   | Data detect voltage |     |  -  | 0.25 - 3.6 |     |
| --- | ------------------- | --- | --- | ---------- | --- |
DAT_REF
| V DP_SRC | D+ source voltage |     | -   | 0.5 - 3.6 |     |
| -------- | ----------------- | --- | --- | --------- | --- |
| V        | D- source voltage |     | -   | 0.5 - 3.6 |     |
DM_SRC
| I   | D- sink current |     | -   | 25 - 175 |     |
| --- | --------------- | --- | --- | -------- | --- |
DM_SINK
| I   | D+ sink current |     | -   | 25 - 175 | µA  |
| --- | --------------- | --- | --- | -------- | --- |
DP_SINK
| I   | Data contact detect current source |     | -   | 7 - 30 |     |
| --- | ---------------------------------- | --- | --- | ------ | --- |
DP_SRC
CAN (controller area network) interface
Refer to Section 5.3.20: I/O port characteristics for more details on the input/output alternate
function characteristics (CANx_TX and CANx_RX).
| 5.3.30  | FMC characteristics |     |     |     |     |
| ------- | ------------------- | --- | --- | --- | --- |
Unless otherwise specified, the parameters given in Table 94 to Table 107 for the FMC
interface are derived from tests performed under the ambient temperature, f frequency
HCLK
and V  supply voltage conditions summarized in Table 17, with the following configuration:
DD
• Output speed is set to OSPEEDRy[1:0] = 11
• Measurement points are done at CMOS levels: 0.5V
DD
Refer to Section 5.3.20: I/O port characteristics for more details on the input/output
characteristics.
Asynchronous waveforms and timings
Figure 61 through Figure 64 represent asynchronous waveforms and Table 94 through
Table 101 provide the corresponding timings. The results shown in these tables are
obtained with the following FMC configuration:
• AddressSetupTime = 0x1
• AddressHoldTime = 0x1
• DataSetupTime = 0x1 (except for asynchronous NWAIT mode , DataSetupTime = 0x5)
• BusTurnAroundDuration = 0x0
• Capcitive load CL = 30 pF
|     | In all timing tables, the T | HCLK  is the HCLK clock period |     |     |     |
| --- | --------------------------- | ------------------------------ | --- | --- | --- |
DocID029808 Rev 3 177/229
201

Electrical characteristics STM32F722xx STM32F723xx
Figure 61. Asynchronous non-multiplexed SRAM/PSRAM/NOR read waveforms
(cid:84)(cid:87)(cid:8)(cid:46)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:37)
(cid:84)(cid:86)(cid:8)(cid:46)(cid:47)(cid:37)(cid:63)(cid:46)(cid:37)(cid:9) (cid:84)(cid:87)(cid:8)(cid:46)(cid:47)(cid:37)(cid:9) (cid:84)(cid:72)(cid:8)(cid:46)(cid:37)(cid:63)(cid:46)(cid:47)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:47)(cid:37)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:37)
(cid:84) (cid:86)(cid:8)(cid:33)(cid:63)(cid:46)(cid:37)(cid:9) (cid:84)(cid:72)(cid:8)(cid:33)(cid:63)(cid:46)(cid:47)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:59)(cid:18)(cid:21)(cid:26)(cid:16)(cid:61)
(cid:33)(cid:68)(cid:68)(cid:82)(cid:69)(cid:83)(cid:83)
(cid:84)
(cid:86)(cid:8)(cid:34)(cid:44)(cid:63)(cid:46)(cid:37)(cid:9) (cid:84)(cid:72)(cid:8)(cid:34)(cid:44)(cid:63)(cid:46)(cid:47)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:34)(cid:44)(cid:59)(cid:17)(cid:26)(cid:16)(cid:61)
(cid:84)(cid:72)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:47)(cid:37)(cid:9) (cid:84)(cid:72)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:47)(cid:37)(cid:9)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61) (cid:36)(cid:65)(cid:84)(cid:65)
(cid:84)(cid:86)(cid:8)(cid:46)(cid:33)(cid:36)(cid:54)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:84)(cid:87)(cid:8)(cid:46)(cid:33)(cid:36)(cid:54)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:33)(cid:36)(cid:54) (cid:8)(cid:17)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)
(cid:84)(cid:72)(cid:8)(cid:46)(cid:37)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:9)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:21)(cid:19)(cid:54)(cid:17)
1. Mode 2/B, C and D only. In Mode 1, FMC_NADV is not used.
178/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
           Table 94. Asynchronous non-multiplexed SRAM/PSRAM/NOR read timings(1)
| Symbol |                 | Parameter | Min       | Max Unit  |
| ------ | --------------- | --------- | --------- | --------- |
| t      | FMC_NE low time |           | 2Thclk -1 | 2Thclk +1 |
w(NE)
| t   | FMC_NEx low to FMC_NOE low |     | 0   | 0.5 |
| --- | -------------------------- | --- | --- | --- |
v(NOE_NE)
| t   | FMC_NOE low time |     | 2Thclk -1 | 2Thclk +1 |
| --- | ---------------- | --- | --------- | --------- |
w(NOE)
| t   | FMC_NOE high to FMC_NE high hold time |     | 0   | -   |
| --- | ------------------------------------- | --- | --- | --- |
h(NE_NOE)
| t v(A_NE) | FMC_NEx low to FMC_A valid           |     | -   | 0.5 |
| --------- | ------------------------------------ | --- | --- | --- |
| t         | Address hold time after FMC_NOE high |     | 0   | -   |
h(A_NOE)
| t   | FMC_NEx low to FMC_BL valid |     | -   | 0.5 |
| --- | --------------------------- | --- | --- | --- |
v(BL_NE)
ns
| t   | FMC_BL hold time after FMC_NOE high |     | 0   | -   |
| --- | ----------------------------------- | --- | --- | --- |
h(BL_NOE)
| t   | Data to FMC_NEx high setup time |     | Thclk -1.5 | -   |
| --- | ------------------------------- | --- | ---------- | --- |
su(Data_NE)
| t su(Data_NOE) | Data to FMC_NOEx high setup time  |     | Thclk -1.5 | -   |
| -------------- | --------------------------------- | --- | ---------- | --- |
| t              | Data hold time after FMC_NOE high |     | 0          | -   |
h(Data_NOE)
| t   | Data hold time after FMC_NEx high |     | 0   | -   |
| --- | --------------------------------- | --- | --- | --- |
h(Data_NE)
| t   | FMC_NEx low to FMC_NADV low |     | -   | 0   |
| --- | --------------------------- | --- | --- | --- |
v(NADV_NE)
| t   | FMC_NADV low time |     | -   | Thclk -0.5 |
| --- | ----------------- | --- | --- | ---------- |
w(NADV)
1. C L  = 30 pF.
 T         able 95. Asynchronous non-multiplexed SRAM/PSRAM/NOR read - NWAIT timings(1)
| Symbol  |                  | Parameter | Min       | Max Unit  |
| ------- | ---------------- | --------- | --------- | --------- |
| t w(NE) | FMC_NE low time  |           | 7Thclk +1 | 7Thclk +1 |
| t       | FMC_NWE low time |           | 5Thclk -1 | 5Thclk +1 |
w(NOE)
ns
| t   | FMC_NWAIT low time |     | Thclk -0.5 | -   |
| --- | ------------------ | --- | ---------- | --- |
w(NWAIT)
| t   | FMC_NWAIT valid before FMC_NEx high |     | 5Thclk +1.5 | -   |
| --- | ----------------------------------- | --- | ----------- | --- |
su(NWAIT_NE)
| t   | FMC_NEx hold time after FMC_NWAIT invalid |     | 4Thclk +1 | -   |
| --- | ----------------------------------------- | --- | --------- | --- |
h(NE_NWAIT)
1. Guaranteed by characterization results.
DocID029808 Rev 3 179/229
201

Electrical characteristics STM32F722xx STM32F723xx
Figure 62. Asynchronous non-multiplexed SRAM/PSRAM/NOR write waveforms
(cid:84)(cid:87)(cid:8)(cid:46)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:37)(cid:88)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:47)(cid:37)
|     | (cid:84)(cid:86)(cid:8)(cid:46)(cid:55)(cid:37)(cid:63)(cid:46)(cid:37)(cid:9) |     | (cid:84)(cid:87)(cid:8)(cid:46)(cid:55)(cid:37)(cid:9) | (cid:84)(cid:72)(cid:8)(cid:46)(cid:37)(cid:63)(cid:46)(cid:55)(cid:37)(cid:9) |     |
| --- | ------------------------------------------------------------------------------ | --- | ------------------------------------------------------ | ------------------------------------------------------------------------------ | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:37)
(cid:84)(cid:86)(cid:8)(cid:33)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:84)(cid:72)(cid:8)(cid:33)(cid:63)(cid:46)(cid:55)(cid:37)(cid:9)
| (cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:59)(cid:18)(cid:21)(cid:26)(cid:16)(cid:61)         |     | (cid:33)(cid:68)(cid:68)(cid:82)(cid:69)(cid:83)(cid:83)                               |                                                                                                |     |     |
| ------------------------------------------------------------------------------------------------ | --- | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --- | --- |
|                                                                                                  |     | (cid:84)(cid:86)(cid:8)(cid:34)(cid:44)(cid:63)(cid:46)(cid:37)(cid:9)                 | (cid:84)(cid:72)(cid:8)(cid:34)(cid:44)(cid:63)(cid:46)(cid:55)(cid:37)(cid:9)                 |     |     |
| (cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:34)(cid:44)(cid:59)(cid:17)(cid:26)(cid:16)(cid:61) |     |                                                                                        | (cid:46)(cid:34)(cid:44)                                                                       |     |     |
|                                                                                                  |     | (cid:84)(cid:86)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:37)(cid:9) | (cid:84)(cid:72)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:55)(cid:37)(cid:9) |     |     |
| (cid:38)(cid:45)(cid:35)(cid:63)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61)         |     |                                                                                        | (cid:36)(cid:65)(cid:84)(cid:65)                                                               |     |     |
(cid:84)(cid:86)(cid:8)(cid:46)(cid:33)(cid:36)(cid:54)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:84)(cid:87)(cid:8)(cid:46)(cid:33)(cid:36)(cid:54)(cid:9)
| (cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:33)(cid:36)(cid:54) | (cid:8)(cid:17)(cid:9) |     |     |     |     |
| ---------------------------------------------------------------- | ---------------------- | --- | --- | --- | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)
(cid:84)(cid:72)(cid:8)(cid:46)(cid:37)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:9)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:21)(cid:20)(cid:54)(cid:17)
1. Mode 2/B, C and D only. In Mode 1, FMC_NADV is not used.
Table 96. Asynchronous non-multiplexed SRAM/PSRAM/NOR write timings(1)
| Symbol  |                            | Parameter |     | Min         | Max Unit   |
| ------- | -------------------------- | --------- | --- | ----------- | ---------- |
| t w(NE) | FMC_NE low time            |           |     | 3Thclk +1   | 3Thclk +1  |
| t       | FMC_NEx low to FMC_NWE low |           |     | Thclk - 0.5 | Thclk +0.5 |
v(NWE_NE)
| t   | FMC_NWE low time |     |     | Thclk - 1.5 | Thclk +0.5 |
| --- | ---------------- | --- | --- | ----------- | ---------- |
w(NWE)
| t h(NE_NWE) | FMC_NWE high to FMC_NE high hold time |     |     | Thclk | -   |
| ----------- | ------------------------------------- | --- | --- | ----- | --- |
| t           | FMC_NEx low to FMC_A valid            |     |     | -     | 0   |
v(A_NE)
t h(A_NWE) Address hold time after FMC_NWE high Thclk - 0.5 -
ns
| t   | FMC_NEx low to FMC_BL valid |     |     | -   | 0.5 |
| --- | --------------------------- | --- | --- | --- | --- |
v(BL_NE)
| t   | FMC_BL hold time after FMC_NWE high |     |     | Thclk - 0.5 | -   |
| --- | ----------------------------------- | --- | --- | ----------- | --- |
h(BL_NWE)
| t v(Data_NE) | Data to FMC_NEx low to Data valid |     |     | -          | Thclk +1.5 |
| ------------ | --------------------------------- | --- | --- | ---------- | ---------- |
| t            | Data hold time after FMC_NWE high |     |     | Thclk +0.5 | -          |
h(Data_NWE)
| t v(NADV_NE) | FMC_NEx low to FMC_NADV low |     |     | -   | 0           |
| ------------ | --------------------------- | --- | --- | --- | ----------- |
| t            | FMC_NADV low time           |     |     | -   | Thclk - 0.5 |
w(NADV)
1. Guaranteed by characterization results.
180/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics

Table 97. Asynchronous non-multiplexed SRAM/PSRAM/NOR write - NWAIT
timings(1)
| Symbol |                         | Parameter | Min         | Max Unit    |
| ------ | ----------------------- | --------- | ----------- | ----------- |
|        | t w(NE) FMC_NE low time |           | 8Thclk -1   | 8Thclk +1   |
| t      | FMC_NWE low time        |           | 6Thclk -1.5 | 6Thclk +0.5 |
w(NWE)
ns
| t   | FMC_NWAIT valid before FMC_NEx high |     | 6Thclk -1 | -   |
| --- | ----------------------------------- | --- | --------- | --- |
su(NWAIT_NE)
FMC_NEx hold time after FMC_NWAIT
| t           |         |     | 4Thclk + 2 | -   |
| ----------- | ------- | --- | ---------- | --- |
| h(NE_NWAIT) | invalid |     |            |     |
1. Guaranteed by characterization results.
Figure 63. Asynchronous multiplexed PSRAM/NOR read waveforms
(cid:84)(cid:87)(cid:8)(cid:46)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63) (cid:46)(cid:37)
|     |     | (cid:84)(cid:86)(cid:8)(cid:46)(cid:47)(cid:37)(cid:63)(cid:46)(cid:37)(cid:9) | (cid:84)(cid:72)(cid:8)(cid:46)(cid:37)(cid:63)(cid:46)(cid:47)(cid:37)(cid:9) |     |
| --- | --- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:47)(cid:37)
(cid:84)(cid:87)(cid:8)(cid:46)(cid:47)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:37)
|     |                                                                                                   | (cid:84)(cid:86)(cid:8)(cid:33)(cid:63)(cid:46)(cid:37)(cid:9) | (cid:84)(cid:72)(cid:8)(cid:33)(cid:63)(cid:46)(cid:47)(cid:37)(cid:9) |     |
| --- | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | ---------------------------------------------------------------------- | --- |
|     | (cid:38)(cid:45)(cid:35)(cid:63) (cid:33)(cid:59)(cid:18)(cid:21)(cid:26)(cid:17)(cid:22)(cid:61) |                                                                |                                                                        |     |
(cid:33)(cid:68)(cid:68)(cid:82)(cid:69)(cid:83)(cid:83)
(cid:84)(cid:86)(cid:8)(cid:34)(cid:44)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:84)(cid:72)(cid:8)(cid:34)(cid:44)(cid:63)(cid:46)(cid:47)(cid:37)(cid:9)
|     | (cid:38)(cid:45)(cid:35)(cid:63) (cid:46)(cid:34)(cid:44)(cid:59)(cid:17)(cid:26)(cid:16)(cid:61) |     |     |     |
| --- | ------------------------------------------------------------------------------------------------- | --- | --- | --- |
(cid:46)(cid:34)(cid:44)
(cid:84)(cid:72)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:37)(cid:9)
|     |                                                                                                   | (cid:84)(cid:86)(cid:8)(cid:33)(cid:63)(cid:46)(cid:37)(cid:9)                         | (cid:84)(cid:83)(cid:85)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:47)(cid:37)(cid:9) | (cid:84)(cid:72)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:47)(cid:37)(cid:9) |
| --- | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
|     | (cid:38)(cid:45)(cid:35)(cid:63) (cid:33)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61) | (cid:33)(cid:68)(cid:68)(cid:82)(cid:69)(cid:83)(cid:83)                               | (cid:36)(cid:65)(cid:84)(cid:65)                                                                       |                                                                                                |
|     | (cid:84)(cid:86)(cid:8)(cid:46)(cid:33)(cid:36)(cid:54)(cid:63)(cid:46)(cid:37)(cid:9)            | (cid:84)(cid:72)(cid:8)(cid:33)(cid:36)(cid:63)(cid:46)(cid:33)(cid:36)(cid:54)(cid:9) |                                                                                                        |                                                                                                |
(cid:84)(cid:87)(cid:8)(cid:46)(cid:33)(cid:36)(cid:54)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:33)(cid:36)(cid:54)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)
(cid:84)(cid:72)(cid:8)(cid:46)(cid:37)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:9)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:21)(cid:21)(cid:54)(cid:17)
DocID029808 Rev 3 181/229
201

Electrical characteristics STM32F722xx STM32F723xx
           Table 98. Asynchronous multiplexed PSRAM/NOR read timings(1)
| Symbol |                 | Parameter | Min       | Max Unit  |
| ------ | --------------- | --------- | --------- | --------- |
| t      | FMC_NE low time |           | 3Thclk -1 | 3Thclk +1 |
w(NE)
| t   | FMC_NEx low to FMC_NOE low |     | 2Thclk | 2Thclk +0.5 |
| --- | -------------------------- | --- | ------ | ----------- |
v(NOE_NE)
| t   | FMC_NOE low time |     | Thclk -1 | Thclk +1 |
| --- | ---------------- | --- | -------- | -------- |
tw(NOE)
| t   | FMC_NOE high to FMC_NE high hold time |     | 0   | -   |
| --- | ------------------------------------- | --- | --- | --- |
h(NE_NOE)
| t v(A_NE) | FMC_NEx low to FMC_A valid  |     | -   | 0.5 |
| --------- | --------------------------- | --- | --- | --- |
| t         | FMC_NEx low to FMC_NADV low |     | 0   | 0.5 |
v(NADV_NE)
| t   | FMC_NADV low time |     | Thclk -0.5 | Thclk +1 |
| --- | ----------------- | --- | ---------- | -------- |
w(NADV)
FMC_AD(address) valid hold time after
| t          |                                      |     | Thclk +0.5 | - ns |
| ---------- | ------------------------------------ | --- | ---------- | ---- |
| h(AD_NADV) | FMC_NADV high)                       |     |            |      |
| t          | Address hold time after FMC_NOE high |     | Thclk -0.5 | -    |
h(A_NOE)
| t   | FMC_BL time after FMC_NOE high |     | 0   | -   |
| --- | ------------------------------ | --- | --- | --- |
h(BL_NOE)
| t   | FMC_NEx low to FMC_BL valid |     | -   | 0.5 |
| --- | --------------------------- | --- | --- | --- |
v(BL_NE)
| t su(Data_NE) | Data to FMC_NEx high setup time |     | Thclk -1.5 | -   |
| ------------- | ------------------------------- | --- | ---------- | --- |
| t             | Data to FMC_NOE high setup time |     | Thclk -1.5 | -   |
su(Data_NOE)
| t   | Data hold time after FMC_NEx high |     | 0   | -   |
| --- | --------------------------------- | --- | --- | --- |
h(Data_NE)
| t   | Data hold time after FMC_NOE high |     | 0   | -   |
| --- | --------------------------------- | --- | --- | --- |
h(Data_NOE)
1. Guaranteed by characterization results.
           Table 99. Asynchronous multiplexed PSRAM/NOR read-NWAIT timings(1)
| Symbol |                 | Parameter | Min       | Max Unit  |
| ------ | --------------- | --------- | --------- | --------- |
| t      | FMC_NE low time |           | 8Thclk -1 | 8Thclk +1 |
w(NE)
| t w(NOE) | FMC_NWE low time |     | 5Thclk -1.5 | 8Thclk +0.5 |
| -------- | ---------------- | --- | ----------- | ----------- |
ns
| t   | FMC_NWAIT valid before FMC_NEx high |     | 5Thclk +1.5 | -   |
| --- | ----------------------------------- | --- | ----------- | --- |
su(NWAIT_NE)
FMC_NEx hold time after FMC_NWAIT
| t h(NE_NWAIT) |     |     | 4Thclk +1 | -   |
| ------------- | --- | --- | --------- | --- |
invalid
1. Guaranteed by characterization results.
182/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
Figure 64. Asynchronous multiplexed PSRAM/NOR write waveforms
(cid:84)(cid:87)(cid:8)(cid:46)(cid:37)(cid:9)
| (cid:38)(cid:45)(cid:35)(cid:63) | (cid:46)(cid:37)(cid:88) |     |     |     |     |
| -------------------------------- | ------------------------ | --- | --- | --- | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:47)(cid:37)
|     |     | (cid:84)(cid:86)(cid:8)(cid:46)(cid:55)(cid:37)(cid:63)(cid:46)(cid:37)(cid:9) | (cid:84)(cid:87)(cid:8)(cid:46)(cid:55)(cid:37)(cid:9) |     | (cid:84)(cid:72)(cid:8)(cid:46)(cid:37)(cid:63)(cid:46)(cid:55)(cid:37)(cid:9) |
| --- | --- | ------------------------------------------------------------------------------ | ------------------------------------------------------ | --- | ------------------------------------------------------------------------------ |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:37)
|                                  |                                                                  | (cid:84)(cid:86)(cid:8)(cid:33)(cid:63)(cid:46)(cid:37)(cid:9) | (cid:84)(cid:72)(cid:8)(cid:33)(cid:63)(cid:46)(cid:55)(cid:37)(cid:9) |     |     |
| -------------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------- | ---------------------------------------------------------------------- | --- | --- |
| (cid:38)(cid:45)(cid:35)(cid:63) | (cid:33)(cid:59)(cid:18)(cid:21)(cid:26)(cid:17)(cid:22)(cid:61) |                                                                | (cid:33)(cid:68)(cid:68)(cid:82)(cid:69)(cid:83)(cid:83)               |     |     |
(cid:84)(cid:86)(cid:8)(cid:34)(cid:44)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:84)(cid:72)(cid:8)(cid:34)(cid:44)(cid:63)(cid:46)(cid:55)(cid:37)(cid:9)
| (cid:38)(cid:45)(cid:35)(cid:63) (cid:46)(cid:34)(cid:44)(cid:59)(cid:17)(cid:26)(cid:16)(cid:61) |                                                                  |                                                                | (cid:46)(cid:34)(cid:44)                                                                               |     |                                                                                                |
| ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | --- | ---------------------------------------------------------------------------------------------- |
|                                                                                                   |                                                                  | (cid:84)(cid:86)(cid:8)(cid:33)(cid:63)(cid:46)(cid:37)(cid:9) | (cid:84)(cid:86)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:33)(cid:36)(cid:54)(cid:9) |     | (cid:84)(cid:72)(cid:8)(cid:36)(cid:65)(cid:84)(cid:65)(cid:63)(cid:46)(cid:55)(cid:37)(cid:9) |
|                                                                                                   |                                                                  | (cid:33)(cid:68)(cid:68)(cid:82)(cid:69)(cid:83)(cid:83)       | (cid:36)(cid:65)(cid:84)(cid:65)                                                                       |     |                                                                                                |
| (cid:38)(cid:45)(cid:35)(cid:63)                                                                  | (cid:33)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61) |                                                                |                                                                                                        |     |                                                                                                |
(cid:84)(cid:72)(cid:8)(cid:33)(cid:36)(cid:63)(cid:46)(cid:33)(cid:36)(cid:54)(cid:9)
(cid:84)(cid:86)(cid:8)(cid:46)(cid:33)(cid:36)(cid:54)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:84)(cid:87)(cid:8)(cid:46)(cid:33)(cid:36)(cid:54)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:33)(cid:36)(cid:54)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)
(cid:84)(cid:72)(cid:8)(cid:46)(cid:37)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:9)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:63)(cid:46)(cid:37)(cid:9)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:21)(cid:22)(cid:54)(cid:17)
           Table 100. Asynchronous multiplexed PSRAM/NOR write timings(1)
| Symbol  |                            | Parameter |     | Min        | Max Unit   |
| ------- | -------------------------- | --------- | --- | ---------- | ---------- |
| t w(NE) | FMC_NE low time            |           |     | 4Thclk -1  | 4Thclk +1  |
| t       | FMC_NEx low to FMC_NWE low |           |     | Thclk -0.5 | Thclk +0.5 |
v(NWE_NE)
| t w(NWE) | FMC_NWE low time                      |     |     | 2Thclk -0.5 | 2Thclk +0.5 |
| -------- | ------------------------------------- | --- | --- | ----------- | ----------- |
| t        | FMC_NWE high to FMC_NE high hold time |     |     | Thclk -0.5  | -           |
h(NE_NWE)
| t   | FMC_NEx low to FMC_A valid |     |     | -   | 0   |
| --- | -------------------------- | --- | --- | --- | --- |
v(A_NE)
| t   | FMC_NEx low to FMC_NADV low |     |     | 0   | 0.5 |
| --- | --------------------------- | --- | --- | --- | --- |
v(NADV_NE)
| t   | FMC_NADV low time |     |     | Thclk | Thclk +1 |
| --- | ----------------- | --- | --- | ----- | -------- |
w(NADV) ns
FMC_AD(adress) valid hold time after
| t h(AD_NADV) |     |     |     | Thclk +0.5 | -   |
| ------------ | --- | --- | --- | ---------- | --- |
FMC_NADV high)
| t   | Address hold time after FMC_NWE high |     |     | Thclk +0.5 | -   |
| --- | ------------------------------------ | --- | --- | ---------- | --- |
h(A_NWE)
| t h(BL_NWE) | FMC_BL hold time after FMC_NWE high |     |     | Thclk -0.5 | -   |
| ----------- | ----------------------------------- | --- | --- | ---------- | --- |
| t           | FMC_NEx low to FMC_BL valid         |     |     | -          | 0.5 |
v(BL_NE)
| t   | FMC_NADV high to Data valid |     |     | -   | Thclk +1.5 |
| --- | --------------------------- | --- | --- | --- | ---------- |
v(Data_NADV)
| t   | Data hold time after FMC_NWE high |     |     | Thclk +0.5 | -   |
| --- | --------------------------------- | --- | --- | ---------- | --- |
h(Data_NWE)
DocID029808 Rev 3 183/229
201

Electrical characteristics STM32F722xx STM32F723xx
1. Guaranteed by characterization results.
Table 101. Asynchronous multiplexed PSRAM/NOR write-NWAIT timings(1)
Symbol Parameter Min Max Unit
t FMC_NE low time 9Thclk - 1 9Thclk + 1
w(NE)
t FMC_NWE low time 7Thclk -0.5 7Thclk + 0.5
w(NWE) ns
t FMC_NWAIT valid before FMC_NEx high 6Thclk + 2 -
su(NWAIT_NE)
FMC_NEx hold time after FMC_NWAIT
t 4Thclk - 1 -
h(NE_NWAIT) invalid
1. Guaranteed by characterization results.
Synchronous waveforms and timings
Figure 65 through Figure 68 represent synchronous waveforms and Table 102 through
Table 105 provide the corresponding timings. The results shown in these tables are
obtained with the following FMC configuration:
• BurstAccessMode = FMC_BurstAccessMode_Enable;
• MemoryType = FMC_MemoryType_CRAM;
• WriteBurst = FMC_WriteBurst_Enable;
• CLKDivision = 1;
• DataLatency = 1 for NOR Flash; DataLatency = 0 for PSRAM
• CL = 30 pF on data and address lines. CL = 10 pF on FMC_CLK unless otherwise
specified.
In all timing tables, the T is the HCLK clock period.
HCLK
– For 2.7 V≤ V ≤ 3.6 V, maximum FMC_CLK = 108 MHz at CL=20 pF or 90 MHz at
DD
CL=30 pF (on FMC_CLK).
– For 1.71 V≤ V <2.7 V, maximum FMC_CLK = 70 MHz at CL=10 pF (on FMC_CLK).
DD
184/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
Figure 65. Synchronous multiplexed NOR/PSRAM read timings
|     | (cid:84)(cid:87)(cid:8)(cid:35)(cid:44)(cid:43)(cid:9) |     | (cid:84)(cid:87)(cid:8)(cid:35)(cid:44)(cid:43)(cid:9) |     | (cid:34)(cid:53)(cid:51)(cid:52)(cid:53)(cid:50)(cid:46)(cid:0)(cid:29)(cid:0)(cid:16) |
| --- | ------------------------------------------------------ | --- | ------------------------------------------------------ | --- | -------------------------------------------------------------------------------------- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:35)(cid:44)(cid:43)
(cid:36)(cid:65)(cid:84)(cid:65)(cid:0)(cid:76)(cid:65)(cid:84)(cid:69)(cid:78)(cid:67)(cid:89)(cid:0)(cid:29)(cid:0)(cid:16)
|     |     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:37)(cid:88)(cid:44)(cid:9) |     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:37)(cid:88)(cid:40)(cid:9) |     |
| --- | --- | ------------------------------------------------------------------------------------------------------ | --- | ------------------------------------------------------------------------------------------------------ | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:37)(cid:88)
| (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:33)(cid:36)(cid:54)(cid:44)(cid:9) |     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:33)(cid:36)(cid:54)(cid:40)(cid:9) |     |     |     |
| -------------------------------------------------------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------------------------------- | --- | --- | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:33)(cid:36)(cid:54)
|     |     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:33)(cid:54)(cid:9) |     |     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:33)(cid:41)(cid:54)(cid:9) |
| --- | --- | -------------------------------------------------------------------------------------- | --- | --- | ---------------------------------------------------------------------------------------------- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:59)(cid:18)(cid:21)(cid:26)(cid:17)(cid:22)(cid:61)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:47)(cid:37)(cid:44)(cid:9)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:47)(cid:37)(cid:40)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:47)(cid:37)
|     |     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:33)(cid:36)(cid:41)(cid:54)(cid:9) |                                                                                                        | (cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:33)(cid:36)(cid:54)(cid:9)         |     |
| --- | --- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | --- |
|     |     |                                                                                                        | (cid:84)(cid:83)(cid:85)(cid:8)(cid:33)(cid:36)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9) | (cid:84)(cid:83)(cid:85)(cid:8)(cid:33)(cid:36)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9) |     |
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:33)(cid:36)(cid:54)(cid:9) (cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:33)(cid:36)(cid:54)(cid:9)
| (cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61) |     | (cid:33)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61) |     | (cid:36)(cid:17) | (cid:36)(cid:18) |
| ------------------------------------------------------------------------------------------------ | --- | ---------------------------------------------------------------- | --- | ---------------- | ---------------- |
(cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9)
(cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)
(cid:8)(cid:55)(cid:33)(cid:41)(cid:52)(cid:35)(cid:38)(cid:39)(cid:0)(cid:29)(cid:0)(cid:17)(cid:66)(cid:12)(cid:0)
(cid:55)(cid:33)(cid:41)(cid:52)(cid:48)(cid:47)(cid:44)(cid:0)(cid:11)(cid:0)(cid:16)(cid:66)(cid:9)
|     |     |     | (cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9) |     | (cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:9) |
| --- | --- | --- | ------------------------------------------------------------------------------------------------------------------------------ | --- | ---------------------------------------------------------------------------------------------------------------------- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)
(cid:8)(cid:55)(cid:33)(cid:41)(cid:52)(cid:35)(cid:38)(cid:39)(cid:0)(cid:29)(cid:0)(cid:16)(cid:66)(cid:12)(cid:0)
(cid:55)(cid:33)(cid:41)(cid:52)(cid:48)(cid:47)(cid:44)(cid:0)(cid:11)(cid:0)(cid:16)(cid:66)(cid:9)
|     |     | (cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9) |     | (cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:9) |     |
| --- | --- | ------------------------------------------------------------------------------------------------------------------------------ | --- | ---------------------------------------------------------------------------------------------------------------------- | --- |
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:21)(cid:23)(cid:54)(cid:17)
DocID029808 Rev 3 185/229
201

Electrical characteristics STM32F722xx STM32F723xx
           Table 102. Synchronous multiplexed NOR/PSRAM read timings(1)
| Symbol |                 | Parameter | Min          | Max Unit |
| ------ | --------------- | --------- | ------------ | -------- |
| t      | FMC_CLK period  |           | 2Thclk - 0.5 | -        |
w(CLK)
| t   | FMC_CLK low to FMC_NEx low (x=0..2) |     |     | 2   |
| --- | ----------------------------------- | --- | --- | --- |
d(CLKL-NExL)
| t   | FMC_CLK high to FMC_NEx high (x= 0…2) |     | Thclk + 0.5 | -   |
| --- | ------------------------------------- | --- | ----------- | --- |
d(CLKH_NExH)
| t   | FMC_CLK low to FMC_NADV low |     | -   | 1   |
| --- | --------------------------- | --- | --- | --- |
d(CLKL-NADVL)
| t d(CLKL-NADVH) | FMC_CLK low to FMC_NADV high          |     | 0   | -   |
| --------------- | ------------------------------------- | --- | --- | --- |
| t               | FMC_CLK low to FMC_Ax valid (x=16…25) |     | -   | 3   |
d(CLKL-AV)
| t   | FMC_CLK high to FMC_Ax invalid (x=16…25) |     | Thclk | -   |
| --- | ---------------------------------------- | --- | ----- | --- |
d(CLKH-AIV)
| t   | FMC_CLK low to FMC_NOE low |     | -   | 2   |
| --- | -------------------------- | --- | --- | --- |
d(CLKL-NOEL) ns
| t   | FMC_CLK high to FMC_NOE high |     | Thclk - 0.5 | -   |
| --- | ---------------------------- | --- | ----------- | --- |
d(CLKH-NOEH)
| t d(CLKL-ADV) | FMC_CLK low to FMC_AD[15:0] valid   |     | -   | 2   |
| ------------- | ----------------------------------- | --- | --- | --- |
| t             | FMC_CLK low to FMC_AD[15:0] invalid |     | 0   | -   |
d(CLKL-ADIV)
FMC_A/D[15:0] valid data before FMC_CLK
| t su(ADV-CLKH) |     |     | 0.5 | -   |
| -------------- | --- | --- | --- | --- |
high
| t   | FMC_A/D[15:0] valid data after FMC_CLK high |     | 4   | -   |
| --- | ------------------------------------------- | --- | --- | --- |
h(CLKH-ADV)
| t   | FMC_NWAIT valid before FMC_CLK high |     | 2   | -   |
| --- | ----------------------------------- | --- | --- | --- |
su(NWAIT-CLKH)
| t   | FMC_NWAIT valid after FMC_CLK high |     | 3   | -   |
| --- | ---------------------------------- | --- | --- | --- |
h(CLKH-NWAIT)
1. Guaranteed by characterization results.
186/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
Figure 66. Synchronous multiplexed PSRAM write timings
(cid:84)(cid:87)(cid:8)(cid:35)(cid:44)(cid:43)(cid:9) (cid:84)(cid:87)(cid:8)(cid:35)(cid:44)(cid:43)(cid:9) (cid:34)(cid:53)(cid:51)(cid:52)(cid:53)(cid:50)(cid:46)(cid:0)(cid:29)(cid:0)(cid:16)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:35)(cid:44)(cid:43)
(cid:36)(cid:65)(cid:84)(cid:65)(cid:0)(cid:76)(cid:65)(cid:84)(cid:69)(cid:78)(cid:67)(cid:89)(cid:0)(cid:29)(cid:0)(cid:16)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:37)(cid:88)(cid:44)(cid:9) (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:37)(cid:88)(cid:40)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:37)(cid:88)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:33)(cid:36)(cid:54)(cid:44)(cid:9) (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:33)(cid:36)(cid:54)(cid:40)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:33)(cid:36)(cid:54)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:33)(cid:54)(cid:9) (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:33)(cid:41)(cid:54)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:59)(cid:18)(cid:21)(cid:26)(cid:17)(cid:22)(cid:61)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:55)(cid:37)(cid:44)(cid:9) (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:55)(cid:37)(cid:40)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:37)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:33)(cid:36)(cid:41)(cid:54)(cid:9) (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:36)(cid:65)(cid:84)(cid:65)(cid:9)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:33)(cid:36)(cid:54)(cid:9) (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:36)(cid:65)(cid:84)(cid:65)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61) (cid:33)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61) (cid:36)(cid:17) (cid:36)(cid:18)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)
(cid:8)(cid:55)(cid:33)(cid:41)(cid:52)(cid:35)(cid:38)(cid:39)(cid:0)(cid:29)(cid:0)(cid:16)(cid:66)(cid:12)
(cid:0)(cid:55)(cid:33)(cid:41)(cid:52)(cid:48)(cid:47)(cid:44)(cid:0)(cid:11)(cid:0)(cid:16)(cid:66)(cid:9) (cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9) (cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:9)
(cid:84)
(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:34)(cid:44)(cid:40)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:34)(cid:44)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:21)(cid:24)(cid:54)(cid:17)
DocID029808 Rev 3 187/229
201

Electrical characteristics STM32F722xx STM32F723xx
           Table 103. Synchronous multiplexed PSRAM write timings(1)
| Symbol |                | Parameter | Min          | Max Unit |
| ------ | -------------- | --------- | ------------ | -------- |
| t      | FMC_CLK period |           | 2Thclk - 0.5 | -        |
w(CLK)
| t   | FMC_CLK low to FMC_NEx low (x=0..2) |     | -   | 2   |
| --- | ----------------------------------- | --- | --- | --- |
d(CLKL-NExL)
| t   | FMC_CLK high to FMC_NEx high (x= 0…2) |     | Thclk +0.5 | -   |
| --- | ------------------------------------- | --- | ---------- | --- |
d(CLKH-NExH)
| t   | FMC_CLK low to FMC_NADV low |     | -   | 1   |
| --- | --------------------------- | --- | --- | --- |
d(CLKL-NADVL)
| t d(CLKL-NADVH) | FMC_CLK low to FMC_NADV high          |     | 0   | -   |
| --------------- | ------------------------------------- | --- | --- | --- |
| t               | FMC_CLK low to FMC_Ax valid (x=16…25) |     | -   | 3   |
d(CLKL-AV)
| t   | FMC_CLK high to FMC_Ax invalid (x=16…25) |     | Thclk | -   |
| --- | ---------------------------------------- | --- | ----- | --- |
d(CLKH-AIV)
| t   | FMC_CLK low to FMC_NWE low |     | -   | 1.5 |
| --- | -------------------------- | --- | --- | --- |
d(CLKL-NWEL)
ns
| t   | FMC_CLK high to FMC_NWE high |     | Thclk +0.5 | -   |
| --- | ---------------------------- | --- | ---------- | --- |
(CLKH-NWEH)
| t d(CLKL-ADV) | FMC_CLK low to FMC_AD[15:0] valid   |     | -   | 3   |
| ------------- | ----------------------------------- | --- | --- | --- |
| t             | FMC_CLK low to FMC_AD[15:0] invalid |     | 0   | -   |
d(CLKL-ADIV)
| t   | FMC_A/D[15:0] valid data after FMC_CLK low |     | -   | 3   |
| --- | ------------------------------------------ | --- | --- | --- |
d(CLKL-DATA)
| t   | FMC_CLK low to FMC_NBL low |     | -   | 2   |
| --- | -------------------------- | --- | --- | --- |
d(CLKL-NBLL)
| t   | FMC_CLK high to FMC_NBL high |     | Thclk +0.5 | -   |
| --- | ---------------------------- | --- | ---------- | --- |
d(CLKH-NBLH)
| t su(NWAIT-CLKH) | FMC_NWAIT valid before FMC_CLK high |     | 2   | -   |
| ---------------- | ----------------------------------- | --- | --- | --- |
| t                | FMC_NWAIT valid after FMC_CLK high  |     | 3   | -   |
h(CLKH-NWAIT)
1. Guaranteed by characterization results.
188/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
Figure 67. Synchronous non-multiplexed NOR/PSRAM read timings
(cid:84)(cid:87)(cid:8)(cid:35)(cid:44)(cid:43)(cid:9) (cid:84)(cid:87)(cid:8)(cid:35)(cid:44)(cid:43)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:35)(cid:44)(cid:43)
| (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:37)(cid:88)(cid:44)(cid:9) |     |     |     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:37)(cid:88)(cid:40)(cid:9) |     |
| ------------------------------------------------------------------------------------------------------ | --- | --- | --- | ------------------------------------------------------------------------------------------------------ | --- |
(cid:36)(cid:65)(cid:84)(cid:65)(cid:0)(cid:76)(cid:65)(cid:84)(cid:69)(cid:78)(cid:67)(cid:89)(cid:0)(cid:29)(cid:0)(cid:16)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:37)(cid:88)
| (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:33)(cid:36)(cid:54)(cid:44)(cid:9) |     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:33)(cid:36)(cid:54)(cid:40)(cid:9) |     |     |     |
| -------------------------------------------------------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------------------------------- | --- | --- | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:33)(cid:36)(cid:54)
|     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:33)(cid:54)(cid:9) |     |     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:33)(cid:41)(cid:54)(cid:9) |     |
| --- | -------------------------------------------------------------------------------------- | --- | --- | ---------------------------------------------------------------------------------------------- | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:59)(cid:18)(cid:21)(cid:26)(cid:16)(cid:61)
|     |     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:47)(cid:37)(cid:44)(cid:9) |     | (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:47)(cid:37)(cid:40)(cid:9) |     |
| --- | --- | ------------------------------------------------------------------------------------------------------ | --- | ------------------------------------------------------------------------------------------------------ | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:47)(cid:37)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:36)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9)
(cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:36)(cid:54)(cid:9)
|                                                                                          |     |                                                                                                                                | (cid:84)(cid:83)(cid:85)(cid:8)(cid:36)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9)                         |                  | (cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:36)(cid:54)(cid:9) |
| ---------------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- | ---------------- | -------------------------------------------------------------------------------------- |
| (cid:38)(cid:45)(cid:35)(cid:63)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61) |     |                                                                                                                                | (cid:36)(cid:17)                                                                                                       | (cid:36)(cid:18) |                                                                                        |
|                                                                                          |     | (cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9) | (cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:9) |                  |                                                                                        |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)
(cid:8)(cid:55)(cid:33)(cid:41)(cid:52)(cid:35)(cid:38)(cid:39)(cid:0)(cid:29)(cid:0)(cid:17)(cid:66)(cid:12)(cid:0)
(cid:55)(cid:33)(cid:41)(cid:52)(cid:48)(cid:47)(cid:44)(cid:0)(cid:11)(cid:0)(cid:16)(cid:66)(cid:9)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9) (cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)
(cid:8)(cid:55)(cid:33)(cid:41)(cid:52)(cid:35)(cid:38)(cid:39)(cid:0)(cid:29)(cid:0)(cid:16)(cid:66)(cid:12)(cid:0)
(cid:55)(cid:33)(cid:41)(cid:52)(cid:48)(cid:47)(cid:44)(cid:0)(cid:11)(cid:0)(cid:16)(cid:66)(cid:9)
|     |     | (cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9) | (cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:9) |     |     |
| --- | --- | ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- | --- | --- |
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:21)(cid:25)(cid:54)(cid:17)
           Table 104. Synchronous non-multiplexed NOR/PSRAM read timings(1)
| Symbol   |                                     | Parameter |     | Min          | Max Unit |
| -------- | ----------------------------------- | --------- | --- | ------------ | -------- |
| t w(CLK) | FMC_CLK period                      |           |     | 2Thclk - 0.5 | -        |
| t        | FMC_CLK low to FMC_NEx low (x=0..2) |           |     | -            | 2        |
(CLKL-NExL)
| t   | FMC_CLK high to FMC_NEx high (x= 0…2) |     |     | Thclk +0.5 | -   |
| --- | ------------------------------------- | --- | --- | ---------- | --- |
d(CLKH-NExH)
| t   | FMC_CLK low to FMC_NADV low |     |     | -   | 0.5 |
| --- | --------------------------- | --- | --- | --- | --- |
d(CLKL-NADVL)
| t   | FMC_CLK low to FMC_NADV high |     |     | 0   | -   |
| --- | ---------------------------- | --- | --- | --- | --- |
d(CLKL-NADVH)
| t d(CLKL-AV) | FMC_CLK low to FMC_Ax valid (x=16…25)    |     |     | -     | 3    |
| ------------ | ---------------------------------------- | --- | --- | ----- | ---- |
| t            | FMC_CLK high to FMC_Ax invalid (x=16…25) |     |     | Thclk | - ns |
d(CLKH-AIV)
| t   | FMC_CLK low to FMC_NOE low |     |     | -   | 2   |
| --- | -------------------------- | --- | --- | --- | --- |
d(CLKL-NOEL)
| t   | FMC_CLK high to FMC_NOE high |     |     | Thclk -0.5 | -   |
| --- | ---------------------------- | --- | --- | ---------- | --- |
d(CLKH-NOEH)
| t   | FMC_D[15:0] valid data before FMC_CLK high |     |     | 0.5 | -   |
| --- | ------------------------------------------ | --- | --- | --- | --- |
su(DV-CLKH)
| t h(CLKH-DV) | FMC_D[15:0] valid data after FMC_CLK high |     |     | 4   | -   |
| ------------ | ----------------------------------------- | --- | --- | --- | --- |
| t            | FMC_NWAIT valid before FMC_CLK high       |     |     | 2   | -   |
(NWAIT-CLKH)
| t   | FMC_NWAIT valid after FMC_CLK high |     |     | 3   | -   |
| --- | ---------------------------------- | --- | --- | --- | --- |
h(CLKH-NWAIT)
|     |     | DocID029808 Rev 3 |     |     | 189/229 |
| --- | --- | ----------------- | --- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
1. Guaranteed by characterization results.
Figure 68. Synchronous non-multiplexed PSRAM write timings
(cid:84)(cid:87)(cid:8)(cid:35)(cid:44)(cid:43)(cid:9) (cid:84)(cid:87)(cid:8)(cid:35)(cid:44)(cid:43)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:35)(cid:44)(cid:43)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:37)(cid:88)(cid:44)(cid:9) (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:37)(cid:88)(cid:40)(cid:9)
(cid:36)(cid:65)(cid:84)(cid:65)(cid:0)(cid:76)(cid:65)(cid:84)(cid:69)(cid:78)(cid:67)(cid:89)(cid:0)(cid:29)(cid:0)(cid:16)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:37)(cid:88)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:33)(cid:36)(cid:54)(cid:44)(cid:9) (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:33)(cid:36)(cid:54)(cid:40)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:33)(cid:36)(cid:54)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:33)(cid:54)(cid:9)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:33)(cid:41)(cid:54)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:59)(cid:18)(cid:21)(cid:26)(cid:16)(cid:61)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:46)(cid:55)(cid:37)(cid:44)(cid:9) (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:55)(cid:37)(cid:40)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:37)
(cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:36)(cid:65)(cid:84)(cid:65)(cid:9) (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:44)(cid:13)(cid:36)(cid:65)(cid:84)(cid:65)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61) (cid:36)(cid:17) (cid:36)(cid:18)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)
(cid:8)(cid:55)(cid:33)(cid:41)(cid:52)(cid:35)(cid:38)(cid:39)(cid:0)(cid:29)(cid:0)(cid:16)(cid:66)(cid:12)(cid:0)(cid:55)(cid:33)(cid:41)(cid:52)(cid:48)(cid:47)(cid:44)(cid:0)(cid:11)(cid:0)(cid:16)(cid:66)(cid:9) (cid:84)(cid:83)(cid:85)(cid:8)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:13)(cid:35)(cid:44)(cid:43)(cid:40)(cid:9) (cid:84)(cid:68)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:34)(cid:44)(cid:40)(cid:9)
(cid:84)(cid:72)(cid:8)(cid:35)(cid:44)(cid:43)(cid:40)(cid:13)(cid:46)(cid:55)(cid:33)(cid:41)(cid:52)(cid:54)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:34)(cid:44)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:22)(cid:16)(cid:54)(cid:17)
190/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
           Table 105. Synchronous non-multiplexed PSRAM write timings(1)
| Symbol |                | Parameter | Min          | Max Unit |
| ------ | -------------- | --------- | ------------ | -------- |
| t      | FMC_CLK period |           | 2Thclk - 0.5 | -        |
(CLK)
| t   | FMC_CLK low to FMC_NEx low (x=0..2) |     | -   | 2   |
| --- | ----------------------------------- | --- | --- | --- |
d(CLKL-NExL)
| t   | FMC_CLK high to FMC_NEx high (x= 0…2) |     | Thclk +0.5 | -   |
| --- | ------------------------------------- | --- | ---------- | --- |
(CLKH-NExH)
| t   | FMC_CLK low to FMC_NADV low |     | -   | 0.5 |
| --- | --------------------------- | --- | --- | --- |
d(CLKL-NADVL)
| t d(CLKL-NADVH) | FMC_CLK low to FMC_NADV high          |     | 0   | -   |
| --------------- | ------------------------------------- | --- | --- | --- |
| t               | FMC_CLK low to FMC_Ax valid (x=16…25) |     | -   | 3   |
d(CLKL-AV)
| t   | FMC_CLK high to FMC_Ax invalid (x=16…25) |     | Thclk | -   |
| --- | ---------------------------------------- | --- | ----- | --- |
d(CLKH-AIV)
ns
| t   | FMC_CLK low to FMC_NWE low |     | -   | 1.5 |
| --- | -------------------------- | --- | --- | --- |
d(CLKL-NWEL)
| t   | FMC_CLK high to FMC_NWE high |     | Thclk +1 | -   |
| --- | ---------------------------- | --- | -------- | --- |
d(CLKH-NWEH)
| t d(CLKL-Data) | FMC_D[15:0] valid data after FMC_CLK low |     | -   | 3   |
| -------------- | ---------------------------------------- | --- | --- | --- |
| t              | FMC_CLK low to FMC_NBL low               |     | -   | 2   |
d(CLKL-NBLL)
| t   | FMC_CLK high to FMC_NBL high |     | Thclk +1 | -   |
| --- | ---------------------------- | --- | -------- | --- |
d(CLKH-NBLH)
| t   | FMC_NWAIT valid before FMC_CLK high |     | 2   | -   |
| --- | ----------------------------------- | --- | --- | --- |
su(NWAIT-CLKH)
| t   | FMC_NWAIT valid after FMC_CLK high |     | 3.5 | -   |
| --- | ---------------------------------- | --- | --- | --- |
h(CLKH-NWAIT)
1. Guaranteed by characterization results.
NAND controller waveforms and timings
Figure 69 through Figure 72 represent synchronous waveforms, and Table 106 and
Table 107 provide the corresponding timings. The results shown in this table are obtained
with the following FMC configuration:
•
COM.FMC_SetupTime = 0x01;
•
COM.FMC_WaitSetupTime = 0x03;
•
COM.FMC_HoldSetupTime = 0x02;
•
COM.FMC_HiZSetupTime = 0x01;
•
ATT.FMC_SetupTime = 0x01;
•
ATT.FMC_WaitSetupTime = 0x03;
•
ATT.FMC_HoldSetupTime = 0x02;
•
ATT.FMC_HiZSetupTime = 0x01;
•
Bank = FMC_Bank_NAND;
•
MemoryDataWidth = FMC_MemoryDataWidth_16b;
•
ECC = FMC_ECC_Enable;
•
ECCPageSize = FMC_ECCPageSize_512Bytes;
•
TCLRSetupTime = 0;
•
TARSetupTime = 0.
| In all timing tables, the T |  is the HCLK clock period.  |     |     |     |
| --------------------------- | --------------------------- | --- | --- | --- |
HCLK
|     |     | DocID029808 Rev 3 |     | 191/229 |
| --- | --- | ----------------- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
Figure 69. NAND controller waveforms for read access
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:35)(cid:37)(cid:88)
(cid:33)(cid:44)(cid:37)(cid:0)(cid:8)(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:17)(cid:23)(cid:9)
(cid:35)(cid:44)(cid:37)(cid:0)(cid:8)(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:17)(cid:22)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:37)
(cid:84)(cid:68)(cid:8)(cid:33)(cid:44)(cid:37)(cid:13)(cid:46)(cid:47)(cid:37)(cid:9) (cid:84)(cid:72)(cid:8)(cid:46)(cid:47)(cid:37)(cid:13)(cid:33)(cid:44)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:47)(cid:37)(cid:0)(cid:8)(cid:46)(cid:50)(cid:37)(cid:9)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:36)(cid:13)(cid:46)(cid:47)(cid:37)(cid:9) (cid:84)(cid:72)(cid:8)(cid:46)(cid:47)(cid:37)(cid:13)(cid:36)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:22)(cid:23)(cid:54)(cid:17)
Figure 70. NAND controller waveforms for write access
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:35)(cid:37)(cid:88)
(cid:33)(cid:44)(cid:37)(cid:0)(cid:8)(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:17)(cid:23)(cid:9)
(cid:35)(cid:44)(cid:37)(cid:0)(cid:8)(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:17)(cid:22)(cid:9)
(cid:84)(cid:68)(cid:8)(cid:33)(cid:44)(cid:37)(cid:13)(cid:46)(cid:55)(cid:37)(cid:9) (cid:84)(cid:72)(cid:8)(cid:46)(cid:55)(cid:37)(cid:13)(cid:33)(cid:44)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:37)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:47)(cid:37)(cid:0)(cid:8)(cid:46)(cid:50)(cid:37)(cid:9)
(cid:84)(cid:86)(cid:8)(cid:46)(cid:55)(cid:37)(cid:13)(cid:36)(cid:9) (cid:84)(cid:72)(cid:8)(cid:46)(cid:55)(cid:37)(cid:13)(cid:36)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:22)(cid:24)(cid:54)(cid:17)
Figure 71. NAND controller waveforms for common memory read access
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:35)(cid:37)(cid:88)
(cid:33)(cid:44)(cid:37)(cid:0)(cid:8)(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:17)(cid:23)(cid:9)
(cid:35)(cid:44)(cid:37)(cid:0)(cid:8)(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:17)(cid:22)(cid:9)
(cid:84)(cid:68)(cid:8)(cid:33)(cid:44)(cid:37)(cid:13)(cid:46)(cid:47)(cid:37)(cid:9) (cid:84)(cid:72)(cid:8)(cid:46)(cid:47)(cid:37)(cid:13)(cid:33)(cid:44)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:37)
(cid:84)(cid:87)(cid:8)(cid:46)(cid:47)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:47)(cid:37)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:36)(cid:13)(cid:46)(cid:47)(cid:37)(cid:9) (cid:84)(cid:72)(cid:8)(cid:46)(cid:47)(cid:37)(cid:13)(cid:36)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:22)(cid:25)(cid:54)(cid:17)
192/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
Figure 72. NAND controller waveforms for common memory write access
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:35)(cid:37)(cid:88)
(cid:33)(cid:44)(cid:37)(cid:0)(cid:8)(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:17)(cid:23)(cid:9)
(cid:35)(cid:44)(cid:37)(cid:0)(cid:8)(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:17)(cid:22)(cid:9)
|     | (cid:84)(cid:68)(cid:8)(cid:33)(cid:44)(cid:37)(cid:13)(cid:46)(cid:47)(cid:37)(cid:9) |     | (cid:84)(cid:87)(cid:8)(cid:46)(cid:55)(cid:37)(cid:9) |     | (cid:84)(cid:72)(cid:8)(cid:46)(cid:47)(cid:37)(cid:13)(cid:33)(cid:44)(cid:37)(cid:9) |
| --- | -------------------------------------------------------------------------------------- | --- | ------------------------------------------------------ | --- | -------------------------------------------------------------------------------------- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:55)(cid:37)
| (cid:38)(cid:45)(cid:35)(cid:63)(cid:46) | (cid:47)(cid:37) |     |     |     |     |
| ---------------------------------------- | ---------------- | --- | --- | --- | --- |
(cid:84)(cid:68)(cid:8)(cid:36)(cid:13)(cid:46)(cid:55)(cid:37)(cid:9)
|     |     |     | (cid:84)(cid:86)(cid:8)(cid:46)(cid:55)(cid:37)(cid:13)(cid:36)(cid:9) | (cid:84)(cid:72)(cid:8)(cid:46)(cid:55)(cid:37)(cid:13)(cid:36)(cid:9) |     |
| --- | --- | --- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:36)(cid:59)(cid:17)(cid:21)(cid:26)(cid:16)(cid:61)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:23)(cid:16)(cid:54)(cid:17)
           Table 106. Switching characteristics for NAND Flash read cycles(1)
| Symbol |                   | Parameter |     | Min         | Max Unit    |
| ------ | ----------------- | --------- | --- | ----------- | ----------- |
| t      | FMC_NOE low width |           |     | 4Thclk -0.5 | 4Thclk +0.5 |
w(N0E)
| t   | FMC_D[15-0] valid data before FMC_NOE high |     |     | 11  | -   |
| --- | ------------------------------------------ | --- | --- | --- | --- |
su(D-NOE)
| t h(NOE-D) | FMC_D[15-0] valid data after FMC_NOE high |     |     | 0   | - ns        |
| ---------- | ----------------------------------------- | --- | --- | --- | ----------- |
| t          | FMC_ALE valid before FMC_NOE low          |     |     | -   | 3Thclk +1.5 |
d(ALE-NOE)
| t   | FMC_NWE high to FMC_ALE invalid |     |     | 4Thclk - 2 | -   |
| --- | ------------------------------- | --- | --- | ---------- | --- |
h(NOE-ALE)
1. Guaranteed by characterization results.
           Table 107. Switching characteristics for NAND Flash write cycles(1)
| Symbol |                   | Parameter |     | Min         | Max Unit    |
| ------ | ----------------- | --------- | --- | ----------- | ----------- |
| t      | FMC_NWE low width |           |     | 4Thclk -0.5 | 4Thclk +0.5 |
w(NWE)
| t   | FMC_NWE low to FMC_D[15-0] valid |     |     | 0   | -   |
| --- | -------------------------------- | --- | --- | --- | --- |
v(NWE-D)
| t h(NWE-D) | FMC_NWE high to FMC_D[15-0] invalid |     |     | 2Thclk - 1 | -   |
| ---------- | ----------------------------------- | --- | --- | ---------- | --- |
ns
| t   | FMC_D[15-0] valid before FMC_NWE high |     |     | 5Thclk - 1 | -   |
| --- | ------------------------------------- | --- | --- | ---------- | --- |
d(D-NWE)
| t d(ALE-NWE) | FMC_ALE valid before FMC_NWE low |     |     | -          | 3Thclk +1.5 |
| ------------ | -------------------------------- | --- | --- | ---------- | ----------- |
| t            | FMC_NWE high to FMC_ALE invalid  |     |     | 2Thclk - 2 | -           |
h(NWE-ALE)
1. Guaranteed by characterization results.
DocID029808 Rev 3 193/229
201

Electrical characteristics STM32F722xx STM32F723xx
SDRAM waveforms and timings
• CL = 30 pF on data and address lines. CL = 10 pF on FMC_SDCLK unless otherwise
specified.
In all timing tables, the T is the HCLK clock period.
HCLK
– For 3.0 V≤ V ≤ 3.6 V, maximum FMC_SDCLK= 100 MHz at CL=20 pF (on
DD
FMC_SDCLK).
– For 2.7 V≤ V ≤ 3.6 V, maximum FMC_SDCLK = 90 MHz at CL=30 pF (on
DD
FMC_SDCLK).
– For 1.71 V≤ V <1.9 V, maximum FMC_SDCLK = 70 MHz at CL=10 pF (on
DD
FMC_SDCLK).
Figure 73. SDRAM read access waveforms (CL = 1)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)
(cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:33)(cid:68)(cid:68)(cid:35)(cid:9)
(cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:33)(cid:68)(cid:68)(cid:50)(cid:9)
(cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:33)(cid:68)(cid:68)(cid:50)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:62)(cid:20)(cid:21)(cid:29)(cid:19)(cid:64) (cid:50)(cid:79)(cid:87)(cid:0)(cid:78) (cid:35)(cid:79)(cid:76)(cid:17) (cid:35)(cid:79)(cid:76)(cid:18) (cid:35)(cid:79)(cid:76)(cid:73) (cid:35)(cid:79)(cid:76)(cid:78)
(cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:33)(cid:68)(cid:68)(cid:35)(cid:9)
(cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:51)(cid:46)(cid:36)(cid:37)(cid:9) (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:51)(cid:46)(cid:36)(cid:37)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:51)(cid:36)(cid:46)(cid:37)(cid:59)(cid:17)(cid:26)(cid:16)(cid:61)
(cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:46)(cid:50)(cid:33)(cid:51)(cid:9) (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:46)(cid:50)(cid:33)(cid:51)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:51)(cid:36)(cid:46)(cid:50)(cid:33)(cid:51)
(cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:46)(cid:35)(cid:33)(cid:51)(cid:9) (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:46)(cid:35)(cid:33)(cid:51)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:51)(cid:36)(cid:46)(cid:35)(cid:33)(cid:51)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:51)(cid:36)(cid:46)(cid:55)(cid:37)
(cid:84)(cid:83)(cid:85)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:40)(cid:63)(cid:36)(cid:65)(cid:84)(cid:65)(cid:9) (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:40)(cid:63)(cid:36)(cid:65)(cid:84)(cid:65)(cid:9)
(cid:38)(cid:45)(cid:35)(cid:63)(cid:36)(cid:59)(cid:19)(cid:17)(cid:26)(cid:16)(cid:61) (cid:36)(cid:65)(cid:84)(cid:65)(cid:17) (cid:36)(cid:65)(cid:84)(cid:65)(cid:18) (cid:36)(cid:65)(cid:84)(cid:65)(cid:73) (cid:36)(cid:65)(cid:84)(cid:65)(cid:78)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:21)(cid:17)(cid:54)(cid:18)
194/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
|            | Table 108. SDRAM read timings(1)  |             |             |       |
| ---------- | --------------------------------- | ----------- | ----------- | ----- |
| Symbol     | Parameter                         | Min         | Max         | Unit  |
| t          | FMC_SDCLK period                  | 2Thclk -0.5 | 2Thclk +0.5 |       |
w(SDCLK)
| t su(SDCLKH _Data) | Data input setup time | 1.5 | -   |     |
| ------------------ | --------------------- | --- | --- | --- |
| t                  | Data input hold time  | 2   | -   |     |
h(SDCLKH_Data)
| t   | Address valid time | -   | 1.5 |     |
| --- | ------------------ | --- | --- | --- |
d(SDCLKL_Add)
| t   | Chip select valid time | -   | 1.5 |     |
| --- | ---------------------- | --- | --- | --- |
d(SDCLKL- SDNE)
ns
| t   | Chip select hold time | 0.5 | -   |     |
| --- | --------------------- | --- | --- | --- |
h(SDCLKL_SDNE)
| t d(SDCLKL_SDNRAS) | SDNRAS valid time | -   | 1   |     |
| ------------------ | ----------------- | --- | --- | --- |
| t                  | SDNRAS hold time  | 0.5 | -   |     |
h(SDCLKL_SDNRAS)
| t   | SDNCAS valid time | -   | 1.5 |     |
| --- | ----------------- | --- | --- | --- |
d(SDCLKL_SDNCAS)
| t   | SDNCAS hold time | 0   | -   |     |
| --- | ---------------- | --- | --- | --- |
h(SDCLKL_SDNCAS)
1. Guaranteed by characterization results.
|            | Table 109. LPSDR SDRAM read timings(1)  |             |             |       |
| ---------- | --------------------------------------- | ----------- | ----------- | ----- |
| Symbol     | Parameter                               | Min         | Max         | Unit  |
| t          | FMC_SDCLK period                        | 2Thclk -0.5 | 2Thclk +0.5 |       |
W(SDCLK)
| t su(SDCLKH_Data) | Data input setup time | 0   | -   |     |
| ----------------- | --------------------- | --- | --- | --- |
| t                 | Data input hold time  | 4.5 | -   |     |
h(SDCLKH_Data)
| t   | Address valid time | -   | 1.5 |     |
| --- | ------------------ | --- | --- | --- |
d(SDCLKL_Add)
| t   | Chip select valid time | -   | 1.5 |     |
| --- | ---------------------- | --- | --- | --- |
d(SDCLKL_SDNE)
ns
| t   | Chip select hold time | 0   | -   |     |
| --- | --------------------- | --- | --- | --- |
h(SDCLKL_SDNE)
| t d(SDCLKL_SDNRAS | SDNRAS valid time | -   | 0.5 |     |
| ----------------- | ----------------- | --- | --- | --- |
| t                 | SDNRAS hold time  | 0   | -   |     |
h(SDCLKL_SDNRAS)
| t d(SDCLKL_SDNCAS) | SDNCAS valid time | -   | 1.5 |     |
| ------------------ | ----------------- | --- | --- | --- |
| t                  | SDNCAS hold time  | 0   | -   |     |
h(SDCLKL_SDNCAS)
1. Guaranteed by characterization results.
|     | DocID029808 Rev 3 |     |     | 195/229 |
| --- | ----------------- | --- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
Figure 74. SDRAM write access waveforms
(cid:38)(cid:45)(cid:35)(cid:63)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)
(cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:33)(cid:68)(cid:68)(cid:35)(cid:9)
(cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:33)(cid:68)(cid:68)(cid:50)(cid:9)
(cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:33)(cid:68)(cid:68)(cid:50)(cid:9)
|     |     | (cid:50)(cid:79)(cid:87)(cid:0)(cid:78) | (cid:35)(cid:79)(cid:76)(cid:17) | (cid:35)(cid:79)(cid:76)(cid:18) | (cid:35)(cid:79)(cid:76)(cid:73) (cid:35)(cid:79)(cid:76)(cid:78) |     |     |
| --- | --- | --------------------------------------- | -------------------------------- | -------------------------------- | ----------------------------------------------------------------- | --- | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:33)(cid:62)(cid:20)(cid:21)(cid:29)(cid:19)(cid:64)
(cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:33)(cid:68)(cid:68)(cid:35)(cid:9)
|     |     | (cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:51)(cid:46)(cid:36)(cid:37)(cid:9) |     |     |     | (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:51)(cid:46)(cid:36)(cid:37)(cid:9) |     |
| --- | --- | ---------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | ---------------------------------------------------------------------------------------------------------------------- | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:51)(cid:36)(cid:46)(cid:37)(cid:59)(cid:17)(cid:26)(cid:16)(cid:61)
| (cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:46)(cid:50)(cid:33)(cid:51)(cid:9) |     |     | (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:46)(cid:50)(cid:33)(cid:51)(cid:9) |     |     |     |     |
| ---------------------------------------------------------------------------------------------------------------------- | --- | --- | ---------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:51)(cid:36)(cid:46)(cid:50)(cid:33)(cid:51)
|     |     |     | (cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:46)(cid:35)(cid:33)(cid:51)(cid:9) |     |     | (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:46)(cid:35)(cid:33)(cid:51)(cid:9) |     |
| --- | --- | --- | ---------------------------------------------------------------------------------------------------------------------- | --- | --- | ---------------------------------------------------------------------------------------------------------------------- | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:51)(cid:36)(cid:46)(cid:35)(cid:33)(cid:51)
|     |     |     | (cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:46)(cid:55)(cid:37)(cid:9) |     |     | (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:46)(cid:55)(cid:37)(cid:9) |     |
| --- | --- | --- | -------------------------------------------------------------------------------------------------------------- | --- | --- | -------------------------------------------------------------------------------------------------------------- | --- |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:51)(cid:36)(cid:46)(cid:55)(cid:37)
(cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:36)(cid:65)(cid:84)(cid:65)(cid:9)
| (cid:38)(cid:45)(cid:35)(cid:63)(cid:36)(cid:59)(cid:19)(cid:17)(cid:26)(cid:16)(cid:61)                       |     |     | (cid:36)(cid:65)(cid:84)(cid:65)(cid:17) | (cid:36)(cid:65)(cid:84)(cid:65)(cid:18)                                                                               | (cid:36)(cid:65)(cid:84)(cid:65)(cid:73) (cid:36)(cid:65)(cid:84)(cid:65)(cid:78) |     |     |
| -------------------------------------------------------------------------------------------------------------- | --- | --- | ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --- | --- |
| (cid:84)(cid:68)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:46)(cid:34)(cid:44)(cid:9) |     |     |                                          | (cid:84)(cid:72)(cid:8)(cid:51)(cid:36)(cid:35)(cid:44)(cid:43)(cid:44)(cid:63)(cid:36)(cid:65)(cid:84)(cid:65)(cid:9) |                                                                                   |     |     |
(cid:38)(cid:45)(cid:35)(cid:63)(cid:46)(cid:34)(cid:44)(cid:59)(cid:19)(cid:26)(cid:16)(cid:61)
(cid:45)(cid:51)(cid:19)(cid:18)(cid:23)(cid:21)(cid:18)(cid:54)(cid:18)
|            |     | Table 110. SDRAM write timings(1)  |     |     |             |             |       |
| ---------- | --- | ---------------------------------- | --- | --- | ----------- | ----------- | ----- |
| Symbol     |     | Parameter                          |     |     | Min         | Max         | Unit  |
| t          |     | FMC_SDCLK period                   |     |     | 2Thclk -0.5 | 2Thclk +0.5 |       |
w(SDCLK)
| t   | )   | Data output valid time |     |     | -   | 1.5 |     |
| --- | --- | ---------------------- | --- | --- | --- | --- | --- |
d(SDCLKL _Data
| t   |     | Data output hold time |     |     | 0   | -   |     |
| --- | --- | --------------------- | --- | --- | --- | --- | --- |
h(SDCLKL _Data)
| t d(SDCLKL_Add) |     | Address valid time |     |     | -   | 1.5 |     |
| --------------- | --- | ------------------ | --- | --- | --- | --- | --- |
| t               |     | SDNWE valid time   |     |     | -   | 1.5 |     |
d(SDCLKL_SDNWE)
| t h(SDCLKL_SDNWE)  |     | SDNWE hold time |     |     | 0.5 | -   |     |
| ------------------ | --- | --------------- | --- | --- | --- | --- | --- |
ns
| t   |     | Chip  select valid time |     |     | -   | 1.5 |     |
| --- | --- | ----------------------- | --- | --- | --- | --- | --- |
d(SDCLKL_ SDNE)
| t   |     | Chip  select hold time |     |     | 0.5 | -   |     |
| --- | --- | ---------------------- | --- | --- | --- | --- | --- |
h(SDCLKL-_SDNE)
| t   |     | SDNRAS valid time |     |     | -   | 1   |     |
| --- | --- | ----------------- | --- | --- | --- | --- | --- |
d(SDCLKL_SDNRAS)
| t   |     | SDNRAS hold time |     |     | 0.5 | -   |     |
| --- | --- | ---------------- | --- | --- | --- | --- | --- |
h(SDCLKL_SDNRAS)
| t d(SDCLKL_SDNCAS)  |     | SDNCAS valid time |     |     | -   | 1.5 |     |
| ------------------- | --- | ----------------- | --- | --- | --- | --- | --- |
| t                   |     | SDNCAS hold time  |     |     | 0.5 | -   |     |
d(SDCLKL_SDNCAS)
1. Guaranteed by characterization results.
196/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
|            | Table 111. LPSDR SDRAM write timings(1)  |                  |     |             |             |       |
| ---------- | ---------------------------------------- | ---------------- | --- | ----------- | ----------- | ----- |
| Symbol     |                                          | Parameter        |     | Min         | Max         | Unit  |
| t          |                                          | FMC_SDCLK period |     | 2Thclk -0.5 | 2Thclk +0.5 |       |
w(SDCLK)
| t d(SDCLKL _Data | )   | Data output valid time |     | -   | 2   |     |
| ---------------- | --- | ---------------------- | --- | --- | --- | --- |
| t                |     | Data output hold time  |     | 0   | -   |     |
h(SDCLKL _Data)
| t   |     | Address valid time |     | -   | 1.5 |     |
| --- | --- | ------------------ | --- | --- | --- | --- |
d(SDCLKL_Add)
| t   |     | SDNWE valid time |     | -   | 1.5 |     |
| --- | --- | ---------------- | --- | --- | --- | --- |
d(SDCLKL-SDNWE)
| t   |     | SDNWE hold time |     | 0   | -   |     |
| --- | --- | --------------- | --- | --- | --- | --- |
h(SDCLKL-SDNWE)
ns
| t d(SDCLKL- SDNE) |     | Chip select valid time |     | -   | 0.5 |     |
| ----------------- | --- | ---------------------- | --- | --- | --- | --- |
| t                 |     | Chip select hold time  |     | 0.  | -   |     |
h(SDCLKL- SDNE)
| t   |     | SDNRAS valid time |     | -   | 2   |     |
| --- | --- | ----------------- | --- | --- | --- | --- |
d(SDCLKL-SDNRAS)
| t   |     | SDNRAS hold time |     | 0   | -   |     |
| --- | --- | ---------------- | --- | --- | --- | --- |
h(SDCLKL-SDNRAS)
| t   |     | SDNCAS valid time |     | -   | 2   |     |
| --- | --- | ----------------- | --- | --- | --- | --- |
d(SDCLKL-SDNCAS)
| t   |     | SDNCAS hold time |     | 0   | -   |     |
| --- | --- | ---------------- | --- | --- | --- | --- |
d(SDCLKL-SDNCAS)
1. Guaranteed by characterization results.
5.3.31  Quad-SPI interface characteristics
Unless otherwise specified, the parameters given in Table 112 and Table 113 for Quad-SPI
are derived from tests performed under the ambient temperature, f  frequency and V
|     |     |     |     |     | AHB | DD  |
| --- | --- | --- | --- | --- | --- | --- |
supply voltage conditions summarized in Table 17: General operating conditions, with the
following configuration:
• Output speed is set to OSPEEDRy[1:0] = 11
• Capacitive load C = 20 pF
• Measurement points are done at CMOS levels: 0.5 ₓ V
DD
Refer to Section 5.3.20: I/O port characteristics for more details on the input/output alternate
function characteristics.
|            | Table 112. Quad-SPI characteristics in SDR mode(1)  |            |          |     |         |      |
| ---------- | --------------------------------------------------- | ---------- | -------- | --- | ------- | ---- |
| Symbol     | Parameter                                           | Conditions |          | Min | Typ Max | Unit |
|            |                                                     | 2.7 V≤ V   | <3.6 V   |     |         |      |
|            |                                                     |            | DD       | -   | - 108   |      |
|            | Quad-SPI clock                                      |            | CL=20 pF |     |         |      |
| Fck1/t(CK) |                                                     |            |          |     |         | MHz  |
frequency
|     |     | 1.71 V<V | <3.6 V |     |       |     |
| --- | --- | -------- | ------ | --- | ----- | --- |
|     |     |          | DD     | -   | - 100 |     |
CL=15 pF
|     |     | DocID029808 Rev 3 |     |     |     | 197/229 |
| --- | --- | ----------------- | --- | --- | --- | ------- |
201

Electrical characteristics STM32F722xx STM32F723xx
Table 112. Quad-SPI characteristics (continued)in SDR mode(1) (continued)
| Symbol  |                      | Parameter |     | Conditions |               | Min | Typ | Max Unit      |
| ------- | -------------------- | --------- | --- | ---------- | ------------- | --- | --- | ------------- |
| tw(CKH) | Quad-SPI clock high  |           |     |            | t(CK)/2 - 0.5 |     | -   | t(CK)/2 + 0.5 |
-
and low time
| tw(CKL) |                       |     |     |     | t(CK)/2 - 0.5 |     | -   | t(CK)/2 + 0.5 |
| ------- | --------------------- | --- | --- | --- | ------------- | --- | --- | ------------- |
| ts(IN)  | Data input setup time |     |     |     |               | 3   | -   | -             |
-
| th(IN)  | Data input hold time |     |         |        |     | 1   | -   | - ns |
| ------- | -------------------- | --- | ------- | ------ | --- | --- | --- | ---- |
|         |                      |     | 2.7 V<V | <3.6 V |     | -   | 1.5 | 3    |
DD
| tv(OUT)  | Data output valid time |     |          |           |     |     |     |     |
| -------- | ---------------------- | --- | -------- | --------- | --- | --- | --- | --- |
|          |                        |     | 1.71 V<V | DD <3.6 V |     | -   | 1.5 | 2.5 |
| th(OUT)  | Data output hold time  |     |          | -         |     | 0.5 | -   | -   |
1. Guaranteed by characterization results.
|            |     | Table 113. Quad-SPI characteristics in DDR mode(1)  |     |            |        |     |     |          |
| ---------- | --- | --------------------------------------------------- | --- | ---------- | ------ | --- | --- | -------- |
| Symbol     |     | Parameter                                           |     | Conditions |        | Min | Typ | Max Unit |
|            |     |                                                     |     | 2.7 V<V    | <3.6 V |     |     |          |
|            |     |                                                     |     | DD         |        | -   | -   | 80       |
CL=20 pF
|            |                          |     |     | 1.8 V<V | <3.6 V |     |     |        |
| ---------- | ------------------------ | --- | --- | ------- | ------ | --- | --- | ------ |
| Fck1/t(CK) | Quad-SPI clock frequency |     |     | DD      |        | -   | -   | 80 MHz |
CL=15 pF
|     |     |     |     | 1.71 V<V | <3.6 V |     |     |     |
| --- | --- | --- | --- | -------- | ------ | --- | --- | --- |
|     |     |     |     | DD       |        | -   | -   | 80  |
CL=10 pF
|         |     |     |     |     |     | t(CK)/2 - |     | t(CK)/2 +  |
| ------- | --- | --- | --- | --- | --- | --------- | --- | ---------- |
| tw(CKH) |     |     |     |     |     |           | -   |            |
|         |     |     |     |     |     | 0.5       |     | 0.5        |
Quad-SPI clock high and
-
low time
|          |     |     |     |         |        | t(CK)/2 -  |     | t(CK)/2 +  |
| -------- | --- | --- | --- | ------- | ------ | ---------- | --- | ---------- |
| tw(CKL)  |     |     |     |         |        |            | -   |            |
|          |     |     |     |         |        | 0.5        |     | 0.5        |
|          |     |     |     | 2.7 V<V | <3.6 V | 1          | -   | -          |
| ts(IN),  |     |     |     | DD      |        |            |     |            |
Data input setup time
tsf(IN)
|           |     |     |     | 1.71 V<V DD | <2 V   | 0.5  | -   | -   |
| --------- | --- | --- | --- | ----------- | ------ | ---- | --- | --- |
|           |     |     |     | 2.7 V<V     | <3.6 V | 2.25 | -   | -   |
| thr(IN),  |     |     |     | DD          |        |      |     |     |
Data input hold time
| thf(IN) |     |     |     | 1.71 V<V | <2 V | 2.75 | -   | -   |
| ------- | --- | --- | --- | -------- | ---- | ---- | --- | --- |
DD
ns
|     |     |     |     | 2.7 V<V | <3.6 V | -   | 9.5 | 11.5 |
| --- | --- | --- | --- | ------- | ------ | --- | --- | ---- |
DD
|     |     |     |     | 1.71 V<V | <3.6 V |     |     |     |
| --- | --- | --- | --- | -------- | ------ | --- | --- | --- |
DD
| tvr(OUT),  |                        |     |     |        |     | -   | 9.5 | 12.25 |
| ---------- | ---------------------- | --- | --- | ------ | --- | --- | --- | ----- |
|            | Data output valid time |     |     | DHHC=0 |     |     |     |       |
tvf(OUT)
|     |     |     |     | DHHC=1 |     |     | Thclk/2  | Thclk/2  |
| --- | --- | --- | --- | ------ | --- | --- | -------- | -------- |
-
|     |     |     |     | Pres=1, 2... |     |     | +2  | +2.5 |
| --- | --- | --- | --- | ------------ | --- | --- | --- | ---- |
|     |     |     |     | DHHC=0       |     | 5.5 | -   | -    |
thr(OUT),
Data output hold time
| thf(OUT) |     |     |     | DHHC=1       |     | Thclk/2  |     |     |
| -------- | --- | --- | --- | ------------ | --- | -------- | --- | --- |
|          |     |     |     |              |     |          | -   | -   |
|          |     |     |     | Pres=1, 2... |     | +0.75    |     |     |
1. Guaranteed by characterization results.
198/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Electrical characteristics
Figure 75. Quad-SPI timing diagram - SDR mode
| (cid:87)                                 | (cid:87)                         | (cid:87)                                         | (cid:87) (cid:87)                                                                         |
| ---------------------------------------- | -------------------------------- | ------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| (cid:85)(cid:11)(cid:38)(cid:46)(cid:12) | (cid:11)(cid:38)(cid:46)(cid:12) | (cid:90)(cid:11)(cid:38)(cid:46)(cid:43)(cid:12) | (cid:90)(cid:11)(cid:38)(cid:46)(cid:47)(cid:12) (cid:73)(cid:11)(cid:38)(cid:46)(cid:12) |
(cid:38)(cid:79)(cid:82)(cid:70)(cid:78)
| (cid:87) (cid:89)(cid:11)(cid:50)(cid:56)(cid:55)(cid:12) | (cid:87) (cid:75)(cid:11)(cid:50)(cid:56)(cid:55)(cid:12) |     |     |
| --------------------------------------------------------- | --------------------------------------------------------- | --- | --- |
(cid:39)(cid:68)(cid:87)(cid:68)(cid:3)(cid:82)(cid:88)(cid:87)(cid:83)(cid:88)(cid:87)
|     | (cid:39)(cid:19) | (cid:39)(cid:20) | (cid:39)(cid:21) |
| --- | ---------------- | ---------------- | ---------------- |
(cid:87) (cid:87)
(cid:86)(cid:11)(cid:44)(cid:49)(cid:12) (cid:75)(cid:11)(cid:44)(cid:49)(cid:12)
(cid:39)(cid:68)(cid:87)(cid:68)(cid:3)(cid:76)(cid:81)(cid:83)(cid:88)(cid:87)
|     | (cid:39)(cid:19) | (cid:39)(cid:20) | (cid:39)(cid:21) |
| --- | ---------------- | ---------------- | ---------------- |
(cid:48)(cid:54)(cid:89)(cid:22)(cid:25)(cid:27)(cid:26)(cid:27)(cid:57)(cid:20)
Figure 76. Quad-SPI timing diagram - DDR mode
| (cid:87)                                 | (cid:87)                         | (cid:87)                                         | (cid:87) (cid:87)                                                                         |
| ---------------------------------------- | -------------------------------- | ------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| (cid:85)(cid:11)(cid:38)(cid:46)(cid:12) | (cid:11)(cid:38)(cid:46)(cid:12) | (cid:90)(cid:11)(cid:38)(cid:46)(cid:43)(cid:12) | (cid:90)(cid:11)(cid:38)(cid:46)(cid:47)(cid:12) (cid:73)(cid:11)(cid:38)(cid:46)(cid:12) |
(cid:38)(cid:79)(cid:82)(cid:70)(cid:78)
| (cid:87) (cid:89)(cid:73)(cid:11)(cid:50)(cid:56)(cid:55)(cid:12) | (cid:87) (cid:75)(cid:85)(cid:11)(cid:50)(cid:56)(cid:55)(cid:12) | (cid:87) (cid:89)(cid:85)(cid:11)(cid:50)(cid:56)(cid:55)(cid:12) (cid:87) (cid:75)(cid:73)(cid:11)(cid:50)(cid:56)(cid:55)(cid:12) |     |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | --- |
(cid:39)(cid:68)(cid:87)(cid:68)(cid:3)(cid:82)(cid:88)(cid:87)(cid:83)(cid:88)(cid:87)
|     | (cid:39)(cid:19) (cid:39)(cid:20)                                                                 | (cid:39)(cid:21) (cid:39)(cid:22) | (cid:39)(cid:23) (cid:39)(cid:24)                                                                 |
| --- | ------------------------------------------------------------------------------------------------- | --------------------------------- | ------------------------------------------------------------------------------------------------- |
|     | (cid:87) (cid:87)                                                                                 |                                   | (cid:87) (cid:87)                                                                                 |
|     | (cid:86)(cid:73)(cid:11)(cid:44)(cid:49)(cid:12) (cid:75)(cid:73)(cid:11)(cid:44)(cid:49)(cid:12) |                                   | (cid:86)(cid:85)(cid:11)(cid:44)(cid:49)(cid:12) (cid:75)(cid:85)(cid:11)(cid:44)(cid:49)(cid:12) |
(cid:39)(cid:68)(cid:87)(cid:68)(cid:3)(cid:76)(cid:81)(cid:83)(cid:88)(cid:87) (cid:39)(cid:19) (cid:39)(cid:20) (cid:39)(cid:21) (cid:39)(cid:22) (cid:39)(cid:23) (cid:39)(cid:24)
(cid:48)(cid:54)(cid:89)(cid:22)(cid:25)(cid:27)(cid:26)(cid:28)(cid:57)(cid:20)
5.3.32  SD/SDIO MMC card host interface (SDMMC) characteristics
Unless otherwise specified, the parameters given in Table 114 for the SDIO/MMC interface
are derived from tests performed under the ambient temperature, f frequency and V
PCLK2  DD
supply voltage conditions summarized in Table 17, with the following configuration:
•
Output speed is set to OSPEEDRy[1:0] = 11
•
Capacitive load C = 30 pF
•
Measurement points are done at CMOS levels: 0.5V
DD
Refer to Section 5.3.20: I/O port characteristics for more details on the input/output
characteristics.
DocID029808 Rev 3 199/229
201

| Electrical characteristics |     |     | STM32F722xx STM32F723xx |     |     |
| -------------------------- | --- | --- | ----------------------- | --- | --- |
Figure 77. SDIO high-speed mode
|     |     |     | (cid:84)(cid:70) | (cid:84)(cid:82) |     |
| --- | --- | --- | ---------------- | ---------------- | --- |
(cid:84)(cid:35)
|     | (cid:84)(cid:55)(cid:8)(cid:35)(cid:43)(cid:40)(cid:9) |     |     | (cid:84)(cid:55)(cid:8)(cid:35)(cid:43)(cid:44)(cid:9) |     |
| --- | ------------------------------------------------------ | --- | --- | ------------------------------------------------------ | --- |
(cid:35)(cid:43)
|     |     | (cid:84)(cid:47)(cid:54) |     | (cid:84)(cid:47)(cid:40) |     |
| --- | --- | ------------------------ | --- | ------------------------ | --- |
(cid:36)(cid:12)(cid:0)(cid:35)(cid:45)(cid:36)
(cid:8)(cid:79)(cid:85)(cid:84)(cid:80)(cid:85)(cid:84)(cid:9)
|     |     |     | (cid:84)(cid:41)(cid:51)(cid:53) | (cid:84)(cid:41)(cid:40) |     |
| --- | --- | --- | -------------------------------- | ------------------------ | --- |
(cid:36)(cid:12)(cid:0)(cid:35)(cid:45)(cid:36)
(cid:8)(cid:73)(cid:78)(cid:80)(cid:85)(cid:84)(cid:9)
(cid:65)(cid:73)(cid:17)(cid:20)(cid:24)(cid:24)(cid:23)
Figure 78. SD default mode
(cid:35)(cid:43)
|     |     | (cid:84)(cid:47)(cid:54)(cid:36) |     | (cid:84)(cid:47)(cid:40)(cid:36) |     |
| --- | --- | -------------------------------- | --- | -------------------------------- | --- |
(cid:36)(cid:12)(cid:0)(cid:35)(cid:45)(cid:36)
(cid:8)(cid:79)(cid:85)(cid:84)(cid:80)(cid:85)(cid:84)(cid:9)
(cid:65)(cid:73)(cid:17)(cid:20)(cid:24)(cid:24)(cid:24)
=2.7V to 3.6V(1)
Table           114. Dynamic characteristics: SD / MMC characteristics, V
DD
| Symbol                                  | Parameter | Conditions | Min | Typ | Max Unit |
| --------------------------------------- | --------- | ---------- | --- | --- | -------- |
| f Clock frequency in data transfer mode |           | -          | 0   | -   | 50 MHz   |
PP
| - SDMMC_CK/fPCLK2 frequency ratio |                | -           | -   | -   | 8/3 - |
| --------------------------------- | -------------- | ----------- | --- | --- | ----- |
| t                                 | Clock low time | fpp =50 MHz | 9   | 10  | -     |
W(CKL)
ns
| t   | Clock high time | fpp =50 MHz | 9   | 10  | -   |
| --- | --------------- | ----------- | --- | --- | --- |
W(CKH)
CMD, D inputs (referenced to CK) in MMC and SD HS mode
| t   | Input setup time HS | fpp =50 MHz | 1   | -   | -   |
| --- | ------------------- | ----------- | --- | --- | --- |
ISU
ns
| t   | Input hold time HS | fpp =50 MHz | 3   | -   | -   |
| --- | ------------------ | ----------- | --- | --- | --- |
IH
CMD, D outputs (referenced to CK) in MMC and SD HS mode
| t   | Output valid time HS | fpp =50 MHz | -   | 11  | 12  |
| --- | -------------------- | ----------- | --- | --- | --- |
OV
ns
| t   | Output hold time HS | fpp =50 MHz | 9   | -   | -   |
| --- | ------------------- | ----------- | --- | --- | --- |
OH
| 200/229 | DocID029808 Rev 3 |     |     |     |     |
| ------- | ----------------- | --- | --- | --- | --- |

| STM32F722xx STM32F723xx |     |     |     |     | Electrical characteristics |     |
| ----------------------- | --- | --- | --- | --- | -------------------------- | --- |
Table 114. Dynamic characteristics: SD / MMC characteristics, V =2.7V to 3.6V(1) (continued)
DD
| Symbol |     | Parameter | Conditions | Min | Typ | Max Unit |
| ------ | --- | --------- | ---------- | --- | --- | -------- |
CMD, D inputs (referenced to CK) in SD default mode
| tISUD | Input setup time SD |     | fpp =25 MHz | 1   | -   | -   |
| ----- | ------------------- | --- | ----------- | --- | --- | --- |
ns
| tIHD | Input hold time SD |     | fpp =25 MHz | 3   | -   | -   |
| ---- | ------------------ | --- | ----------- | --- | --- | --- |
CMD, D outputs (referenced to CK) in SD default mode
|      |                              |     |             | -   | 2   | 2.5 |
| ---- | ---------------------------- | --- | ----------- | --- | --- | --- |
| tOVD | Output valid default time SD |     | fpp =25 MHz |     |     |     |
ns
| tOHD | Output hold default time SD |     | fpp =25 MHz | 0.5 | -   | -   |
| ---- | --------------------------- | --- | ----------- | --- | --- | --- |
1. Guaranteed by characterization results,.
          Table 115. Dynamic characteristics: eMMC characteristics, V =1.71V to 1.9V(1)(2)
DD
| Symbol |                                       | Parameter | Conditions | Min | Typ | Max Unit |
| ------ | ------------------------------------- | --------- | ---------- | --- | --- | -------- |
| f      | Clock frequency in data transfer mode |           | -          | 0   | -   | 50 MHz   |
PP
| -   | SDMMC_CK/fPCLK2 frequency ratio |                | -           | -   | -    | 8/3 - |
| --- | ------------------------------- | -------------- | ----------- | --- | ---- | ----- |
| t   |                                 | Clock low time | fpp =50 MHz | 9.5 | 10.5 | -     |
W(CKL)
ns
| t   |     | Clock high time | fpp =50 MHz | 8.5 | 9.5 | -   |
| --- | --- | --------------- | ----------- | --- | --- | --- |
W(CKH)
CMD, D inputs (referenced to CK) in eMMC mode
| t   |     | Input setup time HS | fpp =50 MHz | 0   | -   | -   |
| --- | --- | ------------------- | ----------- | --- | --- | --- |
ISU
ns
| t   |     | Input hold time HS | fpp =50 MHz | 4.5 | -   | -   |
| --- | --- | ------------------ | ----------- | --- | --- | --- |
IH
CMD, D outputs (referenced to CK) in eMMC mode
| t   |     | Output valid time HS | fpp =50 MHz | -   | 12  | 14  |
| --- | --- | -------------------- | ----------- | --- | --- | --- |
OV
ns
| t   |     | Output hold time HS | fpp =50 MHz | 10.5 | -   | -   |
| --- | --- | ------------------- | ----------- | ---- | --- | --- |
OH
1. Guaranteed by characterization results.
2. Cload = 20 pF.
|     |     | DocID029808 Rev 3 |     |     |     | 201/229 |
| --- | --- | ----------------- | --- | --- | --- | ------- |
201

Package information STM32F722xx STM32F723xx
6  Package information
In order to meet environmental requirements, ST offers these devices in different grades of
ECOPACK® packages, depending on their level of environmental compliance. ECOPACK®
specifications, grade definitions and product status are available at: www.st.com.
ECOPACK® is an ST trademark.
6.1  LQFP64 – 10 x 10 mm, low-profile quad flat package
information
Figure 79. LQFP64 – 10 x 10 mm, low-profile quad flat package outline
(cid:54)(cid:40)(cid:36)(cid:55)(cid:44)(cid:49)(cid:42)(cid:3)(cid:51)(cid:47)(cid:36)(cid:49)(cid:40)
(cid:38)
(cid:21)(cid:36)
|     | (cid:36) |     |     |     |     | (cid:19)(cid:17)(cid:21)(cid:24)(cid:3)(cid:80)(cid:80) |
| --- | -------- | --- | --- | --- | --- | ------------------------------------------------------- |
(cid:42)(cid:36)(cid:56)(cid:42)(cid:40)(cid:3)(cid:51)(cid:47)(cid:36)(cid:49)(cid:40)
|     | (cid:20)(cid:36) |     |     | (cid:70) |     |     |
| --- | ---------------- | --- | --- | -------- | --- | --- |
(cid:70)(cid:70)(cid:70)
(cid:38)
(cid:20)(cid:36)
|     |     |     | (cid:39)         |     |                  | (cid:46) |
| --- | --- | --- | ---------------- | --- | ---------------- | -------- |
|     |     |     | (cid:39)(cid:20) |     |                  | (cid:47) |
|     |     |     | (cid:39)(cid:22) |     | (cid:47)(cid:20) |          |
(cid:22)(cid:22)
(cid:23)(cid:27)
(cid:22)(cid:21)
(cid:23)(cid:28)
(cid:69)
|     |     |     |     | (cid:22)(cid:40) | (cid:20)(cid:40) |     |
| --- | --- | --- | --- | ---------------- | ---------------- | --- |
(cid:40)
|     |                                         | (cid:25)(cid:23) |     | (cid:20)(cid:26) |     |     |
| --- | --------------------------------------- | ---------------- | --- | ---------------- | --- | --- |
|     | (cid:51)(cid:44)(cid:49)(cid:3)(cid:20) | (cid:20)         |     | (cid:20)(cid:25) |     |     |
(cid:72)
(cid:44)(cid:39)(cid:40)(cid:49)(cid:55)(cid:44)(cid:41)(cid:44)(cid:38)(cid:36)(cid:55)(cid:44)(cid:50)(cid:49)
(cid:24)(cid:58)(cid:66)(cid:48)(cid:40)(cid:66)(cid:57)(cid:22)
1. Drawing is not to scale.

Table 116. LQFP64 – 10 x 10 mm, low-profile quad flat package mechanical data
|     |     | millimeters |     |     | inches(1) |     |
| --- | --- | ----------- | --- | --- | --------- | --- |
Symbol
|     | Min   | Typ  | Max  | Min    | Typ    | Max    |
| --- | ----- | ---- | ---- | ------ | ------ | ------ |
| A   |  -    |  -   | 1.60 | -      | -      | 0.0630 |
| A1  | 0.05  | -    | 0.15 | 0.0020 | -      | 0.0059 |
| A2  | 1.350 | 1.40 | 1.45 | 0.0531 | 0.0551 | 0.0571 |
| b   | 0.17  | 0.22 | 0.27 | 0.0067 | 0.0087 | 0.0106 |
202/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
Table 116. LQFP64 – 10 x 10 mm, low-profile quad flat package mechanical data (continued)
inches(1)
millimeters
Symbol
|     | Min  | Typ   | Max  | Min    | Typ    | Max    |
| --- | ---- | ----- | ---- | ------ | ------ | ------ |
| c   | 0.09 | -     | 0.20 | 0.0035 |        | 0.0079 |
| D   | -    | 12.00 | -    | -      | 0.4724 | -      |
| D1  | -    | 10.00 | -    | -      | 0.3937 | -      |
| D3  | -    | 7.50  | -    | -      | 0.2953 | -      |
| E   | -    | 12.00 | -    | -      | 0.4724 | -      |
| E1  | -    | 10.00 | -    | -      | 0.3937 | -      |
| E3  | -    | 7.50  | -    | -      | 0.2953 | -      |
| e   | -    | 0.50  | -    | -      | 0.0197 | -      |
| K   | 0°   | 3.5°  | 7°   | 0°     | 3.5°   | 7°     |
| L   | 0.45 | 0.60  | 0.75 | 0.0177 | 0.0236 | 0.0295 |
| L1  | -    | 1.00  |  -   | -      | 0.0394 | -      |
| ccc | -    | -     | 0.08 | -      | -      | 0.0031 |
1. Values in inches are converted from mm and rounded to 4 decimal digits.
Figure 80. LQFP64 – 10 x 10 mm, low-profile quad flat package recommended
footprint
|     |     |     | (cid:20)(cid:24) | (cid:19)(cid:19) |     |     |
| --- | --- | --- | ---------------- | ---------------- | --- | --- |
(cid:16)(cid:14)(cid:19)
|     |     | (cid:20)(cid:25) |     | (cid:16)(cid:14)(cid:21) |     |     |
| --- | --- | ---------------- | --- | ------------------------ | --- | --- |
(cid:19)(cid:18)
(cid:17)(cid:18)(cid:14)(cid:23)
(cid:17)(cid:16)(cid:14)(cid:19)
(cid:17)(cid:16)(cid:14)(cid:19)
(cid:17)(cid:23)
(cid:22)(cid:20)
(cid:17)(cid:14)(cid:18)
|     |     |     | (cid:17) | (cid:17)(cid:22) |     |     |
| --- | --- | --- | -------- | ---------------- | --- | --- |
(cid:23)(cid:14)(cid:24)
(cid:17)(cid:18)(cid:14)(cid:23)
(cid:65)(cid:73)(cid:17)(cid:20)(cid:25)(cid:16)(cid:25)(cid:67)
1. Dimensions are in millimeters.
|     |     | DocID029808 Rev 3 |     |     |     | 203/229 |
| --- | --- | ----------------- | --- | --- | --- | ------- |
225

Package information STM32F722xx STM32F723xx
LQFP64 device marking
The following figure gives an example of topside marking orientation versus pin 1 identifier
location.
Other optional marking or inset/upset marks, which identify the parts throughout supply
chain operations, are not indicated below.
Figure 81. LQFP64 – 10 x 10 mm, low-profile quad flat package top view example
(cid:51)(cid:85)(cid:82)(cid:71)(cid:88)(cid:70)(cid:87)(cid:3)(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:70)(cid:68)(cid:87)(cid:76)(cid:82)(cid:81)(cid:11)(cid:20)(cid:12) (cid:53)(cid:72)(cid:89)(cid:76)(cid:86)(cid:76)(cid:82)(cid:81)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72)
(cid:53)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:21)
(cid:53)(cid:40)(cid:55)(cid:25)
(cid:39)(cid:68)(cid:87)(cid:72)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72)
(cid:60) (cid:58)(cid:58)
(cid:51)(cid:76)(cid:81)(cid:3)(cid:20)(cid:3)
(cid:76)(cid:81)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:72)(cid:85)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:21)(cid:19)(cid:28)(cid:19)(cid:57)(cid:20)
1. Parts marked as ES or E are not yet qualified and therefore not approved for use in production. ST is not
responsible for any consequences resulting from such use. In no event will ST be liable for the customer
using any of these engineering samples in production. ST’s Quality department must be contacted prior to
any decision to use these engineering samples to run a qualification activity.
204/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
6.2  LQFP100, 14 x 14 mm low-profile quad flat package
information
Figure 82. LQFP100, 14 x 14 mm 100-pin low-profile quad flat package outline
(cid:51)(cid:37)(cid:33)(cid:52)(cid:41)(cid:46)(cid:39)(cid:0)(cid:48)(cid:44)(cid:33)(cid:46)(cid:37)
(cid:35)
(cid:16)(cid:14)(cid:18)(cid:21)(cid:0)(cid:77)(cid:77)
|     | (cid:33) (cid:18)(cid:33) (cid:17)(cid:33) |     |     | (cid:67) |     |     |
| --- | ------------------------------------------ | --- | --- | -------- | --- | --- |
(cid:39)(cid:33)(cid:53)(cid:39)(cid:37)(cid:0)(cid:48)(cid:44)(cid:33)(cid:46)(cid:37)
(cid:67)(cid:67)(cid:67) (cid:35)
|     |     |     | (cid:36) |     | (cid:17)(cid:33) |          |
| --- | --- | --- | -------- | --- | ---------------- | -------- |
|     |     |     |          |     | (cid:44)         | (cid:43) |
(cid:36)(cid:17)
(cid:44)(cid:17)
(cid:36)(cid:19)
|     |     | (cid:23)(cid:21) |     | (cid:21)(cid:17) |     |     |
| --- | --- | ---------------- | --- | ---------------- | --- | --- |
|     |     | (cid:23)(cid:22) |     | (cid:21)(cid:16) |     |     |
(cid:66)
(cid:19)(cid:37) (cid:17)(cid:37) (cid:37)
(cid:17)(cid:16)(cid:16)
(cid:18)(cid:22)
|     | (cid:48)(cid:41)(cid:46)(cid:0)(cid:17) | (cid:17) |     | (cid:18)(cid:21) |     |     |
| --- | --------------------------------------- | -------- | --- | ---------------- | --- | --- |
(cid:41)(cid:36)(cid:37)(cid:46)(cid:52)(cid:41)(cid:38)(cid:41)(cid:35)(cid:33)(cid:52)(cid:41)(cid:47)(cid:46)
|     |     |     |     | (cid:69) |     | (cid:17)(cid:44)(cid:63)(cid:45)(cid:37)(cid:63)(cid:54)(cid:21) |
| --- | --- | --- | --- | -------- | --- | ---------------------------------------------------------------- |
1. Drawing is not to scale.
          Table 117. LQPF100, 14 x 14 mm 100-pin low-profile quad flat package mechanical
data
|     |     | millimeters |     |     | inches(1) |     |
| --- | --- | ----------- | --- | --- | --------- | --- |
Symbol
|     | Min    | Typ               | Max    | Min    | Typ    | Max     |
| --- | ------ | ----------------- | ------ | ------ | ------ | ------- |
| A   | -      | -                 | 1.600  | -      | -      | 0.0630  |
| A1  | 0.050  | -                 | 0.150  | 0.0020 | -      | 0.0059  |
| A2  | 1.350  | 1.400             | 1.450  | 0.0531 | 0.0551 | 0.0571  |
| b   | 0.170  | 0.220             | 0.270  | 0.0067 | 0.0087 | 0.0106  |
| c   | 0.090  | -                 | 0.200  | 0.0035 | -      | 0.0079  |
| D   | 15.800 | 16.000            | 16.200 | 0.6220 | 0.6299 | 0.6378  |
| D1  | 13.800 | 14.000            | 14.200 | 0.5433 | 0.5512 | 0.5591  |
| D3  | -      | 12.000            | -      | -      | 0.4724 | -       |
| E   | 15.800 | 16.000            | 16.200 | 0.6220 | 0.6299 | 0.6378  |
|     |        | DocID029808 Rev 3 |        |        |        | 205/229 |
225

Package information STM32F722xx STM32F723xx
Table 117. LQPF100, 14 x 14 mm 100-pin low-profile quad flat package mechanical
data (continued)
|     |     | millimeters |     |     | inches(1) |     |
| --- | --- | ----------- | --- | --- | --------- | --- |
Symbol
|     | Min    | Typ    | Max    | Min    | Typ    | Max    |
| --- | ------ | ------ | ------ | ------ | ------ | ------ |
| E1  | 13.800 | 14.000 | 14.200 | 0.5433 | 0.5512 | 0.5591 |
| E3  | -      | 12.000 | -      | -      | 0.4724 | -      |
| e   | -      | 0.500  | -      | -      | 0.0197 | -      |
| L   | 0.450  | 0.600  | 0.750  | 0.0177 | 0.0236 | 0.0295 |
| L1  | -      | 1.000  | -      | -      | 0.0394 | -      |
| k   | 0°     | 3.5°   | 7°     | 0°     | 3.5°   | 7°     |
| ccc | -      | -      | 0.080  | -      | -      | 0.0031 |
1. Values in inches are converted from mm and rounded to 4 decimal digits.
Figure 83. LQFP100, 14 x 14 mm, 100-pin low-profile quad flat package
recommended footprint
|     |     | (cid:23)(cid:21) |     | (cid:21)(cid:17) |                  |     |
| --- | --- | ---------------- | --- | ---------------- | ---------------- | --- |
|     |     | (cid:23)(cid:22) |     |                  | (cid:21)(cid:16) |     |
(cid:16)(cid:14)(cid:21)
(cid:16)(cid:14)(cid:19)
(cid:17)(cid:22)(cid:14)(cid:23) (cid:17)(cid:20)(cid:14)(cid:19)
|     |     | (cid:17)(cid:16)(cid:16) |     |     | (cid:18)(cid:22) |     |
| --- | --- | ------------------------ | --- | --- | ---------------- | --- |
(cid:17)(cid:14)(cid:18)
|     |     | (cid:17) |     | (cid:18)(cid:21) |     |     |
| --- | --- | -------- | --- | ---------------- | --- | --- |
(cid:17)(cid:18)(cid:14)(cid:19)
(cid:17)(cid:22)(cid:14)(cid:23)
(cid:65)(cid:73)(cid:17)(cid:20)(cid:25)(cid:16)(cid:22)(cid:67)
1. Dimensions are expressed in millimeters.
206/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
LQFP100 device marking
The following figure gives an example of topside marking orientation versus pin 1 identifier
location.
Other optional marking or inset/upset marks, which identify the parts throughout supply
chain operations, are not indicated below.
Figure 84. LQFP100, 14 x 14 mm, 100-pin low-profile quad flat package
top view example
(cid:51)(cid:85)(cid:82)(cid:71)(cid:88)(cid:70)(cid:87)(cid:3)(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:70)(cid:68)(cid:87)(cid:76)(cid:82)(cid:81)(cid:11)(cid:20)(cid:12)
(cid:52)(cid:53)(cid:46)(cid:20)(cid:19)(cid:39)(cid:24)(cid:19)(cid:19)
(cid:53)(cid:72)(cid:89)(cid:76)(cid:86)(cid:76)(cid:82)(cid:81)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72)
(cid:55)(cid:38)(cid:53)(cid:23) (cid:51)
(cid:39)(cid:68)(cid:87)(cid:72)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72)
(cid:58) (cid:56)(cid:56)
(cid:51)(cid:76)(cid:81)(cid:3)(cid:20)(cid:3)(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:72)(cid:85)
(cid:48)(cid:54)(cid:23)(cid:21)(cid:19)(cid:28)(cid:20)(cid:57)(cid:20)
1. Parts marked as ES or E are not yet qualified and therefore not approved for use in production. ST is not
responsible for any consequences resulting from such use. In no event will ST be liable for the customer
using any of these engineering samples in production. ST’s Quality department must be contacted prior to
any decision to use these engineering samples to run a qualification activity.
DocID029808 Rev 3 207/229
225

Package information STM32F722xx STM32F723xx
6.3  LQFP144, 20 x 20 mm low-profile quad flat package
information
Figure 85. LQFP144, 20 x 20 mm, 144-pin low-profile quad flat package outline
(cid:51)(cid:37)(cid:33)(cid:52)(cid:41)(cid:46)(cid:39)
(cid:48)(cid:44)(cid:33)(cid:46)(cid:37)
(cid:35)
|     | (cid:33) (cid:18)(cid:33) (cid:17)(cid:33) |     |     | (cid:67) |     |     |
| --- | ------------------------------------------ | --- | --- | -------- | --- | --- |
(cid:16)(cid:14)(cid:18)(cid:21)(cid:0)(cid:77)(cid:77)
|     |     | (cid:67)(cid:67)(cid:67) (cid:35) |     |     | (cid:39)(cid:33)(cid:53)(cid:39)(cid:37)(cid:0)(cid:48)(cid:44)(cid:33)(cid:46)(cid:37) |     |
| --- | --- | --------------------------------- | --- | --- | --------------------------------------------------------------------------------------- | --- |
(cid:17)(cid:33)
(cid:36)
|     |     |     |     |     | (cid:44) | (cid:43) |
| --- | --- | --- | --- | --- | -------- | -------- |
(cid:36)(cid:17)
(cid:44)(cid:17)
(cid:36)(cid:19)
|     |     | (cid:17)(cid:16)(cid:24) |     | (cid:23)(cid:19) |     |     |
| --- | --- | ------------------------ | --- | ---------------- | --- | --- |
(cid:17)(cid:16)(cid:25)
(cid:23)(cid:18)
(cid:66)
(cid:19)(cid:37) (cid:17)(cid:37) (cid:37)
(cid:19)(cid:23)
(cid:17)(cid:20)(cid:20)
|     | (cid:48)(cid:41)(cid:46)(cid:0)(cid:17) | (cid:17) |     | (cid:19)(cid:22) |     |     |
| --- | --------------------------------------- | -------- | --- | ---------------- | --- | --- |
(cid:41)(cid:36)(cid:37)(cid:46)(cid:52)(cid:41)(cid:38)(cid:41)(cid:35)(cid:33)(cid:52)(cid:41)(cid:47)(cid:46)
(cid:69)
(cid:17)(cid:33)(cid:63)(cid:45)(cid:37)(cid:63)(cid:54)(cid:19)
1. Drawing is not to scale.
           Table 118. LQFP144, 20 x 20 mm, 144-pin low-profile quad flat package
mechanical data
|     |     | millimeters |     |     | inches(1) |     |
| --- | --- | ----------- | --- | --- | --------- | --- |
Symbol
|     | Min    | Typ    | Max    | Min    | Typ    | Max    |
| --- | ------ | ------ | ------ | ------ | ------ | ------ |
| A   | -      | -      | 1.600  | -      | -      | 0.0630 |
| A1  | 0.050  | -      | 0.150  | 0.0020 | -      | 0.0059 |
| A2  | 1.350  | 1.400  | 1.450  | 0.0531 | 0.0551 | 0.0571 |
| b   | 0.170  | 0.220  | 0.270  | 0.0067 | 0.0087 | 0.0106 |
| c   | 0.090  | -      | 0.200  | 0.0035 | -      | 0.0079 |
| D   | 21.800 | 22.000 | 22.200 | 0.8583 | 0.8661 | 0.874  |
208/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
Table 118. LQFP144, 20 x 20 mm, 144-pin low-profile quad flat package
mechanical data (continued)
|     |     | millimeters |     |     | inches(1) |     |
| --- | --- | ----------- | --- | --- | --------- | --- |
Symbol
|     | Min    | Typ    | Max    | Min    | Typ    | Max    |
| --- | ------ | ------ | ------ | ------ | ------ | ------ |
| D1  | 19.800 | 20.000 | 20.200 | 0.7795 | 0.7874 | 0.7953 |
| D3  | -      | 17.500 | -      | -      | 0.689  | -      |
| E   | 21.800 | 22.000 | 22.200 | 0.8583 | 0.8661 | 0.8740 |
| E1  | 19.800 | 20.000 | 20.200 | 0.7795 | 0.7874 | 0.7953 |
| E3  | -      | 17.500 | -      | -      | 0.6890 | -      |
| e   | -      | 0.500  | -      | -      | 0.0197 | -      |
| L   | 0.450  | 0.600  | 0.750  | 0.0177 | 0.0236 | 0.0295 |
| L1  | -      | 1.000  | -      | -      | 0.0394 | -      |
| k   | 0°     | 3.5°   | 7°     | 0°     | 3.5°   | 7°     |
| ccc | -      | -      | 0.080  | -      | -      | 0.0031 |
1. Values in inches are converted from mm and rounded to 4 decimal digits.
Figure 86. LQFP144, 20 x 20 mm, 144-pin low-profile quad flat package
recommended footprint
(cid:20)(cid:17)(cid:22)(cid:24)
|     | (cid:20)(cid:19)(cid:27) |     |     | (cid:26)(cid:22) |     |     |
| --- | ------------------------ | --- | --- | ---------------- | --- | --- |
|     | (cid:20)(cid:19)(cid:28) |     |     | (cid:26)(cid:21) |     |     |
(cid:19)(cid:17)(cid:22)(cid:24)
(cid:19)(cid:17)(cid:24)
|     |     |     |     | (cid:20)(cid:28)(cid:17)(cid:28) | (cid:20)(cid:26)(cid:17)(cid:27)(cid:24) |     |
| --- | --- | --- | --- | -------------------------------- | ---------------------------------------- | --- |
(cid:21)(cid:21)(cid:17)(cid:25)
|     | (cid:20)(cid:23)(cid:23) |     |     | (cid:22)(cid:26) |     |     |
| --- | ------------------------ | --- | --- | ---------------- | --- | --- |
(cid:20)
(cid:22)(cid:25)
(cid:20)(cid:28)(cid:17)(cid:28)
(cid:21)(cid:21)(cid:17)(cid:25)
(cid:68)(cid:76)(cid:20)(cid:23)(cid:28)(cid:19)(cid:24)(cid:72)
1. Dimensions are expressed in millimeters.
|     |     | DocID029808 Rev 3 |     |     |     | 209/229 |
| --- | --- | ----------------- | --- | --- | --- | ------- |
225

Package information STM32F722xx STM32F723xx
LQP144 device marking
The following figure gives an example of topside marking orientation versus pin 1 identifier
location.
Other optional marking or inset/upset marks, which identify the parts throughout supply
chain operations, are not indicated below.
Figure 87. LQFP144, 20 x 20mm, 144-pin low-profile quad flat package
top view example
(cid:53)(cid:72)(cid:89)(cid:76)(cid:86)(cid:76)(cid:82)(cid:81)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72)
(cid:11)(cid:20)(cid:12)
(cid:51)(cid:85)(cid:82)(cid:71)(cid:88)(cid:70)(cid:87)(cid:3)(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:70)(cid:68)(cid:87)(cid:76)(cid:82)(cid:81) (cid:51)
(cid:52)(cid:53)(cid:46)(cid:20)(cid:19)(cid:39)(cid:24)(cid:19)(cid:19)(cid:59)(cid:38)(cid:53)(cid:23)
(cid:58)(cid:56)(cid:56)
(cid:51)(cid:76)(cid:81)(cid:3)(cid:20) (cid:39)(cid:68)(cid:87)(cid:72)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72)
(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:72)(cid:85)
(cid:48)(cid:54)(cid:23)(cid:21)(cid:19)(cid:28)(cid:21)(cid:57)(cid:20)
1. Parts marked as ES or E are not yet qualified and therefore not approved for use in production. ST is not
responsible for any consequences resulting from such use. In no event will ST be liable for the customer
using any of these engineering samples in production. ST’s Quality department must be contacted prior to
any decision to use these engineering samples to run a qualification activity.
210/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
6.4  LQFP176 24 x 24 mm low-profile quad flat package
information
Figure 88. LQFP176, 24 x 24 mm, 176-pin low-profile quad flat package outline
|     | (cid:35) (cid:51)(cid:69)(cid:65)(cid:84)(cid:73)(cid:78)(cid:71)(cid:0)(cid:80)(cid:76)(cid:65)(cid:78)(cid:69) |     |     |     |     |     |
| --- | ---------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- | --- |
(cid:33)
(cid:67)
|     | (cid:18)(cid:33) | (cid:17)(cid:33) |     |     |     |     |
| --- | ---------------- | ---------------- | --- | --- | --- | --- |
(cid:16)(cid:14)(cid:18)(cid:21)(cid:0)(cid:77)(cid:77)
(cid:71)(cid:65)(cid:85)(cid:71)(cid:69)(cid:0)(cid:80)(cid:76)(cid:65)(cid:78)(cid:69)
(cid:75)
(cid:33)(cid:17)
(cid:44)
|     |     |     | (cid:40)(cid:36) |     | (cid:44)(cid:17) |     |
| --- | --- | --- | ---------------- | --- | ---------------- | --- |
(cid:48)(cid:41)(cid:46)(cid:0)(cid:17)
(cid:36)
(cid:41)(cid:36)(cid:37)(cid:46)(cid:52)(cid:41)(cid:38)(cid:41)(cid:35)(cid:33)(cid:52)(cid:41)(cid:47)(cid:46)
(cid:58)(cid:37)
(cid:37)
(cid:40)(cid:37)
(cid:69)
(cid:58)(cid:36)
(cid:66)
(cid:17)(cid:52)(cid:63)(cid:45)(cid:37)(cid:63)(cid:54)(cid:18)
1. Drawing is not to scale.
           Table 119. LQFP176, 24 x 24 mm, 176-pin low-profile quad flat package
mechanical data
|     |     | millimeters |     |     | inches(1) |     |
| --- | --- | ----------- | --- | --- | --------- | --- |
Symbol
|     | Min    | Typ               | Max    | Min    | Typ | Max     |
| --- | ------ | ----------------- | ------ | ------ | --- | ------- |
| A   | -      | -                 | 1.600  | -      | -   | 0.0630  |
| A1  | 0.050  | -                 | 0.150  | 0.0020 | -   | 0.0059  |
| A2  | 1.350  | -                 | 1.450  | 0.0531 | -   | 0.0060  |
| b   | 0.170  | -                 | 0.270  | 0.0067 | -   | 0.0106  |
| C   | 0.090  | -                 | 0.200  | 0.0035 | -   | 0.0079  |
| D   | 23.900 | -                 | 24.100 | 0.9409 | -   | 0.9488  |
|     |        | DocID029808 Rev 3 |        |        |     | 211/229 |
225

Package information STM32F722xx STM32F723xx
Table 119. LQFP176, 24 x 24 mm, 176-pin low-profile quad flat package
mechanical data (continued)
|     |     | millimeters |     |     | inches(1) |     |
| --- | --- | ----------- | --- | --- | --------- | --- |
Symbol
|     | Min    | Typ   | Max    | Min    | Typ    | Max    |
| --- | ------ | ----- | ------ | ------ | ------ | ------ |
| E   | 23.900 | -     | 24.100 | 0.9409 | -      | 0.9488 |
| e   | -      | 0.500 | -      | -      | 0.0197 | -      |
| HD  | 25.900 | -     | 26.100 | 1.0200 | -      | 1.0276 |
| HE  | 25.900 | -     | 26.100 | 1.0200 | -      | 1.0276 |
| L   | 0.450  | -     | 0.750  | 0.0177 | -      | 0.0295 |
| L1  | -      | 1.000 | -      | -      | 0.0394 | -      |
| ZD  | -      | 1.250 | -      | -      | 0.0492 | -      |
| ZE  | -      | 1.250 | -      | -      | 0.0492 | -      |
| ccc | -      | -     | 0.080  | -      | -      | 0.0031 |
| k   | 0 °    | -     | 7 °    | 0 °    | -      | 7 °    |
1. Values in inches are converted from mm and rounded to 4 decimal digits.
212/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
Figure 89. LQFP176, 24 x 24 mm, 176-pin low-profile quad flat package
recommended footprint
(cid:17)(cid:14)(cid:18)
(cid:17)(cid:23)(cid:22) (cid:17)(cid:19)(cid:19)
(cid:17) (cid:16)(cid:14)(cid:21) (cid:17)(cid:19)(cid:18)
(cid:16)(cid:14)(cid:19)
(cid:20)(cid:20) (cid:24)(cid:25)
(cid:20)(cid:21) (cid:24)(cid:24)
(cid:17)(cid:14)(cid:18)
(cid:18)(cid:17)(cid:14)(cid:24)
(cid:18)(cid:22)(cid:14)(cid:23)
(cid:17)(cid:52)(cid:63)(cid:38)(cid:48)(cid:63)(cid:54)(cid:17)
1. Dimensions are expressed in millimeters.
DocID029808 Rev 3 213/229
225
(cid:23)(cid:14)(cid:22)(cid:18) (cid:24)(cid:14)(cid:17)(cid:18)

Package information STM32F722xx STM32F723xx
LQFP176 device marking
The following figure gives an example of topside marking orientation versus pin 1 identifier
location.
Other optional marking or inset/upset marks, which identify the parts throughout supply
chain operations, are not indicated below.
Figure 90. LQFP176, 24 x 24 mm, 176-pin low-profile quad flat package
top view example
(cid:11)(cid:20)(cid:12)
(cid:51)(cid:85)(cid:82)(cid:71)(cid:88)(cid:70)(cid:87)(cid:3)(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:70)(cid:68)(cid:87)(cid:76)(cid:82)(cid:81)
(cid:52)(cid:53)(cid:46)(cid:20)(cid:19)(cid:39)(cid:24)(cid:19)(cid:19)(cid:42)(cid:38)(cid:53)(cid:23)
(cid:53)(cid:72)(cid:89)(cid:76)(cid:86)(cid:76)(cid:82)(cid:81)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72) (cid:58)(cid:56)(cid:56) (cid:39)(cid:68)(cid:87)(cid:72)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72)
(cid:51)
(cid:51)(cid:76)(cid:81)(cid:3)(cid:20)
(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:72)(cid:85)
(cid:48)(cid:54)(cid:23)(cid:23)(cid:21)(cid:19)(cid:26)(cid:57)(cid:20)
1. Parts marked as ES or E are not yet qualified and therefore not approved for use in production. ST is not
responsible for any consequences resulting from such use. In no event will ST be liable for the customer
using any of these engineering samples in production. ST’s Quality department must be contacted prior to
any decision to use these engineering samples to run a qualification activity.
214/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
6.5  UFBGA144 package information
Figure 91. UFBGA144 - 144-ball, 7 x 7 mm, 0.50 mm pitch, ultra fine pitch ball grid
array package outline
(cid:61) (cid:54)(cid:72)(cid:68)(cid:87)(cid:76)(cid:81)(cid:74)(cid:3)(cid:83)(cid:79)(cid:68)(cid:81)(cid:72)
(cid:71)(cid:71)(cid:71) (cid:61)
| (cid:36)(cid:23) (cid:36)(cid:22) (cid:36)(cid:21) |     |                  | (cid:36)(cid:20) (cid:36)                                      |                                                                |          |     |
| -------------------------------------------------- | --- | ---------------- | -------------------------------------------------------------- | -------------------------------------------------------------- | -------- | --- |
|                                                    |     | (cid:40)(cid:20) |                                                                |                                                                | (cid:59) |     |
|                                                    |     |                  | (cid:36)(cid:20)(cid:3)(cid:69)(cid:68)(cid:79)(cid:79)(cid:3) | (cid:36)(cid:20)(cid:3)(cid:69)(cid:68)(cid:79)(cid:79)(cid:3) |          |     |
(cid:40)
|     |          |          | (cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:72)(cid:85) | (cid:76)(cid:81)(cid:71)(cid:72)(cid:91)(cid:3)(cid:68)(cid:85)(cid:72)(cid:68) |     |     |
| --- | -------- | -------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | --- | --- |
|     | (cid:72) | (cid:41) |                                                                                  |                                                                                 |     |     |
(cid:36)
(cid:41)
|     |     |     | (cid:39)(cid:20) | (cid:39) |     |     |
| --- | --- | --- | ---------------- | -------- | --- | --- |
(cid:72)
(cid:60)
(cid:48)
|     | (cid:20)(cid:21) | (cid:20) |     |     |     |     |
| --- | ---------------- | -------- | --- | --- | --- | --- |
(cid:145)(cid:69)(cid:3)(cid:11)(cid:20)(cid:23)(cid:23)(cid:3)(cid:69)(cid:68)(cid:79)(cid:79)(cid:86)(cid:12)
|     | (cid:37)(cid:50)(cid:55)(cid:55)(cid:50)(cid:48)(cid:3)(cid:57)(cid:44)(cid:40)(cid:58) |     |                                           |                            | (cid:55)(cid:50)(cid:51)(cid:3)(cid:57)(cid:44)(cid:40)(cid:58) |     |
| --- | --------------------------------------------------------------------------------------- | --- | ----------------------------------------- | -------------------------- | --------------------------------------------------------------- | --- |
|     |                                                                                         |     | (cid:145)(cid:72)(cid:72)(cid:72)(cid:48) | (cid:61) (cid:60) (cid:59) |                                                                 |     |
(cid:145)(cid:73)(cid:73)(cid:73) (cid:48) (cid:61)
(cid:36)(cid:19)(cid:36)(cid:54)(cid:66)(cid:48)(cid:40)(cid:66)(cid:57)(cid:21)
1. Drawing is not to scale.
           Table 120. UFBGA144 - 144-ball, 7 x 7 mm, 0.50 mm pitch, ultra fine pitch ball grid
array package mechanical data
|     |     | millimeters |     |     | inches(1) |     |
| --- | --- | ----------- | --- | --- | --------- | --- |
Symbol
|     | Min.   | Typ.              | Max.   | Min.    | Typ.    | Max.    |
| --- | ------ | ----------------- | ------ | ------- | ------- | ------- |
| A   | 0.460  | 0.530             | 0.600  | 0.0181  | 0.0209  | 0.0236  |
| A1  | 0.050  | 0.080             | 0.110  | 0.0020  | 0.0031  | 0.0043  |
| A2  | 0.400  | 0.450             | 0.500  | 0.0157  | 0.0177  | 0.0197  |
| A3  | -      | 0.130             | -      | -       | 0.0051  | -       |
| A4  | 0.270  | 0.320             | 0.370  | 0.0106  | 0.0126  | 0.0146  |
| b   | 0.230  | 0.280             | 0.320  | 0.0091  | 0.0110  | 0.0126  |
| D   | 6.950  | 7.000             | 7.050  | 0.2736  | 0.2756  | 0.2776  |
| D1  | 5.450  | 5.500             | 5.550  | 0.2146  | 0.2165  | 0.2185  |
| E   | 6.950  | 7.000             | 7.050  | 0.2736  | 0.2756  | 0.2776  |
| E1  | 5.450  | 5.500             | 5.550  | 0.2146  | 0.2165  | 0.2185  |
| e   |  -     | 0.500             | -      | -       | 0.0197  | -       |
| F   | 0.700  | 0.750             | 0.800  | 0.0276  | 0.0295  | 0.0315  |
|     |        | DocID029808 Rev 3 |        |         |         | 215/229 |
225

Package information STM32F722xx STM32F723xx
Table 120. UFBGA144 - 144-ball, 7 x 7 mm, 0.50 mm pitch, ultra fine pitch ball grid
array package mechanical data (continued)
|     |     | millimeters |     |     | inches(1) |     |
| --- | --- | ----------- | --- | --- | --------- | --- |
Symbol
|      | Min. | Typ. | Max.    | Min. | Typ. | Max.    |
| ---- | ---- | ---- | ------- | ---- | ---- | ------- |
| ddd  | -    | -    |  0.100  | -    | -    |  0.0039 |
| eee  | -    | -    | 0.150   | -    | -    | 0.0059  |
| fff  | -    | -    | 0.050   | -    | -    | 0.0020  |
1. Values in inches are converted from mm and rounded to 4 decimal digits.
Figure 92. UFBGA144 - 144-ball, 7 x 7 mm, 0.50 mm pitch, ultra fine pitch ball grid
array package recommended footprint
(cid:39)(cid:83)(cid:68)(cid:71)
(cid:39)(cid:86)(cid:80)
(cid:4)(cid:1004)(cid:4)(cid:94)(cid:890)(cid:38)(cid:87)(cid:890)(cid:115)(cid:1005)
           Table 121. UFBGA144 recommended PCB design rules (0.50 mm pitch BGA)
|       | Dimension |     |          | Recommended values |     |     |
| ----- | --------- | --- | -------- | ------------------ | --- | --- |
| Pitch |           |     | 0.50 mm  |                    |     |     |
| Dpad  |           |     | 0.280 mm |                    |     |     |
0.370 mm typ. (depends on the soldermask
Dsm
registration tolerance)
| Stencil opening   |     |     | 0.280 mm                      |     |     |     |
| ----------------- | --- | --- | ----------------------------- | --- | --- | --- |
| Stencil thickness |     |     | Between 0.100 mm and 0.125 mm |     |     |     |
| Pad trace width   |     |     | 0.120 mm                      |     |     |     |
216/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
UFBGA144 device marking
The following figure gives an example of topside marking orientation versus ball A1 identifier
location.
Other optional marking or inset/upset marks, which identify the parts throughout supply
chain operations, are not indicated below.
Figure 93. UFBGA144- 144-ball, 7 x 7 mm, 0.50 mm pitch
package top view example
(cid:52)(cid:53)(cid:46)(cid:20)(cid:19)(cid:39)
(cid:51)(cid:85)(cid:82)(cid:71)(cid:88)(cid:70)(cid:87)(cid:3)
(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:70)(cid:68)(cid:87)(cid:76)(cid:82)(cid:81)(cid:11)(cid:20)(cid:12)
(cid:24)(cid:19)(cid:20)(cid:59)(cid:38)(cid:42)(cid:23)
(cid:39)(cid:68)(cid:87)(cid:72)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72)
(cid:54)(cid:87)(cid:68)(cid:81)(cid:71)(cid:68)(cid:85)(cid:71)(cid:3)(cid:54)(cid:55)(cid:3)(cid:79)(cid:82)(cid:74)(cid:82) (cid:58) (cid:56)(cid:56)
(cid:53)(cid:72)(cid:89)(cid:76)(cid:86)(cid:76)(cid:82)(cid:81)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72)
(cid:37)(cid:68)(cid:79)(cid:79)(cid:3)(cid:20)(cid:3)(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:72)(cid:85)
(cid:51)
(cid:48)(cid:54)(cid:23)(cid:23)(cid:21)(cid:24)(cid:20)(cid:57)(cid:20)
1. Parts marked as ES or E are not yet qualified and therefore not approved for use in production. ST is not
responsible for any consequences resulting from such use. In no event will ST be liable for the customer
using any of these engineering samples in production. ST’s Quality department must be contacted prior to
any decision to use these engineering samples to run a qualification activity.
DocID029808 Rev 3 217/229
225

Package information STM32F722xx STM32F723xx
6.6  UFBGA176+25, 10 x 10, 0.65 mm ultra thin-pitch ball grid
array package information
Figure 94. UFBGA176+25, 10 × 10 × 0.65 mm ultra thin fine-pitch ball grid array
package outline
(cid:38) (cid:94)(cid:286)(cid:258)(cid:410)(cid:349)(cid:374)(cid:336)(cid:3)(cid:393)(cid:367)(cid:258)(cid:374)(cid:286)
| (cid:4)(cid:1006) | (cid:4)(cid:1008) |     | (cid:282)(cid:282)(cid:282) | (cid:18) |     |     |
| ----------------- | ----------------- | --- | --------------------------- | -------- | --- | --- |
(cid:4)
|     |     | (cid:271) | (cid:4)(cid:1005) |     |     |     |
| --- | --- | --------- | ----------------- | --- | --- | --- |
(cid:36)(cid:20)(cid:3)(cid:69)(cid:68)(cid:79)(cid:79)(cid:3)
(cid:36)
|     |     |     | (cid:36)(cid:20)(cid:3)(cid:69)(cid:68)(cid:79)(cid:79)(cid:3) | (cid:76)(cid:81)(cid:71)(cid:72)(cid:91)(cid:3) | (cid:28) |     |
| --- | --- | --- | -------------------------------------------------------------- | ----------------------------------------------- | -------- | --- |
(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:72)(cid:85) (cid:68)(cid:85)(cid:72)(cid:68)
|     | (cid:286) |     | (cid:38) |     |     |     |
| --- | --------- | --- | -------- | --- | --- | --- |
(cid:4)
(cid:38)
(cid:24)
(cid:286)
(cid:17)
(cid:90)
|     | (cid:1005)(cid:1009) |     | (cid:1005) |     |     |     |
| --- | -------------------- | --- | ---------- | --- | --- | --- |
(cid:145)(cid:69)(cid:3)(cid:11)(cid:20)(cid:26)(cid:25)(cid:3)(cid:14)(cid:3)(cid:21)(cid:24)(cid:3)(cid:3)(cid:69)(cid:68)(cid:79)(cid:79)(cid:86)(cid:12)
|     | (cid:17)(cid:75)(cid:100)(cid:100)(cid:75)(cid:68)(cid:3)(cid:115)(cid:47)(cid:28)(cid:116) |     |                                                    |                   | (cid:100)(cid:75)(cid:87)(cid:3)(cid:115)(cid:47)(cid:28)(cid:116) |     |
| --- | ------------------------------------------------------------------------------------------- | --- | -------------------------------------------------- | ----------------- | ------------------------------------------------------------------ | --- |
|     |                                                                                             |     | (cid:145)(cid:72)(cid:72)(cid:72)(cid:48) (cid:38) | (cid:36) (cid:17) |                                                                    |     |
(cid:145)(cid:73)(cid:73)(cid:73) (cid:48) (cid:38)
(cid:4)(cid:1004)(cid:28)(cid:1011)(cid:890)(cid:68)(cid:28)(cid:890)(cid:115)(cid:1010)
1. Drawing is not to scale.
           Table 122. UFBGA176+25, 10 × 10 × 0.65 mm ultra thin fine-pitch ball grid array
package mechanical data
inches(1)
millimeters
Symbol
|     | Min   | Typ    | Max    | Min    | Typ    | Max    |
| --- | ----- | ------ | ------ | ------ | ------ | ------ |
| A   | 0.460 | 0.530  | 0.600  | 0.0181 | 0.0209 | 0.0236 |
| A1  | 0.050 | 0.080  | 0.110  | 0.002  | 0.0031 | 0.0043 |
| A2  | 0.400 | 0.450  | 0.500  | 0.0157 | 0.0177 | 0.0197 |
| b   | 0.230 | 0.280  | 0.330  | 0.0091 | 0.0110 | 0.0130 |
| D   | 9.950 | 10.000 | 10.050 | 0.3917 | 0.3937 | 0.3957 |
| E   | 9.950 | 10.000 | 10.050 | 0.3917 | 0.3937 | 0.3957 |
| e   | -     | 0.650  | -      | -      | 0.0256 | -      |
| F   | 0.400 | 0.450  | 0.500  | 0.0157 | 0.0177 | 0.0197 |
| ddd | -     | -      | 0.080  | -      | -      | 0.0031 |
| eee | -     | -      | 0.150  | -      | -      | 0.0059 |
| fff | -     | -      | 0.080  | -      | -      | 0.0031 |
1. Values in inches are converted from mm and rounded to 4 decimal digits.
218/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
Figure 95. UFBGA176+25, 10 x 10 mm x 0.65 mm, ultra fine-pitch ball grid array
package recommended footprint
(cid:39)(cid:83)(cid:68)(cid:71)
(cid:39)(cid:86)(cid:80)
(cid:4)(cid:1004)(cid:28)(cid:1011)(cid:890)(cid:38)(cid:87)(cid:890)(cid:115)(cid:1005)
Table 123. UFBGA176+25 recommended PCB design rules (0.65 mm pitch BGA)
Dimension Recommended values
Pitch 0.65 mm
Dpad 0.300 mm
0.400 mm typ. (depends on the soldermask reg-
Dsm
istration tolerance)
Stencil opening 0.300 mm
Stencil thickness Between 0.100 mm and 0.125 mm
Pad trace width 0.100 mm
DocID029808 Rev 3 219/229
225

Package information STM32F722xx STM32F723xx
UFBGA176+25 device marking
The following figure gives an example of topside marking orientation versus ball A1 identifier
location.
Other optional marking or inset/upset marks, which identify the parts throughout supply
chain operations, are not indicated below.
Figure 96. UFBGA176+25, 10 × 10 × 0.6 mm ultra thin fine-pitch ball grid array
package top view example
(cid:53)(cid:72)(cid:89)(cid:76)(cid:86)(cid:76)(cid:82)(cid:81)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72)
(cid:51)(cid:85)(cid:82)(cid:71)(cid:88)(cid:70)(cid:87)(cid:3)(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:70)(cid:68)(cid:87)(cid:76)(cid:82)(cid:81)(cid:11)(cid:20)(cid:12)
(cid:53)
(cid:54)(cid:55)(cid:48)(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:21)
(cid:44)(cid:40)(cid:46)(cid:25)
(cid:39)(cid:68)(cid:87)(cid:72)(cid:3)(cid:70)(cid:82)(cid:71)(cid:72)
(cid:37)(cid:68)(cid:79)(cid:79)(cid:3)(cid:36)(cid:20)(cid:3)
(cid:60) (cid:58)(cid:58)
(cid:76)(cid:81)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:72)(cid:85)
(cid:48)(cid:54)(cid:23)(cid:23)(cid:21)(cid:19)(cid:27)(cid:57)(cid:20)
1. Parts marked as ES or E are not yet qualified and therefore not approved for use in production. ST is not
responsible for any consequences resulting from such use. In no event will ST be liable for the customer
using any of these engineering samples in production. ST’s Quality department must be contacted prior to
any decision to use these engineering samples to run a qualification activity.
220/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
6.7 WLCSP100 - 0.4 mm pitch wafer level chip scale package
information
Figure 97.WLCSP100 – 100L, 4.166 x 4.628 mm 0.4 mm pitch wafer level chip scale
package outline
(cid:36)(cid:20)(cid:3)(cid:37)(cid:36)(cid:47)(cid:47)(cid:3)(cid:47)(cid:50)(cid:38)(cid:36)(cid:55)(cid:44)(cid:50)(cid:49)
(cid:36)
(cid:39)(cid:40)(cid:55)(cid:36)(cid:44)(cid:47)(cid:3)(cid:36)
(cid:46)
(cid:37)(cid:50)(cid:55)(cid:55)(cid:50)(cid:48)(cid:3)(cid:57)(cid:44)(cid:40)(cid:58)
(cid:54)(cid:44)(cid:39)(cid:40)(cid:3)(cid:57)(cid:44)(cid:40)(cid:58)
(cid:41)(cid:53)(cid:50)(cid:49)(cid:55)(cid:3)(cid:57)(cid:44)(cid:40)(cid:58)
(cid:39)(cid:40)(cid:55)(cid:36)(cid:44)(cid:47)(cid:3)(cid:36)
(cid:53)(cid:50)(cid:55)(cid:36)(cid:55)(cid:40)(cid:39)(cid:3)(cid:28)(cid:19)(cid:131)
(cid:36)(cid:20)(cid:3)(cid:50)(cid:53)(cid:44)(cid:40)(cid:49)(cid:55)(cid:36)(cid:55)(cid:44)(cid:50)(cid:49)(cid:3)
(cid:53)(cid:40)(cid:41)(cid:40)(cid:53)(cid:40)(cid:49)(cid:38)(cid:40)
(cid:68)(cid:68)(cid:68)
(cid:11)(cid:23)(cid:59)(cid:12)
(cid:55)(cid:50)(cid:51)(cid:3)(cid:57)(cid:44)(cid:40)(cid:58)
(cid:58)(cid:36)(cid:41)(cid:40)(cid:53)(cid:3)(cid:37)(cid:36)(cid:38)(cid:46)(cid:3)(cid:54)(cid:44)(cid:39)(cid:40)
(cid:58)(cid:47)(cid:38)(cid:54)(cid:51)(cid:20)(cid:19)(cid:19)(cid:47)(cid:66)(cid:36)(cid:19)(cid:20)(cid:52)(cid:66)(cid:48)(cid:40)(cid:66)(cid:57)(cid:20)
1. Drawing is not to scale.
DocID029808 Rev 3 221/229
225

Package information STM32F722xx STM32F723xx
          Table 124. WLCSP100 – 100L, 4.166 x 4.628 mm 0.4 mm pitch wafer level chip scale
package mechanical data
inches(1)
millimeters
Symbol
|     | Min   | Typ   | Max   | Typ    | Min    | Max    |
| --- | ----- | ----- | ----- | ------ | ------ | ------ |
| A   | 0.525 | 0.555 | 0.585 | 0.0207 | 0.0219 | 0.0230 |
| A1  | -     | 0.17  | -     | -      | 0.0067 | -      |
| A2  | -     | 0.38  | -     | -      | 0.0150 | -      |
A3(2)
|        | -     | 0.025  | -     | -   | 0.0010 | -      |
| ------ | ----- | ------ | ----- | --- | ------ | ------ |
| Ø b(3) | 0.22  | 0.25   | 0.28  | -   | 0.0098 | 0.0110 |
| D      | 4.166 | 4.201  | 4.236 | -   | 0.1654 | 0.1668 |
| E      | 4.628 | 4.663  | 4.698 | -   | 0.1836 | 0.1850 |
| e      | -     | 0.4    | -     | -   | 0.0157 | -      |
| e1     | -     | 3.6    | -     | -   | 0.1417 | -      |
| e2     | -     | 3.6    | -     | -   | 0.1417 | -      |
| F      | -     | 0.3005 | -     | -   | 0.0118 | -      |
| G      | -     | 0.5315 | -     | -   | 0.0209 | -      |
| N      | -     | 100    | -     | -   | 3.9370 | -      |
| aaa    | -     | 0.1    | -     | -   | 0.0039 | -      |
| bbb    | -     | 0.1    | -     | -   | 0.0039 | -      |
| ccc    | -     | 0.1    | -     | -   | 0.0039 | -      |
| ddd    | -     | 0.05   | -     | -   | 0.0020 | -      |
| eee    | -     | 0.05   | -     | -   | 0.0020 | -      |
1. Values in inches are converted from mm and rounded to 4 decimal digits.
2. Back side coating.
3. Dimension is measured at the maximum bump diameter parallel to primary datum Z.
222/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
Figure 98. WLCSP100 – 100L, 4.166 x 4.628 mm 0.4 mm pitch wafer level chip scale
package recommended footprint
(cid:39)(cid:83)(cid:68)(cid:71)
(cid:39)(cid:86)(cid:80)
(cid:58)(cid:47)(cid:38)(cid:54)(cid:51)(cid:20)(cid:19)(cid:19)(cid:47)(cid:66)(cid:36)(cid:19)(cid:20)(cid:52)(cid:66)(cid:41)(cid:51)(cid:66)(cid:57)(cid:20)
Table 125. WLCSP100 recommended PCB design rules (0.4 mm pitch)
Dimension Recommended values
Pitch 0.4 mm
Dpad 0.225 mm
Dsm 0.290 mm
Stencil thickness 0.1 mm
DocID029808 Rev 3 223/229
225

Package information STM32F722xx STM32F723xx
WLCSP100 device marking
The following figure gives an example of topside marking orientation versus ball A1 identifier
location.
Other optional marking or inset/upset marks, which identify the parts throughout supply
chain operations, are not indicated below.
Figure 99. WLCSP100 – 100L, 4.166 x 4.628 mm 0.4 mm pitch
top view example
(cid:37)(cid:68)(cid:79)(cid:79)(cid:3)(cid:36)(cid:20)(cid:3)(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:72)(cid:85)
(cid:51)(cid:85)(cid:82)(cid:71)(cid:88)(cid:70)(cid:87)(cid:3)(cid:76)(cid:71)(cid:72)(cid:81)(cid:87)(cid:76)(cid:73)(cid:76)(cid:70)(cid:68)(cid:87)(cid:76)(cid:82)(cid:81)(cid:11)(cid:20)(cid:12)
(cid:22)(cid:21)(cid:41)(cid:26)(cid:21)(cid:22)(cid:57)(cid:40)(cid:60)(cid:25)
(cid:90)(cid:286)(cid:448)(cid:349)(cid:400)(cid:349)(cid:381)(cid:374)(cid:3)(cid:272)(cid:381)(cid:282)(cid:286)
(cid:60) (cid:58)(cid:58) (cid:53)
(cid:48)(cid:54)(cid:89)(cid:23)(cid:23)(cid:21)(cid:19)(cid:28)(cid:57)(cid:20)
1. Parts marked as ES or E are not yet qualified and therefore not approved for use in production. ST is not
responsible for any consequences resulting from such use. In no event will ST be liable for the customer
using any of these engineering samples in production. ST’s Quality department must be contacted prior to
any decision to use these engineering samples to run a qualification activity.
224/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Package information
6.8  Thermal characteristics
The maximum chip-junction temperature, T  max, in degrees Celsius, may be calculated
J
using the following equation:
 max x Θ
| T  max = T |  max + (P |     |     | )   |     |     |     |     |
| ---------- | --------- | --- | --- | --- | --- | --- | --- | --- |
| J          | A         | D   |     | JA  |     |     |     |     |
Where:
• T  max is the maximum ambient temperature in °C,
A
• Θ  is the package junction-to-ambient thermal resistance, in °C/W,
JA
• P  max is the sum of P  max and P max (P  max = P  max + P max),
| D   |     |     | INT | I/O  | D   | INT | I/O |     |
| --- | --- | --- | --- | ---- | --- | --- | --- | --- |
• P  max is the product of I andV , expressed in Watts. This is the maximum chip
| INT |     |     |     | DD    DD |     |     |     |     |
| --- | --- | --- | --- | -------- | --- | --- | --- | --- |
internal power.
P  max represents the maximum power dissipation on output pins where:
I/O
| P   |  max = Σ (V |  × I | ) + Σ((V | – V    | ) × I ), |     |     |     |
| --- | ----------- | ---- | -------- | ------ | -------- | --- | --- | --- |
| I/O |             | OL   | OL       | DD  OH | OH       |     |     |     |
taking into account the actual V  / I  and V  / I OH of the I/Os at low and high level in the
|     |     |     | OL  | OL  | OH  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
application.
|            |     | Table 126. Package thermal characteristics  |           |     |     |       |     |      |
| ---------- | --- | ------------------------------------------- | --------- | --- | --- | ----- | --- | ---- |
| Symbol     |     |                                             | Parameter |     |     | Value |     | Unit |
Thermal resistance junction-ambient
22.7
LQFP64 - 10 × 10 mm / 0.5 mm pitch
Thermal resistance junction-ambient
17.9
LQFP100 - 14× 14 mm / 0.5 mm pitch
Thermal resistance junction-ambient
35.85
WLCSP100 - 0.4 mm pitch
Thermal resistance junction-ambient
Θ
| JA  |     |     |     |     |     | 12.6 |     | °C/W |
| --- | --- | --- | --- | --- | --- | ---- | --- | ---- |
LQFP144 - 20 × 20 mm / 0.5 mm pitch
Thermal resistance junction-ambient
10.7
LQFP176 - 24 × 24 mm / 0.5 mm pitch
Thermal resistance junction-ambient
42
UFBGA144 - 7 × 7 mm / 0.5 mm pitch
Thermal resistance junction-ambient
41.2
UFBGA176 - 10× 10 mm / 0.5 mm pitch
Reference document
JESD51-2 Integrated Circuits Thermal Test Method Environment Conditions - Natural
Convection (Still Air). Available from www.jedec.org.
|     |     |     | DocID029808 Rev 3 |     |     |     |     | 225/229 |
| --- | --- | --- | ----------------- | --- | --- | --- | --- | ------- |
225

Ordering information STM32F722xx STM32F723xx
7 Ordering information
Table 127. Ordering information scheme
Example: STM32 F 722 V C T 6 xxx
Device family
STM32 = ARM-based 32-bit microcontroller
Product type
F = general-purpose
Device subfamily
722 = STM32F722xx, no OTG PHY HS
723 = STM32F723xx, with OTG PHY HS
Pin count
R = 64 pins
V = 100 pins
Z = 144 pins
I = 176 pins
Flash memory size
C = 256 Kbytes of Flash memory
E = 512 Kbytes of Flash memory
Package
T = LQFP
K = UFBGA (10 x 10 mm)
I = UFBGA (7 x 7 mm)
Y = WLCSP
Temperature range
6 = Industrial temperature range, –40 to 85 °C.
7 = Industrial temperature range, –40 to 105 °C.
Options
xxx = programmed parts
TR = tape and reel
For a list of available options (speed, package, etc.) or for further information on any aspect
of this device, contact the nearest ST sales office.
226/229 DocID029808 Rev 3

STM32F722xx STM32F723xx Recommendations when using internal reset OFF
Appendix A  Recommendations when using internal reset
OFF
When the internal reset is OFF, the following integrated features are no longer supported:
• The integrated power-on reset (POR) / power-down reset (PDR) circuitry is disabled.
• The brownout reset (BOR) circuitry must be disabled.
• The embedded programmable voltage detector (PVD) is disabled.
• V  functionality is no more available and VBAT pin should be connected to V .
| BAT |     |     |     | DD  |
| --- | --- | --- | --- | --- |
• The over-drive mode is not supported.
A.1  Operating conditions
           Table 128. Limitations depending on the operating power supply range
Maximum
Flash
| Operating  |     | memory  | Maximum Flash  |     |
| ---------- | --- | ------- | -------------- | --- |
Possible Flash
| power  | ADC  | access  | memory access  |     |
| ------ | ---- | ------- | -------------- | --- |
I/O operation memory
| supply  | operation | frequency     | frequency with     |            |
| ------- | --------- | ------------- | ------------------ | ---------- |
|         |           |               | wait states (1)(2) | operations |
| range   |           | with no wait  |                    |            |
states
(f )
Flashmax
|     | Conversion  |     | 180 MHz with 8  | 8-bit erase and  |
| --- | ----------- | --- | --------------- | ---------------- |
V  =1.7 to  – No I/O
| DD  | time up to  | 20 MHz | wait states and  | program  |
| --- | ----------- | ------ | ---------------- | -------- |
2.1 V(3) compensation
|     | 1.2 Msps |     | over-drive OFF | operations only |
| --- | -------- | --- | -------------- | --------------- |
1. Applicable only when the code is executed from Flash memory. When the code is executed from RAM, no
wait state is required.
2. Thanks to the ART accelerator on ITCM interface and L1-cache on AXI interface, the number of wait states
given here does not impact the execution speed from the Flash memory since the ART accelerator or L1-
cache allows to achieve a performance equivalent to 0-wait state program execution.
3. V /V  minimum value of 1.7 V, with the use of an external power supply supervisor (refer to
DD DDA
Section 2.15.1: Internal reset ON).
|     |     | DocID029808 Rev 3 |     | 227/229 |
| --- | --- | ----------------- | --- | ------- |
228

Revision history STM32F722xx STM32F723xx
Revision history
Table 129. Document revision history
Date Revision Changes
03-Feb-2017 1 Initial release.
Updated cover with the maximum SPI speed at 54 Mbit/s.
30-Mar-2017 2
Updated Figure 14: STM32F722xx LQFP64 pinout.
Updated Figure 16: STM32F723xx WLCSP100 ballout (with OTG PHY
HS).
Updated note 1 below all the package device markings.
Updated Section 1: Description.
Updated Table 61: I/O current injection susceptibility note by ‘injection
01-Jun-2017 3 is not possible’.
Updated Table 68: ADC characteristics R min at 1.5 Kohm.
ADC
Updated Figure 46: Recommended NRST pin protection note about the
0.1uF capacitor.
Updated Table 79: DAC characteristics R feature.
LOAD
Updated Figure 40: ACCHSI versus temperature.
228/229 DocID029808 Rev 3

STM32F722xx STM32F723xx
IMPORTANT NOTICE – PLEASE READ CAREFULLY
STMicroelectronics NV and its subsidiaries (“ST”) reserve the right to make changes, corrections, enhancements, modifications, and
improvements to ST products and/or to this document at any time without notice. Purchasers should obtain the latest relevant information on
ST products before placing orders. ST products are sold pursuant to ST’s terms and conditions of sale in place at the time of order
acknowledgement.
Purchasers are solely responsible for the choice, selection, and use of ST products and ST assumes no liability for application assistance or
the design of Purchasers’ products.
No license, express or implied, to any intellectual property right is granted by ST herein.
Resale of ST products with provisions different from the information set forth herein shall void any warranty granted by ST for such product.
ST and the ST logo are trademarks of ST. All other product or service names are the property of their respective owners.
Information in this document supersedes and replaces information previously supplied in any prior versions of this document.
© 2017 STMicroelectronics – All rights reserved
DocID029808 Rev 3 229/229
229