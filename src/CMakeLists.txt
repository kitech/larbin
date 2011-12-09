
include_directories(${PROJECT_SOURCE_DIR} ${PROJECT_SOURCE_DIR}/adns ${PROJECT_SOURCE_DIR}/src)

add_executable(larbin main.cc global.cc
    utils/connexion.cc  utils/hashDup.cc    utils/mypthread.cc       utils/string.cc  utils/url.cc
    utils/debug.cc      utils/histogram.cc  utils/PersistentFifo.cc  utils/text.cc    utils/webserver.cc
    
    # fetch/dynamicspecbuf.cc fetch/savespecbuf.cc fetch/specbuf.cc fetch/defaultspecbuf.cc
    fetch/checker.cc           fetch/fetchPipe.cc  fetch/hashTable.cc    fetch/sequencer.cc  
    fetch/fetchOpen.cc       fetch/file.cc         fetch/site.cc

    interf/input.cc
    interf/output.cc
    interf/useroutput.cc
)


target_link_libraries(larbin pthread adns z)
