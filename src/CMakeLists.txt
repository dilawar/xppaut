FILE(GLOB xppaut_SRC "*.h" "*.c" "*.bitmap")
add_executable(xppaut ${xppaut_SRC})

target_link_libraries(xppaut 
    ${F2C_LIBRARIES} 
    ${SBML_LIBRARIES}
    ${SUNDIALS_LIBRARIES} 
    ${X11_LIBRARIES}
    )

target_include_directories(xppaut PUBLIC ${SUNDIALS_INCLUDE_DIR} ${X11_INCLUDE_DIR})

set_target_properties( xppaut PROPERTIES LINK_FLAGS "-lm -ldl" )

install(TARGETS xppaut DESTINATION bin 
    CONFIGURATIONS Release Debug 
    )
