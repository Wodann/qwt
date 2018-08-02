#----------------------------------------------------------------
# Sources
#----------------------------------------------------------------
set(sinusplot_sources
	sinusplot.cpp
)

#----------------------------------------------------------------
# Target
#----------------------------------------------------------------
add_executable(qwt_example_sinusplot ${sinusplot_sources})

target_link_libraries(qwt_example_sinusplot
	PRIVATE
		qwt
)

#----------------------------------------------------------------
# Deploy
#----------------------------------------------------------------
add_custom_command(
	TARGET qwt_example_sinusplot POST_BUILD
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Core> $<TARGET_FILE_DIR:qwt_example_sinusplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Gui> $<TARGET_FILE_DIR:qwt_example_sinusplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::OpenGL> $<TARGET_FILE_DIR:qwt_example_sinusplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::PrintSupport> $<TARGET_FILE_DIR:qwt_example_sinusplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Svg> $<TARGET_FILE_DIR:qwt_example_sinusplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:Qt5::Widgets> $<TARGET_FILE_DIR:qwt_example_sinusplot>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different
		$<TARGET_FILE:qwt> $<TARGET_FILE_DIR:qwt_example_sinusplot>
)
