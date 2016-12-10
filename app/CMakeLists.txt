# Sets the minimum version of CMake required to build your native library.
# This ensures that a certain set of CMake features is available to
# your build.
cmake_minimum_required(VERSION 3.4.1)
# Specifies a library name, specifies whether the library is STATIC or
# SHARED, and provides relative paths to the source code. You can
# define multiple libraries by adding multiple add.library() commands,
# and CMake builds them for you. When you build your app, Gradle
# automatically packages shared libraries with your APK.
include_directories( src/main/cpp/feature_stab/db_vlvm \
                     src/main/cpp/feature_stab/src \
                     src/main/cpp/feature_stab/src/dbreg \
                     src/main/cpp/feature_mos/src \
                     src/main/cpp/feature_mos/src/mosaic)
add_library(# Specifies the name of the library.
            jni_mosaic
            # Sets the library as a shared library.
            SHARED
            # Provides a relative path to your source file(s).
            src/main/cpp/feature_mos_jni.cpp \
            src/main/cpp/mosaic_renderer_jni.cpp \
            src/main/cpp/feature_mos/src/mosaic/trsMatrix.cpp \
            src/main/cpp/feature_mos/src/mosaic/AlignFeatures.cpp \
            src/main/cpp/feature_mos/src/mosaic/Blend.cpp \
            src/main/cpp/feature_mos/src/mosaic/Delaunay.cpp \
            src/main/cpp/feature_mos/src/mosaic/ImageUtils.cpp \
            src/main/cpp/feature_mos/src/mosaic/Mosaic.cpp \
            src/main/cpp/feature_mos/src/mosaic/Pyramid.cpp \
            src/main/cpp/feature_mos/src/mosaic_renderer/Renderer.cpp \
            src/main/cpp/feature_mos/src/mosaic_renderer/WarpRenderer.cpp \
            src/main/cpp/feature_mos/src/mosaic_renderer/SurfaceTextureRenderer.cpp \
            src/main/cpp/feature_mos/src/mosaic_renderer/YVURenderer.cpp \
            src/main/cpp/feature_mos/src/mosaic_renderer/FrameBuffer.cpp \
            src/main/cpp/feature_stab/db_vlvm/db_feature_detection.cpp \
            src/main/cpp/feature_stab/db_vlvm/db_feature_matching.cpp \
            src/main/cpp/feature_stab/db_vlvm/db_framestitching.cpp \
            src/main/cpp/feature_stab/db_vlvm/db_image_homography.cpp \
            src/main/cpp/feature_stab/db_vlvm/db_rob_image_homography.cpp \
            src/main/cpp/feature_stab/db_vlvm/db_utilities.cpp \
            src/main/cpp/feature_stab/db_vlvm/db_utilities_camera.cpp \
            src/main/cpp/feature_stab/db_vlvm/db_utilities_indexing.cpp \
            src/main/cpp/feature_stab/db_vlvm/db_utilities_linalg.cpp \
            src/main/cpp/feature_stab/db_vlvm/db_utilities_poly.cpp \
            src/main/cpp/feature_stab/src/dbreg/dbreg.cpp \
            src/main/cpp/feature_stab/src/dbreg/dbstabsmooth.cpp \
            src/main/cpp/feature_stab/src/dbreg/vp_motionmodel.c )