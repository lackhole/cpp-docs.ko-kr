---
title: __ptr32, __ptr64
ms.date: 10/09/2018
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
- __ptr32
- __ptr64
- _ptr32
- _ptr64
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
ms.openlocfilehash: 0e979ed51f9c34700cef75113018c23e69a304f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244465"
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64

**Microsoft 전용**

**__ptr32**는 32비트 시스템의 네이티브 포인터를 나타내는 반면 **__ptr64**는 64비트 시스템의 네이티브 포인터를 나타냅니다.

다음 예제에서는 이러한 포인터 형식 각각을 선언하는 방법을 보여 줍니다.

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

32비트 시스템에서 **__ptr64**로 선언한 포인터는 32비트 포인터로 잘립니다. 64비트 시스템에서 **__ptr32**로 선언한 포인터는 64비트 포인터로 강제 변환됩니다.

> [!NOTE]
> 사용할 수 없습니다 **__ptr32** 또는 **__ptr64** 사용 하 여 컴파일하면 **/clr: pure**합니다. 그렇지 않으면 컴파일러 오류 C2472 생성 됩니다. **/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

이전 버전과 호환성에 대 한 **_ptr32** 하 고 **_ptr64** 에 대 한 동의어가 **__ptr32** 및 **__ptr64** 하지 않는 한 컴파일러 옵션 [/Za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 지정 됩니다.

## <a name="example"></a>예제

다음 예제에는 선언 및 사용 하 여 포인터를 할당 하는 방법을 보여 줍니다 합니다 **__ptr32** 하 고 **__ptr64** 키워드입니다.

```cpp
#include <cstdlib>
#include <iostream>

int main()
{
    using namespace std;

    int * __ptr32 p32;
    int * __ptr64 p64;

    p32 = (int * __ptr32)malloc(4);
    *p32 = 32;
    cout << *p32 << endl;

    p64 = (int * __ptr64)malloc(4);
    *p64 = 64;
    cout << *p64 << endl;
}
```

```Output
32
64
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[기본 형식(C++)](../cpp/fundamental-types-cpp.md)