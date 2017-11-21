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

set(CURVE25519_SOURCE_FILES_C
	decaf.c
	elligator.c
	scalar.c
	eddsa.c
	decaf_tables.c
)

add_library(CURVE25519 OBJECT ${CURVE25519_SOURCE_FILES_C})
set_target_properties(CURVE25519 PROPERTIES POSITION_INDEPENDENT_CODE True)
