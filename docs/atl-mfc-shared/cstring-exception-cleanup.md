---
title: CString 예외 정리
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: d131ce8ebe5158d7f3a567580064068742b63707
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236630"
---
# <a name="cstring-exception-cleanup"></a>CString 예외 정리

이전 버전의 MFC 정리 하는 것이 중요 했습니다 [CString](../atl-mfc-shared/reference/cstringt-class.md) 사용 후 개체입니다. MFC 버전 3.0 이상에서는 명시적 정리 작업이 필요 없습니다.

아래는 C++ 이제 MFC를 사용 하는 예외 처리 메커니즘을 필요가 없습니다 예외가 발생 한 후 정리에 대 한 걱정 합니다. 하는 방법에 대 한 C++ ""는 스택을 예외 확인 되 면, 참조 [try, catch 및 throw 문](../cpp/try-throw-and-catch-statements-cpp.md)합니다. MFC를 사용 하는 경우에 **시도**/**CATCH** 매크로 대신 합니다 C++ 키워드 **시도** 및 **catch**, MFC를 사용 하는 C++ , 아래 예외 메커니즘 하도록 할 필요가 없습니다 명시적으로 정리 합니다.

## <a name="see-also"></a>참고자료

[문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[예외 처리](../mfc/exception-handling-in-mfc.md)
