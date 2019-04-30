---
title: '방법: MSIL에서 Throw 하는 네이티브 코드에서 예외를 catch 합니다.'
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions, catching
- catching exceptions, thrown from MSIL
- MSIL, catching exceptions in native code
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
ms.openlocfilehash: 95ce7a2afabc34ea78376b12da61f419dab4af34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62379047"
---
# <a name="how-to-catch-exceptions-in-native-code-thrown-from-msil"></a>방법: MSIL에서 Throw 하는 네이티브 코드에서 예외를 catch 합니다.

네이티브 코드에서 catch 할 수 있습니다 기본 C++ MSIL에서 예외입니다.  CLR 예외를 catch 할 수 있습니다 `__try` 고 `__except`입니다.

자세한 내용은 [구조적 예외 처리 (C /C++)](../cpp/structured-exception-handling-c-cpp.md) 하 고 [ C++ 예외 처리](../cpp/cpp-exception-handling.md).

## <a name="example"></a>예제

다음 샘플 MSIL 예외를 throw 하는 두 함수는 네이티브 예외를 throw 하는 하나 및 다른 모듈을 정의 합니다.

```
// catch_MSIL_in_native.cpp
// compile with: /clr /c
void Test() {
   throw ("error");
}

void Test2() {
   throw (gcnew System::Exception("error2"));
}
```

## <a name="example"></a>예제

다음 샘플에는 네이티브 및 MSIL 예외를 catch 하는 모듈을 정의 합니다.

```
// catch_MSIL_in_native_2.cpp
// compile with: /clr catch_MSIL_in_native.obj
#include <iostream>
using namespace std;
void Test();
void Test2();

void Func() {
   // catch any exception from MSIL
   // should not catch Visual C++ exceptions like this
   // runtime may not destroy the object thrown
   __try {
      Test2();
   }
   __except(1) {
      cout << "caught an exception" << endl;
   }

}

int main() {
   // catch native C++ exception from MSIL
   try {
      Test();
   }
   catch(char * S) {
      cout << S << endl;
   }
   Func();
}
```

```Output
error
caught an exception
```

## <a name="see-also"></a>참고자료

[예외 처리](../extensions/exception-handling-cpp-component-extensions.md)
