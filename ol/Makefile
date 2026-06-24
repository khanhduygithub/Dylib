
export THEOS = $(HOME)/theos
export THEOS_MAKE_PATH = $(THEOS)/makefiles
export SDKVERSION = 16.5
export IPHONEOS_DEPLOYMENT_TARGET = 13.0
export TARGET = iphone:clang:16.5:13.0

ARCHS = arm64
DEBUG = 0
FINALPACKAGE = 1
FOR_RELEASE = 1
THEOS_PACKAGE_SCHEME = rootless

include $(THEOS_MAKE_PATH)/common.mk

TWEAK_NAME = 34306jit

$(TWEAK_NAME)_CCFLAGS = -std=c++17 -fobjc-arc -Wno-deprecated -Wno-error -Wno-unused-variable -Wno-unused-function
$(TWEAK_NAME)_CFLAGS = -fobjc-arc -Wno-deprecated -Wno-error -Wno-unused-variable -Wno-unused-function

$(TWEAK_NAME)_FRAMEWORKS = UIKit Foundation Metal MetalKit QuartzCore CoreGraphics Security

$(TWEAK_NAME)_FILES = ImGuiDrawView.mm \
                      oxorany/oxorany.cpp \
                      $(wildcard Esp/*.mm) \
                      $(wildcard Esp/*.m) \
                      $(wildcard IMGUI/*.cpp) \
                      $(wildcard IMGUI/*.mm)

$(TWEAK_NAME)_CFLAGS += -I. -I./Helper -I./IMGUI -I./Esp -I./Hosts -I./oxorany

include $(THEOS_MAKE_PATH)/tweak.mk
