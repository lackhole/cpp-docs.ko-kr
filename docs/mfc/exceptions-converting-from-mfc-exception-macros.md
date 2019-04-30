---
title: '예외: MFC 예외 매크로에서 변환'
ms.date: 08/27/2018
helpviewer_keywords:
- converting exceptions [MFC]
- exception objects [MFC]
- conversions [MFC], code written with MFC macros
- keywords [MFC], macros
- macrosv, C++ keywords
- exception objects [MFC], deleting
- CException class [MFC], deleting CException class objects
- exceptions [MFC], converting
- exceptions [MFC], deleting exception objects
- catch blocks [MFC], delimiting
- exception handling [MFC], converting exceptions
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
ms.openlocfilehash: 59b83438d5341fd6a139af64a2f365a739438741
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394509"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>예외: MFC 예외 매크로에서 변환

고급 항목입니다.

이 문서에서는 Microsoft Foundation Class 매크로 사용 하 여 작성 된 기존 코드를 변환 하는 방법을 설명 — **시도**, **CATCH**, **THROW**등과-사용 하는 C++ 예외 처리 키워드 **시도**하십시오 **catch**, 및 **throw**합니다. 다루는 주제는 다음과 같습니다.

- [변환 장점](#_core_advantages_of_converting)

- [사용에 대 한 예외 매크로 사용 하 여 코드 변환 C++ 예외](#_core_doing_the_conversion)

##  <a name="_core_advantages_of_converting"></a> 변환의 이점

아마도 필요가 없습니다 기존 코드를 변환할의 매크로 구현은 MFC 버전 3.0 및 이전 버전에서 구현 간의 차이점을 알도록 해야 하지만 합니다. 이러한 차이점 및 코드 동작의 이후 변경 사항은 나오는 [예외: 버전 3.0의에서 예외 매크로 변경 사항](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)합니다.

변환의 주요 장점은 다음과 같습니다.

- 사용 하는 코드는 C++ 예외 처리 키워드는 약간 더 작은를 컴파일합니다. EXE 또는 합니다. DLL입니다.

- C++ 예외 처리 키워드는 융통성이 더 뛰어납니다. 복사할 수 있는 모든 데이터 형식의 예외를 처리할 수 있도록 (**int**, **float**합니다 **char**등) 매크로 클래스의만 예외를 처리 하는 반면, `CException` 및에서 파생 된 클래스

매크로 및 키워드의 주요 차이점 예외 범위를 벗어나면 "자동 으로" 매크로 사용 하 여 코드는 예외가 삭제할 경우 키워드를 사용 하 여 코드는 그렇지 않으므로 예외가 명시적으로 삭제 해야 합니다. 자세한 내용은 문서를 참조 하세요. [예외: 예외 catch 및 삭제](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.

또 다른 차이점은 구문입니다. 매크로 및 키워드의 구문은 세 가지 측면에서 다릅니다.

1. 매크로 인수의 개수가 및 예외 선언 합니다.

   A **CATCH** 매크로 호출에는 다음 구문이 있습니다.

   **CATCH(** *exception_class*, *exception_object_pointer_name* **)**

   클래스 이름 및 개체 포인터 이름 사이 쉼표가 알 수 있습니다.

   에 대 한 예외 선언 된 **catch** 키워드가이 구문을 사용 하 여:

   **catch(** *exception_type* *exception_name* **)**

   이 예외 선언문 예외 catch의 형식을 나타내는 핸들을 차단 합니다.

2. Catch 블록의 delimitation:

   매크로 사용 하 여는 **CATCH** 매크로 (인수)를 첫 번째 catch 블록을 시작, **AND_CATCH** 매크로 이후 catch 블록을 시작 하며 **END_CATCH** 매크로 catch 블록의 시퀀스를 종료합니다.

   키워드를 사용 하 여는 **catch** 키워드 (예외 선언)를 각 catch 블록을 시작 합니다. 해당 하는 합니다 **END_CATCH** 매크로; catch 블록의 닫는 중괄호를 사용 하 여 종료 합니다.

3. Throw 식:

   매크로 사용 하 여 **THROW_LAST** 다시 현재 예외를 throw 합니다. 합니다 **throw** 키워드 없는 인수를 사용 하는 동일한 효과가 있습니다.

##  <a name="_core_doing_the_conversion"></a> 변환을 수행

#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>매크로 사용 하 여 사용 하도록 코드를 변환 하는 C++ 예외 처리 키워드

1. MFC 매크로의 모든 문제를 찾고 **시도**, **CATCH**를 **AND_CATCH**를 **END_CATCH**를 **THROW**, 및 **THROW_LAST**합니다.

2. 대체 하거나 다음 매크로의 모든 항목을 삭제 합니다.

   **시도** (바꿉니다 **시도**)

   **CATCH** (바꿉니다 **catch**)

   **AND_CATCH** (바꿉니다 **catch**)

   **END_CATCH** (삭제)

   **THROW** (바꿉니다 **throw**)

   **THROW_LAST** (바꿉니다 **throw**)

3. 올바른 예외 선언 작성 하는 매크로 인수를 수정 합니다.

   예를 들어 변경

   [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]

   다음으로 변경:

   [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]

4. 필요에 따라 예외 개체를 삭제 하도록 catch 블록의 코드를 수정 합니다. 자세한 내용은 문서를 참조 하세요. [예외: 예외 catch 및 삭제](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.

MFC 예외 매크로 사용 하 여 예외 처리 코드의 예는 다음과 같습니다. 다음 예제에서 코드는 예외 매크로 사용 하기 때문에 사용자에 게 유의 `e` 자동으로 삭제 됩니다.

[!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]

다음 예제에서 코드를 사용 하는 C++ 예외를 명시적으로 삭제 해야 하므로 예외 키워드:

[!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]

자세한 내용은 참조 하세요. [예외: MFC 매크로 사용 하 고 C++ 예외](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)합니다.

## <a name="see-also"></a>참고자료

[예외 처리](../mfc/exception-handling-in-mfc.md)<br/>
