
CyanogenMod 11.0 for SEMC es209ra (Xperia X10)
==============================================

Local manifest needed to build cm-11.0 for the Sony Ericsson Xperia X10.


# Instructions How to build:
-----------------------------

# Create the directories

mkdir -p ~/bin
mkdir -p ~/android/system


# Initialize the CyanogenMod source repository

enter this in the terminal
--------------------
cd ~/android/system/
--------------------

then this :
----------------------------------------------------------------
repo init -u git://github.com/CyanogenMod/android.git -b cm-11.0
----------------------------------------------------------------

# Get the required local manifest to build for es209ra

enter this in the terminal
-----------------------------------------------
mkdir -p ~/android/system/.repo/local_manifests
-----------------------------------------------

then this :
------------------------------------------------------------------------------------------------------------------------------------
curl https://raw.githubusercontent.com/XperiaOverlay/local_manifests/CM11/semc.xml > ~/android/system/.repo/local_manifests/semc.xml
------------------------------------------------------------------------------------------------------------------------------------

# Download the source code

enter this in the terminal
---------
repo sync
---------

# Get the CM prebuilts

enter this in the terminal
-----------------------------
cd ~/android/system/vendor/cm
-----------------------------

then this :
---------------
./get-prebuilts
---------------

# Now you have all necessery source code to make a build, to build it follow the instructions bellow 

# Compile:

enter this in the terminal
-------------------
cd ~/android/system
-------------------

then this
-------------------------------------------------
. build/envsetup.sh && lunch cm_es209ra-userdebug
-------------------------------------------------

and this
--------------
make bacon -j8	
--------------


Credits:

Tof37, CMX10, FreeXperia project, LegacyXperia Project
