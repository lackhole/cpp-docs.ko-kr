---
title: __Declspec (dllimport)을 사용 하 여 응용 프로그램으로 가져오기
ms.date: 11/04/2016
f1_keywords:
- __declspec
- dllimport
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
ms.openlocfilehash: 30e0f6517f2d749962c5cf49dddb1662c9ccf129
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810226"
---
# <a name="import-into-an-application-using-declspecdllimport"></a>__Declspec (dllimport)을 사용 하 여 응용 프로그램으로 가져오기

DLL에서 정의 된 공용 기호를 사용 하는 프로그램을 가져오는 라고 합니다. Dll을 사용 하 여 빌드를 사용 하는 응용 프로그램 사용에 대 한 헤더 파일을 만들 때 **__declspec (dllimport)** 의 공용 기호를 선언 합니다. 키워드 **__declspec (dllimport)** 또는.def 파일을 사용 하 여 내보내면 든 관계 없이 작동 합니다 **__declspec (dllexport)** 키워드입니다.

코드를 읽기 쉽게 정의 대 한 매크로 **__declspec (dllimport)** 매크로 사용 하 여 각 가져온된 기호를 선언 합니다.

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

사용 하 여 **__declspec (dllimport)** 함수 선언에서은 하지만 컴파일러가이 키워드를 사용 하는 경우 보다 효율적인 코드를 생성 합니다. 그러나 사용 해야 합니다 **__declspec (dllimport)** 가져오기 개체가 실행 DLL의 공용 데이터 기호 및 개체에 액세스 합니다. 사용자 DLL 가져오기 라이브러리를 사용 하 여 링크 해야 note 합니다.

DLL과 클라이언트 응용 프로그램 모두에 동일한 헤더 파일을 사용할 수 있습니다. 이렇게 하려면 DLL 빌드 또는 클라이언트 응용 프로그램을 빌드하는 지 여부를 나타내는 특수 전처리기 기호를 사용 합니다. 예를 들어:

```
#ifdef _EXPORTING
   #define CLASS_DECLSPEC    __declspec(dllexport)
#else
   #define CLASS_DECLSPEC    __declspec(dllimport)
#endif

class CLASS_DECLSPEC CExampleA : public CObject
{ ... class definition ... };
```

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [DLL 초기화](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [인라인 함수 가져오기 및 내보내기](importing-and-exporting-inline-functions.md)

- [상호 가져오기](mutual-imports.md)

## <a name="see-also"></a>참고자료

[애플리케이션으로 가져오기](importing-into-an-application.md)
