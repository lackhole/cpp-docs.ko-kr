---
title: C++에서 명시적 PInvoke 사용(DllImport 특성)
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
ms.openlocfilehash: ee9d77920f04f7eba5112c66a906b02b7fc4a658
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384428"
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>C++에서 명시적 PInvoke 사용(DllImport 특성)

사용 하 여 명시적 플랫폼 호출 (또는 PInvoke) 기능을 제공 하는.NET Framework는 `Dllimport` 특성 관리 되는 응용 프로그램이 Dll 내에서 패키지 관리 되지 않는 함수를 호출할 수 있도록 합니다. 명시적 PInvoke 관리 되지 않는 Api는 Dll로 패키지 된 소스 코드를 사용할 수 없는 경우에 필요 합니다. PInvoke 필요 예를 들어 Win32 함수를 호출 합니다. 그렇지 않은 경우 암시적 P를 사용 {Invoke; 참조 [사용 C++ (암시적 PInvoke) Interop](../dotnet/using-cpp-interop-implicit-pinvoke.md) 자세한 내용은 합니다.

PInvoke를 사용 하 여 작동 <xref:System.Runtime.InteropServices.DllImportAttribute>합니다. 첫 번째 인수로 DLL의 이름을, 사용 하는이 특성에 사용 되는 각 DLL 진입점에 대 한 함수 선언 앞에 배치 됩니다. 함수의 시그니처와 해당 DLL에서 내보내기 함수의 이름과 같아야 합니다. (그러나 일부 형식 변환이 정의 하 여 암시적으로 수행할 수 있습니다는 `DllImport` 관리 되는 형식으로 선언 합니다.)

결과 필요한 전환 코드 (또는 썽크)를 포함 하는 각 네이티브 DLL 함수에 대 한 관리 되는 진입점 및 간단한 데이터 변환 합니다. 이러한 진입점을 통해 DLL로 관리 되는 함수를 호출할 수 있습니다. PInvoke의 결과로 모듈을 삽입 하는 코드는 완전히 관리 됩니다.

## <a name="in-this-section"></a>섹션 내용

- [관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)

- [방법: PInvoke를 사용하여 관리 코드로부터 네이티브 DLL 호출](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)

- [방법: PInvoke를 사용하여 문자열 마샬링](../dotnet/how-to-marshal-strings-using-pinvoke.md)

- [방법: PInvoke를 사용하여 구조체 마샬링](../dotnet/how-to-marshal-structures-using-pinvoke.md)

- [방법: PInvoke를 사용하여 배열 마샬링](../dotnet/how-to-marshal-arrays-using-pinvoke.md)

- [방법: PInvoke를 사용하여 함수 포인터 마샬링](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)

- [방법: PInvoke를 사용하여 포함 포인터 마샬링](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)

## <a name="see-also"></a>참고자료

[관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)
