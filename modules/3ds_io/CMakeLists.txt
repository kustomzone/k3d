INCLUDE_DIRECTORIES(${K3D_3DS_INCLUDE_DIRS})

K3D_BUILD_MODULE(k3d-3ds-io)
K3D_CREATE_MODULE_PROXY(k3d-3ds-io)

TARGET_LINK_LIBRARIES(k3d-3ds-io ${K3D_3DS_LIBS})