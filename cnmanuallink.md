---
layout: subpage
title: 手动动态集成
---

1.下载<a href="/assets/framework/WoodPeckeriOS.framework.zip">WoodPeckeriOS.framework</a>，然后将其拷贝到您的项目根目录下（也可以拷贝到其他目录）

<img src="/assets/img/link1.png"/>

2.打开Xcode，导航到Target的Build Setting位置，将Framework Search Paths (`FRAMEWORK_SEARCH_PATHS`) Debug模式的值设置为如下，这一步让Xcode在Build时能找到第1步设置的WoodPeckeriOS.Framework

```
$(inherited) $(SRCROOT)
```
<img src="/assets/img/link2.png"/>

3.在Build Setting中，将Other Linker Flags (`OTHER_LDFLAGS`) Debug模式的值设置为如下，这一步让App在运行时自动加载framework
```
-ObjC -weak_framework WoodPeckeriOS
```
<img src="/assets/img/link3.png"/>

4.在Build Setting，将Runpath Search Paths (`LD_RUNPATH_SEARCH_PATHS`) 的值设置为如下(如果已经存在，则不用重复设置)
```
$(inherited) @executable_path/Frameworks
```
<img src="/assets/img/link4.png"/>

5.导航到Build Phases位置，添加一个Run Script，设置如下脚本（在Debug配置下运行App时，下面脚本将拷贝WoodPeckeriOS.framework到app安装包中）

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

6.现在您可以在Debug模式下使用Woodpecker调试您的App，无需任何代码设置，另外请确认在Release配置下不能正常使用（请检查Release包的/Frameworks目录下不包含WoodPeckeriOS.framework）
<br/>
<br/>
<br/>










