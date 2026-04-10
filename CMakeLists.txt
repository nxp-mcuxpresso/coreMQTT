#
# Copyright 2024-2026 NXP
#
# SPDX-License-Identifier: BSD-3-Clause
#

if (CONFIG_MCUX_COMPONENT_middleware.freertos.coremqtt.template)
    # Template/config header is kept in this NXP integration repo.
    mcux_add_source(
        SOURCES template/core_mqtt_config.h
    )
    mcux_add_include(
        TARGET_FILES ['core_mqtt_config.h'],
        INCLUDES template
    )
endif()

if (CONFIG_MCUX_COMPONENT_middleware.freertos.coremqtt)
    mcux_add_source(
        SOURCES ../coremqtt-upstream/source/core_mqtt.c
                ../coremqtt-upstream/source/core_mqtt_serializer.c
                ../coremqtt-upstream/source/core_mqtt_state.c
                ../coremqtt-upstream/source/include/core_mqtt.h
                ../coremqtt-upstream/source/include/core_mqtt_config_defaults.h
                ../coremqtt-upstream/source/include/core_mqtt_serializer.h
                ../coremqtt-upstream/source/include/core_mqtt_state.h
                ../coremqtt-upstream/source/interface/transport_interface.h
    )
    mcux_add_include(
        INCLUDES ../coremqtt-upstream/source/include
                 ../coremqtt-upstream/source/interface
    )
endif()
