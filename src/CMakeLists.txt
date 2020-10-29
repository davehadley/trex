list(APPEND CMAKE_PREFIX_PATH $ENV{ROOTSYS})
find_package(ROOT 6.15 REQUIRED COMPONENTS RIO Net Tree MathCore)
include(${ROOT_USE_FILE})

root_generate_dictionary(
  ioDict
  TTRExPattern.hxx
  TTPCHitPad.hxx
  OPTIONS
  -inlineInputHeader
  LINKDEF
  ioLinkDef.hh)

include_directories("${CMAKE_CURRENT_SOURCE_DIR}")

add_library(
  libpatrec
  TTPCAStar.cxx
  TTPCHitPad.cxx
  TTPCLayout.cxx
  TTPCOrderedVolGroup.cxx
  TTPCPathVolume.cxx
  TTPCTRExPatAlgorithm.cxx
  TTPCTRExPatSubAlgorithm.cxx
  TTPCUnitVolume.cxx
  TTPCVolGroup.cxx
  TTPCVolGroupMan.cxx
  TSimLoaderCCD.cxx
  TTRExPattern.cxx
  TEventDisplay.cxx
  ioDict.cxx
  TTRExHVCluster.cxx
  TTPCHelixPropagator.cxx
  TTPCLikelihoodMatch.cxx
  TTPCLikelihoodMerge.cxx
  TTPCLinearMerge.cxx
  TTPCLikFitPath.cxx
  TTPCQLikelihood.cxx
  TTPCSeeding.cxx
  TTPCTracking.cxx
  TTPCUtils.cxx
  TTrueHit.cxx
  TTRExPath.cxx
  TTRExJunction.cxx
  TTRExPIDAlgorithm.cxx
  TTrueTrack.cxx)

add_executable(RunTRExReconCCD.exe RunTRExReconCCD.cxx)
target_link_libraries(RunTRExReconCCD.exe libpatrec ${ROOT_LIBRARIES})
