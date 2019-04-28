---
title: volatile (C++)
ms.date: 11/04/2016
f1_keywords:
- volatile_cpp
helpviewer_keywords:
- interrupt handlers and volatile keyword [C++]
- volatile keyword [C++]
- volatile objects
- objects [C++], volatile
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
ms.openlocfilehash: 73243841b2ad02bcc165b2910ac54283028e6cf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243953"
---
# <a name="volatile-c"></a>volatile (C++)

하드웨어에 의해 프로그램에서 수정할 수 있는 개체를 선언하는 데 사용할 수 있는 형식 한정자입니다.

## <a name="syntax"></a>구문

```
volatile declarator ;
```

## <a name="remarks"></a>설명

사용할 수는 [/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러가이 키워드를 해석 하는 방법을 수정 하려면 컴파일러 스위치입니다.

Visual Studio에서 해석 된 **volatile** 대상 아키텍처에 따라 다르게 키워드입니다. ARM에 없는 경우에 대 한 **/volatile** 컴파일러 옵션을 지정 하면 컴파일러가 수행 처럼 **/volatile:iso** 지정 되었습니다. 없는 경우에 ARM 이외의 아키텍처에 대 한 **/volatile** 컴파일러 옵션을 지정 하면 컴파일러가 수행 처럼 **찾는데** 에 지정 했습니다; 따라서 아키텍처에 대 한 강력한에서는 ARM 이외의 지정 하는 것이 좋습니다 **/volatile:iso**, 스레드 간에 공유 되는 메모리를 처리할 때 명시적 동기화 기본 형식 및 컴파일러 내장 함수를 사용 합니다.

사용할 수는 **volatile** 인터럽트 처리기와 같은 비동기 프로세스에 의해 사용 되는 메모리 위치에 대 한 액세스를 제공 하는 한정자입니다.

때 **volatile** 에 포함 된 변수에 사용 되는 [__restrict](../cpp/extension-restrict.md) 키워드를 **volatile** 우선적으로 적용 합니다.

경우는 **구조체** 로 표시 되어 멤버 **volatile**, 다음 **volatile** 전체 구조체에 전파 됩니다. 구조에 없는 경우 복사할 수 있는 길이가 현재 아키텍처에서 하나의 명령을 사용 하 여 **volatile** 해당 구조에 완전히 손실 될 수 있습니다.

합니다 **volatile** 키워드는 다음 조건 중 하나가 참인 경우 필드에 영향을 미치지 않습니다.

- volatile 필드의 길이가 현재 아키텍처에서 하나의 명령을 사용하여 복사할 수 있는 최대 크기를 초과합니다.

- 포함 하는 가장 바깥쪽 길이 **구조체**-중첩 된의 멤버인 경우 또는 **구조체**-현재 아키텍처에서 하나의 명령을 사용 하 여 복사할 수 있는 최대 크기를 초과 합니다.

캐시할 수 없는 변수 프로세서 캐시할 수 없는 메모리 액세스 순서를 변경 하지 않습니다, 하지만로 표시 되어야 합니다 **volatile** 컴파일러 메모리 순서가 변경 되지 않습니다 보장 하기 위해에 액세스 합니다.

로 선언 된 개체 **volatile** 해당 값은 언제 든 지 변경 될 수 있으므로 특정 최적화에 사용 되지 않습니다.  시스템에서는 항상 읽습니다 volatile 개체의 현재 값을 요청 되 면 동일한 개체에서 값에 대 한 이전 지침을 요청 하는 경우에.  또한 개체의 값은 할당에 즉시 기록 됩니다.

## <a name="iso-compliant"></a>ISO 규격

에 익숙한 경우는 C# volatile 키워드 또는의 동작에 익숙한 **volatile** 시각적 개체의 이전 버전의 C++, 주의 C + + 11 ISO 표준 **volatile** 키워드는 다른 Visual Studio에서 지원 됩니다 때 합니다 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러 옵션을 지정 합니다. ARM의 경우 기본적으로 지정됩니다. 합니다 **volatile** 하드웨어 액세스를 위해서만 사용할 C + + 11 ISO 표준 코드에서 키워드는 스레드 간 통신에 사용 하지 마세요. 스레드 간 통신 메커니즘을 같은 사용할 [std:: atomic\<T >](../standard-library/atomic.md) 에서 합니다 [ C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md).

## <a name="end-of-iso-compliant"></a>ISO 규격의 끝

## <a name="microsoft-specific"></a>Microsoft 전용

경우는 **찾는데** 컴파일러 옵션을 사용-ARM 이외의 아키텍처가 대상인 경우 기본적으로-컴파일러 유지 관리 외에 volatile 개체에 대 한 참조 순서를 유지 하기 위해 추가 코드를 생성 합니다. 다른 전역 개체에 대 한 참조 순서를 지정 합니다. 특히 다음과 같습니다.

- volatile 개체 쓰기(volatile 쓰기)는 Release 의미 체계를 사용합니다. 즉 명령 시퀀스에서 volatile 개체에 쓰기 전에 발생하는 전역 또는 정적 개체에 대한 참조는 컴파일된 이진 파일에서 volatile 쓰기 전에 발생합니다.

- volatile 개체 읽기(volatile 읽기)는 Acquire 의미 체계를 사용합니다. 즉 명령 시퀀스에서 volatile 메모리 읽기 다음에 발생하는 전역 또는 정적 개체에 대한 참조는 컴파일된 이진 파일에서 volatile 읽기 다음에 발생합니다.

따라서 일시적 개체를에 메모리 잠금과 릴리스 다중 스레드 응용 프로그램에서 사용할 수 있습니다.

> [!NOTE]
>  경우 때 제공 된 향상된 된 보증에 의존 합니다 **찾는데** 컴파일러 옵션을 사용 하면 코드를 이식 가능 하지 않습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[const](../cpp/const-cpp.md)<br/>
[const 및 volatile 포인터](../cpp/const-and-volatile-pointers.md)