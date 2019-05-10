---
title: '예외: 버전 3.0의에서 예외 매크로 변경 사항'
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
ms.openlocfilehash: fb51ad91e001f0ed153bf4fdb5aa598ab5ba5042
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173281"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>예외: 버전 3.0의에서 예외 매크로 변경 사항

고급 항목입니다.

MFC 버전 3.0 이상에서 사용 하는 예외 처리 매크로 변경 되었습니다 C++ 예외입니다. 이 문서에서는 내용이 매크로 사용 하는 기존 코드의 동작에 주는 영향을 설명 합니다.

이 문서에서는 다음 항목을 다룹니다.

- [예외 형식 및 CATCH 매크로](#_core_exception_types_and_the_catch_macro)

- [예외가 다시 throw](#_core_re.2d.throwing_exceptions)

##  <a name="_core_exception_types_and_the_catch_macro"></a> 예외 형식 및 CATCH 매크로

MFC의 이전 버전에서의 **CATCH** 예외 유형을 확인 하려면 MFC 런타임 형식 정보를 사용 하는 매크로; 예외의 형식이 결정 됩니다, 즉, catch 사이트. 그러나 사용 하 여 C++ 예외를 예외 형식은 항상에 따라 결정 됩니다 throw 사이트 throw 되는 예외 개체의 형식입니다. 드문 경우에서 throw 된 개체의 형식에서 throw 된 개체에 대 한 포인터 형식의 다른 위치에서 호환 되지 않는 그러면 합니다.

다음 예제에서는 MFC 버전 3.0 및 이전 버전 간의 이러한 차이의 결과를 보여 줍니다.

[!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]

이 코드와 다르게 적용 버전 3.0의에서 컨트롤은 항상 첫 번째 전달 하기 때문에 **catch** 에 일치 하는 예외 선언이 블록입니다. Throw 식의 결과

[!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]

으로 throw 되는 `CException*`으로 생성 된 경우에는 `CCustomException`합니다. **CATCH** 이전 사용 하 여 MFC 버전 2.5에서 매크로 `CObject::IsKindOf` 런타임에 형식을 테스트 합니다. 때문에 식

[!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]

가 true 이면 첫 번째 catch 블록이 예외를 catch 합니다. 버전 3.0 사용 하는 C++ 다양 한 예외 처리 매크로, 두 번째 catch 블록을 구현 하는 예외를 throw 된 일치 `CException`합니다.

다음과 같은 코드가 않습니다. 예외 개체는 제네릭을 허용 하는 다른 함수에 전달 될 때 일반적으로 나타나는 `CException*`, "사전 throw" 처리를 수행 하 고 마지막으로 예외를 throw 합니다.

이 문제를 해결 하기 위해 throw 식에서 함수 호출 코드에 이동한 예외 생성 시 컴파일러에 알려진 실제 형식의 예외를 throw 합니다.

##  <a name="_core_re.2d.throwing_exceptions"></a> 예외가 다시 Throw

Catch 블록을 포착 하는 동일한 예외 포인터를 생성할 수 없습니다.

예를 들어이 코드 이전 버전에서는 올바르지만 버전 3.0 사용 하 여 예기치 않은 결과:

[!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]

사용 하 여 **THROW** catch 블록 하면 포인터가 `e` 삭제 될 외부 catch 사이트에 잘못 된 포인터를 받을 수 있도록 합니다. 사용 하 여 **THROW_LAST** 를 다시 throw 할 `e`합니다.

자세한 내용은 참조 하세요. [예외: 예외 catch 및 삭제](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.

## <a name="see-also"></a>참고자료

[예외 처리](../mfc/exception-handling-in-mfc.md)
