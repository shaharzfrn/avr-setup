cmake_minimum_required(VERSION 3.27.1)

##########################################################################
# Setup variables used in the toolchain
##########################################################################



##########################################################################
# tools to beused for programming the AVR
# set all the share variables for all targets (can be override later)
##########################################################################
set(AVR_PROGRAMMER arduino)
set(AVR_UPLOADTOOL_BAUDRATE 57600)
set(AVR_F_CPU 16000000UL) 

#set(AVR_UPLOADTOOL_PORT /dev/cu.usbserial-10)
#set(AVR_MCU atmega328p)

##########################################################################
# Include the base AVR Toolchain, can be blank and using the
# toolchain file via -DCMAKE_TOOLCHAIN_FILE=path/to/avr-gcc.cmake 
# at the cmake command line call
##########################################################################
include(./generic-avr-gcc.cmake)


project(<PROJECT_NAME>)


##########################################################################
# status messages
##########################################################################
message(STATUS "Current uploadtool is: ${AVR_UPLOADTOOL}")
message(STATUS "Current programmer is: ${AVR_PROGRAMMER}")
message(STATUS "Current upload port is: ${AVR_UPLOADTOOL_PORT}")
message(STATUS "Current uploadtool options are: ${AVR_UPLOADTOOL_OPTIONS}")
message(STATUS "Current MCU is set to: ${AVR_MCU}")
message(STATUS "Current H_FUSE is set to: ${AVR_H_FUSE}")
message(STATUS "Current L_FUSE is set to: ${AVR_L_FUSE}")


##########################################################################
# compiler options for all build types
##########################################################################
add_definitions("-DF_CPU=${AVR_F_CPU}")
add_definitions("-Os")
#add_definitions("-fpack-struct")
#add_definitions("-fshort-enums")
#add_definitions("-Wall")
#add_definitions("-Werror")
#add_definitions("-pedantic")
#add_definitions("-pedantic-errors")
#add_definitions("-funsigned-char")
#add_definitions("-funsigned-bitfields")
#add_definitions("-ffunction-sections")
#add_definitions("-c")
#add_definitions("-std=gnu99")

##########################################################################
# add AVR executable
##########################################################################
# add_avr_executable(
#   <executable-name>
#   <sources> <headers>
#)

##########################################################################
# add AVR library
##########################################################################
# add_avr_library(
#    <library-name>
#    <sources> <headers>
# )

##########################################################################
# link library to executable
# NOTE: It needs to be the elf target.
##########################################################################
# target_link_libraries(<executable-name>-${AVR_MCU}.elf <library-name>-${AVR_MCU})
# OR easier
# target_link_libraries(<executable-name> <library-name> <some-external-libary>)



##########################################################################
# include search paths
##########################################################################
# include_directories(<LIB_PATH>)



##########################################################################
# building library and application in their subdirectories
##########################################################################
# add_subdirectory(<PATH_1>)
# add_subdirectory(<PATH_2>)
















