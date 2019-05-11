---
title: 인수 전달 및 명명 규칙
ms.date: 12/17/2018
helpviewer_keywords:
- argument passing [C++], conventions
- arguments [C++], widening
- coding conventions, arguments
- arguments [C++], passing
- registers, return values
- thiscall keyword [C++]
- naming conventions [C++], arguments
- arguments [C++], naming
- passing arguments [C++], conventions
- conventions [C++], argument names
ms.assetid: de468979-eab8-4158-90c5-c198932f93b9
ms.openlocfilehash: 1928f8e479b0533c5a8b2e60de7af9eff93f7eed
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222260"
---
# <a name="argument-passing-and-naming-conventions"></a>인수 전달 및 명명 규칙

**Microsoft 전용**

Microsoft C++ 컴파일러 인수를 전달 하기 위한 규칙을 지정 하 고 함수와 호출자 간에 값을 반환할 수 있습니다. 지원되는 모든 플랫폼에서 모든 규칙을 사용할 수 있는 것은 아니며, 일부 규칙은 플랫폼별 구현을 사용합니다. 대부분의 경우 특정 플랫폼에서 지원되지 않는 규칙을 지정하는 키워드 또는 컴파일러 스위치는 무시되며 플랫폼 기본 규칙이 사용됩니다.

x86 플랫폼에서 모든 인수는 전달될 때 32비트로 확장됩니다. 반환 값도 32비트로 확장되며 EDX:EAX 레지스터 쌍에서 반환되는 8바이트 구조체를 제외하고 EAX 레지스터에서 반환됩니다. 더 큰 구조체는 숨겨진 반환 구조체에 대한 포인터로 EAX 레지스터에서 반환됩니다. 매개 변수는 오른쪽에서 왼쪽으로 스택에 푸시됩니다. POD가 아닌 구조체는 레지스터에서 반환되지 않습니다.

컴파일러는 ESI, EDI, EBX 및 EBP 레지스터가 함수에서 사용되는 경우 이러한 레지스터를 저장하고 복원하는 프롤로그 및 에필로그 코드를 생성합니다.

> [!NOTE]
> 구조체, 공용 구조체 또는 클래스가 값으로 함수에서 반환되는 경우 형식의 모든 정의가 동일해야 하며, 그렇지 않으면 프로그램이 런타임에 실패할 수 있습니다.

사용자 고유의 함수 프롤로그 및 에필로그 코드를 정의 하는 방법에 대 한 자세한 내용은 [Naked 함수 호출](../cpp/naked-function-calls.md)합니다.

대상을 x64 플랫폼에서 참조 하는 코드의 호출 규칙 기본값에 대 한 자세한 [x64 호출 규칙](../build/x64-calling-convention.md)합니다. ARM 플랫폼을 대상으로 하는 코드의 호출 규칙 문제에 대 한 자세한 내용은 [일반적인 Visual C++ ARM 마이그레이션 문제](../build/common-visual-cpp-arm-migration-issues.md)합니다.

다음과 같은 호출 규칙이 Visual C/C++ 컴파일러에서 지원됩니다.

|키워드|스택 정리|매개 변수 전달|
|-------------|-------------------|-----------------------|
|[__cdecl](../cpp/cdecl.md)|호출자|매개 변수를 스택에 역순으로(오른쪽에서 왼쪽으로) 푸시합니다.|
|[__clrcall](../cpp/clrcall.md)|N/A|CLR 식 스택에 매개 변수를 순서대로(왼쪽에서 오른쪽으로) 로드합니다.|
|[__stdcall](../cpp/stdcall.md)|호출 수신자|매개 변수를 스택에 역순으로(오른쪽에서 왼쪽으로) 푸시합니다.|
|[__fastcall](../cpp/fastcall.md)|호출 수신자|레지스터에 저장된 다음 스택에 푸시됩니다.|
|[__thiscall](../cpp/thiscall.md)|호출 수신자|스택에; **이** 포인터가 ECX에에서 저장|
|[__vectorcall](../cpp/vectorcall.md)|호출 수신자|레지스터에 저장된 다음 스택에 역순으로(오른쪽에서 왼쪽으로) 푸시됩니다.|

관련 정보를 참조 하세요 [사용 되지 않는 호출 규칙](../cpp/obsolete-calling-conventions.md)합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[호출 규칙](../cpp/calling-conventions.md)