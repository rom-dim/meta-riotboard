# This requires the meta-qt5 layer in your bblayers.conf !!!!

# source: http://wiki.wandboard.org/index.php/Building_Qt5_using_yocto_on_Wandboard
# If you plan to use Qt5 eglfs plugin for accelerated graphics using the framebuffer,
# you need to discard X11 and wayland so the proper graphics drivers get included.
# To achieve this add the following to your conf/local.conf :
# DISTRO_FEATURES_remove = "x11 wayland"


DESCRIPTION = "A Qt 5.5.1+ image. Tailored for the UDOO boards"

IMAGE_FEATURES += "splash ssh-server-openssh package-management debug-tweaks"

QT_TOOLS = " \
    qtbase-fonts \
    qtbase-plugins \
    qtbase-tools \
    qtbase-examples  \
    qtdeclarative \
    qtdeclarative-plugins \
    qtdeclarative-tools \
    qtdeclarative-qmlplugins \
    qtsensors \
    qtimageformats-plugins \
    qtsystems \
    qtsystems-tools \
    qtsystems-qmlplugins \
    qtscript \
    qtgraphicaleffects-qmlplugins \
    qtconnectivity-qmlplugins \
    qtlocation-plugins \
    qtlocation-qmlplugins \
    cinematicexperience \
    qt5-env \
"

PACKAGECONFIG_append_pn-qtbase = " accessibility"

REMOTE_DEBUGGING = " \
    gdbserver \
    openssh-sftp-server \
"

IMAGE_INSTALL = "\
    packagegroup-core-boot \
    packagegroup-base \
    ${QT_TOOLS} \
    ${REMOTE_DEBUGGING} \
    cairo pango fontconfig freetype pulseaudio dbus \
    alsa-lib alsa-tools alsa-state fsl-alsa-plugins \
"

inherit core-image

# for populate_sdk to create a valid toolchain
inherit populate_sdk_qt5

