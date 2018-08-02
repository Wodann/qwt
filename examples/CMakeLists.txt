#----------------------------------------------------------------
# Packages
#----------------------------------------------------------------
find_package(Qt5OpenGL REQUIRED)
find_package(Qt5PrintSupport REQUIRED)
find_package(Qt5Svg REQUIRED)
find_package(Qt5Widgets REQUIRED)

#----------------------------------------------------------------
# Source
#----------------------------------------------------------------
add_subdirectory(animation)
add_subdirectory(barchart)
add_subdirectory(bode)
add_subdirectory(controls)
add_subdirectory(cpuplot)
add_subdirectory(curvdemo1)
add_subdirectory(dials)
add_subdirectory(distrowatch)
add_subdirectory(event_filter)
add_subdirectory(friedberg)
add_subdirectory(itemeditor)
add_subdirectory(legends)
add_subdirectory(oscilloscope)
add_subdirectory(radio)
add_subdirectory(rasterview)
add_subdirectory(realtime)
add_subdirectory(refreshtest)
add_subdirectory(scatterplot)
add_subdirectory(simpleplot)
add_subdirectory(sinusplot)
add_subdirectory(spectrogram)
add_subdirectory(stockchart)
add_subdirectory(sysinfo)
add_subdirectory(tvplot)
