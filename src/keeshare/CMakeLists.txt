if(WITH_XC_KEESHARE)
    set(keeshare_SOURCES
        SettingsPageKeeShare.cpp
        SettingsWidgetKeeShare.cpp
        DatabaseSettingsPageKeeShare.cpp
        DatabaseSettingsWidgetKeeShare.cpp
        group/EditGroupWidgetKeeShare.cpp
        group/EditGroupPageKeeShare.cpp
        KeeShare.cpp
        KeeShareSettings.cpp
        ShareImport.cpp
        ShareExport.cpp
        ShareObserver.cpp
        )

    find_package(Minizip REQUIRED)

    add_library(keeshare STATIC ${keeshare_SOURCES})
    target_link_libraries(keeshare PUBLIC Qt5::Core Qt5::Widgets ${BOTAN2_LIBRARIES} ${ZLIB_LIBRARIES} PRIVATE ${MINIZIP_LIBRARIES})
    include_directories(${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_BINARY_DIR})
endif(WITH_XC_KEESHARE)
