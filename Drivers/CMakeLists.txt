cmake_minimum_required(VERSION 3.22)

project("STMDriver")

add_library("STM32F7xx" STATIC 
    "STM32F7xx_HAL_Driver/Src/stm32f7xx_ll_utils.c"
    )




target_include_directories("STM32F7xx"
    PUBLIC "CMSIS/Device/ST/STM32F7xx/Include"
    PUBLIC "CMSIS/Include"
    PUBLIC "STM32F7xx_HAL_Driver/Inc"
)