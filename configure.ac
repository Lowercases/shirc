#
#   shirc -- IRC support for shell scripting
#   Copyright (C) 2009, 2010  Ignacio Nin
#
#   This program is free software; you can redistribute it and/or modify
#   it under the terms of the GNU General Public License as published by
#   the Free Software Foundation; either version 2 of the License, or
#   (at your option) any later version.
#
#   This program is distributed in the hope that it will be useful,
#   but WITHOUT ANY WARRANTY; without even the implied warranty of
#   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#   GNU General Public License for more details.
#
#   You should have received a copy of the GNU General Public License
#   along with this program; if not, write to the Free Software
#   Foundation, Inc.,
#   51 Franklin Street, Fifth Floor, Boston, MA  02110-1301  USA
#

#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.61)
AC_INIT([shirc], [0.0.3], [ignacio.nin@adinet.com.uy])
AM_INIT_AUTOMAKE([dist-bzip2 no-dist-gzip])

# Checks for programs.
AC_CHECK_PROG(BASH, bash, [not-found])
[
if test "x$BASH" == "xnot-found"
then
    echo bash not found -- please install or specify
    exit 1
fi
]

AC_CHECK_PROG(NC, nc, [nc])
[
if test "x$NC" != "xnc"
then
    echo nc $NC not found -- please install or specify
    exit 1
fi
]

AC_SUBST([NC], [$NC])

AC_CHECK_PROG(SED, sed, [sed])
[
if test "x$SED" != "xsed"
then
    echo sed not found -- please install
    exit 1
fi
]

# Checks for libraries.

# Checks for header files.

# Checks for typedefs, structures, and compiler characteristics.

# Checks for library functions.

if test "x$prefix" == "xNONE"
then
    AC_SUBST(PKGDATADIR, $ac_default_prefix/share/$PACKAGE_NAME)
else
    AC_SUBST(PKGDATADIR, $prefix/share/$PACKAGE_NAME)
fi

### Some definitions to avoid computing time later.

# uptime() builtin time calculation
AC_SUBST([SHIRCDEF_SECPERYEAR], [`expr 60 \* 60 \* 24 \* 365`])
AC_SUBST([SHIRCDEF_SECPERMONTH], [`expr 60 \* 60 \* 24 \* 31`])
AC_SUBST([SHIRCDEF_SECPERDAY], [`expr 60 \* 60 \* 24`])
AC_SUBST([SHIRCDEF_SECPERHOUR], [`expr 60 \* 60`])    # :P
AC_SUBST([SHIRCDEF_SECPERMINUTE], [60])               # :P :P

AC_CONFIG_FILES([Makefile
                 src/Makefile

                 src/shirc.sh
                 src/callback.sh
                 src/fifo.sh
                 src/ignore.sh
                 src/irc.sh
                 src/messages.sh
                 src/state.sh
                 src/text.sh

                 src/shircbot
                ])
AC_OUTPUT
