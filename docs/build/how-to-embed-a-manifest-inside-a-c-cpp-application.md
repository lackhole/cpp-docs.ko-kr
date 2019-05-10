---
title: '방법: C에 매니페스트 포함 /C++ 응용 프로그램'
ms.date: 05/06/2019
helpviewer_keywords:
- manifests [C++]
- embedding manifests
- makefiles, updating to embed manifest
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
ms.openlocfilehash: ee60620f2815bb20e2d0f3ecec768d99533437a9
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220708"
---
# <a name="how-to-embed-a-manifest-inside-a-cc-application"></a>방법: C에 매니페스트 포함 /C++ 응용 프로그램

대부분의 시나리오에서 올바른 런타임 동작을 사용 하면이 없기 때문에 응용 프로그램 또는 최종 이진 라이브러리의 매니페스트를 포함 하는 것이 좋습니다. 기본적으로 Visual Studio는 프로젝트를 빌드할 때 매니페스트를 포함 하려고 합니다. 자세한 내용은 [Visual Studio에서 매니페스트 생성](manifest-generation-in-visual-studio.md)합니다. 그러나 nmake를 사용 하 여 응용 프로그램을 빌드할 경우 메이크파일에 일부 변경을 수행 해야 합니다. 이 섹션에는 최종 이진 파일에 매니페스트를 자동으로 포함 되도록 메이크파일을 변경 하는 방법을 보여 줍니다.

## <a name="two-approaches"></a>두 가지 방법

응용 프로그램이 나 라이브러리에는 매니페스트를 포함 하는 방법은 두 가지가 있습니다.

- 증분 빌드를 수행 하지 않습니다 하는 경우 빌드 후 단계로 다음과 같은 명령줄을 사용 하 여 매니페스트를 직접 포함할 수 있습니다.

   ```cmd
   mt.exe -manifest MyApp.exe.manifest -outputresource:MyApp.exe;1
   ```

   또는

   ```cmd
   mt.exe -manifest MyLibrary.dll.manifest -outputresource:MyLibrary.dll;2
   ```

   DLL에 대 한 EXE 및 2에 대 한 1을 사용 합니다.

- 증분 빌드를 수행 하는 경우 다음 단계를 사용 합니다.

   - MyApp.exe.manifest 파일을 생성 하기 위해 이진 파일을 연결 합니다.

   - 매니페스트 리소스 파일로 변환 합니다.

   - 다시 연결할 (증분) 이진 파일에 매니페스트 리소스를 포함 합니다.

다음 예제에서는 두 가지 기술을 통합 하는 메이크파일을 변경 하는 방법을 보여 줍니다.

## <a name="makefiles-before"></a>메이크파일 (이전)

MyApp.exe에 하나의 파일에서 작성 된 간단한 응용 프로그램에 대 한 nmake 스크립트를 고려 합니다.

```
# build MyApp.exe
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
```

이 스크립트를 Visual Studio를 사용 하 여 변경 되지 않고 실행 하는 경우 성공적으로 MyApp.exe를 만듭니다. 또한 런타임에 종속 어셈블리를 로드 하는 운영 체제에서 사용할 외부 매니페스트 파일 MyApp.exe.manifest를 만듭니다.

Nmake 스크립트가 MyLibrary.dll 매우 유사 합니다.

```
# build MyLibrary.dll
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
```

## <a name="makefiles-after"></a>메이크파일 (이후)

원래 메이크파일을 4 개의 약간 변경 해야 하는 매니페스트를 포함 하 여 빌드해야 합니다. MyApp.exe 메이크파일:

```
# build MyApp.exe
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_EXE)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

MyLibrary.dll 메이크파일:

```
# build MyLibrary.dll
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_DLL)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2.

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3.

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

이제 메이크파일 실제 작업과 makefile.inc makefile.targ.inc 수행 하는 두 개의 파일을 포함 합니다.

Makefile.inc 만들고를 다음을 복사 합니다.

```
# makefile.inc -- Include this file into existing makefile at the very top.

# _VC_MANIFEST_INC specifies whether build is incremental (1 - incremental).
# _VC_MANIFEST_BASENAME specifies name of a temporary resource file.

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
_VC_MANIFEST_INC=1
_VC_MANIFEST_BASENAME=__VC90.Debug

!else
CPPFLAGS=$(CPPFLAGS) /MD
_VC_MANIFEST_INC=0
_VC_MANIFEST_BASENAME=__VC90

!endif

####################################################
# Specifying name of temporary resource file used only in incremental builds:

!if "$(_VC_MANIFEST_INC)" == "1"
_VC_MANIFEST_AUTO_RES=$(_VC_MANIFEST_BASENAME).auto.res
!else
_VC_MANIFEST_AUTO_RES=
!endif

####################################################
# _VC_MANIFEST_EMBED_EXE - command to embed manifest in EXE:

!if "$(_VC_MANIFEST_INC)" == "1"

#MT_SPECIAL_RETURN=1090650113
#MT_SPECIAL_SWITCH=-notify_resource_update
MT_SPECIAL_RETURN=0
MT_SPECIAL_SWITCH=
_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -out:$(_VC_MANIFEST_BASENAME).auto.manifest $(MT_SPECIAL_SWITCH) & \
if "%ERRORLEVEL%" == "$(MT_SPECIAL_RETURN)" \
rc /r $(_VC_MANIFEST_BASENAME).auto.rc & \
link $** /out:$@ $(LFLAGS)

!else

_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -outputresource:$@;1

!endif

####################################################
# _VC_MANIFEST_CLEAN - command to clean resources files generated temporarily:

!if "$(_VC_MANIFEST_INC)" == "1"

_VC_MANIFEST_CLEAN=-del $(_VC_MANIFEST_BASENAME).auto.res \
    $(_VC_MANIFEST_BASENAME).auto.rc \
    $(_VC_MANIFEST_BASENAME).auto.manifest

!else

_VC_MANIFEST_CLEAN=

!endif

# End of makefile.inc
####################################################
```

만들어서 **makefile.targ.inc** 에 다음을 복사 합니다.

```
# makefile.targ.inc - include this at the very bottom of the existing makefile

####################################################
# Commands to generate initial empty manifest file and the RC file
# that references it, and for generating the .res file:

$(_VC_MANIFEST_BASENAME).auto.res : $(_VC_MANIFEST_BASENAME).auto.rc

$(_VC_MANIFEST_BASENAME).auto.rc : $(_VC_MANIFEST_BASENAME).auto.manifest
    type <<$@
#include <winuser.h>
1RT_MANIFEST"$(_VC_MANIFEST_BASENAME).auto.manifest"
<< KEEP

$(_VC_MANIFEST_BASENAME).auto.manifest :
    type <<$@
<?xml version='1.0' encoding='UTF-8' standalone='yes'?>
<assembly xmlns='urn:schemas-microsoft-com:asm.v1' manifestVersion='1.0'>
</assembly>
<< KEEP

# end of makefile.targ.inc
```

## <a name="see-also"></a>참고자료

[ 프로그램의 매니페스트 생성 이해](understanding-manifest-generation-for-c-cpp-programs.md)
