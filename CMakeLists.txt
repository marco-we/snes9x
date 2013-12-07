CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

PROJECT(snes9x)

#
# SNES9x
#

SET(SNES9X_DIR ${CMAKE_CURRENT_SOURCE_DIR})

SET(BASE_SRC_FILES
    ${SNES9X_DIR}/bsx.cpp
    ${SNES9X_DIR}/c4.cpp
    ${SNES9X_DIR}/c4emu.cpp
    ${SNES9X_DIR}/cheats.cpp
    ${SNES9X_DIR}/cheats2.cpp
    ${SNES9X_DIR}/clip.cpp
    ${SNES9X_DIR}/conffile.cpp
    ${SNES9X_DIR}/controls.cpp
    ${SNES9X_DIR}/cpu.cpp
    ${SNES9X_DIR}/cpuexec.cpp
    ${SNES9X_DIR}/cpuops.cpp
    ${SNES9X_DIR}/crosshairs.cpp
    ${SNES9X_DIR}/debug.cpp
    ${SNES9X_DIR}/dma.cpp
    ${SNES9X_DIR}/dsp.cpp
    ${SNES9X_DIR}/dsp1.cpp
    ${SNES9X_DIR}/dsp2.cpp
    ${SNES9X_DIR}/dsp3.cpp
    ${SNES9X_DIR}/dsp4.cpp
    ${SNES9X_DIR}/fxdbg.cpp
    ${SNES9X_DIR}/fxemu.cpp
    ${SNES9X_DIR}/fxinst.cpp
    ${SNES9X_DIR}/gfx.cpp
    ${SNES9X_DIR}/globals.cpp
    ${SNES9X_DIR}/loadzip.cpp
    ${SNES9X_DIR}/logger.cpp
    ${SNES9X_DIR}/memmap.cpp
    ${SNES9X_DIR}/movie.cpp
    ${SNES9X_DIR}/netplay.cpp
    ${SNES9X_DIR}/obc1.cpp
    ${SNES9X_DIR}/ppu.cpp
    ${SNES9X_DIR}/sa1.cpp
    ${SNES9X_DIR}/sa1cpu.cpp
    ${SNES9X_DIR}/screenshot.cpp
    ${SNES9X_DIR}/sdd1.cpp
    ${SNES9X_DIR}/sdd1emu.cpp
    ${SNES9X_DIR}/server.cpp
    ${SNES9X_DIR}/seta.cpp
    ${SNES9X_DIR}/seta010.cpp
    ${SNES9X_DIR}/seta011.cpp
    ${SNES9X_DIR}/seta018.cpp
    ${SNES9X_DIR}/snapshot.cpp
    ${SNES9X_DIR}/snes9x.cpp
    ${SNES9X_DIR}/spc7110.cpp
    ${SNES9X_DIR}/srtc.cpp
    ${SNES9X_DIR}/statemanager.cpp
    ${SNES9X_DIR}/stream.cpp
    ${SNES9X_DIR}/tile.cpp
    ${SNES9X_DIR}/65c816.h
    ${SNES9X_DIR}/bsx.h
    ${SNES9X_DIR}/c4.h
    ${SNES9X_DIR}/cheats.h
    ${SNES9X_DIR}/conffile.h
    ${SNES9X_DIR}/controls.h
    ${SNES9X_DIR}/cpuaddr.h
    ${SNES9X_DIR}/cpuexec.h
    ${SNES9X_DIR}/cpumacro.h
    ${SNES9X_DIR}/cpuops.h
    ${SNES9X_DIR}/crosshairs.h
    ${SNES9X_DIR}/debug.h
    ${SNES9X_DIR}/display.h
    ${SNES9X_DIR}/dma.h
    ${SNES9X_DIR}/dsp.h
    ${SNES9X_DIR}/font.h
    ${SNES9X_DIR}/fxemu.h
    ${SNES9X_DIR}/fxinst.h
    ${SNES9X_DIR}/getset.h
    ${SNES9X_DIR}/gfx.h
    ${SNES9X_DIR}/language.h
    ${SNES9X_DIR}/logger.h
    ${SNES9X_DIR}/memmap.h
    ${SNES9X_DIR}/messages.h
    ${SNES9X_DIR}/missing.h
    ${SNES9X_DIR}/movie.h
    ${SNES9X_DIR}/netplay.h
    ${SNES9X_DIR}/obc1.h
    ${SNES9X_DIR}/pixform.h
    ${SNES9X_DIR}/port.h
    ${SNES9X_DIR}/ppu.h
    ${SNES9X_DIR}/sa1.h
    ${SNES9X_DIR}/sar.h
    ${SNES9X_DIR}/screenshot.h
    ${SNES9X_DIR}/sdd1.h
    ${SNES9X_DIR}/sdd1emu.h
    ${SNES9X_DIR}/seta.h
    ${SNES9X_DIR}/snapshot.h
    ${SNES9X_DIR}/snes9x.h
    ${SNES9X_DIR}/spc7110.h
    ${SNES9X_DIR}/spc7110dec.h
    ${SNES9X_DIR}/spc7110emu.h
    ${SNES9X_DIR}/srtc.h
    ${SNES9X_DIR}/srtcemu.h
    ${SNES9X_DIR}/statemanager.h
    ${SNES9X_DIR}/stream.h
    ${SNES9X_DIR}/tile.h)
SOURCE_GROUP("core" FILES ${SRC_FILES})
LIST(APPEND LIB_SRC_FILES ${BASE_SRC_FILES})

SET(APU_SRC_FILES
    ${SNES9X_DIR}/apu/apu.cpp
    ${SNES9X_DIR}/apu/apu.h
    ${SNES9X_DIR}/apu/hermite_resampler.h
    ${SNES9X_DIR}/apu/resampler.h
    ${SNES9X_DIR}/apu/ring_buffer.h
    ${SNES9X_DIR}/apu/bapu/dsp/sdsp.cpp
    ${SNES9X_DIR}/apu/bapu/dsp/SPC_DSP.cpp
    ${SNES9X_DIR}/apu/bapu/dsp/blargg_common.h
    ${SNES9X_DIR}/apu/bapu/dsp/blargg_config.h
    ${SNES9X_DIR}/apu/bapu/dsp/blargg_endian.h
    ${SNES9X_DIR}/apu/bapu/dsp/blargg_source.h
    ${SNES9X_DIR}/apu/bapu/dsp/SPC_DSP.h
    ${SNES9X_DIR}/apu/bapu/dsp/sdsp.hpp
    ${SNES9X_DIR}/apu/bapu/smp/iplrom.cpp
    ${SNES9X_DIR}/apu/bapu/smp/smp.cpp
    ${SNES9X_DIR}/apu/bapu/smp/smp_state.cpp
    ${SNES9X_DIR}/apu/bapu/smp/smp.hpp
    ${SNES9X_DIR}/apu/bapu/smp/debugger/debugger.cpp
    ${SNES9X_DIR}/apu/bapu/smp/debugger/debugger.hpp
    ${SNES9X_DIR}/apu/bapu/snes/snes.hpp)
SOURCE_GROUP("apu" FILES ${APU_SRC_FILES})
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/${SNES9X_DIR}/apu/bapu)
LIST(APPEND LIB_SRC_FILES ${APU_SRC_FILES})

SET(FILTER_SRC_FILES
    ${SNES9X_DIR}/filter/2xsai.cpp
    ${SNES9X_DIR}/filter/2xsai.h
    ${SNES9X_DIR}/filter/blit.cpp
    ${SNES9X_DIR}/filter/blit.h
    ${SNES9X_DIR}/filter/epx.cpp
    ${SNES9X_DIR}/filter/epx.h
    ${SNES9X_DIR}/filter/hq2x.cpp
    ${SNES9X_DIR}/filter/hq2x.h
    ${SNES9X_DIR}/filter/snes_ntsc.c
    ${SNES9X_DIR}/filter/snes_ntsc.h
    ${SNES9X_DIR}/filter/snes_ntsc_config.h
    ${SNES9X_DIR}/filter/snes_ntsc_impl.h)
SOURCE_GROUP("filter" FILES ${FILTER_SRC_FILES})
LIST(APPEND LIB_SRC_FILES ${FILTER_SRC_FILES})

SET(LIBRETRO_SRC_FILES
    ${SNES9X_DIR}/libretro/libretro.cpp
    ${SNES9X_DIR}/libretro/libretro.h)
SOURCE_GROUP("libretro" FILES ${LIBRETRO_SRC_FILES})
LIST(APPEND LIB_SRC_FILES ${LIBRETRO_SRC_FILES})

INCLUDE_DIRECTORIES(${SNES9X_DIR} ${SNES9X_DIR}/apu/bapu)

SET(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -O3")
 
IF(WIN32)
	ADD_DEFINITIONS(-D__WIN32__)
	ADD_DEFINITIONS(-D__WIN32_LIBSNES__)
	ADD_DEFINITIONS(-D_CRT_SECURE_NO_WARNINGS)
ENDIF()

ADD_LIBRARY(snes9x SHARED ${LIB_SRC_FILES})	

SET(ZLIB_DIR ${CMAKE_CURRENT_SOURCE_DIR}/zlib-1.2.8)
ADD_SUBDIRECTORY(${ZLIB_DIR} zlib EXCLUDE_FROM_ALL)
INCLUDE_DIRECTORIES(${ZLIB_DIR})

TARGET_LINK_LIBRARIES(snes9x zlib)
