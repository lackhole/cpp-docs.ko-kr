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
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588476"
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64

**Microsoft 전용**

**__ptr32**는 32비트 시스템의 네이티브 포인터를 나타내는 반면 **__ptr64**는 64비트 시스템의 네이티브 포인터를 나타냅니다.

다음 예제에서는 이러한 포인터 형식을 선언하는 방법을 보여 줍니다.

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

32비트 시스템에서 **__ptr64**로 선언한 포인터는 32비트 포인터로 잘립니다. 64비트 시스템에서 **__ptr32**로 선언한 포인터는 64비트 포인터로 강제 변환됩니다.

> [!NOTE]
> **/clr: pure** 옵션을 사용하여 컴파일할 경우 **__ptr32**나 **__ptr64**를 사용할 수 없습니다. 사용시 C2472 컴파일러 오류가 발생합니다. **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 지원 중단 예정이고 Visual Studio 2017에서는 지원되지 않습니다.

이전 버전과의 호환성을 위해 **_ptr32**와 **_ptr64**는 **__ptr32**와 **__ptr64**의 동의어입니다. 단, 컴파일러 옵션 [/Za \(언어 확장 사용안함)](../build/reference/za-ze-disable-language-extensions.md)를 사용하면 둘은 구분됩니다.

## <a name="example"></a>예제

다음 예제에는 **__ptr32**와 **__ptr64**를 사용하여 포인터를 선언하고 할당하는 방법을 보여줍니다.

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
