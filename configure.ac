dnl Process this file with autoconf to produce a configure script.
AC_PREREQ(2.59)
AC_INIT(alsa-ucm-conf, 0.0.9)

AC_CONFIG_MACRO_DIR([m4])

AC_CANONICAL_HOST
AM_INIT_AUTOMAKE

dnl *************************************************
AM_CONDITIONAL([INSTALL_M4], [test -n "${ACLOCAL}"])

# Test for new silent rules and enable only if they are available
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

AC_PREFIX_DEFAULT(/usr)

dnl Checks for programs.

AC_PROG_INSTALL

test "x$prefix" = xNONE && prefix=$ac_default_prefix

dnl ALSA configuration directory
AC_ARG_WITH(configdir,
    AS_HELP_STRING([--with-configdir=dir],
	[path where ALSA config files are stored]),
    confdir="$withval", confdir="")
if test -z "$confdir"; then
    eval dir="$datadir"
    case "$dir" in
    /*) ;;
    *) dir="$prefix/share"
    esac
    confdir="$dir/alsa"
fi
ALSA_CONFIG_DIR="$confdir"
AC_DEFINE_UNQUOTED(ALSA_CONFIG_DIR, "$confdir", [directory containing ALSA configuration database])
AC_SUBST(ALSA_CONFIG_DIR)

topology_available=""
AC_ARG_ENABLE(topology_build,
 AS_HELP_STRING([--disable-topology-build], [Disable topology building via topology-build]),
 topology_build="$enableval", topology_build="yes")
if test "$topology_build" = "yes"; then
  AC_CHECK_PROG([topology_available], [alsatplg], [yes])
fi
AM_CONDITIONAL(BUILD_TOPOLOGY, test x"$topology_available" = xyes)

dnl topology configuration directory
AC_ARG_WITH(topologydir,
    AS_HELP_STRING([--with-topologydir=dir],
	[path where topology files are stored]),
    topodir="$withval", topodir="")
if test -z "$topodir"; then
    eval dir="$datadir"
    case "$dir" in
    /*) ;;
    *) dir="$prefix/share"
    esac
    topodir="$dir/alsa/topology"
fi
TOPOLOGY_CONFIG_DIR="$topodir"
AC_DEFINE_UNQUOTED(TOPOLOGY_CONFIG_DIR, "$topodir", [directory containing topology files])
AC_SUBST(TOPOLOGY_CONFIG_DIR)

AC_OUTPUT(Makefile src/Makefile \
          src/ucm/Makefile \
	  src/ucm/ASUSTeKCOMPUTERINC.-T100HAN-1.0-T100HAN/Makefile \
	  src/ucm/broadwell-rt286/Makefile \
	  src/ucm/broxton-rt298/Makefile \
	  src/ucm/bytcht-cx2072x/Makefile \
	  src/ucm/bytcht-es8316/Makefile \
	  src/ucm/bytcht-es8316-mono-spk-in1-mic/Makefile \
	  src/ucm/bytcht-es8316-mono-spk-in2-mic/Makefile \
	  src/ucm/bytcht-es8316-stereo-spk-in1-mic/Makefile \
	  src/ucm/bytcht-es8316-stereo-spk-in2-mic/Makefile \
	  src/ucm/bytcr-rt5640/Makefile \
	  src/ucm/bytcr-rt5640-mono-spk-dmic1-mic/Makefile \
	  src/ucm/bytcr-rt5640-mono-spk-in1-mic/Makefile \
	  src/ucm/bytcr-rt5640-mono-spk-in3-mic/Makefile \
	  src/ucm/bytcr-rt5640-stereo-spk-dmic1-mic/Makefile \
	  src/ucm/bytcr-rt5640-stereo-spk-in1-mic/Makefile \
	  src/ucm/bytcr-rt5640-stereo-spk-in3-mic/Makefile \
	  src/ucm/bytcr-rt5651/Makefile \
	  src/ucm/bytcr-rt5651-mono-spk-in1-mic/Makefile \
	  src/ucm/bytcr-rt5651-mono-spk-in2-mic/Makefile \
	  src/ucm/bytcr-rt5651-mono-spk-in2-mic-hp-swapped/Makefile \
	  src/ucm/bytcr-rt5651-stereo-spk-dmic-mic/Makefile \
	  src/ucm/bytcr-rt5651-stereo-spk-in1-mic/Makefile \
	  src/ucm/bytcr-rt5651-stereo-spk-in2-mic/Makefile \
	  src/ucm/bytcr-rt5651-stereo-spk-in12-mic/Makefile \
	  src/ucm/chtnau8824/Makefile \
	  src/ucm/chtrt5645/Makefile \
	  src/ucm/chtrt5645-mono-speaker-analog-mic/Makefile \
	  src/ucm/chtrt5650/Makefile \
	  src/ucm/cube-i1_TF-Defaultstring-CherryTrailCR/Makefile \
	  src/ucm/DAISY-I2S/Makefile \
	  src/ucm/DB410c/Makefile \
	  src/ucm/DB820c/Makefile \
	  src/ucm/Dell-WD15-Dock/Makefile \
	  src/ucm/GoogleNyan/Makefile \
	  src/ucm/gpd-win-pocket-rt5645/Makefile \
	  src/ucm/HDAudio-Gigabyte-ALC1220DualCodecs/Makefile \
	  src/ucm/HDAudio-Lenovo-DualCodecs/Makefile \
	  src/ucm/kblrt5660/Makefile \
	  src/ucm/LENOVO-80XF-LenovoMIIX320_10ICR-LNVNB161216/Makefile \
	  src/ucm/PandaBoard/Makefile \
	  src/ucm/PandaBoardES/Makefile \
	  src/ucm/PAZ00/Makefile \
	  src/ucm/PIPO-W2S-Defaultstring-CherryTrailCR/Makefile \
	  src/ucm/SDP4430/Makefile \
	  src/ucm/skylake-rt286/Makefile \
	  src/ucm/TECLAST-X80Pro-Defaultstring-CherryTrailCR/Makefile \
	  src/ucm/tegraalc5632/Makefile \
	  src/ucm/VEYRON-I2S/Makefile \
	  src/ucm/codecs/Makefile \
	  src/ucm/codecs/cx2072x/Makefile \
	  src/ucm/codecs/es8316/Makefile \
	  src/ucm/codecs/nau8824/Makefile \
	  src/ucm/codecs/rt5640/Makefile \
	  src/ucm/codecs/rt5645/Makefile \
	  src/ucm/codecs/rt5651/Makefile \
	  src/ucm/platforms/Makefile \
	  src/ucm/platforms/bytcr/Makefile \
	  src/topology/Makefile \
	  src/topology/broadwell/Makefile \
	  src/topology/bxtrt298/Makefile \
	  src/topology/sklrt286/Makefile \
	  src/topology/sklrt286/broadwell/Makefile \
	  src/topology/sklrt286/bxtrt298/Makefile)
