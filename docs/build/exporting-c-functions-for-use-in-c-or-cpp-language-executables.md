---
title: C 함수를 C 또는 C++ 언어 실행 파일에서 사용할 수 있도록 내보내기
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], exporting
- functions [C], C or C++ executables and
- __cplusplus macro
- exporting DLLs [C++], C functions in C++ executables
- exporting functions [C++], C functions in C++ executables
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
ms.openlocfilehash: b7ba2ed30615efb3b05e71cecf0ea69898feb8ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273575"
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>C 함수를 C 또는 C++ 언어 실행 파일에서 사용할 수 있도록 내보내기

DLL에 함수를 포함 하는 경우 C 언어에서 액세스 하려는 C로 작성 또는 C++ 를 사용 해야 언어 모듈을 **__cplusplus** 언어를 결정 하는 전처리기 매크로 컴파일되고 이러한 선언 사용 되는 경우에 C 링크가 있는 함수는 C++ 언어 모듈입니다. 이 기술을 사용 하 여 DLL에 대 한 헤더 파일을 제공 하는 경우 C에서 이러한 함수를 사용할 수 있습니다 및 C++ 사용자가 변경 되지 않고 있습니다.

다음 코드와 C에서 사용할 수 있는 헤더 파일 및 C++ 클라이언트 응용 프로그램:

```h
// MyCFuncs.h
#ifdef __cplusplus
extern "C" {  // only need to export C interface if
              // used by C++ source code
#endif

__declspec( dllimport ) void MyCFunc();
__declspec( dllimport ) void AnotherCFunc();

#ifdef __cplusplus
}
#endif
```

C 함수를 연결 해야 하는 경우에 C++ 실행 파일 및 함수 선언이 헤더 파일에 사용 하지 않은 위의 방법을 C++ 원본 파일 컴파일러가 C 함수 이름을 지정 하지 않도록 설정 하려면 다음을 수행 합니다.

```cpp
extern "C" {
#include "MyCHeader.h"
}
```

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [.def 파일을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport)을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기](exporting-and-importing-using-afx-ext-class.md)

- [사용할 내보내기 방법 결정](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport)을 사용하여 응용 프로그램으로 가져오기](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 초기화](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [데코레이팅된 이름](reference/decorated-names.md)

- [extern을 사용하여 링크 지정](../cpp/using-extern-to-specify-linkage.md)

## <a name="see-also"></a>참고자료

[DLL에서 내보내기](exporting-from-a-dll.md)
