#
# Copyright 2024 NXP
#
# SPDX-License-Identifier: MIT
#

if (CONFIG_MCUX_COMPONENT_middleware.freertos.coremqtt.template)
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
        SOURCES source/core_mqtt.c source/core_mqtt_serializer.c source/core_mqtt_state.c source/include/core_mqtt.h source/include/core_mqtt_config_defaults.h source/include/core_mqtt_default_logging.h source/include/core_mqtt_serializer.h source/include/core_mqtt_state.h source/interface/transport_interface.h
    )
    mcux_add_include(
        INCLUDES source/include source/interface
    )
endif()
