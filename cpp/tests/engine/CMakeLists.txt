find_library(GTest REQUIRED)

add_executable(test_dictionary test_dictionary.cpp )
target_link_libraries(test_dictionary csp_engine GTest::gtest GTest::gtest_main rt)

add_executable(test_tick_buffer test_tick_buffer.cpp)
target_link_libraries(test_tick_buffer csp_engine GTest::gtest GTest::gtest_main)

add_executable(test_time_series test_time_series.cpp)
target_link_libraries(test_time_series csp_engine_static gtest gtest_main pthread)

add_executable(test_partial_switch_csp_type test_partial_switch_csp_type.cpp)
target_link_libraries(test_partial_switch_csp_type csp_engine GTest::gtest GTest::gtest_main)

add_executable(test_window_buffer test_window_buffer.cpp)
target_link_libraries(test_window_buffer csp_engine GTest::gtest GTest::gtest_main)

install(TARGETS test_tick_buffer test_time_series test_partial_switch_csp_type test_dictionary test_window_buffer
        RUNTIME DESTINATION tests/bin/
        LIBRARY DESTINATION tests/lib/
        ARCHIVE DESTINATION tests/lib/)
