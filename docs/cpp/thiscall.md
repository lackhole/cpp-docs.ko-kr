---
title: __thiscall
ms.date: 11/04/2016
f1_keywords:
- __thiscall
- __thiscall_cpp
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
ms.openlocfilehash: fc5a32fedf52377889b61103856e2125733cd696
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266789"
---
# <a name="thiscall"></a>__thiscall

**Microsoft 전용**

합니다 **__thiscall** 멤버 함수에 사용 되 고 호출 규칙에서 사용 하는 기본 호출 규칙 C++ 변수 인수를 사용 하지 않는 멤버 함수입니다. 아래 **__thiscall**를 호출 수신자 수 없는 스택을 정리 `vararg` 함수입니다. 인수는 스택에 오른쪽에서 왼쪽으로 사용 하 여 합니다 **이** x86 스택의 한 없습니다 ECX 레지스터를 통해 전달 되는 포인터 아키텍처입니다.

사용 하는 이유 **__thiscall** 클래스가 해당 멤버 함수는 사용 중인 `__clrcall` 기본적으로 합니다. 이 경우 사용할 수 있습니다 **__thiscall** 구성원으로 지정 하려면 개별 함수 네이티브 코드에서 호출할 수 있습니다.

로 컴파일하는 경우 [/clr: pure](../build/reference/clr-common-language-runtime-compilation.md), 모든 함수 및 함수 포인터는 `__clrcall` 달리 지정 되지 않은 합니다. **/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

Visual 이전 릴리스에서 C++ 2005 합니다 **__thiscall** 호출 규칙 지정할 수 없습니다 명시적으로 프로그램에서 있으므로 **__thiscall** 키워드가 없습니다.

`vararg` 멤버 함수만 사용 합니다 **__cdecl** 호출 규칙입니다. 사용 하 여 모든 함수 인수가 스택에 푸시되는 **이** 포인터 마지막 스택에 배치

이 호출 규칙에만 적용 되므로 C++, 없는 C 이름 데코레이션 구성표는 합니다.

ARM 및 x64 컴퓨터 **__thiscall** 수락 하 고 컴파일러에서 무시 합니다.

비정적 클래스 함수의 경우 함수가 아웃오브 라인으로 정의되면 호출 규칙 한정자를 아웃오브 라인 정의에서 지정하지 않아도 됩니다. 즉, 클래스 비정적 멤버 메서드의 경우 선언하는 동안 지정된 호출 규칙이 정의 시 가정됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)