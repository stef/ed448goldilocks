############################################################################
# CMakeLists.txt
#
#    Released under the MIT License.  See LICENSE.txt for license information.
#
############################################################################

include_directories(
	${PROJECT_SOURCE_DIR}/src/p25519
	${PROJECT_SOURCE_DIR}/src/GENERATED/c/p25519
)

include_directories(
	${PROJECT_SOURCE_DIR}/src/p25519/${TARGET_ARCH_DIR_P25519}
)

set(P25519_HEADER_FILES
	f_field.h
	${PROJECT_SOURCE_DIR}/src/p25519/${TARGET_ARCH_DIR_P25519}/f_impl.h
)
set(P25519_SOURCE_FILES_C
	${PROJECT_SOURCE_DIR}/src/p25519/${TARGET_ARCH_DIR_P25519}/f_impl.c
	${PROJECT_SOURCE_DIR}/src/p25519/f_arithmetic.c
	f_generic.c
)

add_library(p25519 OBJECT ${P25519_HEADER_FILES} ${P25519_SOURCE_FILES_C})
set_target_properties(p25519 PROPERTIES POSITION_INDEPENDENT_CODE True)
