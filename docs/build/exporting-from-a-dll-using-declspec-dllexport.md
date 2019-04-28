---
title: __declspec(dllexport)을 사용하여 DLL에서 내보내기
ms.date: 11/04/2016
f1_keywords:
- dllexport
- __declspec
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
ms.openlocfilehash: 3b6b9733776f30fc8dcbfeee709b7d24e0f0187b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195318"
---
# <a name="exporting-from-a-dll-using-declspecdllexport"></a>__declspec(dllexport)을 사용하여 DLL에서 내보내기

Microsoft 도입 **__export** 시각적 개체의 16 비트 컴파일러 버전의 C++ 컴파일러에서 내보내기 이름을 자동으로 생성 하는.lib 파일에 배치할 수 있도록 합니다. 이.lib 파일 DLL을 사용 하 여 연결 하려면 정적.lib와 마찬가지로 사용할 수 있습니다.

새 컴파일러 버전에서는 내보낼 수 있습니다 데이터, 함수, 클래스 또는 클래스 멤버 함수의 사용 하 여 DLL을 **__declspec (dllexport)** 키워드입니다. **__declspec (dllexport)** .def 파일을 사용할 필요가 개체 파일에 내보내기 지시문을 추가 합니다.

데코 레이트 된 내보내려고 할 때이 편의 가장 두드러지게 나타납니다는 C++ 함수 이름입니다. 이름 데코레이션 표준 사양이 없으므로 내보내기 함수의 이름을 컴파일러 버전 간에 변경 될 수 있습니다. 사용 하는 경우 **__declspec (dllexport)**, DLL 및 종속 된.exe 파일은 명명 규칙 변경에 대 한 계정에만 필요 합니다.

많은 내보내기 지시문와 같은 서 수, NONAME 및 PRIVATE.def 파일 에서만에서 설정할 수 있으며.def 파일 없이 이러한 특성을 지정할 방법이 없습니다. 그러나 **__declspec (dllexport)** .def를 사용 하는 것 외에도 파일 빌드 오류가 발생 하지 않습니다.

함수를 내보내려면 합니다 **__declspec (dllexport)** 키워드 키워드가 지정 된 경우 호출 규칙 키워드의 왼쪽에 나타나야 합니다. 예를 들어:

```
__declspec(dllexport) void __cdecl Function1(void);
```

모든 public 데이터 멤버 및 클래스의 멤버 함수를 내보내려면 키워드 해야 클래스 이름의 왼쪽에 다음과 같이 나타납니다.

```
class __declspec(dllexport) CExampleExport : public CObject
{ ... class definition ... };
```

> [!NOTE]
>  `__declspec(dllexport)` 사용 하는 함수에 적용할 수 없습니다는 `__clrcall` 호출 규칙입니다.

함수 프로토타입 및/또는 내보내기 및 추가 클래스를 포함 하는 헤더 파일이 DLL을 빌드할 때 일반적으로 만들고 **__declspec (dllexport)** 헤더 파일의 선언에 있습니다. 코드를 읽기 쉽게 정의 대 한 매크로 **__declspec (dllexport)** 내보내는 각 기호를 사용 하 여 매크로 사용 합니다.

```
#define DllExport   __declspec( dllexport )
```

**__declspec (dllexport)** 함수 이름을 DLL의 내보내기 테이블에 저장 합니다. 테이블의 크기를 최적화 하려면를 참조 하세요 [이름 대신 서 수를 사용 하 여 DLL에서 함수 내보내기](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)합니다.

> [!NOTE]
>  DLL 소스 코드를 Win16에서에서 Win32로 이식 하는 경우 대체의 인스턴스마다 **__export** 사용 하 여 **__declspec (dllexport)** 합니다.

참조로 Win32 Winbase.h 헤더 파일을 통해 검색 합니다. 예제가 **__declspec (dllimport)** 사용 합니다.

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [.def 파일을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-def-files.md)

- [AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기](exporting-and-importing-using-afx-ext-class.md)

- [C++ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C 함수를 C 또는 C++ 언어 실행 파일에서 사용할 수 있도록 내보내기](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [사용할 내보내기 방법 결정](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport)을 사용하여 응용 프로그램으로 가져오기](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 초기화](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [__Declspec 키워드](../cpp/declspec.md)

- [인라인 함수 가져오기 및 내보내기](importing-and-exporting-inline-functions.md)

- [상호 가져오기](mutual-imports.md)

## <a name="see-also"></a>참고자료

[DLL에서 내보내기](exporting-from-a-dll.md)
