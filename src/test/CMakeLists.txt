# -*-cmake-*-

ADD_EXECUTABLE(test_avatar test_Avatar.cpp)
TARGET_LINK_LIBRARIES(test_avatar ${LIBS} clmTracker)

TARGET_LINK_LIBRARIES(test_avatar avatarAnim)

ADD_EXECUTABLE(full_screen_avatar full_screen_Avatar.cpp)
TARGET_LINK_LIBRARIES(full_screen_avatar ${LIBS} clmTracker)

TARGET_LINK_LIBRARIES(full_screen_avatar avatarAnim)

ADD_EXECUTABLE(speed_test speed_test.cpp command-line-options.cpp)
TARGET_LINK_LIBRARIES(speed_test ${LIBS} clmTracker avatarAnim)

ADD_EXECUTABLE(full_screen_speed_test full_screen_speed_test.cpp command-line-options.cpp)
TARGET_LINK_LIBRARIES(full_screen_speed_test ${LIBS} clmTracker avatarAnim)

ADD_EXECUTABLE(add_avatar add_avatar.cpp)
TARGET_LINK_LIBRARIES(add_avatar ${LIBS} avatarAnim)
