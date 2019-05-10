---
title: 컴파일러 오류 C2472
ms.date: 11/04/2016
f1_keywords:
- C2472
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
ms.openlocfilehash: d2f104bb61915f8d19d5fff22eea17929c0e8d74
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350912"
---
# <a name="compiler-error-c2472"></a>컴파일러 오류 C2472

> '*함수*'에서 관리 되는 코드를 생성할 수 없습니다: '*메시지*'; 혼합된 이미지를 생성 하려면 /clr을 사용 하 여 컴파일

## <a name="remarks"></a>설명

이 오류는 관리 코드에서 지원하지 않는 형식이 순수 CLR(공용 언어 런타임) 환경 내에서 사용되는 경우에 발생합니다. 오류를 해결하려면 **/clr** 을 사용하여 컴파일하세요.

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

## <a name="example"></a>예제

다음 샘플에서는 C2472를 생성합니다.

```cpp
// C2472.cpp
// compile with: /clr:pure
// C2472 expected

#include <cstdlib>

int main()
{
   int * __ptr32 p32;
   int * __ptr64 p64;

   p32 = (int * __ptr32)malloc(4);
   p64 = p32;
}
```

## <a name="see-also"></a>참고자료

- [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)
