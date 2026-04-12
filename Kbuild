ifeq ($(DSP_ROOT),)
DSP_ROOT := $(srctree)/techpack/dsp
endif

ifeq ($(CONFIG_ARCH_PINEAPPLE), y)
include $(DSP_ROOT)/config/pineappledsp.conf
LINUXINCLUDE += -include $(DSP_ROOT)/config/pineappledspconf.h
endif

ifeq ($(CONFIG_ARCH_SUN), y)
include $(DSP_ROOT)/config/sundsp.conf
LINUXINCLUDE += -include $(DSP_ROOT)/config/sundspconf.h
endif

ifeq ($(CONFIG_ARCH_NIOBE), y)
include $(DSP_ROOT)/config/niobedsp.conf
LINUXINCLUDE += -include $(DSP_ROOT)/config/niobedspconf.h
endif

ifeq ($(CONFIG_ARCH_PARROT), y)
include $(DSP_ROOT)/config/parrotdsp.conf
LINUXINCLUDE += -include $(DSP_ROOT)/config/parrotdspconf.h
endif

LINUXINCLUDE += -I$(DSP_ROOT)/include/linux
LINUXINCLUDE += -I$(DSP_ROOT)/include/uapi

frpc-adsprpc-y := dsp/fastrpc.o	\
			 dsp/fastrpc_rpmsg.o \

cdsp-loader-y := dsp/cdsp-loader.o

obj-$(CONFIG_QCOM_FASTRPC) := frpc-adsprpc.o cdsp-loader.o

BOARD_VENDOR_KERNEL_MODULES += $(KERNEL_MODULES_OUT)/frpc-adsprpc.ko
#BOARD_VENDOR_KERNEL_MODULES += $(KERNEL_MODULES_OUT)/cdsp-loader.ko
