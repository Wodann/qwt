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
set(stockchart_sources
	griditem.cpp
	griditem.h
	legend.cpp
	legend.h
	main.cpp
	plot.cpp
	plot.h
	quotefactory.cpp
	quotefactory.h
)

#----------------------------------------------------------------
# Target
#----------------------------------------------------------------
add_executable(qwt_example_stockchart ${stockchart_sources})

target_link_libraries(qwt_example_stockchart
	PRIVATE
		qwt
)

#----------------------------------------------------------------
# Deploy
#----------------------------------------------------------------
add_custom_command(
	TARGET qwt_example_stockchart POST_BUILD
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Core> $<TARGET_FILE_DIR:qwt_example_stockchart>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Gui> $<TARGET_FILE_DIR:qwt_example_stockchart>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::OpenGL> $<TARGET_FILE_DIR:qwt_example_stockchart>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::PrintSupport> $<TARGET_FILE_DIR:qwt_example_stockchart>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Svg> $<TARGET_FILE_DIR:qwt_example_stockchart>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Widgets> $<TARGET_FILE_DIR:qwt_example_stockchart>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:qwt> $<TARGET_FILE_DIR:qwt_example_stockchart>
)
