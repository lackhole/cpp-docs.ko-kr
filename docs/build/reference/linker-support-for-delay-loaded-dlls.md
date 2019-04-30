---
title: 링커의 지연 로드된 DLL 지원
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
ms.openlocfilehash: b6e514a6b13aced4fcd765df091810504f948588
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176254"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>링커의 지연 로드된 DLL 지원

MSVC 링커는 이제 Dll의 지연된 로드를 지원합니다. 이 줄여 줍니다 Windows SDK 함수를 사용 해야 **LoadLibrary** 하 고 **GetProcAddress** DLL 지연 로드를 구현 합니다.

Visual 하기 전에 C++ 6.0 런타임 시 DLL을 로드 하는 유일한 방법은 사용해 **LoadLibrary** 및 **GetProcAddress**; 운영 체제 DLL을 로드 하면 실행 파일 또는 로드 된 DLL를 사용 하 여 합니다.

시각적 개체를 사용 하 여 시작 C++ 6.0에서는 암시적으로 DLL에 링크 하는 경우, 링커 옵션을 제공 지연 로드할 DLL 프로그램 DLL의 함수를 호출할 때까지 합니다.

응용 프로그램을 지연 시킬 수를 사용 하 여 DLL을 로드 합니다 [/DELAYLOAD (가져오기 로드 지연)](delayload-delay-load-import.md) 도우미 함수를 사용 하 여 링커 옵션 (기본 시각적 개체에서 제공 하는 구현 C++). 도우미 함수를 호출 하 여 런타임 시 DLL을 로드할 됩니다 **LoadLibrary** 하 고 **GetProcAddress** 있습니다.

DLL 지연 로드 하는 경우를 고려해 야 합니다.

- 프로그램은 DLL의 함수를 호출할 수 있습니다.

- 프로그램 실행 년 말에 DLL에서 함수 호출 되지 않을 수 있습니다.

DLL의 지연 된 로드 중 빌드 중 지정할 수는 있습니다. EXE 또는 합니다. DLL 프로젝트입니다. 입니다. 하나 이상의 Dll의 로드를 지연 시키는 DLL 프로젝트 호출 하지 않습니다 자체 지연 로드 된 진입점 Dllmain에서.

다음 항목에서는 Dll 지연 로드를 설명 합니다.

- [지연 로드할 DLL 지정](specifying-dlls-to-delay-load.md)

- [지연 로드된 DLL의 명시적 언로드](explicitly-unloading-a-delay-loaded-dll.md)

- [지연 로드된 DLL에 대한 모든 가져오기 로드](loading-all-imports-for-a-delay-loaded-dll.md)

- [가져오기 바인딩](binding-imports.md)

- [오류 처리 및 알림](error-handling-and-notification.md)

- [지연 로드된 가져오기 덤프](dumping-delay-loaded-imports.md)

- [DLL 지연 로드의 제약 조건](constraints-of-delay-loading-dlls.md)

- [도우미 함수 이해](understanding-the-helper-function.md)

- [사용자 도우미 함수 개발](developing-your-own-helper-function.md)

## <a name="see-also"></a>참고자료

[Visual C++의 DLL](../dlls-in-visual-cpp.md)<br/>
[MSVC 링커 참조](linking.md)
