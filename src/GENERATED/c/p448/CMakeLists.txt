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


set(P448_HEADER_FILES
	f_field.h
	${PROJECT_SOURCE_DIR}/src/p448/${TARGET_ARCH_DIR_P448}/f_impl.h
)
set(P448_SOURCE_FILES_C
	${PROJECT_SOURCE_DIR}/src/p448/${TARGET_ARCH_DIR_P448}/f_impl.c
	${PROJECT_SOURCE_DIR}/src/p448/f_arithmetic.c
	f_generic.c
)

add_library(p448 OBJECT ${P448_HEADER_FILES} ${P448_SOURCE_FILES_C})
set_target_properties(p448 PROPERTIES POSITION_INDEPENDENT_CODE True)
