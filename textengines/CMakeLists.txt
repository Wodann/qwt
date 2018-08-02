#----------------------------------------------------------------
# Packages
#----------------------------------------------------------------
find_package(Qt5Xml REQUIRED)

#----------------------------------------------------------------
# Sources
#----------------------------------------------------------------
set(qwt_mathml_headers
	include/qwt_mathml_text_engine.h
	include/qwt_mml_document.h
)

set(qwt_mathml_sources
	mathml/qwt_mathml_text_engine.cpp
	mathml/qwt_mml_document.cpp
)

#----------------------------------------------------------------
# Target
#----------------------------------------------------------------
add_library(qwt_mathml SHARED ${qwt_mathml_headers} ${qwt_mathml_sources})

target_include_directories(qwt_mathml
	PUBLIC
		${CMAKE_CURRENT_SOURCE_DIR}/include
)

target_compile_definitions(qwt_mathml
	PUBLIC
		$<$<BOOL:MSVC>:QWT_DLL>
	PRIVATE
		$<$<BOOL:MSVC>:QWT_MAKEDLL>
)

target_link_libraries(qwt_mathml
	PRIVATE
		Qt5::Xml
		qwt
)
