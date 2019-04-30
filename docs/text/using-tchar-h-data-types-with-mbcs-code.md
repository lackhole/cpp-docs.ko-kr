---
title: _MBCS 코드와 TCHAR.H 데이터 형식 사용
ms.date: 11/04/2016
f1_keywords:
- TCHAR
helpviewer_keywords:
- mapping generic-text
- generic-text data types [C++]
- generic-text mappings [C++]
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
ms.openlocfilehash: 0e26aefd8b9099a2ca5e76ce9e2b7d1def2f9854
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410501"
---
# <a name="using-tcharh-data-types-with-mbcs-code"></a>_MBCS 코드와 TCHAR.H 데이터 형식 사용

매니페스트 상수 `_MBCS`가 정의되면 제네릭 텍스트 루틴은 다음 중 하나의 루틴으로 지정됩니다.

- 멀티바이트 기반의 바이트, 문자 및 문자열을 적절하게 처리하는 SBCS 루틴. 이 경우 문자열 인수는 `char*` 형식이어야 합니다. 예를 들어 `_tprintf` 매핑됩니다 `printf`; 문자열 인수는 `printf` 형식의 `char*`합니다. 문자열 형식에 `_TCHAR`을 사용하면 `_TCHAR*`가 `char*`로 매핑되어 `printf`가 요구하는 형식 및 실제 사용되는 매개 변수 형식이 일치하게 됩니다.

- MBCS 관련 루틴. 이 경우 문자열 인수는 `unsigned char*` 형식이어야 합니다. 예를들어 `_tcsrev`는 `unsigned char*` 형식의 문자열을 사용하고 반환하는 `_mbsrev`과 매핑됩니다. 문자열 형식에 `_TCHAR` 제네릭 텍스트 데이터 형식을 사용하면 `_TCHAR`이 `char` 형식으로 매핑되기 때문에 형식 충돌이 발생합니다.

이러한 형식 충돌로 C 컴파일러 경고나 C++ 컴파일러 오류가 발생하는 것을 방지하기 위한 다음 3가지 방법이 있습니다.

- 기본 동작을 사용합니다. tchar.h에는 다음 예제와 같이 런타임 라이브러리의 루틴에 대한 제네릭 텍스트 루틴 프로토타입이 정의되어 있습니다.

    ```cpp
    char * _tcsrev(char *);
    ```

   기본적으로 `_tcsrev`에 대한 프로토타입은 Libc.lib의 작은 함수 썽크(thunk)를 통해 `_mbsrev`와 매핑됩니다. 이렇게 되면 `_mbsrev`수신 매개 변수와 반환 값의 형식이 `_TCHAR*`로 변환되는 `char *`에서 `unsigned char *`로 변경됩니다. 이 방법을 사용하면 `_TCHAR`을 사용할 때 형식의 일치를 보장하지만, 함수 호출에서 발생하는 오버헤드로 인해 속도가 상대적으로 느린 단점이 있습니다.

- 코드에서 다음 전처리기 문을 통합하여 함수 인라인을 사용합니다.

    ```cpp
    #define _USE_INLINING
    ```

   이 방법을 사용하면 tchar.h에 구현된 인라인 함수 썽크가 제네릭 텍스트 루틴을 해당 MBCS 루틴에 직접 매핑하도록 합니다. tchar.h에서 정의된 다음의 코드를 보며 코드가 어떻게 수행되는지 확인합니다.

    ```cpp
    __inline char *_tcsrev(char *_s1)
    {return (char *)_mbsrev((unsigned char *)_s1);}
    ```

   인라인을 사용할 수 있는 경우 형식 일치가 보장되고 추가적으로 시간이 소요되지 않으므로 최선의 방법입니다.

- 코드에서 다음 전처리기 문을 통합하여 직접 매핑을 사용합니다.

    ```cpp
    #define _MB_MAP_DIRECT
    ```

   기본 동작을 사용하지 않으려고 하거나 인라인을 사용할 수 없는 경우 이 방법이 가장 빠른 대안입니다. 일반 텍스트 루틴이 매크로에 의해 MBCS 버전의 tchar.h의 다음 예제와 같이 루틴에 직접 매핑해야 발생 합니다.

    ```cpp
    #define _tcschr _mbschr
    ```

   이 방법을 사용하는 경우에 문자열 인수 및 문자열 반환 값의 데이터 형식이 적절하게 사용되었는지 주의해야 합니다. 형식 캐스팅을 사용하여 적절한 형식 일치를 보장하거나 `_TXCHAR` 일반 텍스트 데이터 형식을 사용할 수 있습니다. `_TXCHAR`은 SBCS 기반에서 **char** 형식으로 매핑되지만 MBCS 기반에서는 **unsigned char**로 매핑됩니다. 일반 텍스트 매크로에 대한 자세한 내용은 [일반 텍스트 매핑](../c-runtime-library/generic-text-mappings.md)의 *런타임 라이브러리 참조*를 참고합니다.

## <a name="see-also"></a>참고자료

[tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)
