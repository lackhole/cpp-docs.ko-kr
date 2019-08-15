---
title: wmain 사용 지원
ms.date: 11/04/2016
f1_keywords:
- wWinMain
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
ms.openlocfilehash: 4af389c00f6065df631f891dadcb0b2f350f984d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491194"
---
# <a name="support-for-using-wmain"></a>wmain 사용 지원

Visual C++에서 개발된 유니코드 기반 응용프로그램이라면 **wmain** 함수를 정의하여 와이드 문자 인수를 받아 편리하게 사용할 수 있습니다. `main` 함수와 비슷한 형식으로 **wmain**을 선언합니다. 선언 후 와이드 문자 기반의 인수를 이용할 수 있으며 와이드 문자 기반 환경 포인터를 사용할 수도 있습니다. **wmain**의 `argv` 및 `envp` 매개 변수는 `wchar_t*` 형식입니다. 다음 예제를 참고하세요.

```cpp
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

> [!NOTE]
> 유니코드 기반의 MFC 응용 프로그램은 `wWinMain`을 진입점으로 사용합니다. 이런 경우 `CWinApp::m_lpCmdLine` 또한 유니코드 문자열입니다. `wWinMainCRTStartup`을 [/ENTRY](../build/reference/entry-entry-point-symbol.md) 링커 옵션과 함께 설정했는지 확인합니다.

**main** 함수를 사용하면 프로그램 시작 시 기본적으로 런타임 라이브러리에 의해 멀티바이트 문자 환경이 만들어집니다. 환경의 와이드 문자 복사본는 `_wgetenv` 또는 `_wputenv` 함수 호출의 경우처럼 필요할 때만 만들어집니다. `_wputenv`가 처음 호출되거나 멀티 바이트 문자 집합(MBCS) 환경이 사용 가능한 상태에서 `_wgetenv`가 처음 호출되는 시점에 와이드 문자 기반 문자열 환경이 만들어 집니다. 만들어진 환경은 `_wenviron` 전역 변수가 가리키고 있는데, 이는 와이드 문자 버전의 `_environ` 전역 변수입니다. 이 시점에서 MBCS 및 유니코드, 두 환경의 복사본이 동시에 존재하며 프로그램의 수명 기간 동안 운영 시스템에 의해 유지 관리됩니다.

마찬가지로 프로그램에서 **wmain** 함수를 사용하면 프로그램이 시작될 때 와이드 문자 환경이 만들어지고 `_wenviron` 전역 변수가 해당 환경을 가리킵니다. `_putenv`이나 `getenv`의 첫 번째 호출에서 MBCS(ASCII) 환경이 만들어지고, 이는 `_environ` 전역 변수가 가리킵니다.

## <a name="see-also"></a>참고자료

[유니코드 지원](../text/support-for-unicode.md)<br/>
[유니코드 프로그래밍 요약](../text/unicode-programming-summary.md)<br/>
[WinMain 함수](/windows/win32/api/winbase/nf-winbase-winmain)
