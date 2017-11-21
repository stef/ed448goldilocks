############################################################################
# CMakeLists.txt
#
#    Released under the MIT License.  See LICENSE.txt for license information.
#
############################################################################

include_directories(
	${PROJECT_SOURCE_DIR}/src/p448
	${PROJECT_SOURCE_DIR}/src/GENERATED/c/p448
)

include_directories(
	${PROJECT_SOURCE_DIR}/src/p448/${TARGET_ARCH_DIR_P448}
)

set(CURVE448_SOURCE_FILES_C
	decaf.c
	elligator.c
	scalar.c
	eddsa.c
	decaf_tables.c
)

add_library(CURVE448 OBJECT ${CURVE448_SOURCE_FILES_C})
set_target_properties(CURVE448 PROPERTIES POSITION_INDEPENDENT_CODE True)
