---
title: __declspec(dllimport)을 사용하여 데이터 가져오기
ms.date: 11/04/2016
f1_keywords:
- dllimport
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: 74ad93e640a4e961f7670077227bb5c35a42c20f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818429"
---
# <a name="importing-data-using-declspecdllimport"></a>__declspec(dllimport)을 사용하여 데이터 가져오기

사용 하 여 데이터의 경우 **__declspec (dllimport)** 는 간접 참조 계층을 제거 하는 편리한 항목입니다. DLL에서 데이터를 가져올 때에 여전히 가져오기 주소 테이블을 통해 검색 해야 합니다. 앞 **__declspec (dllimport)**, 즉, DLL에서 내보낸 데이터에 액세스 하는 경우 추가 수준의 간접 참조를 위해 기억해 야 했습니다.

```
// project.h
#ifdef _DLL   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

데이터를 내보낼 때 다음에 있습니다. DEF 파일:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

및 해당 DLL 외부에서 액세스 합니다.

```
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

데이터를 표시 하는 경우 **__declspec (dllimport)**, 컴파일러를 간접 참조 코드를 자동으로 생성 합니다. 위의 단계에 걱정할 필요가 없습니다. 앞서 설명한 것 처럼 사용 하지 마세요 **__declspec (dllimport)** DLL을 빌드할 때 데이터에 대해 선언 합니다. DLL 내에서 함수 데이터 개체;에 액세스 하려면 가져오기 주소 테이블을 사용 하지 마십시오 따라서 추가 수준의 간접 참조가 있는 없습니다 됩니다.

DLL에서 데이터를 자동으로 내보내려면이 선언을 사용 합니다.

```
__declspec(dllexport) ULONG ulDataInDLL;
```

## <a name="see-also"></a>참고자료

[애플리케이션으로 가져오기](importing-into-an-application.md)
