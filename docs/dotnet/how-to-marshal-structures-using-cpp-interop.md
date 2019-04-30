---
title: '방법: 사용 하 여 구조체 마샬링 C++ Interop'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Interop, structures
- structures [C++], marshaling
- data marshaling [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: c2080200-f983-4d6e-a557-cd870f060a54
ms.openlocfilehash: 93aeabc3fe984bee8a9281281320d61dccd182bf
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345694"
---
# <a name="how-to-marshal-structures-using-c-interop"></a>방법: 사용 하 여 구조체 마샬링 C++ Interop

이 항목에서는 시각적 개체의 한 측면을 보여 줍니다. C++ 상호 운용성. 자세한 내용은 [사용 C++ (암시적 PInvoke) Interop](../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다.

다음 코드 예제에서 사용 된 [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md) 구현 #pragma 지시문 관리는 관리 되지 않는 함수에서 동일한 파일에 별도 파일에 정의 된 경우 이러한 함수에서 동일한 방식으로 상호 운용 합니다. 관리 되지 않는 함수만 포함 된 파일 사용 하 여 컴파일할 필요가 없습니다 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 값 및 참조에 의해 관리 되는 구조체를 관리 되지 않는 함수에 전달 하는 방법을 보여 줍니다. 만 간단 하 고 기본 데이터 형식을 포함 하는이 예제의 구조 때문에 (참조 [Blittable 형식 및 비 Blittable 형식](/dotnet/framework/interop/blittable-and-non-blittable-types)), 특별 한 마샬링가 필요 합니다. 참조 포인터를 포함 하는 것과 같은 비 blittable 구조를 마샬링할 [방법: 사용 하 여 포인터를 포함 하는 마샬링 C++ Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)합니다.

```
// PassStruct1.cpp
// compile with: /clr

#include <stdio.h>
#include <math.h>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

struct Location {
   int x;
   int y;
};

double GetDistance(Location loc1, Location loc2) {
   printf_s("[unmanaged] loc1(%d,%d)", loc1.x, loc1.y);
   printf_s(" loc2(%d,%d)\n", loc2.x, loc2.y);

   double h = loc1.x - loc2.x;
   double v = loc1.y = loc2.y;
   double dist = sqrt( pow(h,2) + pow(v,2) );

   return dist;
}

void InitLocation(Location* lp) {
   printf_s("[unmanaged] Initializing location...\n");
   lp->x = 50;
   lp->y = 50;
}

#pragma managed

int main() {
   Location loc1;
   loc1.x = 0;
   loc1.y = 0;

   Location loc2;
   loc2.x = 100;
   loc2.y = 100;

   double dist = GetDistance(loc1, loc2);
   Console::WriteLine("[managed] distance = {0}", dist);

   Location loc3;
   InitLocation(&loc3);
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);
}
```

## <a name="example"></a>예제

다음 예제에서는 값 및 참조에 의해 관리 되지 않는 구조체를 관리 되는 함수에 전달 하는 방법을 보여 줍니다. 만 간단 하 고 기본 데이터 형식을 포함 하는이 예제의 구조 때문에 (참조 [Blittable 형식 및 비 Blittable 형식](/dotnet/framework/interop/blittable-and-non-blittable-types)), 특별 한 마샬링가 필요 합니다. 참조 포인터를 포함 하는 것과 같은 비 blittable 구조를 마샬링할 [방법: 사용 하 여 포인터를 포함 하는 마샬링 C++ Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)합니다.

```
// PassStruct2.cpp
// compile with: /clr
#include <stdio.h>
#include <math.h>
using namespace System;

// native structure definition
struct Location {
   int x;
   int y;
};

#pragma managed

double GetDistance(Location loc1, Location loc2) {
   Console::Write("[managed] got loc1({0},{1})", loc1.x, loc1.y);
   Console::WriteLine(" loc2({0},{1})", loc2.x, loc2.y);

   double h = loc1.x - loc2.x;
   double v = loc1.y = loc2.y;
   double dist = sqrt( pow(h,2) + pow(v,2) );

   return dist;
}

void InitLocation(Location* lp) {
   Console::WriteLine("[managed] Initializing location...");
   lp->x = 50;
   lp->y = 50;
}

#pragma unmanaged

int UnmanagedFunc() {
   Location loc1;
   loc1.x = 0;
   loc1.y = 0;

   Location loc2;
   loc2.x = 100;
   loc2.y = 100;

   printf_s("(unmanaged) loc1=(%d,%d)", loc1.x, loc1.y);
   printf_s(" loc2=(%d,%d)\n", loc2.x, loc2.y);

   double dist = GetDistance(loc1, loc2);
   printf_s("[unmanaged] distance = %f\n", dist);

   Location loc3;
   InitLocation(&loc3);
   printf_s("[unmanaged] got x=%d y=%d\n", loc3.x, loc3.y);

    return 0;
}

#pragma managed

int main() {
   UnmanagedFunc();
}
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
