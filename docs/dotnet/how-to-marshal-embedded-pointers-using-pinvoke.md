---
title: '방법: PInvoke를 사용 하 여 포함된 포인터 마샬링'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
ms.openlocfilehash: 943a1a2784a37353157cd38da7ebdc9827006fe5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325210"
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>방법: PInvoke를 사용 하 여 포함된 포인터 마샬링

플랫폼 호출 (P/Invoke) 기능을 사용 하 여 관리 코드에서 관리 되지 않는 Dll에서 구현 되는 함수를 호출할 수 있습니다. DLL에 대 한 소스 코드를 사용할 수 없는 경우 P/Invoke 상호 운용에 대 한 유일한 옵션입니다. 그러나 Visual 다른.NET 언어와 달리 C++ P/Invoke를 대안을 제공 합니다. 자세한 내용은 참조 하세요. [사용 C++ (암시적 PInvoke) Interop](../dotnet/using-cpp-interop-implicit-pinvoke.md) 하 고 [방법: 사용 하 여 포인터를 포함 하는 마샬링 C++ Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)합니다.

## <a name="example"></a>예제

구조체를 네이티브 코드로 전달 네이티브 구조체에 데이터 레이아웃 측면에서 해당 하는 관리 되는 구조 만들어짐이 필요 합니다. 그러나 포인터를 포함 하는 구조체에는 특별 한 처리가 필요 합니다. 기본 구조에 포함 된 각 포인터에 대 한 구조체의 관리 되는 버전의 인스턴스를 포함 해야 합니다 <xref:System.IntPtr> 형식입니다. 또한 메모리 이러한 인스턴스는 명시적으로 할당 해야에 대 한 초기화 및 사용 하 여 해제 합니다 <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>, <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A>, 및 <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> 메서드.

다음 코드는 비관리 및 관리 되는 모듈 구성 됩니다. 관리 되지 않는 모듈에 대 한 포인터를 포함 하는 ListString 라는 구조를 받아들이는 함수입니다 및 TakesListStruct 라는 함수를 정의 하는 DLL입니다. 관리 되는 모듈은 TakesListStruct 함수 가져오고 MListStruct double *로 표시 되는 점을 제외 하 고 네이티브 ListStruct에 해당 하는 호출 구조를 정의 하는 명령줄 응용 프로그램을 <xref:System.IntPtr> 인스턴스. TakesListStruct를 호출 하기 전에 main 함수를 할당 하 고이 필드를 참조 하는 메모리를 초기화 합니다.

```cpp
// TraditionalDll6.cpp
// compile with: /EHsc /LD
#include <stdio.h>
#include <iostream>
#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

#pragma pack(push, 8)
struct ListStruct {
   int count;
   double* item;
};
#pragma pack(pop)

extern "C" {
   TRADITIONALDLL_API void TakesListStruct(ListStruct);
}

void TakesListStruct(ListStruct list) {
   printf_s("[unmanaged] count = %d\n", list.count);
   for (int i=0; i<list.count; i++)
      printf_s("array[%d] = %f\n", i, list.item[i]);
}
```

```cpp
// EmbeddedPointerMarshalling.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Sequential, Pack=8)]
value struct MListStruct {
   int count;
   IntPtr item;
};

value struct TraditionalDLL {
    [DllImport("TraditionalDLL6.dll")]
   static public void TakesListStruct(MListStruct);
};

int main() {
   array<double>^ parray = gcnew array<double>(10);
   Console::WriteLine("[managed] count = {0}", parray->Length);

   Random^ r = gcnew Random();
   for (int i=0; i<parray->Length; i++) {
      parray[i] = r->NextDouble() * 100.0;
      Console::WriteLine("array[{0}] = {1}", i, parray[i]);
   }

   int size = Marshal::SizeOf(double::typeid);
   MListStruct list;
   list.count = parray->Length;
   list.item = Marshal::AllocCoTaskMem(size * parray->Length);

   for (int i=0; i<parray->Length; i++) {
      IntPtr t = IntPtr(list.item.ToInt32() + i * size);
      Marshal::StructureToPtr(parray[i], t, false);
   }

   TraditionalDLL::TakesListStruct( list );
   Marshal::FreeCoTaskMem(list.item);
}
```

사용 하 여 기존의 관리 되는 코드에 노출 되지 않습니다 없는 부분 DLL #include 지시문입니다. 사실, DLL은 액세스 런타임에 되므로 문제 함수를 사용 하 여 가져온 <xref:System.Runtime.InteropServices.DllImportAttribute> 컴파일 시 검색 되지 것입니다.

## <a name="see-also"></a>참고자료

[C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
