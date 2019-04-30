---
title: 링커 도구 경고 LNK4210
ms.date: 11/04/2016
f1_keywords:
- LNK4210
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
ms.openlocfilehash: 75376129ce0033c717a4da3074cee9de132d357d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395068"
---
# <a name="linker-tools-warning-lnk4210"></a>링커 도구 경고 LNK4210

> 섹션 *섹션* exists, 있습니다 수 수 처리 되지 않은 정적 이니셜라이저 또는 종결자

## <a name="remarks"></a>설명

일부 코드는 정적 이니셜라이저 또는 종결자를 도입 했습니다 있지만 VCRuntime 라이브러리 시작 코드 또는 (정적 이니셜라이저 또는 종결자를 실행 해야 함)는 해당 하는 응용 프로그램을 시작할 때 실행 되지 않습니다. 정적 이니셜라이저 또는 종결자를 필요로 하는 코드의 몇 가지 예는 다음과 같습니다.

- 생성자, 소멸자 또는 가상 함수 테이블을 사용 하 여 전역 클래스 변수입니다.

- 전역 변수는 비 컴파일 시간 상수를 사용 하 여 초기화 합니다.

이 문제를 해결 하려면 다음 중 하나를 시도 합니다.

- 정적 이니셜라이저를 사용 하 여 모든 코드를 제거 합니다.

- 사용 하지 마세요 [/NOENTRY](../../build/reference/noentry-no-entry-point.md)합니다. /NOENTRY를 제거한 후에 제거 해야 수도 [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) 링커 명령줄에서.

- 빌드 /MT을 사용 하는 경우 링커 명령줄에 libcmt.lib, libvcruntime.lib 및 libucrt.lib를 추가 합니다. /MTd를 사용 하는 빌드 경우 libcmtd.lib, vcruntimed.lib입니다 및 libucrtd.lib이 추가 합니다.

- /Clr에서 이동 하는 경우: 순수 컴파일을 /clr을 제거 합니다 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 링커 줄에서 옵션입니다. 이 CRT 초기화를 활성화 하 고 응용 프로그램 시작 시 실행 될 정적 이니셜라이저를 허용 합니다. **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

합니다 [/GS](../../build/reference/gs-buffer-security-check.md) 컴파일러 옵션으로 초기화 작업을 수행 합니다 `__security_init_cookie` 함수입니다. 이 초기화에서 실행 되는 VCRuntime 라이브러리 시작 코드에는 기본적으로 제공 됩니다 `_DllMainCRTStartup`합니다.

- /ENTRY를 사용 하 여 프로젝트를 빌드하고 및 /ENTRY 전달 되는 경우 함수 이외의 `_DllMainCRTStartup`, 함수를 호출 해야 합니다 `_CRT_INIT` CRT를 초기화 합니다. DLL /GS를 사용 하 여 정적 이니셜라이저 등이 필요 하거나 MFC 또는 ATL 코드의 컨텍스트에서 라고 하는 경우에이 호출 만으로 충분 하지 않습니다. 참조 [Dll 및 시각적 개체 C++ 런타임 라이브러리 동작](../../build/run-time-library-behavior.md) 에 대 한 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

- [링커 옵션 설정](../../build/reference/linking.md)
