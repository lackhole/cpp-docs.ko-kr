---
title: 컴파일러 경고(수준 1) C4789
ms.date: 03/25/2019
f1_keywords:
- C4789
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
ms.openlocfilehash: 36a5032098c5caabb1b050833e487fd58679a782
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187233"
---
# <a name="compiler-warning-level-1-c4789"></a>컴파일러 경고(수준 1) C4789

> 버퍼 '*식별자*' 크기인 *N* 바이트 오버런 됩니다. *M* 바이트가 오프셋부터 쓰입니다 *L*

## <a name="remarks"></a>설명

**C4789** 특정 C 런타임 (CRT) 함수를 사용할 경우 버퍼 오버런에 경고 합니다. 또한 매개 변수가 전달 하거나 할당이 적용 됩니다. 크기 불일치 보고할 수 있습니다. 경고는 데이터 크기는 컴파일 타임에 알려진 경우에 발생 합니다. 이 경고는 일반적인 데이터 크기 불일치 검색을 방지할 수 있는 상황에 사용됩니다.

**C4789** 경우 경고 데이터는 컴파일 타임에 너무 작은 것으로 알려진 경우는 데이터 블록을 복사 합니다.

경고에는 복사본을 이러한 CRT 함수 중 하나의 내장 형식을 사용 하는 경우 발생 합니다.

- [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)

- [memset](../../c-runtime-library/reference/memset-wmemset.md)

- [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md), [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)

경고는 더 큰 데이터 형식으로 매개 변수를 캐스팅 하는 lvalue 참조에서 복사 할당을 확인 하는 경우에 나타납니다.

Visual C++ 실행 하지 않는 코드 경로 대 한이 경고를 생성할 수 있습니다. 다음 예제와 같이 `#pragma`를 사용하여 이 경고를 일시적으로 비활성화할 수 있습니다.

```cpp
#pragma warning( push )
#pragma warning( disable : 4789 )
// unused code that generates compiler warning C4789`
#pragma warning( pop )
```

이 관용구 Visual 유지 C++ 에서 특정 코드 블록에 대 한 경고를 생성 합니다. `#pragma warning(push)`는 `#pragma warning(disable: 4789)`에서 변경하기 전까지 기존 상태를 유지합니다. `#pragma warning(pop)`는 푸시된 상태를 복원하고 `#pragma warning(disable:4789)`의 효과를 제거합니다. 에 대 한 자세한 내용은 C++ 전처리기 지시문 `#pragma`를 참조 하세요 [경고](../../preprocessor/warning.md) 및 [Pragma 지시문 및 __Pragma 키워드](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

## <a name="example"></a>예제

다음 샘플에서는 C4789를 생성합니다.

```cpp
// C4789.cpp
// compile with: /Oi /W1 /c
#include <string.h>
#include <stdio.h>

int main()
{
    char a[20];
    strcpy(a, "0000000000000000000000000\n");   // C4789

    char buf2[20];
    memset(buf2, 'a', 21);   // C4789

    char c;
    wchar_t w = 0;
    memcpy(&c, &w, sizeof(wchar_t));
}
```

## <a name="example"></a>예제

또한 다음 샘플에서는 C4789를 생성합니다.

```cpp
// C4789b.cpp
// compile with: /W1 /O2 /c
// processor: x86
short G;

void main()
{
   int * p = (int *)&G;
   *p = 3;   // C4789 - writes an int through a pointer to short
}
```