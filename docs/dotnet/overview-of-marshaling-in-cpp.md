---
title: C++ 마샬링 개요
ms.date: 06/28/2018
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
ms.openlocfilehash: 9e3b8f561ce6609eb2afedb527a16c4803f69c53
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384740"
---
# <a name="overview-of-marshaling-in-c"></a>C++ 마샬링 개요

혼합된 모드의 경우에 따라 마샬링해야 네이티브 및 관리 되는 형식 간의 데이터. 도입 된 visual Studio 2008 합니다 *마샬링 라이브러리* 하는 데 마샬링할을 간단한 방법으로 데이터를 변환 합니다.  마샬링 라이브러리 함수의 집합을 구성 및 `marshal_context` 공용 형식에 대 한 마샬링을 수행 하는 클래스입니다. 라이브러리에서 이러한 헤더에 정의 되어는 **msclr 포함** Visual Studio 버전에 대 한 디렉터리:

|헤더|설명|
|---------------|-----------------|
|marshal.h|`marshal_context` 클래스 및 상황에 맞는 없는 마샬링 함수|
|marshal_atl.h| ATL 형식을 마샬링하는 함수|
|marshal_cppstd.h|표준의 마샬링을 함수 C++ 형식|
|marshal_windows.h|Windows 형식 마샬링에 대 한 함수|

에 대 한 기본 경로 **msclr** 폴더는 다음과 같은 버전에 따라 있고 빌드 번호:

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

유무에 관계 없이 마샬링 라이브러리를 사용할 수는 [marshal_context 클래스](../dotnet/marshal-context-class.md)합니다. 일부 변환 컨텍스트가 필요 합니다. 다른 변환을 사용 하 여 구현할 수 있습니다 합니다 [marshal_as](../dotnet/marshal-as.md) 함수입니다. 다음 표에 현재 지원 되는 변환이, 컨텍스트를의 필요 여부 및 마샬링 파일에 포함 해야 합니다.

|형식에서|입력|마샬링 메서드|파일 포함|
|---------------|-------------|--------------------|------------------|
|System::String^|const char \*|marshal_context|marshal.h|
|const char \*|System::String^|marshal_as|marshal.h|
|Char \*|System::String^|marshal_as|marshal.h|
|System::String^|const wchar_t\*|marshal_context|marshal.h|
|const wchar_t \*|System::String^|marshal_as|marshal.h|
|wchar_t \*|System::String^|marshal_as|marshal.h|
|System::IntPtr|HANDLE|marshal_as|marshal_windows.h|
|HANDLE|System::IntPtr|marshal_as|marshal_windows.h|
|System::String^|BSTR|marshal_context|marshal_windows.h|
|BSTR|System::String^|marshal_as|marshal.h|
|System::String^|bstr_t|marshal_as|marshal_windows.h|
|bstr_t|System::String^|marshal_as|marshal_windows.h|
|System::String^|std::string|marshal_as|marshal_cppstd.h|
|std::string|System::String^|marshal_as|marshal_cppstd.h|
|System::String^|std::wstring|marshal_as|marshal_cppstd.h|
|std::wstring|System::String^|marshal_as|marshal_cppstd.h|
|System::String^|CStringT\<char>|marshal_as|marshal_atl.h|
|CStringT\<char>|System::String^|marshal_as|marshal_atl.h|
|System::String^|CStringT<wchar_t>|marshal_as|marshal_atl.h|
|CStringT<wchar_t>|System::String^|marshal_as|marshal_atl.h|
|System::String^|CComBSTR|marshal_as|marshal_atl.h|
|CComBSTR|System::String^|marshal_as|marshal_atl.h|

마샬링 형식을 네이티브로 관리 되는 데이터를 마샬링하는 네이티브 형식으로 변환 하는 정리 자동에 대 한 소멸자가 없는 경우에 컨텍스트에 필요 합니다. 마샬링 컨텍스트는 해당 소멸자에서 할당 된 기본 데이터 형식을 제거합니다. 따라서 컨텍스트에서 삭제 될 때까지 컨텍스트를 필요로 하는 변환은 잘못 됩니다. 마샬링된 값을 저장 하려면 고유한 변수 값을 복사 해야 합니다.

> [!NOTE]
>  포함 된 `NULL`의문자열에 문자열을 마샬링 한 결과를 보장 되지 않습니다. 포함 된 `NULL`s 잘립니다 문자열 발생할 수 있습니다 또는 유지 될 수 있습니다.

이 예제에서는 include 헤더 선언에서 msclr 디렉터리를 포함 하는 방법을 보여 줍니다.

`#include "msclr\marshal_cppstd.h"`

마샬링 라이브러리는 확장 가능 하므로 고유한 마샬링 형식을 추가할 수 있습니다. 마샬링 라이브러리를 확장 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 마샬링 라이브러리 확장명](../dotnet/how-to-extend-the-marshaling-library.md)합니다.

이전 버전에서 사용 하 여 데이터를 마샬링할 수 없습니다 [플랫폼 호출](/dotnet/framework/interop/consuming-unmanaged-dll-functions)합니다. 에 대 한 자세한 내용은 `PInvoke`를 참조 하세요 [관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)합니다.

## <a name="see-also"></a>참고자료

[C++ 지원 라이브러리](../dotnet/cpp-support-library.md)<br/>
[방법: 마샬링 라이브러리 확장](../dotnet/how-to-extend-the-marshaling-library.md)
