# SPDX-License-Identifier: GPL-2.0

ifeq ($(CONFIG_BUILD_ARM64_DT_OVERLAY),y)
	dtbo-$(CONFIG_ARCH_SM6150) += \
		sm6150-rumi-overlay.dtbo \
		sm6150-qrd-overlay.dtbo \
		sm6150-idp-overlay.dtbo \
		sm6150p-qrd-overlay.dtbo \
		sm6150p-idp-overlay.dtbo \
		sm6150-external-codec-idp-overlay.dtbo \
		sm6150-usbc-idp-overlay.dtbo \
		sm6150-usbc-minidp-idp-overlay.dtbo \
		sm6150-cmd-mode-display-idp-overlay.dtbo \
		sa6155-adp-star-overlay.dtbo \
		sa6155p-adp-star-overlay.dtbo \
		sa6155-adp-air-overlay.dtbo \
		sa6155p-adp-air-overlay.dtbo \
		sa6155p-v2-adp-star-overlay.dtbo \
		sa6155p-v2-adp-air-overlay.dtbo

sm6150-rumi-overlay.dtbo-base := sm6150.dtb
sm6150-qrd-overlay.dtbo-base := sm6150.dtb
sm6150-idp-overlay.dtbo-base := sm6150.dtb
sm6150p-qrd-overlay.dtbo-base := sm6150p.dtb
sm6150p-idp-overlay.dtbo-base := sm6150p.dtb
sm6150-external-codec-idp-overlay.dtbo-base := sm6150.dtb
sm6150-usbc-idp-overlay.dtbo-base := sm6150.dtb
sm6150-usbc-minidp-idp-overlay.dtbo-base := sm6150.dtb
sm6150-cmd-mode-display-idp-overlay.dtbo-base := sm6150.dtb
sa6155-adp-star-overlay.dtbo-base := sa6155.dtb
sa6155p-adp-star-overlay.dtbo-base := sa6155p.dtb
sa6155p-v2-adp-star-overlay.dtbo-base := sa6155p.dtb
sa6155-adp-air-overlay.dtbo-base := sa6155.dtb
sa6155p-adp-air-overlay.dtbo-base := sa6155p.dtb
sa6155p-v2-adp-air-overlay.dtbo-base := sa6155p.dtb
else
dtb-$(CONFIG_ARCH_SM6150)	+= sm6150-rumi.dtb \
	sm6150-qrd.dtb \
	sm6150-idp.dtb \
	sm6150p-qrd.dtb \
	sm6150p-idp.dtb \
	sm6150-external-codec-idp.dtb \
	sm6150-usbc-idp.dtb \
	sm6150-usbc-minidp-idp.dtb \
	sm6150-cmd-mode-display-idp.dtb \
	sa6155-adp-star.dtb \
	sa6155p-adp-star.dtb \
	sa6155-adp-air.dtb \
	sa6155p-adp-air.dtb \
	sa6155p-v2-adp-star.dtb \
	sa6155p-v2-adp-air.dtb

endif

ifeq ($(CONFIG_BUILD_ARM64_DT_OVERLAY),y)
	dtbo-$(CONFIG_ARCH_SDMMAGPIE) += \
		sdmmagpie-idp-overlay.dtbo \
		sdmmagpie-atp-overlay.dtbo \
		sdmmagpie-rumi-overlay.dtbo \
		sdmmagpie-qrd-overlay.dtbo \
		davinci-sdmmagpie-overlay.dtbo \
		davinci_m0a-sdmmagpie-overlay.dtbo \
		davinci_m0b-sdmmagpie-overlay.dtbo \
		sdmmagpiep-idp-overlay.dtbo \
		sdmmagpiep-atp-overlay.dtbo \
		sdmmagpiep-qrd-overlay.dtbo \
		sdmmagpie-external-codec-idp-overlay.dtbo \
		sdmmagpie-usbc-idp-overlay.dtbo \
		sdmmagpie-dual-display-idp-overlay.dtbo

sdmmagpie-idp-overlay.dtbo-base := sdmmagpie.dtb
sdmmagpie-atp-overlay.dtbo-base := sdmmagpie.dtb
sdmmagpie-rumi-overlay.dtbo-base := sdmmagpie.dtb
sdmmagpie-qrd-overlay.dtbo-base := sdmmagpie.dtb
davinci-sdmmagpie-overlay.dtbo-base := sdmmagpie.dtb
davinci_m0a-sdmmagpie-overlay.dtbo-base := sdmmagpie.dtb
davinci_m0b-sdmmagpie-overlay.dtbo-base := sdmmagpie.dtb
phoenix-sdmmagpie-overlay.dtbo-base := sdmmagpie.dtb
sdmmagpiep-idp-overlay.dtbo-base := sdmmagpiep.dtb
sdmmagpiep-atp-overlay.dtbo-base := sdmmagpiep.dtb
sdmmagpiep-qrd-overlay.dtbo-base := sdmmagpiep.dtb
sdmmagpie-external-codec-idp-overlay.dtbo-base := sdmmagpie.dtb
sdmmagpie-usbc-idp-overlay.dtbo-base := sdmmagpie.dtb
sdmmagpie-dual-display-idp-overlay.dtbo-base := sdmmagpie.dtb
else
dtb-$(CONFIG_ARCH_SDMMAGPIE)	+= sdmmagpie-rumi.dtb \
	sdmmagpie-idp.dtb \
	sdmmagpie-atp.dtb \
	sdmmagpie-qrd.dtb \
	sdmmagpiep-idp.dtb \
	sdmmagpiep-atp.dtb \
	sdmmagpiep-qrd.dtb \
	davinci-sdmmagpie.dtb \
	davinci_m0a-sdmmagpie.dtb \
	davinci_m0b-sdmmagpie.dtb \
	phoenix-sdmmagpie.dtb \
	sdmmagpie-external-codec-idp.dtb \
	sdmmagpie-usbc-idp.dtb \
	sdmmagpie-dual-display-idp.dtb
endif

ifeq ($(CONFIG_ARM64),y)
always		:= $(dtb-y)
subdir-y	:= $(dts-dirs)
else
targets += dtbs
targets += $(addprefix ../, $(dtb-y))

$(obj)/../%.dtb: $(src)/%.dts FORCE
	$(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(dtb-y))
endif
clean-files	:= *.dtb *.dtbo
