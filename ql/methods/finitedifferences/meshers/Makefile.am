
AM_CPPFLAGS = -I${top_builddir} -I${top_srcdir}

this_includedir=${includedir}/${subdir}
this_include_HEADERS = \
	all.hpp \
    concentrating1dmesher.hpp \
    exponentialjump1dmesher.hpp \
    fdm1dmesher.hpp \
    fdmblackscholesmesher.hpp \
    fdmblackscholesmultistrikemesher.hpp \
    fdmhestonvariancemesher.hpp \
    fdmmeshercomposite.hpp \
    fdmmesher.hpp \
    fdmsimpleprocess1dmesher.hpp \
    predefined1dmesher.hpp \
    uniform1dmesher.hpp \
    uniformgridmesher.hpp

cpp_files = \
    concentrating1dmesher.cpp \
    exponentialjump1dmesher.cpp \
    fdmblackscholesmesher.cpp \
    fdmblackscholesmultistrikemesher.cpp \
    fdmhestonvariancemesher.cpp \
    fdmmeshercomposite.cpp \
    fdmsimpleprocess1dmesher.cpp \
    uniformgridmesher.cpp

if UNITY_BUILD

nodist_libFdmMeshers_la_SOURCES = unity.cpp

unity.cpp: Makefile.am
	echo "/* This file is automatically generated; do not edit.     */" > $@
	echo "/* Add the files to be included into Makefile.am instead. */" >> $@
	echo >> $@
	for i in $(cpp_files); do \
		echo "#include \"$$i\"" >> $@; \
	done

EXTRA_DIST = $(cpp_files)

else

libFdmMeshers_la_SOURCES = $(cpp_files)

endif

noinst_LTLIBRARIES = libFdmMeshers.la

all.hpp: Makefile.am
	echo "/* This file is automatically generated; do not edit.     */" > $@
	echo "/* Add the files to be included into Makefile.am instead. */" >> $@
	echo >> $@
	for i in $(filter-out all.hpp, $(this_include_HEADERS)); do \
		echo "#include <${subdir}/$$i>" >> $@; \
	done
	echo >> $@
	subdirs='$(SUBDIRS)'; for i in $$subdirs; do \
		echo "#include <${subdir}/$$i/all.hpp>" >> $@; \
	done

