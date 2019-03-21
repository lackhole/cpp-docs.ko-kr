---
title: 관리 코드에서 네이티브 함수 호출
ms.date: 11/04/2016
helpviewer_keywords:
- native functions called from managed code [C++]
- managed code [C++], interoperability
- platform invoke [C++], interoperability
- interoperabiliy [C++], calling native functions from managed code
- calling native functions from managed code
- interop [C++], calling native functions from managed code
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
ms.openlocfilehash: 285bfabbd5935df303a39ada11c388713ae24f34
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743253"
---
# <a name="calling-native-functions-from-managed-code"></a>관리 코드에서 네이티브 함수 호출

공용 언어 런타임 Platform Invocation Services 또는 PInvoke를는 관리 되는 네이티브 동적 연결 라이브러리 (Dll)의 C 스타일 함수를 호출 하는 코드를 제공 합니다. COM 상호 운용성 It Just Works, "ijw 메커니즘은 런타임에서 동일한 데이터 마샬링이 사용 됩니다.

자세한 내용은 다음을 참조하세요.

- [C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

- [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

이 단원의 샘플에서는 대해서만 설명 하는 방법을 `PInvoke` 사용할 수 있습니다. `PInvoke` 프로시저 마샬링 코드를 작성 하는 대신 특성에 선언적으로 마샬링 정보를 제공할 수 있으므로 사용자 지정된 데이터 마샬링을 간소화할 수 있습니다.

> [!NOTE]
>  마샬링 라이브러리는 최적화 된 방식으로 네이티브 및 관리 되는 환경 간에 데이터를 마샬링하는 대안을 제공 합니다. 참조 [Overview of Marshaling c + +에서](../dotnet/overview-of-marshaling-in-cpp.md) 마샬링 라이브러리에 대 한 자세한 내용은 합니다. 마샬링 라이브러리는 함수에 대 한 데이터만 사용할 수 있습니다.

## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke 및 DllImport 특성

다음 예제에서는 사용을 보여 줍니다. `PInvoke` Visual c + + 프로그램에서 합니다. 네이티브 함수 puts는 msvcrt.dll에서 정의 됩니다. DllImport 특성은 puts 선언에 사용 됩니다.

```
// platform_invocation_services.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[DllImport("msvcrt", CharSet=CharSet::Ansi)]
extern "C" int puts(String ^);

int main() {
   String ^ pStr = "Hello World!";
   puts(pStr);
}
```

다음 샘플 앞의 예와 동일 하지만 IJW를 사용 합니다.

```
// platform_invocation_services_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#include <stdio.h>

int main() {
   String ^ pStr = "Hello World!";
   char* pChars = (char*)Marshal::StringToHGlobalAnsi(pStr).ToPointer();
   puts(pChars);

   Marshal::FreeHGlobal((IntPtr)pChars);
}
```

### <a name="advantages-of-ijw"></a>IJW의 이점

- 쓸 필요가 없습니다 `DLLImport` 특성 선언을 프로그램을 사용 하 여 관리 되지 않는 Api에 대 한 합니다. 방금 헤더 파일 및 가져오기 라이브러리를 사용 하 여 링크를 포함 합니다.

- IJW 메커니즘은 약간 더 빠릅니다 (예를 들어 IJW 스텁이 필요 하지 않은 데이터 항목을 고정 하거나 복사 해야 하는 값은 개발자가 명시적으로 수행 되기 때문에 확인 하려면).

- 명확 하 게 성능 문제를 보여 줍니다. 이 경우 번역할 유니코드 문자열에서 ANSI 문자열 및 해당 하는 경우는 점과 메모리 할당 및 할당 취소 IJW를 사용 하는 코드를 작성 하는 개발자 호출 된다는 사실을 예제의 경우 `_putws` 를 사용 하 여 및 `PtrToStringChars` 성능이 향상 될 것입니다.

- 호출 하면 많은 관리 되지 않는 Api에서 동일한 데이터를 사용 하 여이 한 번 전달 마샬링하고 마샬링된 복사본을 매번 다시 마샬링하 보다 훨씬 효율적입니다.

### <a name="disadvantages-of-ijw"></a>IJW의 단점

- 마샬링 지정 되어야 합니다 명시적으로 대신 코드에서 특성 (있는 자주 적절 한 기본값).

- 마샬링 코드는 인라인, 응용 프로그램 논리의 흐름이 침해 될 소지가 많습니다.

- 명시적 마샬링 Api는 반환할 `IntPtr` 32 비트에서 64 비트 이식성에 대 한 형식을 사용 해야 추가 `ToPointer` 호출 합니다.

C + +에서 노출 되는 특정 메서드는 보다 효율적인 고 명시적인 메서드인 반면 더 복잡해 진다는 합니다.

응용 프로그램은 주로 관리 되지 않는 데이터 형식 또는.NET Framework Api 보다 좀 더 관리 되지 않는 Api를 호출 하는 경우 좋습니다 하는 경우 IJW 기능을 사용 합니다. 대부분 관리 되는 응용 프로그램에서 가끔 관리 되지 않는 API를 호출 하려면 선택은 더 미묘 합니다.

## <a name="pinvoke-with-windows-apis"></a>Windows Api와 함께 PInvoke

PInvoke는 Windows의 함수를 호출 하는 데 유용 합니다.

이 예제에서는 Visual c + + 프로그램을 Win32 API의 일부인 MessageBox 함수와 상호 운용 합니다.

```cpp
// platform_invocation_services_4.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;
typedef void* HWND;
[DllImport("user32", CharSet=CharSet::Ansi)]
extern "C" int MessageBox(HWND hWnd, String ^ pText, String ^ pCaption, unsigned int uType);

int main() {
   String ^ pText = "Hello World! ";
   String ^ pCaption = "PInvoke Test";
   MessageBox(0, pText, pCaption, 0);
}
```

출력은 제목이 PInvoke Test 및 Hello World 텍스트를 포함 하는 메시지 상자입니다.

마샬링 정보도 PInvoke에서 DLL의 함수를 조회 사용 됩니다. User32.dll에서에 실제로 MessageBox 함수가 없지만 CharSet = charset:: Ansi 유니코드 버전인 MessageBoxW 대신 ANSI 버전인 MessageBoxA를 사용 하는 PInvoke 사용 합니다. 일반적으로 ANSI로.NET Framework 문자열 개체의 네이티브 유니코드 형식에서 오버 헤드가 번역은 제거 하는 관리 되지 않는 Api의 유니코드 버전을 사용 하는 것이 좋습니다.

## <a name="when-not-to-use-pinvoke"></a>PInvoke를 사용 하지 않는 경우

PInvoke를 사용 하 여 Dll에서 모든 C 스타일 함수에 대해 적합 하지 않습니다. 예를 들어 있는 함수가 Mylib.dll에에서 다음과 같이 선언 됩니다.

`char * MakeSpecial(char * pszString);`

Visual c + + 응용 프로그램에서 PInvoke를 사용 하는 경우 다음과 유사한 코드를 작성 해야 합니다.

```cpp
[DllImport("mylib")]
extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);
```

이 경우 makespecial 반환 되는 관리 되지 않는 문자열에 대 한 메모리를 삭제할 수 없습니다. PInvoke를 통해 호출 된 다른 함수는 사용자가 할당을 해제할 수 없는 내부 버퍼에 대 한 포인터를 반환 합니다. 이 경우 IJW 기능을 사용 하는 것이 좋습니다.

## <a name="limitations-of-pinvoke"></a>PInvoke의 제한 사항

네이티브 함수를 매개 변수로 사용 했던 것과 동일한 포인터를 반환할 수 없습니다. 네이티브 함수에 PInvoke에서 마샬링 한 포인터를 반환 합니다, 메모리 손상 되 고 예외 충돌 될 수 있습니다.

```cpp
__declspec(dllexport)
char* fstringA(char* param) {
   return param;
}
```

다음 샘플은이 문제를 나타냅니다. 및 출력이 해제 된 메모리에서 가져온 프로그램 올바른 출력 보일 수, 하는 경우에 합니다.

```
// platform_invocation_services_5.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;
#include <limits.h>

ref struct MyPInvokeWrap {
public:
   [ DllImport("user32.dll", EntryPoint = "CharLower", CharSet = CharSet::Ansi) ]
   static String^ CharLower([In, Out] String ^);
};

int main() {
   String ^ strout = "AabCc";
   Console::WriteLine(strout);
   strout = MyPInvokeWrap::CharLower(strout);
   Console::WriteLine(strout);
}
```

## <a name="marshaling-arguments"></a>마샬링 인수

사용 하 여 `PInvoke`를 마샬링할 필요가 없습니다 간에 관리와 같은 폼을 사용 하 여 c + + 네이티브 기본 형식입니다. 예를 들어 마샬링이 없는 Int32와 int 또는 Double과 double 사이는 필수입니다.

그러나 동일한 폼이 없는 형식은 마샬링해야 합니다. Char, string 및 struct 형식이 포함 됩니다. 다음 표에서 다양 한 형식에 대해 마샬러에 사용 하는 매핑을 보여 줍니다.

|wtypes.h|Visual C++|Visual c + + /clr을 사용한|공용 언어 런타임|
|--------------|------------------|-----------------------------|-----------------------------|
|HANDLE|void \*|void \*|IntPtr, UIntPtr|
|BYTE|unsigned char|unsigned char|Byte|
|SHORT|short|short|Int16|
|WORD|unsigned short|unsigned short|UInt16|
|INT|int|int|Int32|
|UINT|unsigned int|unsigned int|UInt32|
|LONG|long|long|Int32|
|BOOL|long|bool|부울|
|DWORD|unsigned long|unsigned long|UInt32|
|ULONG|unsigned long|unsigned long|UInt32|
|CHAR|char|char|Char|
|LPCSTR|Char \*|String ^ [in], StringBuilder ^ [에서 out]|String ^ [in], StringBuilder ^ [에서 out]|
|LPCSTR|const char \*|String ^|문자열|
|LPWSTR|wchar_t \*|String ^ [in], StringBuilder ^ [에서 out]|String ^ [in], StringBuilder ^ [에서 out]|
|LPCWSTR|const wchar_t \*|String ^|문자열|
|FLOAT|float|float|Single|
|DOUBLE|double|double|Double|

마샬러는 자동으로 해당 주소는 관리 되지 않는 함수에 전달 되 면 런타임 힙에 할당 된 메모리를 고정 합니다. 고정 가비지 수집기가 압축 하는 동안 메모리의 할당된 된 블록을 이동할 수 없습니다.

DllImport의 CharSet 매개 변수를이 항목의 앞부분에 표시 된 예제에서는 관리 되는 문자열을 지정 해야 마샬링할 수 있습니다. 이 경우 네이티브 쪽에 대해 ANSI 문자열로 마샬링할 수 해야 합니다.

MarshalAs 특성을 사용 하 여 네이티브 함수의 개별 인수에 대 한 마샬링 정보를 지정할 수 있습니다. 문자열을 마샬링하기 위한 여러 가지 \* 인수: BStr, ANSIBStr, TBStr, LPStr, LPWStr 및 LPTStr 합니다. 기본값은 LPStr입니다.

이 예제에서는 문자열을 더블 바이트 유니코드 문자열 LPWStr로 마샬링됩니다. 출력은 Hello World의 첫 글자! 마샬링된 문자열의 두 번째 바이트는 null이 고 배치 하기 때문에이 문자열의 끝 표식으로 해석 합니다.

```
// platform_invocation_services_3.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[DllImport("msvcrt", EntryPoint="puts")]
extern "C" int puts([MarshalAs(UnmanagedType::LPWStr)] String ^);

int main() {
   String ^ pStr = "Hello World!";
   puts(pStr);
}
```

MarshalAs 특성은 System::Runtime::InteropServices 네임 스페이스입니다. 배열과 같은 다른 데이터 형식 특성을 사용할 수 있습니다.

항목의 앞부분에서 설명 했 듯이 마샬링 라이브러리는 네이티브 및 관리 되는 환경 간에 데이터를 마샬링하기의 최적화 된 새 메서드를 제공 합니다. 자세한 내용은 [Overview of Marshaling c + +에서](../dotnet/overview-of-marshaling-in-cpp.md)합니다.

## <a name="performance-considerations"></a>성능 고려 사항

PInvoke는 오버 헤드가 발생의 10과 30 사이의 x86 명령을 호출 합니다. 이 고정된 비용 외에도 마샬링을 사용 하면 추가 오버 헤드입니다. 관리 및 비관리 코드에서 표현이 동일한 blittable 형식 간에 마샬링 비용은 없습니다. 예를 들어 int와 Int32 사이 변환 비용은 없습니다.

성능 향상을 위해 호출당 데이터를 더 적게 마샬링하는 호출을 많이 하는 대신 최대한 많은 데이터를 마샬링하는 PInvoke 호출을 더 적은 경우

## <a name="see-also"></a>참고자료

[네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)
