---
title: 미리 컴파일된 헤더 파일
ms.date: 12/10/2018
f1_keywords:
- pch
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
ms.openlocfilehash: 5afda50c43f93baa2d73e6afb68f436560c3243e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826382"
---
# <a name="precompiled-header-files"></a>미리 컴파일된 헤더 파일

Visual Studio에서 새 프로젝트를 만들면를 *미리 컴파일된 헤더 파일* 라는 "pch.h" 프로젝트에 추가 됩니다. (Visual Studio의 이전 버전에서는 파일 호출한 "stdafx.h"입니다.) 파일의 목적은 빌드 프로세스 속도입니다. 모든 안정적인 헤더 파일, 예를 들어 표준 라이브러리 헤더와 같은 `<vector>`, 여기에 포함 해야 합니다. 미리 컴파일된 헤더 또는 포함 하는 모든 파일이 수정 되는 경우에 컴파일됩니다. 만 변경 하면 프로젝트 소스 코드에서 하는 경우 빌드 미리 컴파일된 헤더에 대해 컴파일을 건너뜁니다. 

미리 컴파일된 헤더에 대 한 컴파일러 옵션은 [/Y](reference/y-precompiled-headers.md)합니다. 프로젝트 속성 페이지의 옵션은 아래에 **구성 속성 > C/c + + > 미리 컴파일된 헤더**합니다. 미리 컴파일된 헤더를 사용 하지 않도록 선택할 수 있으며 헤더를 지정할 수 있습니다 파일 이름 및 이름 및 출력 파일의 경로입니다. 

## <a name="custom-precompiled-code"></a>사용자 지정 미리 컴파일된 코드

작성 하는 데 많은 시간이 걸리는 대형 프로젝트에 대 한 사용자 지정 미리 컴파일된 파일을 만드는 것도 고려해볼는 것이 좋습니다. Microsoft C 및 C++ 컴파일러는 인라인 코드를 포함하여 모든 C 또는 C++ 코드를 미리 컴파일하는 옵션을 제공합니다. 이 성능 기능을 사용하여 안정적인 코드 본문을 컴파일하고, 코드의 컴파일된 상태를 파일에 저장하고, 후속 컴파일 중 미리 컴파일된 코드와 아직 개발 중인 코드를 결합할 수 있습니다. 안정적인 코드는 다시 컴파일할 필요가 없기 때문에 각 후속 컴파일 속도가 향상됩니다.

## <a name="when-to-precompile-source-code"></a>소스 코드를 미리 컴파일하는 시기

경우에 특히 컴파일 시간을 줄이려면 개발 주기 동안 미리 컴파일된 코드는 유용 합니다.

- 항상 양의 자주 변경 되지 않는 코드를 사용 합니다.

- 프로그램에는 여러 모듈을 표준 포함 파일 집합과 같은 컴파일 옵션을 사용 하는 모든 구성 됩니다. 모든 파일을 포함 하는 경우 하나의 미리 컴파일된 헤더를 미리 컴파일할 수 있습니다.

첫 번째 컴파일-미리 컴파일된 헤더 (PCH) 파일을 만드는 것, 후속 컴파일 보다 약간 더 오래 걸리면 합니다. 후속 컴파일 미리 컴파일된 코드를 포함 하 여 보다 신속 하 게 진행할 수 있습니다.

C 및 c + + 프로그램을 미리 컴파일할 수 있습니다. C + + 프로그래밍에서는 헤더 파일에 클래스 인터페이스 정보를 구분 하는 것이 있습니다. 나중에 클래스를 사용 하는 프로그램에 이들 헤더 파일을 포함할 수 있습니다. 이러한 헤더를 미리 컴파일하면, 프로그램을 컴파일하는 데 걸리는 시간을 줄일 수 있습니다.

> [!NOTE]
> 소스 파일 당 미리 컴파일된 헤더 (.pch) 파일을 하나만 사용할 수 있지만 프로젝트에 여러 개의.pch 파일을 사용할 수 있습니다.

## <a name="two-choices-for-precompiling-code"></a>코드를 미리 컴파일하기 위한 두 가지 선택 사항

Visual c + +를 사용 하 여 모든 C 또는 c + + 코드를 미리 컴파일할 수 있습니다. 헤더 파일에만 미리 컴파일하도록 제한 되지 않습니다.

계획이 필요 하지만 더 빨라 컴파일 간단한 헤더 파일이 아닌 소스 코드를 미리 컴파일하는 경우.

미리 컴파일하는 작업의 소스 코드를 포함 하려는 경우 또는는 소스 파일 헤더 파일의 공통 집합을 사용 하지만를 동일한 순서로 포함 되지 않습니다 하는 코드를 미리 컴파일하십시오.

미리 컴파일된 헤더 옵션은 [/Yc (미리 컴파일된 헤더 파일 만들기)](reference/yc-create-precompiled-header-file.md) 하 고 [/Yu (미리 컴파일된 헤더 파일 사용)](reference/yu-use-precompiled-header-file.md)합니다. 사용 하 여 **/Yc** 미리 컴파일된 헤더를 만들려고 합니다. 선택적으로 사용할 [hdrstop](../preprocessor/hdrstop.md) pragma **/Yc** 및 소스 코드를 모두 헤더 파일을 미리 컴파일할 수 있습니다. 선택 **/Yu** 를 기존 컴파일에서 기존의 미리 컴파일된 헤더를 사용 합니다. 사용할 수도 있습니다 **/Fp** 사용 하 여는 **/Yc** 하 고 **/Yu** 미리 컴파일된 헤더에 대 한 대체 이름을 제공 하는 옵션입니다.

에 대 한 컴파일러 옵션 참조 항목 **/Yu** 하 고 **/Yc** 개발 환경에서이 기능에 액세스 하는 방법을 설명 합니다.

## <a name="precompiled-header-consistency-rules"></a>미리 컴파일된 헤더의 일관성 규칙

PCH 파일에서 컴퓨터 환경에 대 한 정보 뿐만 아니라 프로그램의 메모리 주소 정보에 포함 하기 때문에 만들어진 컴퓨터의 PCH 파일만 사용 해야 합니다.

## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>미리 컴파일된 헤더의 파일별 사용에 대한 일관성 규칙

합니다 [/Yu](reference/yu-use-precompiled-header-file.md) 컴파일러 옵션을 사용 하는 데는 PCH 파일을 지정할 수 있습니다.

PCH 파일을 사용 하는 경우 컴파일러 가정 동일한 컴파일 환경-일치 하는 컴파일러 옵션, pragma, 및 등을 사용 하는-가 별도로 지정 하지 않으면 PCH 파일을 만들 때 적용 된 것입니다. 컴파일러에서 불일치를 감지 하면 경고를 실행 하 고 가능한 경우 불일치가 식별 합니다. 반드시 이러한 경고 문제가 PCH 파일을 나타내지 않습니다. 단순히 경고 충돌 하는 경우. PCH 파일에 대 한 일관성 요구 사항은 다음 섹션에서 설명 합니다.

### <a name="compiler-option-consistency"></a>컴파일러 옵션 일관성

다음 컴파일러 옵션 PCH 파일을 사용 하는 경우 불일치 경고를 트리거할 수 있습니다.

- 전처리기를 사용 하 여 생성 되는 매크로 (/ D) 옵션 PCH 파일이 생성 한 컴파일 및 현재 컴파일 간에 동일 해야 합니다. 정의 된 상수 상태의 선택 하지 않으면 있지만 이러한 변경 하는 경우 예기치 않은 결과가 발생할 수 있습니다.

- PCH 파일 /E 하 고 /EP 옵션과 작동 하지 않습니다.

- PCH 파일 중 하나는 찾아보기 정보 생성을 사용 하 여 만들어야 (/ FR) 옵션 또는 지역 변수 제외 (/ Fr) 만들어야만 후속 컴파일 PCH 파일 사용 하 여 이러한 옵션을 사용할 수 있습니다.

### <a name="c-70-compatible-z7"></a>C 7.0 호환 (/ Z7)

PCH 파일을 만들 때이 옵션이 적용 되는 경우 PCH 파일을 사용 하는 후속 컴파일 디버깅 정보를 사용할 수 있습니다.

하는 경우 C 7.0 호환 (/ Z7) 옵션이 적용 되지 않습니다 PCH 파일이 생성 되 면, PCH 파일 및/z7을 사용 하는 후속 컴파일에서는 경고가 발생 합니다. 디버깅 정보는 현재.obj 파일에 배치 되며 PCH 파일에 정의 된 로컬 기호는 디버거에서 사용할 수 없습니다.

### <a name="include-path-consistency"></a>포함 경로 일관성

PCH 파일을 만들 때 포함 경로 대 한 내용은 없습니다. PCH 파일을 사용 하는 경우 컴파일러는 항상 현재 컴파일에서 포함 경로 사용 합니다.

### <a name="source-file-consistency"></a>원본 파일 일관성

미리 컴파일된 헤더 파일 사용 (/Yu) 옵션을 지정 하면 컴파일러는 미리 컴파일된 수는 소스 코드에 표시 되는 모든 전처리기 지시문 (pragma 포함)를 무시 합니다. 이러한 전처리기 지시문에 의해 지정 된 컴파일 미리 컴파일된 헤더 파일 만들기 (/Yc) 옵션에 사용 되는 컴파일과 같아야 합니다.

### <a name="pragma-consistency"></a>Pragma 일관성

PCH 파일을 만들 때 일반적으로 처리 하는 Pragma 이후에 PCH 파일이 사용 하 여 파일을 영향을 줍니다. 합니다 `comment` 고 `message` pragma 컴파일의 나머지 영향을 주지 않습니다.

이러한 pragma PCH 파일 내에서 코드를만 영향을 줍니다. 이후에 PCH 파일을 사용 하는 코드는 영향을 주지 않습니다.

||||
|-|-|-|
|`comment`|`page`|`subtitle`|
|`linesize`|`pagesize`|`title`|
|`message`|`skip`||

이러한 pragma 미리 컴파일된 헤더의 일부로 유지 되 고 미리 컴파일된 헤더를 사용 하는 컴파일의 나머지 부분에 영향을 줍니다.

||||
|-|-|-|
|`alloc_text`|`include_alias`|`pack`|
|`auto_inline`|`init_seg`|`pointers_to_members`|
|`check_stack`|`inline_depth`|`setlocale`|
|`code_seg`|`inline_recursion`|`vtordisp`|
|`data_seg`|`intrinsic`|`warning`|
|`function`|`optimize`||

## <a name="consistency-rules-for-yc-and-yu"></a>/Yc 및 /Yu에 대한 일관성 규칙

/Yc 또는 /Yu를 사용 하 여 만든 미리 컴파일된 헤더를 사용 하면 컴파일러는 PCH 파일을 만들 때 존재 하는 현재 컴파일 환경을 비교 합니다. 이전 (일치 하는 컴파일러 옵션, pragma, 및 등을 사용 하 여) 현재 컴파일의 일관 된 환경을 지정 해야 합니다. 컴파일러에서 불일치를 감지 하면 경고를 실행 하 고 가능한 경우 불일치가 식별 합니다. 이러한 경고 PCH 파일을 사용 하 여 문제를 반드시 나타내지 않습니다. 단순히 경고 충돌 하는 경우. 다음 섹션에서는 미리 컴파일된 헤더에 대 한 일관성 요구 사항에 설명 합니다.

### <a name="compiler-option-consistency"></a>컴파일러 옵션 일관성

이 표에서 미리 컴파일된 헤더를 사용 하는 경우 불일치 경고를 발생 시킬 수 있는 컴파일러 옵션을 보여 줍니다.

|옵션|이름|규칙|
|------------|----------|----------|
|/D|상수 및 매크로 정의 합니다.|미리 컴파일된 헤더를 생성 한 컴파일 및 현재 컴파일 간에 동일 해야 합니다. 정의 된 상수 상태의 선택 하지 않으면 하지만 파일에 변경 된 상수 값에 의존 하는 경우 예기치 않은 결과가 발생할 수 있습니다.|
|/EP 또는 /E|전처리기 출력을 표준 출력에 복사|미리 컴파일된 헤더 /E 또는 /EP 옵션과 함께 작동 하지 않습니다.|
|/Fr 또는 /FR|Microsoft 소스 브라우저 정보 생성|/Yu 옵션을 사용 하 여 유효한 /Fr 및 /FR 옵션는 또한 받아야 적용 미리 컴파일된 헤더를 만들 때. 미리 컴파일된 헤더를 사용 하는 후속 컴파일도 원본 브라우저 정보를 생성 합니다. 브라우저 정보 단일.sbr 파일에 배치 되 고 CodeView 정보가와 동일한 방식으로 다른 파일에서 참조 됩니다. 소스 브라우저 정보의 배치를 재정의할 수 없습니다.|
|/ GA, /GD, /GE, /Gw, 또는 /GW|Windows 프로토콜 옵션|미리 컴파일된 헤더를 생성 한 컴파일 및 현재 컴파일 간에 동일 해야 합니다. 이러한 옵션이 서로 다른 경우 경고 메시지가 발생 합니다.|
|/ZI|완전 한 디버깅 정보 생성|미리 컴파일된 헤더를 만들 때이 옵션이 적용 되는 미리 컴파일을 사용 하는 후속 컴파일 디버깅 정보를 사용할 수 있습니다. /Zi 적용 되지 않습니다 미리 컴파일된 헤더를 만들 때, 하는 경우와 /Zi 옵션을 사용 하는 후속 컴파일에서는 경고가 발생 합니다. 디버깅 정보는 현재 개체 파일에 배치 되며 미리 컴파일된 헤더에 정의 된 로컬 기호는 디버거에서 사용할 수 없습니다.|

> [!NOTE]
>  미리 컴파일된 헤더 기능 C 및 c + + 소스 파일에만 사용 하 여 위한 것입니다.

## <a name="using-precompiled-headers-in-a-project"></a>프로젝트에 미리 컴파일된 헤더 사용

이전 섹션에서는 미리 컴파일된 헤더의 개요를 제공 합니다. /Yc 및 /Yu를 /Fp 옵션 및 [hdrstop](../preprocessor/hdrstop.md) pragma입니다. 이 섹션에서는 프로젝트에 수동 미리 컴파일된 헤더 옵션을 사용 하는 방법 설명 예제 메이크파일 및 관리 하는 코드를 사용 하 여 종료 됩니다.

프로젝트에 수동 미리 컴파일된 헤더 옵션을 사용 하 여 다른 방법에 대 한 Visual c + +의 기본 설치 중에 만든 MFC\SRC 디렉터리에 있는 메이크파일 중 하나를 조사 합니다. 이러한 메이크파일 여기에 제시 된 것과 비슷한 방법 데 Microsoft 프로그램 유지 관리 유틸리티 (NMAKE) 매크로 사용 있고 빌드 프로세스의 제어를 제공 합니다.

## <a name="pch-files-in-the-build-process"></a>빌드 프로세스의 PCH 파일

소프트웨어 프로젝트의 코드 베이스는 일반적으로 여러 C 또는 c + + 소스 파일, 개체 파일, 라이브러리 및 헤더 파일에 포함 됩니다. 일반적으로 메이크파일을 이러한 요소의 결합 한 실행 파일을 조정합니다. 다음 그림은 미리 컴파일된 헤더 파일을 사용 하는 메이크파일의 구조를 보여줍니다. NMAKE 매크로 이름 및 파일 이름을이 다이어그램에 있는 예제 코드와 일치 되 [PCH 용 샘플 메이크파일](#sample-makefile-for-pch) 하 고 [PCH에 대 한 예제 코드](#example-code-for-pch)합니다.

그림 3 개의 다이어그램 장치를 사용 하 여 빌드 프로세스의 흐름을 보여 줍니다. 사각형을 나타내는 명명 된 각 파일 또는 매크로 세 가지 매크로 하나 이상의 파일을 나타냅니다. 음영 처리 된 영역은 각 컴파일 또는 링크 동작을 나타냅니다. 화살표는 컴파일 또는 연결 프로세스 하는 동안 결합 되는 파일 및 매크로 보여 줍니다.

![미리 컴파일된 헤더 파일을 사용 하는 메이크파일의 구조](media/vc30ow1.gif "미리 컴파일된 헤더 파일을 사용 하는 메이크파일의 구조") <br/>
미리 컴파일된 헤더 파일을 사용하는 메이크파일의 구조

다이어그램의 맨 위에 있는 모두 STABLEHDRS 경계와 하지 컴파일해야 할 파일을 나열할 수 없는 NMAKE 매크로입니다. 이러한 파일 명령 문자열에 의해 컴파일됩니다.

`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`

미리 컴파일된 헤더 파일 (STABLE.pch) 존재 하지 않는 경우에 또는 두 매크로에 나열 된 파일을 변경한 경우. 두 경우 모두 미리 컴파일된 헤더 파일에는 STABLEHDRS 매크로에서 나열 된 파일의 코드가 포함 됩니다. 경계 매크로에서 미리 컴파일된 마지막 파일을 나열 합니다.

헤더 파일 또는 C 또는 c + + 소스 파일에 이러한 매크로 목록의 파일 수 있습니다. (C 및 c + + 모듈을 사용 하 여 단일 PCH 파일을 사용할 수 없습니다.) 사용할 수 있는 참고 합니다 **hdrstop** 미리 컴파일 경계 파일 내에서 특정 시점을 중지 하는 매크로입니다. 참조 [hdrstop](../preprocessor/hdrstop.md) 자세한 내용은 합니다.

다이어그램에 계속 APPLIB.obj 최종 응용 프로그램에 사용 된 지원 코드를 나타냅니다. APPLIB.cpp에서 만든 하 고 파일 UNSTABLEHDRS 매크로에 나열 된 미리 컴파일된 코드를 미리 컴파일된 헤더입니다.

MYAPP.obj 최종 응용을 프로그램을 나타냅니다. MYAPP.cpp에서 만든 하 고 파일 UNSTABLEHDRS 매크로에 나열 된 미리 컴파일된 코드를 미리 컴파일된 헤더입니다.

마지막으로, 실행 파일 (MYAPP 합니다. EXE) OBJ 매크로 (APPLIB.obj 및 MYAPP.obj)에 나열 된 파일을 연결 하 여 만들어집니다.

## <a name="sample-makefile-for-pch"></a>PCH용 샘플 메이크파일

다음 메이크파일 매크로 사용 및! 경우에 적합 합니다! 다른! ENDIF 프로젝트 자체 적응을 간소화 하기 위해 흐름 제어 명령 구조입니다.

```NMAKE
# Makefile : Illustrates the effective use of precompiled
#            headers in a project
# Usage:     NMAKE option
# option:    DEBUG=[0|1]
#            (DEBUG not defined is equivalent to DEBUG=0)
#
OBJS = myapp.obj applib.obj
# List all stable header files in the STABLEHDRS macro.
STABLEHDRS = stable.h another.h
# List the final header file to be precompiled here:
BOUNDRY = stable.h
# List header files under development here:
UNSTABLEHDRS = unstable.h
# List all compiler options common to both debug and final
# versions of your code here:
CLFLAGS = /c /W3
# List all linker options common to both debug and final
# versions of your code here:
LINKFLAGS = /NOD /ONERROR:NOEXE
!IF "$(DEBUG)" == "1"
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f
LINKFLAGS = $(LINKFLAGS) /COD
LIBS      = slibce
!ELSE
CLFLAGS   = $(CLFLAGS) /Oselg /Gs
LINKFLAGS = $(LINKFLAGS)
LIBS      = slibce
!ENDIF
myapp.exe: $(OBJS)
    link $(LINKFLAGS) @<<
$(OBJS), myapp, NUL, $(LIBS), NUL;
<<
# Compile myapp
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp
# Compile applib
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp
# Compile headers
stable.pch : $(STABLEHDRS)
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp
```

"구조체의는 메이크파일을 사용 하는 미리 컴파일된 헤더 파일" 그림에 나오는 STABLEHDRS, 경계, 및 UNSTABLEHDRS 매크로 외 [빌드 프로세스의 PCH 파일](#pch-files-in-the-build-process),이 메이크파일 CLFLAGS 매크로 및는 LINKFLAGS 제공 매크로입니다. 이러한 매크로 사용 하 여 컴파일러 및 디버그 또는 응용 프로그램의 실행 파일의 최종 버전을 빌드 하는지 여부를 적용 하는 링커 옵션을 나열 해야 합니다. 이기도 LIBS 매크로 라이브러리를 나열할 수 프로젝트가 필요 합니다.

메이크파일을 사용 하 여! 경우에 적합 합니다! 다른! ENDIF NMAKE 명령줄에서 디버그 기호를 정의 하는지 여부를 검색 하려면:

```NMAKE
NMAKE DEBUG=[1|0]
```

이 기능을 사용 하면 개발 하는 동안 동일한 메이크파일을 사용 하 고 프로그램의 최종 버전은-디버그를 사용 하 여 최종 버전에 대 한 0입니다. 다음 명령줄은 동일 합니다.

```NMAKE
NMAKE
NMAKE DEBUG=0
```

메이크파일에 대 한 자세한 내용은 참조 하세요. [NMAKE 참조](reference/nmake-reference.md)합니다. 도 참조 하세요 [MSVC 컴파일러 옵션](reference/compiler-options.md) 하며 [MSVC 링커 옵션](reference/linker-options.md)합니다.

## <a name="example-code-for-pch"></a>PCH에 대한 예제 코드

다음 소스 파일에 설명 된 메이크파일에 되 [빌드 프로세스의 PCH 파일](#pch-files-in-the-build-process) 하 고 [PCH 용 샘플 메이크파일](#sample-makefile-for-pch)합니다. 참고 주석을 중요 한 정보를 포함 합니다.

```cpp
// ANOTHER.H : Contains the interface to code that is not
//             likely to change.
//
#ifndef __ANOTHER_H
#define __ANOTHER_H
#include<iostream>
void savemoretime( void );
#endif // __ANOTHER_H
```

```cpp
// STABLE.H : Contains the interface to code that is not likely
//            to change. List code that is likely to change
//            in the makefile's STABLEHDRS macro.
//
#ifndef __STABLE_H
#define __STABLE_H
#include<iostream>
void savetime( void );
#endif // __STABLE_H
```

```cpp
// UNSTABLE.H : Contains the interface to code that is
//              likely to change. As the code in a header
//              file becomes stable, remove the header file
//              from the makefile's UNSTABLEHDR macro and list
//              it in the STABLEHDRS macro.
//
#ifndef __UNSTABLE_H
#define __UNSTABLE_H
#include<iostream.h>
void notstable( void );
#endif // __UNSTABLE_H
```

```cpp
// APPLIB.CPP : This file contains the code that implements
//              the interface code declared in the header
//              files STABLE.H, ANOTHER.H, and UNSTABLE.H.
//
#include"another.h"
#include"stable.h"
#include"unstable.h"
// The following code represents code that is deemed stable and
// not likely to change. The associated interface code is
// precompiled. In this example, the header files STABLE.H and
// ANOTHER.H are precompiled.
void savetime( void )
    { cout << "Why recompile stable code?\n"; }
void savemoretime( void )
    { cout << "Why, indeed?\n\n"; }
// The following code represents code that is still under
// development. The associated header file is not precompiled.
void notstable( void )
    { cout << "Unstable code requires"
            << " frequent recompilation.\n";
    }
```

```cpp
// MYAPP.CPP : Sample application
//             All precompiled code other than the file listed
//             in the makefile's BOUNDRY macro (stable.h in
//             this example) must be included before the file
//             listed in the BOUNDRY macro. Unstable code must
//             be included after the precompiled code.
//
#include"another.h"
#include"stable.h"
#include"unstable.h"
int main( void )
{
    savetime();
    savemoretime();
    notstable();
}
```

## <a name="see-also"></a>참고자료

[C/C++ 빌드 참조](reference/c-cpp-building-reference.md)<br/>
[MSVC 컴파일러 옵션](reference/compiler-options.md)
