set(TEST_SOURCES
    test_aes.c
    test_cbc_mode.c
    test_ccm_mode.c
    test_cmac_mode.c
    test_ctr_mode.c
    test_ctr_prng.c
    test_ecc_dh.c
    test_ecc_dsa.c
    test_hmac_prng.c
    test_hmac.c
    test_sha256.c)

foreach(test_src ${TEST_SOURCES})
    get_filename_component(test_name ${test_src} NAME_WE)

    if (${test_name} MATCHES "test_ecc_*")
        list(APPEND test_src test_ecc_utils.c)
    endif()

    add_executable(${test_name} ${test_src})
    set_target_properties(${test_name} PROPERTIES
        LINKER_LANGUAGE C
        C_STANDARD 99)
    target_link_libraries(${test_name} tinycrypt)
    add_test(NAME ${test_name} COMMAND ${test_name})
endforeach()