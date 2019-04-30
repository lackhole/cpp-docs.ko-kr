---
title: '예외: MFC 매크로 사용 하 고 C++ 예외'
ms.date: 11/04/2016
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
ms.openlocfilehash: 00e88ddabf3a8e8b591bebae7ebc8ced0e1dc637
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406017"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>예외: MFC 매크로 사용 하 고 C++ 예외

이 문서에서는 두 MFC 예외 처리 매크로 사용 하는 코드 작성 시 고려 사항 설명 및 C++ 예외 처리 키워드입니다.

이 문서에서는 다음 항목을 다룹니다.

- [혼합 예외 키워드 및 매크로](#_core_mixing_exception_keywords_and_macros)

- [Try catch 블록 내에서 블록](#_core_try_blocks_inside_catch_blocks)

##  <a name="_core_mixing_exception_keywords_and_macros"></a> 혼합 예외 키워드 및 매크로

MFC 예외 매크로 혼합할 수 있습니다 하 고 C++ 동일한 프로그램에서 예외 키워드입니다. MFC 매크로와 혼합할 수 없습니다 하지만 C++ 같은 블록에서 예외 키워드로 개체 반면를 범위를 벗어날 때 자동으로 예외 처리 키워드를 사용 하는 코드는 예외를 삭제 하므로 그렇지 않습니다. 자세한 내용은 문서를 참조 하세요. [예외: 예외 catch 및 삭제](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.

매크로 및 키워드 간의 주요 차이점은 매크로 예외 범위를 벗어날 때 "자동으로"는 예외가 삭제는입니다. 이 키워드를 사용 하는 코드는 필요는 없습니다. catch 블록에서 발생 한 예외를 명시적으로 삭제 되어야 합니다. 매크로 혼합 하 고 C++ 예외 키워드로 예외 개체는 삭제 되지 경우 메모리 누수를 발생 하거나 예외를 두 번 삭제 될 때 손상 힙 수 있습니다.

예를 들어, 다음 코드에서 예외 포인터를 무효화:

[!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

때문에 문제 발생 `e` 실행 "내부" 밖으로 전달 될 경우 삭제 됩니다 **CATCH** 블록입니다. 사용 하 여는 **THROW_LAST** 매크로 대신 합니다 **THROW** 문을 사용 하면 됩니다는 "외부" **CATCH** 유효한 포인터를 수신 하는 블록:

[!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

##  <a name="_core_try_blocks_inside_catch_blocks"></a> Try Catch 블록 내에서 블록

내에서 현재 예외를 throw 할 다시 수를 **시도** 내에 있는 블록을 **CATCH** 블록. 다음 예에서는 유효 하지 않습니다.

[!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

자세한 내용은 참조 하세요. [예외: 예외 내용 검사](../mfc/exceptions-examining-exception-contents.md)합니다.

## <a name="see-also"></a>참고자료

[예외 처리](../mfc/exception-handling-in-mfc.md)
