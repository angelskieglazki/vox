AC_PREREQ([2.69])
AC_INIT([vox], [0.0.1], [mpano91@gmail.com])
AC_DEFINE([PACKAGE_DESCRIPTION], ["C project application"], [Application description])
AC_DEFINE([HAVE_STDNORETURN_H], [], [Description])
AC_CONFIG_HEADERS([src/config.h])
AC_CONFIG_SRCDIR([src/main.c])
AM_INIT_AUTOMAKE
PKG_PROG_PKG_CONFIG

# Remember externally set CFLAGS
EXTERNAL_CFLAGS="$CFLAGS"

# Checks for programs. These may set default variables, such as CFLAGS
AC_PROG_CPP
AC_PROG_CC_C99
AC_PROG_RANLIB

# Reset the externally set CFLAGS after calling AC_PROG*
CFLAGS="$EXTERNAL_CFLAGS"

# Use the C language and compiler for the following checks
AC_LANG([C])

# Checks for header files.
AC_HEADER_STDC
AC_CHECK_HEADERS([stdio.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_TYPE_SIZE_T

# ***************************************************************************
# Documentation
# ***************************************************************************
# Checks for doxygen
#AC_CHECK_PROG(HAVE_DOXYGEN, doxygen, true, false)
#AM_CONDITIONAL(HAVE_DOXYGEN, $HAVE_DOXYGEN)
#if test $HAVE_DOXYGEN = "false"; then
#    AC_MSG_WARN([*** doxygen not found, docs will not be built])
#else
#DX_HTML_FEATURE(OFF)
#DX_CHM_FEATURE(OFF)
#DX_CHI_FEATURE(OFF)
#DX_MAN_FEATURE(OFF)
#DX_RTF_FEATURE(OFF)
#DX_XML_FEATURE(OFF)
#DX_PDF_FEATURE(OFF)
#DX_PS_FEATURE(OFF)
#DX_INIT_DOXYGEN([vox], Doxyfile, docs)
#            
#fi

# Add debug support
AC_ARG_ENABLE(debug,
  AS_HELP_STRING(
    [--enable-debug],
    [enable debugging, default: no]),
    [case "${enableval}" in
      yes) debug=true ;;
      no)  debug=false ;;
      *)   AC_MSG_ERROR([bad value ${enableval} for --enable-debug]) ;;
    esac],
    [debug=false])
AM_CONDITIONAL(DEBUG, test x"$debug" = x"true")
AM_COND_IF(DEBUG,
    AC_DEFINE(DEBUG, 1, [Define to 0 if this is a release build]),
    AC_DEFINE(DEBUG, 0, [Define to 1 or higher if this is a debug build]))

AC_CONFIG_SUBDIRS([cdk])


AC_CONFIG_FILES([Makefile
		cdk/Makefile
                 src/Makefile])

AC_OUTPUT
