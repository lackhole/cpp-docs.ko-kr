---
title: '예외: 예외 catch 및 삭제'
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
ms.openlocfilehash: 511850c3c17a4eb70529202f4b0c2b36132fc8ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173295"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>예외: 예외 catch 및 삭제

다음 지침 및 예제를 catch 하 고 예외를 삭제 하는 방법을 보여 줍니다. 대 한 자세한 내용은 합니다 **시도**, **catch**, 및 **throw** 키워드를 참조 하십시오 [ C++ 예외 처리](../cpp/cpp-exception-handling.md).

예외 핸들러가 예외를 삭제 하지 않으면 예외를 catch 하는 코드 때마다 메모리 누수가 발생 하기 때문에, 처리 된 예외 개체를 삭제 해야 합니다.

프로그램 **catch** 블록에서 예외를 삭제 해야 경우:

- 합니다 **catch** 블록에는 새 예외를 throw 합니다.

   물론, 동일한 예외가 다시 throw 되는 경우 예외를 삭제 해야 합니다.

   [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- 내에서 실행 하 여 반환 된 **catch** 블록입니다.

> [!NOTE]
>  삭제 하는 경우는 `CException`를 사용 하 여는 `Delete` 멤버 함수는 예외를 삭제 합니다. 사용 하지 않는 합니다 **삭제** 키워드를 힙에 예외가 없는 경우 오류가 발생할 수 있으므로 합니다.

#### <a name="to-catch-and-delete-exceptions"></a>Catch 하 고 예외를 삭제 하려면

1. 사용 합니다 **시도** 설정 하는 키워드는 **시도** 블록입니다. 내에서 예외를 throw 할 수 있는 모든 프로그램 문을 실행 하는 **시도** 블록입니다.

   사용 된 **catch** 설정 하는 키워드를 **catch** 블록. 예외 처리 코드에 배치 된 **catch** 블록. 코드를 **catch** 블록은 경우에 실행 됩니다 내의 코드는 **시도** 블록에 지정 된 형식의 예외를 throw 합니다 **catch** 문.

   스 켈 레 톤에서는 다음 방법을 **시도** 및 **catch** 블록은 일반적으로 정렬 합니다.

   [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   첫 번째 제어가 전달 예외가 throw 되 면 **catch** 선언이 예외가 예외 형식과 일치 하는 블록입니다. 다양 한 유형의 순차를 사용 하 여 예외를 선택적으로 처리할 수 있습니다 **catch** 아래에 나열 된 차단:

   [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

자세한 내용은 참조 하세요. [예외: MFC 예외 매크로에서 변환](../mfc/exceptions-converting-from-mfc-exception-macros.md)합니다.

## <a name="see-also"></a>참고자료

[예외 처리](../mfc/exception-handling-in-mfc.md)
