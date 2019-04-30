---
title: '방법: PInvoke를 사용 하는 배열 마샬링'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
ms.openlocfilehash: 60b49135928e3dadffc2a3c7a422646d2f3a768d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325444"
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>방법: PInvoke를 사용 하는 배열 마샬링

이 항목에서는 C 스타일 문자열 CLR 문자열 형식을 사용 하 여 호출 하는 방법을 네이티브 함수에 설명 <xref:System.String> 지원.NET Framework 플랫폼 호출을 사용 합니다. Visual C++ 프로그래머는 사용 하는 것이 좋습니다는 C++ Interop 기능 대신 (가능한 경우) P/Invoke는 작은 컴파일 타임 오류를 보고, 형식이 안전한 아니며 구현 되기 번거로울 수를 제공 하기 때문입니다. P/Invoke가 유일한 옵션인 관리 되지 않는 API는 DLL로 패키지 하 고 소스 코드를 사용할 수 없는 경우 (참조이 고, 그렇지 [사용 C++ (암시적 PInvoke) Interop](../dotnet/using-cpp-interop-implicit-pinvoke.md)).

## <a name="example"></a>예제

네이티브 및 관리 되는 배열에에서 배치 되어 다른 방식으로 메모리를 성공적으로 관리 되 는/관리 경계를 넘어 전달 마샬링 또는 변환 해야 합니다. 이 항목에서는 어떻게 단순 (blitable) 항목의 배열을 전달할 수 네이티브 함수가 관리 코드에서 하는 방법을 보여 줍니다.

관리/관리 되지 않는 데이터는 일반적으로 마샬링 true 인는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성 사용 되는 각 네이티브 함수에 대 한 관리 되는 진입점을 만드는 데 사용 됩니다. 함수의 배열을 인수로 사용 하는 경우는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성 데이터를 마샬링하는 방법을 지정 컴파일러에도 사용 해야 합니다. 다음 예제에서는 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 관리 되는 배열을 C 스타일 배열로 마샬링됩니다 있는지를 나타내는 데 사용 됩니다.

다음 코드는 비관리 및 관리 되는 모듈 구성 됩니다. 관리 되지 않는 모듈에는 정수 배열을 허용 하는 함수를 정의 하는 DLL입니다. 두 번째 모듈은 있지만이 함수를 가져옵니다 하 고, 관리 되는 배열 측면에서 정의 하 고, 사용 하는 관리 되는 명령줄 응용 프로그램을 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 배열 호출 될 때 네이티브 배열로 변환 되어야 함을 지정 하는 특성입니다.

/Clr을 사용한 관리 되는 모듈이 컴파일됩니다.

```cpp
// TraditionalDll4.cpp
// compile with: /LD /EHsc
#include <iostream>

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);
}

void TakesAnArray(int len, int a[]) {
   printf_s("[unmanaged]\n");
   for (int i=0; i<len; i++)
      printf("%d = %d\n", i, a[i]);
}
```

```cpp
// MarshalBlitArray.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL {
   [DllImport("TraditionalDLL4.dll")]
   static public void TakesAnArray(
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);
};

int main() {
   array<int>^ b = gcnew array<int>(3);
   b[0] = 11;
   b[1] = 33;
   b[2] = 55;
   TraditionalDLL::TakesAnArray(3, b);

   Console::WriteLine("[managed]");
   for (int i=0; i<3; i++)
      Console::WriteLine("{0} = {1}", i, b[i]);
}
```

기존를 통해 관리 되는 코드에 노출 되지 않습니다 없는 부분 DLL #include 지시문입니다. 사실, DLL를 실행할 때만 액세스 하므로 문제 함수를 사용 하 여 가져온 <xref:System.Runtime.InteropServices.DllImportAttribute> 컴파일 시 검색 되지 것입니다.

## <a name="see-also"></a>참고자료

[C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
