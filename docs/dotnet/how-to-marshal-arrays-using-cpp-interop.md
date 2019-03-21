---
title: '방법: C + + Interop를 사용 하 여 배열 마샬링'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [C++], marshaling
- marshaling [C++], arrays
- interop [C++], arrays
- C++ Interop, arrays
- data marshaling [C++], arrays
ms.assetid: c2b37ab1-8acf-4855-ad3c-7d2864826b14
ms.openlocfilehash: 0b27fd65b7d42bff2a009b14c39d9547d8a4a919
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740006"
---
# <a name="how-to-marshal-arrays-using-c-interop"></a>방법: C + + Interop를 사용 하 여 배열 마샬링

이 항목에서는 Visual c + + 상호 운용성의 한 측면을 보여 줍니다. 자세한 내용은 [c + + Interop 사용 (암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다.

다음 코드 예제에서 사용 된 [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md) 구현 #pragma 지시문 관리는 관리 되지 않는 함수에서 동일한 파일에 별도 파일에 정의 된 경우 이러한 함수에서 동일한 방식으로 상호 운용 합니다. 관리 되지 않는 함수만 포함 된 파일 사용 하 여 컴파일할 필요가 없습니다 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 관리 되는 배열을 관리 되지 않는 함수에 전달 하는 방법에 설명 합니다. 관리 되는 함수를 사용 하 여 [pin_ptr (C + + /cli CLI)](../windows/pin-ptr-cpp-cli.md) 배열에 대 한 관리 되지 않는 함수를 호출 하기 전에 가비지 수집 하지 않으려면입니다. 관리 되지 않는 함수 포인터로 고정 된 GC 힙에 제공 함으로써 배열의 복사본을 만드는 오버 헤드를 방지할 수 있습니다. 관리 되지 않는 함수에는 GC 힙 메모리에 액세스 하는, 배열의 내용을 수정 및 변경 내용이 설명 하기 위해 관리 되는 컨트롤을 다시 시작할 때를 반영 합니다.

```
// PassArray1.cpp
// compile with: /clr
#ifndef _CRT_RAND_S
#define _CRT_RAND_S
#endif

#include <iostream>
#include <stdlib.h>
using namespace std;

using namespace System;

#pragma unmanaged

void TakesAnArray(int* a, int c) {
   cout << "(unmanaged) array received:\n";
   for (int i=0; i<c; i++)
      cout << "a[" << i << "] = " << a[i] << "\n";

   unsigned int number;
   errno_t err;

   cout << "(unmanaged) modifying array contents...\n";
   for (int i=0; i<c; i++) {
      err = rand_s( &number );
      if ( err == 0 )
         a[i] = number % 100;
   }
}

#pragma managed

int main() {
   array<int>^ nums = gcnew array<int>(5);

   nums[0] = 0;
   nums[1] = 1;
   nums[2] = 2;
   nums[3] = 3;
   nums[4] = 4;

   Console::WriteLine("(managed) array created:");
   for (int i=0; i<5; i++)
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);

   pin_ptr<int> pp = &nums[0];
   TakesAnArray(pp, 5);

   Console::WriteLine("(managed) contents:");
   for (int i=0; i<5; i++)
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);
}
```

## <a name="example"></a>예제

다음 예제에서는 관리 되는 함수에 관리 되지 않는 배열을 전달 하는 방법을 보여 줍니다. 컨트롤을 회복 될 때 관리 되지 않는 함수에 적용 하는 데 관리 되는 함수에 의해 변경 내용을 허용 하는 직접 (달리 관리 되는 배열을 만들고 배열 콘텐츠를 복사), 배열의 메모리를 액세스 하는 관리 되는 함수입니다.

```
// PassArray2.cpp
// compile with: /clr
#include <iostream>
using namespace std;

using namespace System;

#pragma managed

void ManagedTakesAnArray(int* a, int c) {
   Console::WriteLine("(managed) array received:");
   for (int i=0; i<c; i++)
      Console::WriteLine("a[{0}] = {1}", i, a[i]);

   cout << "(managed) modifying array contents...\n";
   Random^ r = gcnew Random(DateTime::Now.Second);
   for (int i=0; i<c; i++)
      a[i] = r->Next(100);
}

#pragma unmanaged

void NativeFunc() {
   int nums[5] = { 0, 1, 2, 3, 4 };

   printf_s("(unmanaged) array created:\n");
   for (int i=0; i<5; i++)
      printf_s("a[%d] = %d\n", i, nums[i]);

   ManagedTakesAnArray(nums, 5);

   printf_s("(ummanaged) contents:\n");
   for (int i=0; i<5; i++)
      printf_s("a[%d] = %d\n", i, nums[i]);
}

#pragma managed

int main() {
   NativeFunc();
}
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
