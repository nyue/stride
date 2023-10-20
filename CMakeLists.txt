project(stride)

set(STRIDE_SOURCES
  splitstr.c
  rdpdb.c
  initchn.c
  geometry.c
  thr2one.c
  one2thr.c
  filename.c
  tolostr.c
  strutil.c
  place_h.c
  hbenergy.c
  memory.c
  helix.c
  sheet.c
  rdmap.c
  phipsi.c
  command.c
  molscr.c
  die.c
  hydrbond.c
  mergepat.c
  fillasn.c
  escape.c
  p_jrnl.c
  p_rem.c
  p_atom.c
  p_helix.c
  p_sheet.c
  p_turn.c
  p_ssbond.c
  p_expdta.c
  p_model.c
  p_compnd.c
  report.c
  nsc.c
  area.c
  ssbond.c
  chk_res.c
  chk_atom.c
  turn.c
  pdbasn.c
  dssp.c
  outseq.c
  chkchain.c
  elem.c
  measure.c
  asngener.c
  p_endmdl.c
  stred.c
  contact_order.c
  contact_map.c
  )

add_library(stride STATIC
  ${STRIDE_SOURCES}
  )

add_executable(stride_exe
  stride.c
  )

target_link_libraries(stride_exe
  stride
  m
  )

install(TARGETS
  stride_exe
  DESTINATION
  bin
  )

install(TARGETS
  stride
  DESTINATION
  lib
  )

install(FILES
  stride.h
  DESTINATION
  include
  )

install(FILES
  doc/notes.dos
  doc/notes.mac
  doc/relnotes.doc
  doc/stride.doc
  DESTINATION
  docs
  )

include(CPack)
