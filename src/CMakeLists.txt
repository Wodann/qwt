#----------------------------------------------------------------
# Packages
#----------------------------------------------------------------
# Find includes in corresponding build include_directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
# Instruct CMake to run moc automatically when needed
set(CMAKE_AUTOMOC ON)
# Create code from a list of Qt designer ui files
set(CMAKE_AUTOUIC ON)

set(CMAKE_PREFIX_PATH "" CACHE PATH "Path to Qt")

find_package(Qt5Concurrent REQUIRED)
find_package(Qt5OpenGL REQUIRED)
find_package(Qt5PrintSupport REQUIRED)
find_package(Qt5Svg REQUIRED)
find_package(Qt5Widgets REQUIRED)

#----------------------------------------------------------------
# Sources
#----------------------------------------------------------------
set(qwt_headers
	${PROJECT_SOURCE_DIR}/include/qwt_abstract_legend.h
	${PROJECT_SOURCE_DIR}/include/qwt_abstract_scale.h
	${PROJECT_SOURCE_DIR}/include/qwt_abstract_scale_draw.h
	${PROJECT_SOURCE_DIR}/include/qwt_abstract_slider.h
	${PROJECT_SOURCE_DIR}/include/qwt_analog_clock.h
	${PROJECT_SOURCE_DIR}/include/qwt_arrow_button.h
	${PROJECT_SOURCE_DIR}/include/qwt_clipper.h
	${PROJECT_SOURCE_DIR}/include/qwt_color_map.h
	${PROJECT_SOURCE_DIR}/include/qwt_column_symbol.h
	${PROJECT_SOURCE_DIR}/include/qwt_compass.h
	${PROJECT_SOURCE_DIR}/include/qwt_compass_rose.h
	${PROJECT_SOURCE_DIR}/include/qwt_counter.h
	${PROJECT_SOURCE_DIR}/include/qwt_curve_fitter.h
	${PROJECT_SOURCE_DIR}/include/qwt_date.h
	${PROJECT_SOURCE_DIR}/include/qwt_date_scale_draw.h
	${PROJECT_SOURCE_DIR}/include/qwt_date_scale_engine.h
	${PROJECT_SOURCE_DIR}/include/qwt_dial.h
	${PROJECT_SOURCE_DIR}/include/qwt_dial_needle.h
	${PROJECT_SOURCE_DIR}/include/qwt_dyngrid_layout.h
	${PROJECT_SOURCE_DIR}/include/qwt_event_pattern.h
	${PROJECT_SOURCE_DIR}/include/qwt_global.h
	${PROJECT_SOURCE_DIR}/include/qwt_graphic.h
	${PROJECT_SOURCE_DIR}/include/qwt_interval.h
	${PROJECT_SOURCE_DIR}/include/qwt_interval_symbol.h
	${PROJECT_SOURCE_DIR}/include/qwt_knob.h
	${PROJECT_SOURCE_DIR}/include/qwt_legend.h
	${PROJECT_SOURCE_DIR}/include/qwt_legend_data.h
	${PROJECT_SOURCE_DIR}/include/qwt_legend_label.h
	${PROJECT_SOURCE_DIR}/include/qwt_magnifier.h
	${PROJECT_SOURCE_DIR}/include/qwt_math.h
	${PROJECT_SOURCE_DIR}/include/qwt_matrix_raster_data.h
	${PROJECT_SOURCE_DIR}/include/qwt_null_paintdevice.h
	${PROJECT_SOURCE_DIR}/include/qwt_painter.h
	${PROJECT_SOURCE_DIR}/include/qwt_painter_command.h
	${PROJECT_SOURCE_DIR}/include/qwt_panner.h
	${PROJECT_SOURCE_DIR}/include/qwt_picker.h
	${PROJECT_SOURCE_DIR}/include/qwt_picker_machine.h
	${PROJECT_SOURCE_DIR}/include/qwt_pixel_matrix.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_abstract_barchart.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_barchart.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_canvas.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_curve.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_dict.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_directpainter.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_glcanvas.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_grid.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_histogram.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_intervalcurve.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_item.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_layout.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_legenditem.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_magnifier.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_marker.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_multi_barchart.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_panner.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_picker.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_rasteritem.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_renderer.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_rescaler.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_scaleitem.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_seriesitem.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_shapeitem.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_spectrogram.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_spectrocurve.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_svgitem.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_textlabel.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_tradingcurve.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_zoneitem.h
	${PROJECT_SOURCE_DIR}/include/qwt_plot_zoomer.h
	${PROJECT_SOURCE_DIR}/include/qwt_point_3d.h
	${PROJECT_SOURCE_DIR}/include/qwt_point_data.h
	${PROJECT_SOURCE_DIR}/include/qwt_point_mapper.h
	${PROJECT_SOURCE_DIR}/include/qwt_point_polar.h
	${PROJECT_SOURCE_DIR}/include/qwt_raster_data.h
	${PROJECT_SOURCE_DIR}/include/qwt_round_scale_draw.h
	${PROJECT_SOURCE_DIR}/include/qwt_samples.h
	${PROJECT_SOURCE_DIR}/include/qwt_sampling_thread.h
	${PROJECT_SOURCE_DIR}/include/qwt_scale_div.h
	${PROJECT_SOURCE_DIR}/include/qwt_scale_draw.h
	${PROJECT_SOURCE_DIR}/include/qwt_scale_engine.h
	${PROJECT_SOURCE_DIR}/include/qwt_scale_map.h
	${PROJECT_SOURCE_DIR}/include/qwt_scale_widget.h
	${PROJECT_SOURCE_DIR}/include/qwt_series_data.h
	${PROJECT_SOURCE_DIR}/include/qwt_series_store.h
	${PROJECT_SOURCE_DIR}/include/qwt_slider.h
	${PROJECT_SOURCE_DIR}/include/qwt_spline.h
	${PROJECT_SOURCE_DIR}/include/qwt_symbol.h
	${PROJECT_SOURCE_DIR}/include/qwt_system_clock.h
	${PROJECT_SOURCE_DIR}/include/qwt_text.h
	${PROJECT_SOURCE_DIR}/include/qwt_text_engine.h
	${PROJECT_SOURCE_DIR}/include/qwt_text_label.h
	${PROJECT_SOURCE_DIR}/include/qwt_thermo.h
	${PROJECT_SOURCE_DIR}/include/qwt_transform.h
	${PROJECT_SOURCE_DIR}/include/qwt_wheel.h
	${PROJECT_SOURCE_DIR}/include/qwt_widget_overlay.h
)

set(qwt_sources
	qwt_abstract_legend.cpp
	qwt_abstract_scale.cpp
	qwt_abstract_scale_draw.cpp
	qwt_abstract_slider.cpp
	qwt_analog_clock.cpp
	qwt_arrow_button.cpp
	qwt_clipper.cpp
	qwt_color_map.cpp
	qwt_column_symbol.cpp
	qwt_compass.cpp
	qwt_compass_rose.cpp
	qwt_counter.cpp
	qwt_curve_fitter.cpp
	qwt_date.cpp
	qwt_date_scale_draw.cpp
	qwt_date_scale_engine.cpp
	qwt_dial.cpp
	qwt_dial_needle.cpp
	qwt_dyngrid_layout.cpp
	qwt_event_pattern.cpp
	qwt_graphic.cpp
	qwt_interval.cpp
	qwt_interval_symbol.cpp
	qwt_knob.cpp
	qwt_legend.cpp
	qwt_legend_data.cpp
	qwt_legend_label.cpp
	qwt_magnifier.cpp
	qwt_math.cpp
	qwt_matrix_raster_data.cpp
	qwt_null_paintdevice.cpp
	qwt_painter.cpp
	qwt_painter_command.cpp
	qwt_panner.cpp
	qwt_picker.cpp
	qwt_picker_machine.cpp
	qwt_pixel_matrix.cpp
	qwt_plot.cpp
	qwt_plot_abstract_barchart.cpp
	qwt_plot_axis.cpp
	qwt_plot_barchart.cpp
	qwt_plot_canvas.cpp
	qwt_plot_curve.cpp
	qwt_plot_dict.cpp
	qwt_plot_directpainter.cpp
	qwt_plot_glcanvas.cpp
	qwt_plot_grid.cpp
	qwt_plot_histogram.cpp
	qwt_plot_intervalcurve.cpp
	qwt_plot_item.cpp
	qwt_plot_layout.cpp
	qwt_plot_legenditem.cpp
	qwt_plot_magnifier.cpp
	qwt_plot_marker.cpp
	qwt_plot_multi_barchart.cpp
	qwt_plot_panner.cpp
	qwt_plot_picker.cpp
	qwt_plot_rasteritem.cpp
	qwt_plot_renderer.cpp
	qwt_plot_rescaler.cpp
	qwt_plot_scaleitem.cpp
	qwt_plot_seriesitem.cpp
	qwt_plot_shapeitem.cpp
	qwt_plot_spectrocurve.cpp
	qwt_plot_spectrogram.cpp
	qwt_plot_svgitem.cpp
	qwt_plot_textlabel.cpp
	qwt_plot_tradingcurve.cpp
	qwt_plot_xml.cpp
	qwt_plot_zoneitem.cpp
	qwt_plot_zoomer.cpp
	qwt_point_3d.cpp
	qwt_point_data.cpp
	qwt_point_mapper.cpp
	qwt_point_polar.cpp
	qwt_raster_data.cpp
	qwt_round_scale_draw.cpp
	qwt_sampling_thread.cpp
	qwt_scale_div.cpp
	qwt_scale_draw.cpp
	qwt_scale_engine.cpp
	qwt_scale_map.cpp
	qwt_scale_widget.cpp
	qwt_series_data.cpp
	qwt_slider.cpp
	qwt_spline.cpp
	qwt_symbol.cpp
	qwt_system_clock.cpp
	qwt_text.cpp
	qwt_text_engine.cpp
	qwt_text_label.cpp
	qwt_thermo.cpp
	qwt_transform.cpp
	qwt_wheel.cpp
	qwt_widget_overlay.cpp
)

#----------------------------------------------------------------
# Target
#----------------------------------------------------------------
add_library(qwt SHARED ${qwt_headers} ${qwt_sources})

target_compile_definitions(qwt
	PUBLIC
		$<$<BOOL:MSVC>:QWT_DLL>
	PRIVATE
		$<$<BOOL:MSVC>:QWT_MAKEDLL>
)

target_include_directories(qwt
	PUBLIC
		${PROJECT_SOURCE_DIR}/include
)

target_link_libraries(qwt
	PUBLIC
		Qt5::Core
		Qt5::OpenGL
	PRIVATE
		Qt5::Concurrent
		Qt5::PrintSupport
		Qt5::Svg
)
