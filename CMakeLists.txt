
# ====================================================================================
cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# ====================================================================================
set(PICO_BOARD pico_w CACHE STRING "Board type")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(led_control_webserver C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(${PROJECT_NAME}
    ${PROJECT_NAME}.c
        lib/ssd1306.c
      
)

pico_set_program_name(${PROJECT_NAME} "led_control_webserver")
pico_set_program_version(${PROJECT_NAME} "0.1")

# Generate PIO header - matriz de led
pico_generate_pio_header(${PROJECT_NAME} ${CMAKE_CURRENT_LIST_DIR}/ws2818b.pio)

# Modify the below lines to enable/disable output over UART/USB
pico_enable_stdio_uart(${PROJECT_NAME} 0)
pico_enable_stdio_usb(${PROJECT_NAME} 1)


# Add the standard library to the build
target_link_libraries(${PROJECT_NAME}
        pico_stdlib
        hardware_gpio
        hardware_adc
        pico_cyw43_arch_lwip_threadsafe_background
        pico_bootsel_via_double_reset # PARA COLOCAR A PLACA NO MODO DE GRAVACAO
pico_bootrom # PARA COLOCAR A PLACA NO MODO DE GRAVACAO
hardware_pio # para matriz de leds
hardware_clocks # para matriz de leds
hardware_pwm
hardware_i2c
 pico_time
 hardware_pio # para matriz de leds
)

# Add the standard include files to the build
target_include_directories(${PROJECT_NAME} PRIVATE
    ${CMAKE_CURRENT_LIST_DIR}
    ${PICO_SDK_PATH}/lib/lwip/src/include
    ${PICO_SDK_PATH}/lib/lwip/src/include/arch
    ${PICO_SDK_PATH}/lib/lwip/src/include/lwip
)

target_sources(${PROJECT_NAME} PRIVATE
    ${PICO_SDK_PATH}/lib/lwip/src/apps/http/httpd.c
    ${PICO_SDK_PATH}/lib/lwip/src/apps/http/fs.c
)


# Add any user requested libraries

pico_add_extra_outputs(${PROJECT_NAME})
