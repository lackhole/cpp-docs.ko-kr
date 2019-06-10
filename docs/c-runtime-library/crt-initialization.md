---
title: CRT 초기화
ms.date: 11/04/2016
helpviewer_keywords:
- CRT initialization [C++]
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
ms.openlocfilehash: 03126b8fdf1c3824b114d822c269655c22e5ee9f
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446678"
---
# <a name="crt-initialization"></a>CRT 초기화

이 항목에서는 CRT가 네이티브 코드에서 전역 상태를 초기화하는 방법에 대해 설명합니다.

기본적으로 링커는 자체 시작 코드를 제공하는 CRT 라이브러리를 포함합니다. 이 시작 코드는 CRT 라이브러리를 초기화하고 전역 이니셜라이저를 호출한 다음 콘솔 애플리케이션에 대해 사용자 제공 `main` 함수를 호출합니다.

## <a name="initializing-a-global-object"></a>전역 개체 초기화

다음 코드를 살펴보세요.

```
int func(void)
{
    return 3;
}

int gi = func();

int main()
{
    return gi;
}
```

C/C++ 표준에 따라 `func()`을 실행하기 전에 `main()`를 호출해야 합니다. 하지만 누가 호출할까요?

이를 결정하는 한 방법은 `func()`에서 중단점을 설정하고, 애플리케이션을 디버깅하고, 스택을 검토하는 것입니다. 이는 CRT 소스 코드가 Visual Studio에 포함되어 있기 때문에 가능합니다.

스택에서 함수를 찾을 때는 CRT가 함수 포인터 목록을 반복하며 함수 포인터를 발견하면서 각 포인터를 호출하는 것을 확인할 수 있습니다. 이러한 함수는 `func()` 또는 클래스 인스턴스에 대한 생성자와 유사합니다.

CRT는 Microsoft C++ 컴파일러에서 함수 포인터 목록을 가져옵니다. 컴파일러는 전역 이니셜라이저를 발견하면 `.CRT$XCU` 섹션에 동적 이니셜라이저를 생성합니다. 여기서 `CRT`는 섹션 이름이고 `XCU`는 그룹 이름입니다. 이러한 동적 이니셜라이저 목록을 가져오려면 **dumpbin /all main.obj** 명령을 실행한 다음 `.CRT$XCU` 섹션을 검색합니다(main.cpp가 C 파일이 아니라 C++ 파일로 컴파일된 경우). 이는 다음과 유사합니다.

```
SECTION HEADER #6
.CRT$XCU name
       0 physical address
       0 virtual address
       4 size of raw data
     1F2 file pointer to raw data (000001F2 to 000001F5)
     1F6 file pointer to relocation table
       0 file pointer to line numbers
       1 number of relocations
       0 number of line numbers
40300040 flags
         Initialized Data
         4 byte align
         Read Only

RAW DATA #6
  00000000: 00 00 00 00                                      ....

RELOCATIONS #6
                                                Symbol    Symbol
Offset    Type              Applied To         Index     Name
--------  ----------------  -----------------  --------  ------
00000000  DIR32                      00000000         C  ??__Egi@@YAXXZ (void __cdecl `dynamic initializer for 'gi''(void))
```

CRT는 두 포인터를 정의합니다.

- `__xc_a`의 `.CRT$XCA`

- `.CRT$XCZ`의 `__xc_z`

두 그룹 모두에 `__xc_a` 및 `__xc_z`를 제외하고 정의된 다른 기호가 없습니다.

링커는 다양한 `.CRT` 그룹을 읽을 때 해당 그룹을 한 섹션에서 결합하고 사전순으로 정렬합니다. 즉, Microsoft C++ 컴파일러가 `.CRT$XCU`에 넣는 사용자 정의 글로벌 이니셜라이저가 항상 `.CRT$XCA` 뒤와 `.CRT$XCZ` 앞에 옵니다.

이 섹션은 다음과 유사합니다.

```
.CRT$XCA
            __xc_a
.CRT$XCU
            Pointer to Global Initializer 1
            Pointer to Global Initializer 2
.CRT$XCZ
            __xc_z
```

따라서 CRT 라이브러리는 `__xc_a`와 `__xc_z`를 모두 사용하여 전역 이니셜라이저 목록의 시작과 끝을 결정합니다. 이는 이미지가 로드된 후 메모리에서 전역 이니셜라이저가 배치되는 방식 때문입니다.

## <a name="see-also"></a>참고 항목

[CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)
