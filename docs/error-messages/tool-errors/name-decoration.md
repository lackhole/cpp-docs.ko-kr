---
title: 이름 데코레이션
ms.date: 09/05/2018
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
ms.openlocfilehash: b916a73e0b8f86755384914fa85ef8a901e4a64c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041525"
---
# <a name="name-decoration"></a>이름 데코레이션

이름 장식은 대개 C++ 명명 체계를 지칭하지만 다른 여러 C 사례에도 적용될 수 있습니다. C++에서는 기본적으로 함수 이름, 매개 변수 및 반환 형식을 사용하여 함수의 링커 이름을 만듭니다. 다음 함수를 살펴보세요.

```
void CALLTYPE test(void)
```

아래 표에는 여러 호출 규칙에 대한 링커 이름이 나와 있습니다.

|호출 규칙|extern "C" 또는 .c 파일|.cpp, .cxx 또는 /TP|
|------------------------|---------------------------|------------------------|
|C 명명 규칙(`__cdecl`)|`_test`|`?test@@ZAXXZ`|
|Fastcall 명명 규칙(`__fastcall`)|`@test@0`|`?test@@YIXXZ`|
|표준 호출 명명 규칙(`__stdcall`)|`_test@0`|`?test@@YGXXZ`|
|Vectorcall 명명 규칙(`__vectorcall`)|`test@@0`|`?test@@YQXXZ`|

C++에서 C 함수를 호출하려면 extern "C"를 사용합니다. extern "C"를 사용하면 비클래스 C++ 함수에 대해 C 명명 규칙이 강제로 사용됩니다. 컴파일러 스위치에 유의 **/Tc** 하거나 **/Tp**, 파일 이름 확장명을 무시 하 고 C로 파일을 컴파일하지 컴파일러에 지시 하는 또는 C++, 각각. 이러한 옵션을 사용하는 경우 예상치 않은 이름이 생성될 수 있습니다.

함수 프로토타입의 매개 변수가 일치하지 않는 경우에도 이 오류가 발생할 수 있습니다. 이름 장식에서는 함수의 매개 변수가 데코레이트된 최종 함수 이름에 통합됩니다. 함수 선언의 매개 변수 형식과 일치하지 않는 매개 변수 형식을 사용하여 함수를 호출해도 LNK2001이 발생할 수 있습니다.

현재는 컴파일러 공급업체나 각 컴파일러 버전 간에 사용 가능한 C++ 이름 지정 표준이 없습니다. 따라서 다른 컴파일러로 컴파일한 개체 파일을 연결하는 경우 같은 명명 체계가 생성되지 않아 확인할 수 없는 external이 작성될 수 있습니다.

## <a name="see-also"></a>참고자료

[링커 도구 오류 LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)