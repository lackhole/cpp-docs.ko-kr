---
title: 컴파일러 오류 C2749
ms.date: 11/04/2016
f1_keywords:
- C2749
helpviewer_keywords:
- C2749
ms.assetid: a81aef36-cdca-4d78-89d5-b72eff2500b2
ms.openlocfilehash: 80ac01eaba8e5291ee5558d226ebea2c3d8ff47e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360218"
---
# <a name="compiler-error-c2749"></a>컴파일러 오류 C2749

'type': throw 또는 catch /clr: safe 사용 하 여 관리 되는 클래스에 대 한 핸들 수

사용 하는 경우 **/clr: safe**, throw 또는 catch 참조 형식만 가능 합니다.

자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C2749 오류가 생성 됩니다.

```
// C2749.cpp
// compile with: /clr:safe
ref struct MyStruct {
public:
   int i;
};

int main() {
   MyStruct ^x = gcnew MyStruct;

   // Delete the following 4 lines to resolve.
   try {
      throw (1);   // C2749
   }
   catch(int){}

   // OK
   try {
      throw (x);
   }
   catch(MyStruct ^){}
}
```