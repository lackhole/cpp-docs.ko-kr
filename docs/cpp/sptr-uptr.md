---
title: __sptr, __uptr
ms.date: 10/10/2018
f1_keywords:
- __uptr_cpp
- __sptr_cpp
- __uptr
- __sptr
- _uptr
- _sptr
helpviewer_keywords:
- __sptr modifier
- __uptr modifier
ms.assetid: c7f5f3b2-9106-4a0b-a6de-d1588ab153ed
ms.openlocfilehash: 957f744ca6c5a7be807c1dc68fcd2b602b72300e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330961"
---
# <a name="sptr-uptr"></a>__sptr, __uptr

**Microsoft 전용**

사용 된 **__sptr** 또는 **__uptr** 컴파일러가 64 비트 포인터에 대 한 32 비트 포인터를 변환 하는 방법을 지정 하는 32 비트 포인터 선언에서 한정자입니다. 예를 들어 32비트 포인터는 64비트 포인터 변수에 할당되거나 64비트 플랫폼에서 역참조될 때 변환됩니다.

64비트 플랫폼 지원에 대한 Microsoft 설명서에서는 경우에 따라 32비트 포인터의 최상위 비트를 부호 비트로 지칭합니다. 기본적으로 컴파일러는 부호 확장을 사용하여 32비트 포인터를 64비트 포인터로 변환합니다. 즉, 64비트 포인터의 최하위 32비트는 32비트 포인터의 값으로 설정되며 최상위 32비트는 32비트 포인터의 부호 비트 값으로 설정됩니다. 이 변환은 부호 비트가 0인 경우 올바른 결과를 생성하지만 부호 비트가 1인 경우에는 올바른 결과를 생성하지 않습니다. 예를 들어 32비트 주소 0x7FFFFFFF는 동일한 64비트 주소 0x000000007FFFFFFF를 생성하지만 32비트 주소 0x80000000은 0xFFFFFFFF80000000으로 올바르지 않게 변경됩니다.

합니다 **__sptr**, 부호 있는 포인터를 한정자는 포인터 변환 64 비트 포인터의 최상위 비트가 32 비트 포인터의 부호 비트로 설정 되도록 지정 합니다. 합니다 **__uptr**, 또는 부호 없는 포인터 한정자는 변환에서 설정 된 가장 중요 한 비트가 0으로 지정 합니다. 다음 선언 표시 합니다 **__sptr** 및 **__uptr** 정규화 되지 않은 두 포인터를 사용 하는 한정자를 사용 하 여 한정 된 두 포인터를 [__ptr32](../cpp/ptr32-ptr64.md) 형식 및 함수 매개 변수입니다.

```cpp
int * __sptr psp;
int * __uptr pup;
int * __ptr32 __sptr psp32;
int * __ptr32 __uptr pup32;
void MyFunction(char * __uptr __ptr32 myValue);
```

사용 합니다 **__sptr** 하 고 **__uptr** 포인터 선언 사용 하 여 한정자입니다. 한정자를 사용 하 여 위치에는 [포인터 형식 한정자](../c-language/pointer-declarations.md), 즉, 한정자 별표를 수행 해야 합니다. 한정자와 함께 사용할 수 없습니다 [멤버에 대 한 포인터](../cpp/pointers-to-members.md)합니다. 한정자는 포인터 선언이 아닌 선언에 영향을 주지 않습니다.

이전 버전과 호환성에 대 한 **_sptr** 하 고 **_uptr** 에 대 한 동의어가 **__sptr** 및 **__uptr** 컴파일러 옵션 [/Za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 지정 됩니다.

## <a name="example"></a>예제

다음 예제에서는 사용 하는 32 비트 포인터를 선언 합니다 **__sptr** 하 고 **__uptr** 한정자를 각 32 비트 포인터는 64 비트 포인터 변수에 할당 한 다음 각 64-16 진수 값을 표시 비트 포인터입니다. 이 예제는 네이티브 64비트 컴파일러로 컴파일되며 64비트 플랫폼에서 실행됩니다.

```cpp
// sptr_uptr.cpp
// processor: x64
#include "stdio.h"

int main()
{
    void *        __ptr64 p64;
    void *        __ptr32 p32d; //default signed pointer
    void * __sptr __ptr32 p32s; //explicit signed pointer
    void * __uptr __ptr32 p32u; //explicit unsigned pointer

// Set the 32-bit pointers to a value whose sign bit is 1.
    p32d = reinterpret_cast<void *>(0x87654321);
    p32s = p32d;
    p32u = p32d;

// The printf() function automatically displays leading zeroes with each 32-bit pointer. These are unrelated
// to the __sptr and __uptr modifiers.
    printf("Display each 32-bit pointer (as an unsigned 64-bit pointer):\n");
    printf("p32d:       %p\n", p32d);
    printf("p32s:       %p\n", p32s);
    printf("p32u:       %p\n", p32u);

    printf("\nDisplay the 64-bit pointer created from each 32-bit pointer:\n");
    p64 = p32d;
    printf("p32d: p64 = %p\n", p64);
    p64 = p32s;
    printf("p32s: p64 = %p\n", p64);
    p64 = p32u;
    printf("p32u: p64 = %p\n", p64);
    return 0;
}
```

```Output
Display each 32-bit pointer (as an unsigned 64-bit pointer):
p32d:       0000000087654321
p32s:       0000000087654321
p32u:       0000000087654321

Display the 64-bit pointer created from each 32-bit pointer:
p32d: p64 = FFFFFFFF87654321
p32s: p64 = FFFFFFFF87654321
p32u: p64 = 0000000087654321
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md)