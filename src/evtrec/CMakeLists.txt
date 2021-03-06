# CMakeLists.cxx -- gastpc/EvtRec

set(EVTREC_HDRS
    EventRecord.h
    MCGenInfo.h
    MCParticle.h
    MCTrack.h
    MCHit.h
    RecoParticle.h
    Vector3D.h
    Vector4D.h)

set(EVTREC_SRCS
    EventRecord.cxx
    MCGenInfo.cxx
    MCParticle.cxx
    MCTrack.cxx
    MCHit.cxx
    RecoParticle.cxx
    Vector3D.cxx
    Vector4D.cxx
    RootFileReader.cxx
    RootFileWriter.cxx)

include_directories("${CMAKE_CURRENT_SOURCE_DIR}")

root_generate_dictionary(G__GasTPCEvtRec ${EVTREC_HDRS} LINKDEF LinkDef.h)

add_library(GasTPCEvtRec SHARED ${EVTREC_SRCS} G__GasTPCEvtRec.cxx)

target_link_libraries(GasTPCEvtRec ${ROOT_LIBRARIES})

install(
  TARGETS GasTPCEvtRec
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib)

install(FILES ${CMAKE_CURRENT_BINARY_DIR}/G__GasTPCEvtRec_rdict.pcm
        DESTINATION lib)
# install(FILES ${CMAKE_CURRENT_BINARY_DIR}/libGasTPCEvtRec_rdict.pcm
# DESTINATION lib)
