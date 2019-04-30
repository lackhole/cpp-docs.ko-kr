---
title: '예외: 예외의 개체 해제'
ms.date: 11/04/2016
helpviewer_keywords:
- throwing exceptions [MFC], freeing objects in exceptions
- local exception handling
- memory leaks, caused by exception
- try-catch exception handling [MFC], destroying objects
- destroying objects [MFC]
- freeing objects [MFC]
- throwing exceptions [MFC], after destroying
- exception handling [MFC], destroying objects
ms.assetid: 3b14b4ee-e789-4ed2-b8e3-984950441d97
ms.openlocfilehash: 23fe85018d1bc2c41371afec2ad6931755e4e682
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406069"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>예외: 예외의 개체 해제

이 문서에 필요 하 고 예외가 발생 하면 개체를 해제 하는 방법을 설명 합니다. 다루는 주제는 다음과 같습니다.

- [로컬에서 예외 처리](#_core_handling_the_exception_locally)

- [개체를 삭제 한 후 예외를 throw 합니다.](#_core_throwing_exceptions_after_destroying_objects)

응용 프로그램 인터럽트 일반 프로그램 흐름 또는 프레임 워크에 의해 throw 된 예외입니다. 따라서 예외가 발생 하는 경우 제대로 정도의 처리할 수 있도록 개체 닫기 추적을 유지 하는 것이 반드시 합니다.

이 작업을 수행 하는 두 기본 방법이 있습니다.

- 로컬로 사용 하 여 예외를 처리 합니다 **시도** 하 고 **catch** 키워드를 문이 두 개를 사용 하 여 모든 개체를 삭제 합니다.

- 모든 개체를 삭제 합니다 **catch** 추가로 처리 하기 위한 블록 외부 예외가 throw 되기 전에 차단 합니다.

이러한 두 가지 방법은 아래 솔루션에서 문제가 있는 다음 예제를 보여 줍니다.

[!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]

위에서 작성 된 대로 `myPerson` 에서 예외가 발생 하는 경우 삭제 되지 것입니다 `SomeFunc`합니다. 실행 일반 함수 종료 및 개체를 삭제 하는 코드를 무시 된 다음 외부 예외 처리기를 직접 이동 됩니다. 개체에 대 한 포인터 예외 함수 떠나고 프로그램 실행 되는 개체에서 사용한 메모리는 복구할 수 없습니다 하는 경우 범위를 벗어납니다. 이 메모리 누수가 발생 합니다. 메모리 진단을 사용 하 여 감지 됩니다.

##  <a name="_core_handling_the_exception_locally"></a> 로컬에서 예외 처리

합니다 **try/catch** 패러다임 메모리 누수를 방지 하 고, 예외가 발생 한 경우 개체는 소멸 됩니다 있도록 방어적 프로그래밍 방법을 제공 합니다. 예를 들어이 문서의 앞부분에 표시 된 예제는 다음과 같이 작성할 수 없습니다.

[!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]

이 새 예제에서는 예외를 catch 하 고 로컬로 처리 하는 예외 처리기를 설정 합니다. 그런 다음 함수를 정상적으로 종료 하 고 개체를 소멸 시킵니다. 이 예의 중요 한 측면은 예외를 catch 하는 컨텍스트를 사용 하 여 설정 되어 있는지를 **try/catch** 블록입니다. 로컬 예외 프레임을 하지 않고 함수는 모를 예외가 throw 되었다는 사실을 정상적으로 종료 하 고 개체를 삭제할 수 없을 수 있습니다.

##  <a name="_core_throwing_exceptions_after_destroying_objects"></a> 개체를 삭제 한 후 예외를 throw 합니다.

예외를 처리 하는 다른 방법은 다음 외부 예외 처리 컨텍스트를 전달 하는 것입니다. 사용자 **catch** 블록 로컬로 할당 된 개체의 몇 가지 정리 작업을 수행 하 고 다음 추가 처리를 위해 예외를 throw 합니다.

Throw 함수 수도 힙 개체의 할당을 취소 해야 합니다. 함수도 할당을 취소 해야 힙 개체는 예외를 throw 하기 전에 다음 함수는 일반적인 경우에 반환 하기 전에 힙 개체를 할당 취소는 항상 하는 경우. 다른 한편으로 함수는 일반적으로 할당을 취소 하지 개체 일반적인 경우에 반환 하기 전에, 하는 경우 다음 결정 해야 합니다 상황별으로 힙 개체를 할당 취소 해야 하는지 여부를 합니다.

다음 예제에서는 어떻게 로컬로 할당 된 개체를 정리할 수 있습니다.

[!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]

예외 메커니즘을 자동으로 할당 취소 프레임 개체 또한 프레임 개체의 소멸자가 호출 됩니다.

예외를 throw 할 수 있는 함수를 호출 하는 경우 사용할 수 있습니다 **try/catch** 블록에는 예외를 catch 하 고 사용자가 만든 모든 개체 삭제를 확인 합니다. 특히, 많은 MFC 함수 예외를 throw 할 수 있습니다 주의 합니다.

자세한 내용은 참조 하세요. [예외: 예외 catch 및 삭제](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.

## <a name="see-also"></a>참고자료

[예외 처리](../mfc/exception-handling-in-mfc.md)
