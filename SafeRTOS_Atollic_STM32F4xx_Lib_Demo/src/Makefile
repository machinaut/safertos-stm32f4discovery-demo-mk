# Makefile for building SafeRTOS Demo for STM32F4-Discovery board

all: build

#build: lib kernel common project
build: lib project

lib:
	$(Q)$(MAKE) -C Libraries

common:
	$(Q)$(MAKE) -C common

project:
	$(Q)$(MAKE) -C source
