---
title: WINVER 및 _WIN32_WINNT 수정
ms.date: 09/04/2017
helpviewer_keywords:
- WINVER in an upgraded Visual Studio C++ project
- _WIN32_WINNT in an upgraded Visual Studio C++ project
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
ms.openlocfilehash: a624118bdd192c5ec677be81f0b410d2392e62e9
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65449078"
---
# <a name="modifying-winver-and-win32winnt"></a>WINVER 및 _WIN32_WINNT 수정

Visual C++에서는 더 이상 Windows 95, Windows 98, Windows ME, Windows NT 또는 Windows 2000을 대상으로 지정할 수 없습니다. **WINVER** 또는 **_WIN32_WINNT** 매크로가 이러한 Windows 버전 중 하나에 할당되어 있으면 해당 매크로를 수정해야 합니다. **WINVER** 또는 **_WIN32_WINNT** 매크로가 더 이상 지원되지 않는 Windows 버전에 할당되어 있는 경우 이전 버전의 Visual C++를 사용하여 만든 프로젝트를 업그레이드하면 해당 매크로와 관련된 컴파일 오류가 표시될 수 있습니다.

## <a name="remarks"></a>주의

매크로를 수정하려면 헤더 파일(예: Windows를 대상으로 하는 프로젝트를 만들 때 포함된 targetver.h)에서 다음 줄을 추가합니다.

```C
#define WINVER 0x0A00
#define _WIN32_WINNT 0x0A00
```

그러면 Windows 10 운영 체제가 대상으로 지정됩니다. 이러한 값은 Windows 헤더 파일 SDKDDKVer.h에 포함되어 있습니다. 이 헤더 파일은 각 Windows 버전의 매크로도 정의합니다. SDKDDKVer.h를 포함하기 전에 #define 문을 추가해야 합니다. SDKDDKVer.h의 Windows 10 버전에서 각 Windows 버전의 값을 인코드하는 줄은 다음과 같습니다.

```C
//
// _WIN32_WINNT version constants
//
#define _WIN32_WINNT_NT4                    0x0400 // Windows NT 4.0
#define _WIN32_WINNT_WIN2K                  0x0500 // Windows 2000
#define _WIN32_WINNT_WINXP                  0x0501 // Windows XP
#define _WIN32_WINNT_WS03                   0x0502 // Windows Server 2003
#define _WIN32_WINNT_WIN6                   0x0600 // Windows Vista
#define _WIN32_WINNT_VISTA                  0x0600 // Windows Vista
#define _WIN32_WINNT_WS08                   0x0600 // Windows Server 2008
#define _WIN32_WINNT_LONGHORN               0x0600 // Windows Vista
#define _WIN32_WINNT_WIN7                   0x0601 // Windows 7
#define _WIN32_WINNT_WIN8                   0x0602 // Windows 8
#define _WIN32_WINNT_WINBLUE                0x0603 // Windows 8.1
#define _WIN32_WINNT_WINTHRESHOLD           0x0A00 // Windows 10
#define _WIN32_WINNT_WIN10                  0x0A00 // Windows 10
```

찾고 있는 SDKDDKVer.h의 복사본에 나열된 이러한 모든 Windows 버전이 표시되지 않는 경우 이전 버전의 Windows SDK를 사용하고 있을 수 있습니다. 기본적으로 Visual Studio 2017의 Win32 프로젝트는 Windows 10 SDK를 사용합니다.

> [!NOTE]
> 내부 MFC 헤더를 애플리케이션에 포함하는 경우에는 값 작동 여부가 보장되지 않습니다.

`/D` 컴파일러 옵션을 사용하여 이 매크로를 정의할 수도 있습니다. 자세한 내용은 [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md)을 참조하세요.

이러한 매크로의 의미에 대한 자세한 내용은 [Windows 헤더 사용](/windows/desktop/WinProg/using-the-windows-headers)을 참조하세요.

## <a name="see-also"></a>참고 항목

[Visual C++ 변경 기록](../porting/visual-cpp-change-history-2003-2015.md)
