set(%{APPNAMELC}_SRCS
   %{APPNAMELC}.cpp
   main.cpp
   %{APPNAMELC}view.cpp
 )

kde4_add_ui_files(%{APPNAMELC}_SRCS %{APPNAMELC}view_base.ui prefs_base.ui)

kde4_add_kcfg_files(%{APPNAMELC}_SRCS settings.kcfgc )

kde4_add_executable(%{APPNAMELC} ${%{APPNAMELC}_SRCS})

target_link_libraries(%{APPNAMELC} ${KDE4_KDEUI_LIBS} )

install(TARGETS %{APPNAMELC} ${INSTALL_TARGETS_DEFAULT_ARGS} )


########### install files ###############

install( PROGRAMS %{APPNAMELC}.desktop  DESTINATION ${XDG_APPS_INSTALL_DIR} )
install( FILES %{APPNAMELC}.kcfg  DESTINATION  ${KCFG_INSTALL_DIR} )
install( FILES %{APPNAMELC}ui.rc  DESTINATION  ${DATA_INSTALL_DIR}/%{APPNAMELC} )
