#
# (C) Copyright 2000-2003
# Wolfgang Denk, DENX Software Engineering, wd@denx.de.
#
# SPDX-License-Identifier:	GPL-2.0+
#

extra-y	:= start.o

obj-y	+= cpu.o
ifndef CONFIG_$(SPL_TPL_)TIMER
obj-y	+= generic_timer.o
endif
obj-y	+= cache_v8.o
obj-y	+= exceptions.o
obj-y	+= cache.o
obj-y	+= tlb.o
obj-y	+= transition.o
obj-y	+= fwcall.o
obj-y	+= cpu-dt.o

obj-$(CONFIG_ARM_SMCCC)		+= smccc-call.o

ifeq ($(CONFIG_SPL_BUILD)$(CONFIG_TPL_BUILD),)
obj-$(CONFIG_ARM_CPU_SUSPEND)	+= ../armv7/suspend.o sleep.o
endif

ifndef CONFIG_SPL_BUILD
obj-$(CONFIG_ARMV8_SPIN_TABLE) += spin_table.o spin_table_v8.o
endif
obj-$(CONFIG_$(SPL_)ARMV8_SEC_FIRMWARE_SUPPORT) += sec_firmware.o sec_firmware_asm.o

obj-$(CONFIG_FSL_LAYERSCAPE) += fsl-layerscape/
obj-$(CONFIG_S32V234) += s32v234/
obj-$(CONFIG_ARCH_ZYNQMP) += zynqmp/
obj-$(CONFIG_TARGET_HIKEY) += hisilicon/
obj-$(CONFIG_ARMV8_PSCI) += psci.o
obj-$(CONFIG_ARCH_SUNXI) += lowlevel_init.o
obj-$(CONFIG_ARMV8_CE_SHA1) += sha1_ce_glue.o sha1_ce_core.o
obj-$(CONFIG_ARMV8_CE_SHA256) += sha256_ce_glue.o sha256_ce_core.o
