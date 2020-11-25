# libmaxminddb
include(libmaxminddb.cmake)

# libmaxminddb headers
include_directories(${LIBMAXMINDDB_DEST}/include/)
set(maxmindversion 1.3.2)

add_compile_options(-DPACKAGE_VERSION="${maxmindversion}")

include_directories(libmaxminddb-${maxmindversion}/ libmaxminddb-${maxmindversion}/src libmaxminddb-${maxmindversion}/include)

set(src
  libmaxminddb-${maxmindversion}/src/maxminddb.c
  libmaxminddb-${maxmindversion}/src/data-pool.c
  geoip2.c)

FLB_PLUGIN(filter_geoip2 "${src}" "")
