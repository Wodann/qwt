#----------------------------------------------------------------
# Packages
#----------------------------------------------------------------
# Find includes in corresponding build include_directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
# Instruct CMake to run moc automatically when needed
set(CMAKE_AUTOMOC ON)
# Create code from a list of Qt designer ui files
set(CMAKE_AUTOUIC ON)

#----------------------------------------------------------------
# Sources
#----------------------------------------------------------------
set(cpuplot_sources
	cpupiemarker.cpp
	cpupiemarker.h
	cpuplot.cpp
	cpuplot.h
	cpustat.cpp
	cpustat.h
)

#----------------------------------------------------------------
# Target
#----------------------------------------------------------------
add_executable(qwt_example_cpuplot ${cpuplot_sources})

target_link_libraries(qwt_example_cpuplot
	PRIVATE
		qwt
)

#----------------------------------------------------------------
# Deploy
#----------------------------------------------------------------
add_custom_command(
	TARGET qwt_example_cpuplot POST_BUILD
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Core> $<TARGET_FILE_DIR:qwt_example_cpuplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Gui> $<TARGET_FILE_DIR:qwt_example_cpuplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::OpenGL> $<TARGET_FILE_DIR:qwt_example_cpuplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::PrintSupport> $<TARGET_FILE_DIR:qwt_example_cpuplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Svg> $<TARGET_FILE_DIR:qwt_example_cpuplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Widgets> $<TARGET_FILE_DIR:qwt_example_cpuplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:qwt> $<TARGET_FILE_DIR:qwt_example_cpuplot>
)
