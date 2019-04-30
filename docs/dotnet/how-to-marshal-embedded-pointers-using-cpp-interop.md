---
title: '방법: 사용 하 여 포인터를 포함 하는 마샬링 C++ Interop'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- structures [C++], marshaling embedded pointers
- interop [C++], embedded pointers
- C++ Interop, embedded pointers
- marshaling [C++], embedded pointers
- pointers [C++], marshaling
- data marshaling [C++], embedded pointers
ms.assetid: 05fb8858-97f2-47aa-86b2-2c0ad713bdb2
ms.openlocfilehash: c6d622060aaf700b6ea1a3bfe797ab3190eee797
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345734"
---
# <a name="how-to-marshal-embedded-pointers-using-c-interop"></a>방법: 사용 하 여 포인터를 포함 하는 마샬링 C++ Interop

다음 코드 예제에서 사용 된 [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md) 구현 #pragma 지시문 관리는 관리 되지 않는 함수에서 동일한 파일에 별도 파일에 정의 된 경우 이러한 함수에서 동일한 방식으로 상호 운용 합니다. 관리 되지 않는 함수만 포함 된 파일 사용 하 여 컴파일할 필요가 없습니다 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 관리 되는 함수에서 포인터를 포함 하는 구조체를 사용 하는 관리 되지 않는 함수를 호출할 수 있습니다 하는 방법을 보여 줍니다. 관리 되는 함수 구조체의 인스턴스를 만들고 새 키워드를 사용 하 여 포함된 된 포인터를 초기화 (대신 합니다 [ref new, gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) 키워드). 없기 때문에이 네이티브 힙의 메모리 할당, 가비지 수집 하지 않으려면 배열을 고정 필요가 없습니다. 그러나 메모리는 메모리 누수를 방지 하려면 명시적으로 삭제 되어야 합니다.

```
// marshal_embedded_pointer.cpp
// compile with: /clr
#include <iostream>

using namespace System;
using namespace System::Runtime::InteropServices;

// unmanaged struct
struct ListStruct {
   int count;
   double* item;
};

#pragma unmanaged

void UnmanagedTakesListStruct(ListStruct list) {
   printf_s("[unmanaged] count = %d\n", list.count);
   for (int i=0; i<list.count; i++)
      printf_s("array[%d] = %f\n", i, list.item[i]);
}

#pragma managed

int main() {
   ListStruct list;
   list.count = 10;
   list.item = new double[list.count];

   Console::WriteLine("[managed] count = {0}", list.count);
   Random^ r = gcnew Random(0);
   for (int i=0; i<list.count; i++) {
      list.item[i] = r->NextDouble() * 100.0;
      Console::WriteLine("array[{0}] = {1}", i, list.item[i]);
   }

   UnmanagedTakesListStruct( list );
   delete list.item;
}
```

```Output
[managed] count = 10
array[0] = 72.624326996796
array[1] = 81.7325359590969
array[2] = 76.8022689394663
array[3] = 55.8161191436537
array[4] = 20.6033154021033
array[5] = 55.8884794618415
array[6] = 90.6027066011926
array[7] = 44.2177873310716
array[8] = 97.754975314138
array[9] = 27.370445768987
[unmanaged] count = 10
array[0] = 72.624327
array[1] = 81.732536
array[2] = 76.802269
array[3] = 55.816119
array[4] = 20.603315
array[5] = 55.888479
array[6] = 90.602707
array[7] = 44.217787
array[8] = 97.754975
array[9] = 27.370446
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
