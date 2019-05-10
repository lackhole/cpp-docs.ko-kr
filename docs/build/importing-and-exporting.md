---
title: 가져오기 및 내보내기
ms.date: 05/06/2019
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
ms.openlocfilehash: 03931f7f128ab0666890bb8e76677db67dda8fc7
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220632"
---
# <a name="importing-and-exporting"></a>가져오기 및 내보내기

응용 프로그램에 공용 기호를 가져오거나 두 메서드를 사용 하 여 DLL에서 함수를 내보낼 수 있습니다.

- 모듈 정의 (.def) 파일을 사용 하 여 DLL을 빌드할 때

- 키워드를 사용 하 여 **__declspec** 하거나 **__declspec (dllexport)** 주 응용 프로그램의 함수 정의에서

## <a name="using-a-def-file"></a>.Def 파일을 사용 하 여

모듈 정의 (.def) 파일은 DLL의 다양 한 특성을 설명 하는 하나 이상의 모듈 문이 들어 있는 텍스트 파일입니다. 사용 하지 않는 경우 **__declspec (dllimport)** 또는 **__declspec (dllexport)** DLL을 DLL의 함수를 내보내려면.def 파일이 필요 합니다.

.Def 파일을 사용할 수 있습니다 [응용 프로그램으로 가져오기](importing-using-def-files.md) 나 [DLL에서 내보내기](exporting-from-a-dll-using-def-files.md)합니다.

## <a name="using-declspec"></a>__Declspec를 사용 하 여

사용할 필요가 없습니다 **__declspec (dllimport)** 이렇게 하지만 올바르게 컴파일되도록 하려면 코드에 대 한 더 나은 코드를 생성 하도록 컴파일러에 있습니다. 컴파일러는 함수에에서 있는지 여부를 DLL를 DLL 경계를 교차 하는 함수 호출에 제공 됩니다 일반적으로 간접 참조 수준을 건너뛰는 코드를 생성 하기 위해 컴파일러를 허용 하는 것을 결정할 수 없기 때문에 더 나은 코드를 생성할 수 있습니다. 그러나 사용 해야 합니다 **__declspec (dllimport)** DLL에 사용 되는 변수를 가져오려고 합니다.

적절 한.def 파일의 EXPORTS 섹션을 사용 하 여 **__declspec (dllexport)** 필요 하지 않습니다. **__declspec (dllexport)** .def 파일을 사용 하지 않고.exe 또는.dll 파일에서 함수 내보내기 하는 쉬운 방법을 제공 하기 위해 추가 되었습니다.

Win32 이식 가능한 실행 파일 형식으로 가져오기를 수정 하기 위한 방문 해야 하는 페이지 수를 최소화 하도록 설계 되었습니다. 이렇게 하려면 가져오기 주소 테이블을 호출 하는 한 곳에서 모든 프로그램에 대 한 모든 가져오기 주소를 배치 합니다. 이렇게 하면 로더이 가져오기에 액세스할 때만 하나 또는 두 개의 페이지를 수정할 수 있습니다.

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [응용 프로그램으로 가져오기](importing-into-an-application-using-declspec-dllimport.md)

- [DLL에서 내보내기](exporting-from-a-dll.md)

## <a name="see-also"></a>참고자료

[C를 만들기 /C++ Visual Studio에서 Dll](dlls-in-visual-cpp.md)
