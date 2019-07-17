---
title: '&lt;exception&gt;'
ms.date: 11/04/2016
f1_keywords:
- <exception>
helpviewer_keywords:
- exception header
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
ms.openlocfilehash: 5036f2efc782c3b2f385960cd9cbf6935212f720
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240760"
---
# <a name="ltexceptiongt"></a>&lt;exception&gt;

여러 가지 형식 및 예외 처리와 관련된 함수를 정의합니다. 시스템이 오류에서 복구될 수 있는 경우에 예외 처리가 사용됩니다. 함수에서 프로그램으로 반환되는 컨트롤에 대한 방법을 제공합니다. 예외 처리를 통합하는 목표는 프로그램의 견고성을 높이는 동시에 오류 발생 시 체계적으로 복구하는 방법을 제공하는 것입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<exception>

**네임스페이스:** std

## <a name="members"></a>멤버

### <a name="typedefs"></a>형식 정의

|||
|-|-|
|[exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)|예외에 대한 포인터를 설명하는 형식입니다.|
|[terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)|`terminate_handler`로 사용하는 데 적합한 함수에 대한 포인터를 설명하는 형식입니다.|
|[unexpected_handler](../standard-library/exception-typedefs.md#unexpected_handler)|`unexpected_handler`로 사용하는 데 적합한 함수에 대한 포인터를 설명하는 형식입니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[current_exception](../standard-library/exception-functions.md#current_exception)|현재 예외에 대한 포인터를 가져옵니다.|
|[get_terminate](../standard-library/exception-functions.md#get_terminate)|현재 `terminate_handler` 함수를 가져옵니다.|
|[get_unexpected](../standard-library/exception-functions.md#get_unexpected)|현재 `unexpected_handler` 함수를 가져옵니다.|
|[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)|예외의 복사본이 들어있는 `exception_ptr` 개체를 만듭니다.|
|[rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)|매개 변수로 전달되는 예외를 throw합니다.|
|[rethrow_if_nested](../standard-library/exception-functions.md#rethrow_if_nested)|캐스팅 및 중첩 된 예외를 throw 합니다.|
|[set_terminate](../standard-library/exception-functions.md#set_terminate)|프로그램을 종료할 때 호출할 새 `terminate_handler`를 설정합니다.|
|[set_unexpected](../standard-library/exception-functions.md#set_unexpected)|예기치 않은 예외가 발생할 경우를 위해 새 `unexpected_handler`를 설정합니다.|
|[terminate](../standard-library/exception-functions.md#terminate)|종료 처리기를 호출합니다.|
|[throw_with_nested](../standard-library/exception-functions.md#throw_with_nested)|중첩 된 경우 예외를 throw 합니다.|
|[uncaught_exception](../standard-library/exception-functions.md#uncaught_exception)|throw된 예외가 현재 처리 중인 경우만 **true**를 반환합니다.|
|[unexpected](../standard-library/exception-functions.md#unexpected)|예기치 않은 처리기를 호출합니다.|

### <a name="classes"></a>클래스

|||
|-|-|
|[bad_exception 클래스](../standard-library/bad-exception-class.md)|이 클래스는 `unexpected_handler`에서 throw할 수 있는 예외를 설명합니다.|
|[exception 클래스](../standard-library/exception-class.md)|이 클래스는 특정 식과 C++ 표준 라이브러리로 throw된 모든 예외에 대한 기본 클래스로 사용됩니다.|
|[nested_exception 클래스](../standard-library/nested-exception-class.md)|클래스 캡처되고 저장 나중에 사용할 수 있는 예외를 설명 합니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
