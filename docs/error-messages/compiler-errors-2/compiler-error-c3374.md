---
title: 컴파일러 오류 C3374
ms.date: 11/04/2016
f1_keywords:
- C3374
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
ms.openlocfilehash: 4b00b1cea8ac462c82c11d9f5b207706af74959c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022634"
---
# <a name="compiler-error-c3374"></a>컴파일러 오류 C3374

대리자 인스턴스를 만들지 않으면 'function'의 주소를 가져올 수 없습니다.

대리자 인스턴스를 만드는 컨텍스트가 아닌 다른 컨텍스트에서 함수의 주소를 가져왔습니다.

다음 샘플에서는 C3374 오류가 발생하는 경우를 보여 줍니다.

```
// C3374.cpp
// compile with: /clr
public delegate void MyDel(int i);

ref class A {
public:
   void func1(int i) {
      System::Console::WriteLine("in func1 {0}", i);
   }
};

int main() {
   &A::func1;   // C3374

   // OK
   A ^ a = gcnew A;
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);
}
```

## <a name="see-also"></a>참고자료

[방법: 대리자 정의 및 사용(C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)