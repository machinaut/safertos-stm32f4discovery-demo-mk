FP_FLAGS ?= -mfloat-abi=hard -mfpu=fpv4-sp-d16
PREFIX ?= arm-none-eabi

CC = $(PREFIX)-gcc
CFLAGS = -Os -fno-common -ffunction-sections -fdata-sections \
	-Wall -Wextra -Wimplicit-function-declaration -Wredundant-decls \
	-Wmissing-prototypes -Wstrict-prototypes -Wundef -Wshadow \
	-I../Libraries/Device/STM32F4xx/Include -I../Libraries/CMSIS/Include -MD \
	-mcpu=cortex-m4 -mthumb $(FP_FLAGS) -DSTM32F4 -DUSE_STDPERIPH_DRIVER \
	-I../common/include -I../include -I../kernel_source/include \
	-I../Libraries/STM32F4xx_StdPeriph_Driver/inc
LDFLAGS =

OBJS =	FullDemo.o \
	MathsTest.o \
	ParTest.o \
	PortSpecifics.o \
	SafeRTOSConfig.o \
	main.o \
	stm32f4xx_it.o \
	system_stm32f4xx.o

startup_stm32f4xx.o: startup_stm32f4xx.s
	$(Q)$(CC) $(CFLAGS) $(LDFLAGS) -o $@ -c $<

%.o: %.c
	$(Q)$(CC) $(CFLAGS) -o $@ -c $<

all: $(OBJS) startup_stm32f4xx.o

