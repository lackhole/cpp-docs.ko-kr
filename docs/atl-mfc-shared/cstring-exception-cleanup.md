---
title: CString 예외 정리
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: d131ce8ebe5158d7f3a567580064068742b63707
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746229"
---
# <a name="cstring-exception-cleanup"></a>CString 예외 정리

이전 버전의 MFC 정리 하는 것이 중요 했습니다 [CString](../atl-mfc-shared/reference/cstringt-class.md) 사용 후 개체입니다. MFC 버전 3.0 이상에서는 명시적 정리 작업이 필요 없습니다.

C + + 예외 처리 이제 MFC를 사용 하는 메커니즘에서 예외가 발생 한 후 정리를 걱정할 필요가 없습니다. 하는 방법에 대 한 c + + "" 지우며 스택을 해제 되 면 예외를 참조 하십시오 [try, catch 및 throw 문](../cpp/try-throw-and-catch-statements-cpp.md)합니다. MFC를 사용 하는 경우에 **시도**/**CATCH** c + + 키워드 대신 매크로 **시도** 하 고 **catch**, MFC c + +를 사용 하 여 아래 예외 메커니즘 하도록 할 필요가 없습니다 명시적으로 정리 합니다.

## <a name="see-also"></a>참고자료

[문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[예외 처리](../mfc/exception-handling-in-mfc.md)
