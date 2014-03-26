LIBNAME = stm32f4xx_stdperiph_driver
SRCLIBDIR ?= ../..

FP_FLAGS ?= -mfloat-abi=hard -mfpu=fpv4-sp-d16
PREFIX ?= arm-none-eabi

CC = $(PREFIX)-gcc
CFLAGS = -Os -fno-common -ffunction-sections -fdata-sections \
	-Wall -Wextra -Wimplicit-function-declaration -Wredundant-decls \
	-Wmissing-prototypes -Wstrict-prototypes -Wundef -Wshadow \
	-I../inc -I../../Device/STM32F4xx/Include -I../../CMSIS/Include -MD \
	-mcpu=cortex-m4 -mthumb $(FP_FLAGS) -DSTM32F4 -DUSE_STDPERIPH_DRIVER

OBJS =	misc.o \
	stm32f4xx_adc.o \
	stm32f4xx_can.o \
	stm32f4xx_crc.o \
	stm32f4xx_cryp.o \
	stm32f4xx_cryp_aes.o \
	stm32f4xx_cryp_des.o \
	stm32f4xx_cryp_tdes.o \
	stm32f4xx_dac.o \
	stm32f4xx_dbgmcu.o \
	stm32f4xx_dcmi.o \
	stm32f4xx_dma.o \
	stm32f4xx_exti.o \
	stm32f4xx_flash.o \
	stm32f4xx_fsmc.o \
	stm32f4xx_gpio.o \
	stm32f4xx_hash.o \
	stm32f4xx_hash_md5.o \
	stm32f4xx_hash_sha1.o \
	stm32f4xx_i2c.o \
	stm32f4xx_iwdg.o \
	stm32f4xx_pwr.o \
	stm32f4xx_rcc.o \
	stm32f4xx_rng.o \
	stm32f4xx_rtc.o \
	stm32f4xx_sdio.o \
	stm32f4xx_spi.o \
	stm32f4xx_syscfg.o \
	stm32f4xx_tim.o \
	stm32f4xx_usart.o \
	stm32f4xx_wwdg.o

%.o: %.c
	$(Q)$(CC) $(CFLAGS) -o $@ -c $<

all: $(OBJS)
