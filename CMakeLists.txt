cmake_minimum_required(VERSION 3.22)

set(CMAKE_TRY_COMPILE_TARGET_TYPE "STATIC_LIBRARY")


project("STMExample")

add_subdirectory("Drivers")



add_executable(
    "TIMER_PWM_Example"
    "Src/main.c"
    "Src/stm32f7xx_it.c"
    "Src/system_stm32f7xx.c"
)

#Temporary definitions usually this should be defined on the project level
target_compile_definitions("TIMER_PWM_Example"
    PUBLIC "STM32F767xx"
    )


include_directories( "Drivers/CMSIS/Include")
include_directories( "Drivers/CMSIS/Device/ST/STM32F7xx/Include")
include_directories( "Drivers/STM32F7xx_HAL_Driver/Inc")

target_include_directories("TIMER_PWM_Example" PRIVATE "Inc")

#error:
#/home/gcc-arm-11/gcc-arm-11.2-2022.02-x86_64-arm-none-eabi/bin/../lib/gcc/arm-none-eabi/11.2.1/../../../../arm-none-eabi/bin/ld: cannot find -lSTM32F7xx
target_link_libraries("TIMER_PWM_Example" "libSTM32F7xx.a")

set(CMAKE_C_FLAGS "-mcpu=cortex-m7")

