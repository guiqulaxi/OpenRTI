# Query something from an fdd
add_executable(fddget-1516 fddget.cpp)
target_link_libraries(fddget-1516 rti1516 fedtime1516 OpenRTI)

# FIXME also test for the privilegeToDelete?? REALLY??
# add_test(rti1516/fddget-1516-1 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-1.xml"
#   -o HLAobjectRoot -a HLAprivilegeToDeleteObject -a privilegeToDelete -i HLAinteractionRoot)
add_test(rti1516/fddget-1516-1 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-1.xml"
  -o HLAobjectRoot -a HLAprivilegeToDeleteObject
  -i HLAinteractionRoot)
add_test(rti1516/fddget-1516-2 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-1.xml"
  -o ObjectClass1 -a HLAprivilegeToDeleteObject -a Attribute1
  -i InteractionClass1 -p Parameter1)
add_test(rti1516/fddget-1516-3 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-1.xml"
  -o HLAobjectRoot.ObjectClass1 -a HLAprivilegeToDeleteObject -a HLAobjectRoot.ObjectClass1.Attribute1
  -i HLAinteractionRoot.InteractionClass1 -p HLAinteractionRoot.InteractionClass1.Parameter1)

add_test(rti1516/fddget-1516-4 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-1.xml"
  -o ObjectClass2 -a HLAprivilegeToDeleteObject -a Attribute1 -a Attribute2
  -i InteractionClass2 -p Parameter1 -p Parameter2)
add_test(rti1516/fddget-1516-5 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-1.xml"
  -o HLAobjectRoot.ObjectClass1.ObjectClass2 -a HLAprivilegeToDeleteObject -a HLAobjectRoot.ObjectClass1.Attribute1 -a HLAobjectRoot.ObjectClass1.ObjectClass2.Attribute2
  -i HLAinteractionRoot.InteractionClass1.InteractionClass2 -p HLAinteractionRoot.InteractionClass1.Parameter1 -p HLAinteractionRoot.InteractionClass1.InteractionClass2.Parameter2)

add_test(rti1516/fddget-1516-6 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-1.xml"
  -o ObjectClass3 -a HLAprivilegeToDeleteObject -a Attribute3
  -i InteractionClass3 -p Parameter3)
add_test(rti1516/fddget-1516-7 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-1.xml"
  -o HLAobjectRoot.ObjectClass3 -a HLAprivilegeToDeleteObject -a HLAobjectRoot.ObjectClass3.Attribute3
  -i HLAinteractionRoot.InteractionClass3 -p HLAinteractionRoot.InteractionClass3.Parameter3)

# Now using a different object model not containing the root object
add_test(rti1516/fddget-1516-11 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-2.xml"
  -o HLAobjectRoot -a HLAprivilegeToDeleteObject
  -i HLAinteractionRoot)
add_test(rti1516/fddget-1516-12 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-2.xml"
  -o ObjectClass1 -a HLAprivilegeToDeleteObject -a Attribute1
  -i InteractionClass1 -p Parameter1)
add_test(rti1516/fddget-1516-13 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-2.xml"
  -o ObjectClass1 -a HLAprivilegeToDeleteObject -a ObjectClass1.Attribute1
  -i InteractionClass1 -p InteractionClass1.Parameter1)

add_test(rti1516/fddget-1516-14 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-2.xml"
  -o ObjectClass2 -a HLAprivilegeToDeleteObject -a Attribute1 -a Attribute2
  -i InteractionClass2 -p Parameter1 -p Parameter2)
add_test(rti1516/fddget-1516-15 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-2.xml"
  -o ObjectClass1.ObjectClass2 -a HLAprivilegeToDeleteObject -a ObjectClass1.Attribute1 -a ObjectClass1.ObjectClass2.Attribute2
  -i InteractionClass1.InteractionClass2 -p InteractionClass1.Parameter1 -p InteractionClass1.InteractionClass2.Parameter2)

add_test(rti1516/fddget-1516-16 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-2.xml"
  -o ObjectClass3 -a HLAprivilegeToDeleteObject -a Attribute3
  -i InteractionClass3 -p Parameter3)
add_test(rti1516/fddget-1516-17 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-2.xml"
  -o ObjectClass3 -a HLAprivilegeToDeleteObject -a ObjectClass3.Attribute3
  -i InteractionClass3 -p InteractionClass3.Parameter3)


# Just repeat one of the tests with data: url object models
add_test(rti1516/fddget-1516-20 "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/fddget-1516" -D -O "${CMAKE_CURRENT_SOURCE_DIR}/fdd-2.xml"
  -o ObjectClass3 -a HLAprivilegeToDeleteObject -a Attribute3
  -i InteractionClass3 -p Parameter3)
