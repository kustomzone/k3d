K3D_TEST(python.module
  K3D_PYTHON_SCRIPT ${CMAKE_CURRENT_SOURCE_DIR}/module.py
  LABELS python)

K3D_TEST(python.angle_axis
  K3D_PYTHON_SCRIPT ${CMAKE_CURRENT_SOURCE_DIR}/angle_axis.py
  LABELS python)

K3D_TEST(python.get_dependency
  K3D_PYTHON_SCRIPT ${CMAKE_CURRENT_SOURCE_DIR}/get_dependency.py
  LABELS python)

K3D_TEST(python.named_arrays
  K3D_PYTHON_SCRIPT ${CMAKE_CURRENT_SOURCE_DIR}/named_arrays.py
  LABELS python)

K3D_TEST(python.node.selection
  K3D_PYTHON_SCRIPT ${CMAKE_CURRENT_SOURCE_DIR}/node_selection.py
  LABELS python)

K3D_TEST(python.property_linking
  K3D_PYTHON_SCRIPT ${CMAKE_CURRENT_SOURCE_DIR}/property_linking.py
  LABELS python)

K3D_TEST(python.property.value
  K3D_PYTHON_SCRIPT ${CMAKE_CURRENT_SOURCE_DIR}/property_value.py
  LABELS python)

K3D_TEST(python.renderman.attributes
  K3D_PYTHON_SCRIPT ${CMAKE_CURRENT_SOURCE_DIR}/renderman_attributes.py
  LABELS python)

K3D_TEST(python.renderman.options
  K3D_PYTHON_SCRIPT ${CMAKE_CURRENT_SOURCE_DIR}/renderman_options.py
  LABELS python)

K3D_TEST(python.user_properties
  K3D_PYTHON_SCRIPT ${CMAKE_CURRENT_SOURCE_DIR}/user_properties.py
  LABELS python)

# Smoke-test generic share scripts ...
FILE(GLOB SCRIPT_LIST ${share_SOURCE_DIR}/scripts/*.py)
LIST(SORT SCRIPT_LIST)

FOREACH(SCRIPT ${SCRIPT_LIST})
  GET_FILENAME_COMPONENT(SCRIPT_NAME ${SCRIPT} NAME_WE)
  K3D_TEST(python.share.${SCRIPT_NAME}
    K3D_PYTHON_SCRIPT ${SCRIPT}
    ARGUMENTS "--script-file=${CMAKE_CURRENT_SOURCE_DIR}/document_environment.py"
    LABELS python)
ENDFOREACH()

