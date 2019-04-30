---
title: '방법: PInvoke를 사용 하는 구조체 마샬링'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
ms.openlocfilehash: d5c64a3e93cd85d7e38bac7c0ea3fa3c3301abc9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387242"
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>방법: PInvoke를 사용 하는 구조체 마샬링

이 문서에서는 어떻게 네이티브 함수를 P/Invoke를 사용 하 여 관리 되는 함수에서 C 스타일 구조체를 호출할 수 있습니다. 하지만 사용 하는 것이 좋습니다는 C++ P/Invoke는 작은 컴파일 타임 오류를 보고, 형식이 안전한 아닙니다를 제공 하 고 관리 되지 않는 API는 DLL로 패키지 하 고 소스 코드에는 없는 경우 구현 되기 번거로울 수 있으므로 대신 P/Invoke Interop 기능 P/Invoke를 사용할 수 있는 유일한 옵션입니다. 다음 문서를 참조 하십시오.

- [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [방법: PInvoke를 사용하여 문자열 마샬링](../dotnet/how-to-marshal-strings-using-pinvoke.md)

기본적으로 네이티브 및 관리 되는 구조에에서 배치 되어 다르게 메모리 했습니다 데이터 무결성을 유지 하기 위해 추가 단계를 수행 해야 구조 관리 되 는/관리 경계를 넘어 전달 합니다.

이 문서에서는 관리 되는 해당 하는 네이티브 구조체와 관리 되지 않는 함수에는 결과 구조체를 전달 하는 방법을 정의 하는 데 필요한 단계를 설명 합니다. 이 문서에서는 가정 하는 간단한 구조-문자열 또는 포인터를 포함 하지 않는 것 등 사용 됩니다. 비 blittable 상호 운용성에 대 한 정보를 참조 하세요 [사용 C++ (암시적 PInvoke) Interop](../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다. P/Invoke는 비 blittable 형식 반환 값으로 사용할 수 없습니다. Blittable 형식은 관리 코드와 비관리 코드에서 표현이 동일한 합니다. 자세한 내용은 [Blittable 형식 및 비 Blittable 형식](/dotnet/framework/interop/blittable-and-non-blittable-types)합니다.

간단한 마샬링 blittable 구조를 관리 되 는/관리 경계를 넘어 먼저 필요한 각 네이티브 구조체의 관리 되는 버전을 정의 하는 것입니다. 이러한 구조 이름에는 제한이 법적; 두 구조체는 데이터 레이아웃 이외의 네이티브 및 관리 되는 버전 간의 관계가 없습니다. 따라서 관리 되는 버전 크기 및 기본 버전으로 동일한 순서로 동일한 필드를 포함 하는 중요 한 것입니다. (방법이 구조체의 관리 및 네이티브 버전 되므로 해당 비 호환성 문제가 드러나지 않습니다 런타임까지 보장 하기 위한 메커니즘이 없습니다. 프로그래머의 두 구조체가 같은 데이터 레이아웃을 갖도록 합니다.)

관리 되는 구조체의 멤버는 경우에 따라 성능 향상을 위해 다시 정렬, 이므로 사용 하는 데 필요한는 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 구조 순차적으로 배치 됩니다. 또한 설정을 기본 구조에서 사용 하는 것과 동일 하 게 하려면 압축 구조를 명시적으로 설정 하는 것이 좋습니다. (하지만 기본적으로 시각적 개체 C++ 관리 되는 코드를 모두에 대 한 압축 하는 8 바이트 구조체를 사용 하 여.)

1. 다음을 사용 하 여 <xref:System.Runtime.InteropServices.DllImportAttribute> 구조를 허용 하는 모든 관리 되지 않는 함수에 해당 하는 진입점을 선언 하지만 함수 시그니처에서의 두 버전 모두에 동일한 이름을 사용 하는 경우는 구조체의 관리 되는 버전을 사용 하 여 구조체입니다.

1. 이제 관리 되는 코드는 실제로 관리 되는 함수 처럼 관리 되지 않는 함수에 구조체의 관리 되는 버전을 전달할 수 있습니다. 이러한 구조는 다음 예제와 같이 값 이나 참조로 전달할 수 있습니다.

## <a name="example"></a>예제

다음 코드는 비관리 및 관리 되는 모듈 구성 됩니다. 관리 되지 않는 모듈에는 위치 및 위치 구조의 두 인스턴스를 받아들이는 GetDistance 라는 함수를 호출 하는 구조를 정의 하는 DLL입니다. 두 번째 모듈은 관리 되는 명령줄 응용 프로그램 GetDistance 함수 가져오기입니다 MLocation 위치 구조체의 관리 되는 해당 하는 측면에서 정의 합니다. 실제로; 구조체의 두 버전에 대해 동일한 이름을 사용할 것은 그러나 다른 이름은 DllImport 프로토타입은 관리 되는 버전을 기준으로 정의 되어 있는지 보여 주기 위해 여기서 사용 됩니다.

사용 하 여 기존의 관리 되는 코드에 노출 되지 않습니다 없는 부분 DLL #include 지시문입니다. 사실, DLL은 런타임에 액세스 되므로 문제 DllImport를 사용 하 여 가져온 함수를 사용 하 여 컴파일 시간에 검색 되지 것입니다.

```
// TraditionalDll3.cpp
// compile with: /LD /EHsc
#include <iostream>
#include <stdio.h>
#include <math.h>

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
   #define TRADITIONALDLL_API __declspec(dllexport)
#else
   #define TRADITIONALDLL_API __declspec(dllimport)
#endif

#pragma pack(push, 8)
struct Location {
   int x;
   int y;
};
#pragma pack(pop)

extern "C" {
   TRADITIONALDLL_API double GetDistance(Location, Location);
   TRADITIONALDLL_API void InitLocation(Location*);
}

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
```

## <a name="example"></a>예제

```
// MarshalStruct_pi.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Sequential, Pack=8)]
value struct MLocation {
   int x;
   int y;
};

value struct TraditionalDLL {
   [DllImport("TraditionalDLL3.dll")]
   static public double GetDistance(MLocation, MLocation);
   [DllImport("TraditionalDLL3.dll")]
   static public double InitLocation(MLocation*);
};

int main() {
   MLocation loc1;
   loc1.x = 0;
   loc1.y = 0;

   MLocation loc2;
   loc2.x = 100;
   loc2.y = 100;

   double dist = TraditionalDLL::GetDistance(loc1, loc2);
   Console::WriteLine("[managed] distance = {0}", dist);

   MLocation loc3;
   TraditionalDLL::InitLocation(&loc3);
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);
}
```

```Output
[unmanaged] loc1(0,0) loc2(100,100)
[managed] distance = 141.42135623731
[unmanaged] Initializing location...
[managed] x=50 y=50
```

## <a name="see-also"></a>참고자료

[C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
