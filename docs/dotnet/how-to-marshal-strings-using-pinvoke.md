---
title: '방법: PInvoke를 사용 하는 문자열 마샬링'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
ms.openlocfilehash: f316e33f1711ea0053fb68c0af7e89f90b793e05
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404405"
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>방법: PInvoke를 사용 하는 문자열 마샬링

이 항목에서는 C 스타일 문자열 CLR 문자열을 사용 하 여 호출 하는 방법을 네이티브 함수에 설명 지원.NET Framework 플랫폼 호출을 사용 하 여 system:: string을 입력 합니다. Visual C++ 프로그래머는 사용 하는 것이 좋습니다는 C++ Interop 기능 대신 (가능한 경우) P/Invoke는 작은 컴파일 타임 오류를 보고, 형식이 안전한 아니며 구현 되기 번거로울 수를 제공 하기 때문입니다. 관리 되지 않는 API는 DLL로 패키지 하 고 소스 코드를 사용할 수 없는 경우 다음 P/Invoke 유일한 옵션 이지만 참조이 고, 그렇지 [사용 C++ (암시적 PInvoke) Interop](../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다.

관리 및 관리 되지 않는 문자열에에서 배치 되어 다른 방식으로 메모리를 필요 하므로 관리 되는 관리 되지 않는 함수에서 문자열을 전달 합니다 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 문자열 데이터를 마샬링하기 위한 필요한 변환 메커니즘을 삽입 하도록 컴파일러에 지시 하는 특성 올바르고 안전 하 게 합니다.

내장 데이터 형식만 사용 하는 함수의 <xref:System.Runtime.InteropServices.DllImportAttribute> 는 네이티브 함수에 대해서-C 스타일 문자열에 대 한 핸들을 사용 하도록 이러한 진입점을 정의 하는 대신 문자열을 전달할 관리 되는 진입점을 선언 하는 데는 <xref:System.String> 형식 대신 사용할 수 있습니다. 이 경우 필요한 변환을 수행 하는 코드를 삽입 하도록 컴파일러에 라는 메시지가 표시 됩니다. 각 함수 인수 문자열을 사용 하는 관리 되지 않는 함수에 대 한는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 문자열 개체를 기본 함수를 C 스타일 문자열로 마샬링되어야 한다는 나타내기 위해 사용 해야 합니다.

## <a name="example"></a>예제

다음 코드는 비관리 및 관리 되는 모듈 구성 됩니다. 관리 되지 않는 모듈에는 char *의 형태로 ANSI C 스타일 문자열로 받아들이는 TakesAString 라는 함수를 정의 하는 DLL입니다. 관리 되는 모듈은 TakesAString 함수를 가져오지만 char 대신 관리 되는 System.String으로 정의 하는 명령줄 응용 프로그램을\*입니다. <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성 TakesAString 호출 되 면 관리 되는 문자열을 마샬링되어야 하는 방법을 나타내는 데 사용 됩니다.

```
// TraditionalDll2.cpp
// compile with: /LD /EHsc
#include <windows.h>
#include <stdio.h>
#include <iostream>

using namespace std;

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAString(char*);
}

void TakesAString(char* p) {
   printf_s("[unmanaged] %s\n", p);
}
```

```
// MarshalString.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL
{
   [DllImport("TraditionalDLL2.dll")]
      static public void
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);
};

int main() {
   String^ s = gcnew String("sample string");
    Console::WriteLine("[managed] passing managed string to unmanaged function...");
   TraditionalDLL::TakesAString(s);
   Console::WriteLine("[managed] {0}", s);
}
```

이 방법을 사용 하면 관리 되는 문자열의 복사본에서 네이티브 함수에서 문자열에 대 한 변경 내용을 반영 되지 것입니다 있도록 관리 되지 않는 힙에서 생성 해야 하는 문자열의 복사본입니다.

기존의 통해 관리 되는 코드에 노출 되지 않습니다 없는 부분 DLL #include 지시문입니다. 사실, DLL은 액세스만, 런타임 시 되므로 문제 함수를 사용 하 여 가져온 `DllImport` 컴파일 시 검색 되지 것입니다.

## <a name="see-also"></a>참고자료

[C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
