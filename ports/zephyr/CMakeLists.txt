# SPDX-License-Identifier: CC0-1.0

add_library(minih264 OBJECT minih264e_zephyr.c)
target_include_directories(minih264 PUBLIC "${CMAKE_CURRENT_LIST_DIR}/../..")
target_compile_definitions(minih264 PUBLIC
  H264E_ENABLE_DENOISE=0
  H264E_MAX_THREADS=0
  H264E_SVC_API=0
  MINIH264_FORCE_PLAIN_C=1
)
target_compile_options(minih264 PRIVATE -Wno-unused-function)
target_link_libraries(minih264 PRIVATE zephyr_interface)
