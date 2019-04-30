---
title: 인라인 함수 가져오기 및 내보내기
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions [C++], inline functions
- inline functions [C++], importing
- DLLs [C++], importing
- importing functions [C++]
- DLLs [C++], exporting from
- importing inline functions [C++]
- inline functions [C++], exporting
- functions [C++], importing
- functions [C++], exporting
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
ms.openlocfilehash: ed523d84228124d4a8d99e443c0c744f362f1c56
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273445"
---
# <a name="importing-and-exporting-inline-functions"></a>인라인 함수 가져오기 및 내보내기

가져오는 함수를 인라인으로 정의할 수 있습니다. 그 효과는 표준 함수를 인라인으로 정의할 때와 거의 비슷하며, 이러한 함수 호출은 매크로와 마찬가지로 인라인 코드로 확장됩니다. 함수를 인라인으로 정의하면 효율성을 위해 멤버 함수 일부를 인라인할 수 있는 DLL의 C++ 클래스를 지원하는 데 매우 유용합니다.

가져오는 인라인 함수의 한 가지 특징은 사용자가 함수의 주소를 C++ 형식으로 가져올 수 있다는 점입니다. 컴파일러는 DLL에 상주하는 인라인 함수의 복사본 주소를 반환합니다. 가져오는 인라인 함수의 또 다른 특징은 가져오는 전역 데이터와 달리 가져오는 함수의 정적 지역 데이터를 초기화할 수 있다는 점입니다.

> [!CAUTION]
>  가져온 인라인 함수를 제공할 때에는 버전 충돌이 일어날 수 있으므로 특별히 주의해야 합니다. 인라인 함수는 응용 프로그램 코드로 확장됩니다. 따라서 나중에 이 함수를 다시 쓰는 경우 해당 응용 프로그램을 다시 컴파일해야만 함수가 업데이트됩니다. (반면, 일반적인 DLL 함수는 해당 함수를 사용하는 응용 프로그램을 다시 빌드하지 않아도 업데이트됩니다.)

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [DLL에서 내보내기](exporting-from-a-dll.md)

- [.def 파일을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport)을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기](exporting-and-importing-using-afx-ext-class.md)

- [C++ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [사용할 내보내기 방법 결정](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport)을 사용하여 응용 프로그램으로 가져오기](importing-into-an-application-using-declspec-dllimport.md)

## <a name="see-also"></a>참고자료

[가져오기 및 내보내기](importing-and-exporting.md)
