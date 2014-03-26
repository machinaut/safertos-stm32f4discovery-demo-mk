FP_FLAGS ?= -mfloat-abi=hard -mfpu=fpv4-sp-d16
PREFIX ?= arm-none-eabi

CC = $(PREFIX)-gcc
CFLAGS = -Os -fno-common -ffunction-sections -fdata-sections \
	-Wall -Wextra -Wimplicit-function-declaration -Wredundant-decls \
	-Wmissing-prototypes -Wstrict-prototypes -Wundef -Wshadow \
	-I../inc -I../../Device/STM32F4xx/Include -I../../CMSIS/Include -MD \
	-mcpu=cortex-m4 -mthumb $(FP_FLAGS) -DSTM32F4 -DUSE_STDPERIPH_DRIVER \
	-Iinclude -I../include -I../kernel_source/include

OBJS =	BlockQ.o \
	PollQ.o \
	blocktim.o \
	comtest.o \
	countsem.o \
	death.o \
	dynamic.o \
	flash.o \
	semtest.o \

%.o: %.c
	$(Q)$(CC) $(CFLAGS) -o $@ -c $<

all: $(OBJS)
