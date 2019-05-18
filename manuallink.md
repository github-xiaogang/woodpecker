---
layout: subpage
title: Integrating Woodpecker via Linking
---

1.Download <a href="/assets/framework/WoodPeckeriOS.framework.zip">WoodPeckeriOS.framework</a>，then copy WoodPeckeriOS.framework to the root directory of your project in Finder.

<img src="/assets/img/link1.png"/>

2.Open your project in Xcode, then navigate to the Build Setting of your target, and add the following to the Debug configuration of the Framework Search Paths (FRAMEWORK_SEARCH_PATHS) setting:

```
$(inherited) $(SRCROOT)
```
<img src="/assets/img/link2.png"/>

3.Still in the Build Settings tab, add the following to the Debug configuration of the Other Linker Flags (OTHER_LDFLAGS) setting:

```
-ObjC -weak_framework WoodPeckeriOS
```
<img src="/assets/img/link3.png"/>

4.Still in the Build Settings tab, add the following to the Debug configuration of the Runpath Search Paths (LD_RUNPATH_SEARCH_PATHS) if it is not already present:

```
$(inherited) @executable_path/Frameworks
```
<img src="/assets/img/link4.png"/>

5.Select the Build Phases tab and add a new Run Script phase — name it "Integrate Woodpecker" or something suitably descriptive. Paste in the following shell script:

```
# If configuration is not Debug, skip this script.
[ "${CONFIGURATION}" != "Debug" ] && exit 0

FRAMEWORK_FILENAME="WoodPeckeriOS.framework"
FRAMEWORK_PATH="${SRCROOT}/WoodPeckeriOS.framework"

FRAMEWORK_WORKPATH="${CODESIGNING_FOLDER_PATH}/Frameworks"

if [ ! -d "{FRAMEWORK_WORKPATH}" ]; then
    mkdir "${FRAMEWORK_WORKPATH}"
fi

if [ -e "${FRAMEWORK_PATH}" ]; then
    cp -Rf "$FRAMEWORK_PATH" "${FRAMEWORK_WORKPATH}/${FRAMEWORK_FILENAME}"
    if [ -n "${EXPANDED_CODE_SIGN_IDENTITY}" ]; then
        codesign -fs "${EXPANDED_CODE_SIGN_IDENTITY}" "${FRAMEWORK_WORKPATH}/${FRAMEWORK_FILENAME}"
    fi
    echo "${FRAMEWORK_FILENAME} is included in this build, and has been copied to $CODESIGNING_FOLDER_PATH"
else
    echo "${FRAMEWORK_FILENAME} could not be found."
fi
```
<img src="/assets/img/link5.png"/>

6.Now everything is okay, you can enjory Woodpecker now, in Xcode, build and run your application using a scheme that is set to use the Debug configuration. If you are running your iOS application on a device, ensure that it is on the same Wi-Fi network as Mac running Woodpecker.
<br/>

7.Last step, please verify that Woodpecker could not work in Release configuration, you can check the built package and ensure it doesn't contains WoodPeckeriOS.framework in /Frameworks directory.

<br/>
<br/>
<br/>










