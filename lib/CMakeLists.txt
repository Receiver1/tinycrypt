file(GLOB_RECURSE TINYCRYPT_SOURCES "*.c" "*.h")

add_library(tinycrypt STATIC 
    ${TINYCRYPT_SOURCES})

set_target_properties(tinycrypt PROPERTIES
    LINKER_LANGUAGE C
    C_STANDARD 99)