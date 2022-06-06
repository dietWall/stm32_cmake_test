cmake_minimum_required(VERSION 3.22)

set(CMAKE_TRY_COMPILE_TARGET_TYPE "STATIC_LIBRARY")

project("STMDriver")

include_directories(
    "CMSIS/Device/ST/STM32F7xx/Include"
    "CMSIS/Include"
    "STM32F7xx_HAL_Driver/Inc"
)

add_library("STM32F7xx" STATIC 
    "STM32F7xx_HAL_Driver/Src/stm32f7xx_ll_utils.c"
    )

#Temporary definitions usually this should be defined on the project level
target_compile_definitions("STM32F7xx" 
    PUBLIC "STM32F767xx"
    )
