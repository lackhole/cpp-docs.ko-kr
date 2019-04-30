---
title: '방법: PInvoke를 사용 하 여 관리 되는 코드에서 네이티브 Dll 호출'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
ms.openlocfilehash: e51e094cc013250fc254a09e279745f1f9c108ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222813"
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>방법: PInvoke를 사용 하 여 관리 되는 코드에서 네이티브 Dll 호출

플랫폼 호출 (P/Invoke) 기능을 사용 하 여 관리 코드에서 관리 되지 않는 Dll에서 구현 되는 함수를 호출할 수 있습니다. DLL에 대 한 소스 코드를 사용할 수 없는 경우 P/Invoke 상호 운용에 대 한 유일한 옵션입니다. 그러나 Visual 다른.NET 언어와 달리 C++ P/Invoke를 대안을 제공 합니다. 자세한 내용은 [사용 C++ (암시적 PInvoke) Interop](../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다.

## <a name="example"></a>예제

다음 코드 예제에서는 Win32 [GetSystemMetrics](/windows/desktop/api/winuser/nf-winuser-getsystemmetrics) 현재 픽셀의 화면 해상도 검색 하는 함수입니다.

내장 형식만 인수로 사용할 값을 반환 하는 함수에 대 한 추가 작업 없이 필요 합니다. 함수 포인터, 배열 및 구조와 같은 다른 데이터 형식에 적절 한 데이터 마샬링이 되도록 추가 특성을 필요 합니다.

필요한 경우에 것이 좋습니다이 예제에서 설명한 대로 전역 네임 스페이스에 존재 하지 않는 있도록 P/Invoke 선언 값 클래스의 정적 멤버를 확인 합니다.

```
// pinvoke_basic.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value class Win32 {
public:
   [DllImport("User32.dll")]
   static int GetSystemMetrics(int);

   enum class SystemMetricIndex {
      // Same values as those defined in winuser.h.
      SM_CXSCREEN = 0,
      SM_CYSCREEN = 1
   };
};

int main() {
   int hRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CXSCREEN) );
   int vRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CYSCREEN) );
   Console::WriteLine("screen resolution: {0},{1}", hRes, vRes);
}
```

## <a name="see-also"></a>참고자료

[C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
