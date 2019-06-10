---
title: 호환성
ms.date: 11/04/2016
f1_keywords:
- c.programs
helpviewer_keywords:
- CRT, compatibility
- compatibility, C run-time libraries
- compatibility
ms.assetid: 346709cb-edda-4909-9a19-3d253eddb6b7
ms.openlocfilehash: 5e9d2edca8da128343bd14ea86a8c1c0023a244b
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446674"
---
# <a name="compatibility"></a>호환성

UCRT(유니버설 C 런타임 라이브러리)는 C++ 규칙에 필요한 C 표준 라이브러리를 대부분 지원합니다. \<tgmath.h>에 정의된 형식 제네릭 매크로와 \<complex.h>의 엄격한 형식 호환성을 제외하고 C99(ISO/IEC 9899:1999) 라이브러리를 구현합니다. 또한 UCRT는 POSIX.1(ISO/IEC 9945-1:1996, POSIX 시스템 애플리케이션 인터페이스) C 라이브러리의 큰 하위 집합을 구현하지만 어떠한 특정 POSIX 표준에도 완전히 부합되지 않습니다.  뿐만 아니라 UCRT는 표준에 속하지 않는 여러 Microsoft 특정 함수 및 매크로를 구현합니다.

Microsoft Visual C++ 구현과 관련된 함수는 vcruntime 라이브러리에 있습니다.  이러한 함수는 대부분 내부에서 사용되며 사용자 코드에서 호출할 수 없습니다. 일부는 디버깅 및 구현 호환성에 사용하도록 문서화되어 있습니다.

C++ 표준은 구현에 대한 전역 네임스페이스에 밑줄로 시작하는 이름을 예약합니다. POSIX 함수는 전역 네임스페이스에 있지만 표준 C 런타임 라이브러리에 속하지 않으므로 이러한 함수의 Microsoft 특정 구현에 선행 밑줄이 있습니다. 이식성을 위해 UCRT는 기본 이름도 지원하지만 기본 이름을 사용하는 코드를 컴파일할 때 Microsoft C++ 컴파일러가 사용 중단 경고를 실행합니다. 기본 POSIX 이름만 사용되지 않고 함수는 사용됩니다. 이 경고를 표시하지 않으려면 원래 POSIX 이름을 사용하는 코드에서 헤더를 포함하기 전에 `_CRT_NONSTDC_NO_WARNINGS` 을 정의합니다.

표준 C 라이브러리의 특정 함수에는 잘못 사용된 매개 변수 및 확인되지 않은 버퍼로 인한 안전하지 않은 사용 기록이 있습니다. 이러한 함수가 코드에서 보안 문제의 원인이 되는 경우가 많습니다. Microsoft는 매개 변수 사용을 확인하고 런타임에 문제가 감지될 때 잘못된 매개 변수 처리기를 호출하는 이러한 함수의 더 안전한 버전 집합을 만들었습니다.  기본적으로 Microsoft C++ 컴파일러는 더 안전한 변형을 사용할 수 있는 함수가 사용될 때 사용 중단 경고를 실행합니다. 코드를 C++로 컴파일할 때 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` 을 1로 정의하여 대부분의 경고를 제거할 수 있습니다. 이렇게 하면 템플릿 오버로드를 사용하여 포팅 가능한 소스 코드를 유지하는 동시에 더 안전한 변형을 호출합니다. 이 경고를 표시하지 않으려면 이러한 함수를 사용하는 코드에서 헤더를 포함하기 전에 `_CRT_SECURE_NO_WARNINGS` 를 정의합니다. 자세한 내용은 [Security Features in the CRT](../c-runtime-library/security-features-in-the-crt.md)을 참조하세요.

설명서 내에서 특정 함수에 대해 언급된 경우를 제외하고 UCRT는 Windows API와 호환됩니다.  특정 함수는 Windows 8 스토어 앱 또는 Windows 10의 UWP(유니버설 Windows 플랫폼) 앱에서 지원되지 않습니다. 이러한 함수는 Windows 런타임 및 [UWP](/uwp)에서 지원되지 않는 함수를 열거하는 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수 앱](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)에 나와 있습니다.

## <a name="related-articles"></a>관련 문서

|제목|설명|
|-----------|-----------------|
|[UWP 앱, Windows 런타임 및 C 런타임](../c-runtime-library/windows-store-apps-the-windows-runtime-and-the-c-run-time.md)|UCRT 루틴이 유니버설 Windows 앱 또는 Microsoft 스토어 앱과 호환되지 않는 경우를 설명합니다.|
|[ANSI C 준수](../c-runtime-library/ansi-c-compliance.md)|UCRT의 표준 규격 이름 지정을 설명합니다.|
|[UNIX](../c-runtime-library/unix.md)|프로그램을 UNIX에 이식하는 작업에 대한 지침을 제공합니다.|
|[Windows 플랫폼(CRT)](../c-runtime-library/windows-platforms-crt.md)|CRT가 지원되는 운영 체제를 나열합니다.|
|[이전 버전과의 호환성](../c-runtime-library/backward-compatibility.md)|이전 CRT 이름을 새 CRT 이름에 매핑하는 방법을 설명합니다.|
|[CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)|CRT 라이브러리 파일(.lib) 및 관련된 컴파일러 옵션에 대한 개요를 제공합니다.|