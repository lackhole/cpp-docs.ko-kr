---
title: 사용할 내보내기 방법 결정
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- exporting DLLs [C++], method comparison
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
ms.openlocfilehash: 974c32cef87801599ba0d14fd146e84ad874467f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816297"
---
# <a name="determine-which-exporting-method-to-use"></a>사용할 내보내기 방법 결정

두 가지 방법 중 하나로 함수를 내보낼 수-.def 파일 또는 `__declspec(dllexport)` 키워드입니다. 어떤 방법을 사용 하는 것이 DLL에 대 한 더 나은 결정을 하려면 이러한 질문을 고려 합니다.

- 나중에 더 많은 함수를 내보내려면 계획 입니까?

- 다시 작성할 수 있습니다 하거나 다시 빌드할 수 없는 응용 프로그램에서 사용 되는 응용 프로그램에 의해서만 사용 되는 DLL은-타사에서 만든 응용 프로그램 예를 들어?

## <a name="pros-and-cons-of-using-def-files"></a>.Def 파일을 사용 하 여의 장점 및 단점

내보내기 서 수를 제어 하는.def 파일 제공 함수를 내보내는 중입니다. 내보낸된 함수를 DLL에 추가할 때 다른 내보낸된 함수 보다 더 높은 서 수 값을 할당할 수 있습니다. 이렇게 하면 암시적 연결을 사용 하는 응용 프로그램 새 함수가 포함 된 가져오기 라이브러리를 사용 하 여 다시 연결할 필요가 없습니다. 디자인 하는 경우 DLL을 사용 하 여 많은 응용 프로그램에서 새 기능을 추가 하 고 계속 이미 의존 하는 응용 프로그램을 사용 하 여 제대로 작동 하도록 확인 수 있으므로 매우 유용 합니다. 예를 들어, MFC Dll의.def 파일을 사용 하 여 빌드됩니다.

.Def 파일을 사용 하 여 또 다른 이점은 사용할 수 있는 것은 `NONAME` 함수를 내보내려면 특성입니다. 서 수만 DLL의 내보내기 테이블에 추가합니다. 사용 하 여 내보낸 함수의 다를 수 있는 Dll에 대 한는 `NONAME` 특성 DLL 파일의 크기를 줄일 수 있습니다. 모듈 정의 문을 작성 하는 방법에 대 한 자세한 내용은 [모듈 정의 문의 규칙](reference/rules-for-module-definition-statements.md)합니다. 서 수 내보내기에 대 한 정보를 참조 하세요 [이름 대신 서 수를 사용 하 여 DLL에서 함수 내보내기](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)합니다.

.Def 파일을 사용 하는 단점은 인지는 c + + 파일에서 함수를 내보내는 경우 데코레이팅된 이름을.def는에 삽입할 해야 하거나 파일을 이름 데코레이션을 방지 하려면 extern "C"를 사용 하 여 내보낸된 함수를 정의 MSVC 컴파일러에서.

데코레이팅된 이름을.def 파일에 추가한 경우이 사용 하 여 가져올 수 있습니다 합니다 [DUMPBIN](reference/dumpbin-reference.md) 도구 또는 링커를 사용 하 여 [/map](reference/map-generate-mapfile.md) 옵션입니다. 컴파일러에서 생성 되는 트 데코 레이 된 이름이 컴파일러로 적용 됩니다. 따라서 데코레이팅된 이름을.def 파일에 컴파일러에서 생성 되는 경우, DLL에 연결 하는 응용 프로그램 빌드해야 호출 응용 프로그램의 데코레이팅된 이름과 일치 내보낸 동일한 버전의 컴파일러를 사용 하 여 i 이름 n DLL의.def 파일을 사용 합니다.

## <a name="pros-and-cons-of-using-declspecdllexport"></a>__Declspec (dllexport)을 사용 하 여의 장점 및 단점

사용 하 여 `__declspec(dllexport)` .def 파일을 유지 하 고 내보낸 함수의 데코레이팅된 이름을 가져오기에 대해 걱정할 필요가 없습니다 때문에 유용 합니다. 그러나이 방법으로 내보내기의 유용성 의향이 없다면 다시 작성 하는 연결 된 응용 프로그램의 수로 제한 됩니다. 새로운 내보내기 사용 하 여 DLL을 빌드해야 하는 경우 내보낸 c + + 함수의 데코레이팅된 이름을 다시 다른 버전의 컴파일러를 사용 하는 경우 변경 될 수 있으므로 응용 프로그램을 다시 작성할 수도 있습니다.

### <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [.def 파일을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport)을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기](exporting-and-importing-using-afx-ext-class.md)

- [C++ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C 함수를 C 또는 C++ 언어 실행 파일에서 사용할 수 있도록 내보내기](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [__declspec(dllimport)을 사용하여 응용 프로그램으로 가져오기](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 초기화](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [인라인 함수 가져오기 및 내보내기](importing-and-exporting-inline-functions.md)

- [상호 가져오기](mutual-imports.md)

- [데코레이팅된 이름](reference/decorated-names.md)

## <a name="see-also"></a>참고자료

[DLL에서 내보내기](exporting-from-a-dll.md)
