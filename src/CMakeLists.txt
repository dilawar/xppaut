FILE(GLOB xppaut_SRC "*.h" "*.c" "*.bitmap")
add_executable(xppaut ${xppaut_SRC})




target_include_directories(xppaut PUBLIC ${SUNDIALS_INCLUDE_DIR} ${X11_INCLUDE_DIR})

target_link_libraries(xppaut 
    ${F2C_LIBRARIES} 
    ${SBML_LIBRARIES}
    ${SUNDIALS_LIBRARIES} 
    ${X11_LIBRARIES}
    )

install(TARGETS xppaut DESTINATION bin 
    CONFIGURATIONS Release Debug 
    )
