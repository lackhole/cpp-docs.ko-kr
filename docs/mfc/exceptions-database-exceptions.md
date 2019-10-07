---
title: 예외 데이터베이스 예외
ms.date: 09/17/2019
helpviewer_keywords:
- DAO [MFC], exceptions
- exceptions [MFC], database
- exception handling [MFC], databases
- ODBC exceptions [MFC]
- ODBC [MFC], exceptions
- database exceptions [MFC]
- databases [MFC], exception handling
- error codes [MFC], database exception handling
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
ms.openlocfilehash: c279c5b788cc7bd8a68fe36128c116d8df91c2eb
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095815"
---
# <a name="exceptions-database-exceptions"></a>예외 데이터베이스 예외

이 문서에서는 데이터베이스 예외를 처리 하는 방법을 설명 합니다. 이 문서에 포함 된 대부분의 자료는 ODBC (Open Database Connectivity) 또는 DAO (Data Access Objects)의 MFC 클래스를 사용 하 여 작업 하 고 있는지 여부를 적용 합니다. 하나 또는 다른 모델에 관련 된 자료는 명시적으로 표시 됩니다. 다루는 주제는 다음과 같습니다.

- [예외 처리 방법](#_core_approaches_to_exception_handling)

- [데이터베이스 예외 처리 예제](#_core_a_database_exception.2d.handling_example)

##  <a name="_core_approaches_to_exception_handling"></a>예외 처리 방법

이 접근 방식은 DAO (사용 되지 않음) 또는 ODBC를 사용 하 여 작업 하는 경우와 동일 합니다.

예외 조건을 처리 하려면 항상 예외 처리기를 작성 해야 합니다.

데이터베이스 예외를 catch 하는 가장 실용적인 방법은 예외 시나리오를 사용 하 여 응용 프로그램을 테스트 하는 것입니다. 코드의 작업에 대해 발생할 수 있는 예외를 확인 하 고 예외를 강제로 실행 합니다. 그런 다음 추적 출력을 검토 하 여 throw 되는 예외를 확인 하거나 디버거에서 반환 된 오류 정보를 검사 합니다. 이렇게 하면 사용 중인 예외 시나리오에 대해 표시 되는 반환 코드를 알 수 있습니다.

### <a name="error-codes-used-for-odbc-exceptions"></a>ODBC 예외에 사용 되는 오류 코드

**AFX_SQL_ERROR_XXX**형식의 이름이 있는 프레임 워크에서 정의 된 반환 코드 외에도 일부 [Cdbexceptions](../mfc/reference/cdbexception-class.md) 는 [ODBC](../data/odbc/odbc-basics.md) 반환 코드를 기반으로 합니다. 이러한 예외에 대 한 반환 코드에는 **SQL_ERROR_XXX**형식의 이름이 있습니다.

데이터베이스 클래스에서 반환할 수 있는 프레임 워크 정의 및 ODBC 정의의 반환 코드는 클래스 `CDBException`의 [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) 데이터 멤버 아래에 설명 되어 있습니다. ODBC에서 정의한 반환 코드에 대 한 추가 정보는 MSDN Library의 ODBC SDK *프로그래머 참조* 에서 확인할 수 있습니다.

### <a name="error-codes-used-for-dao-exceptions"></a>DAO 예외에 사용 되는 오류 코드

DAO 예외의 경우 추가 정보를 일반적으로 사용할 수 있습니다. Catch 된 [CDaoException](../mfc/reference/cdaoexception-class.md) 개체의 세 가지 데이터 멤버를 통해 오류 정보에 액세스할 수 있습니다.

- [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) 에는 데이터베이스와 관련 된 DAO의 오류 개체 컬렉션에서 오류 정보를 캡슐화 하는 [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) 개체에 대 한 포인터가 포함 되어 있습니다.

- [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) 에는 MFC DAO 클래스의 확장 된 오류 코드가 포함 되어 있습니다. **AFX_DAO_ERROR_XXX**형식의 이름을 가진 이러한 오류 코드는의 데이터 멤버 아래에 `CDaoException`설명 되어 있습니다.

- [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) 에는 DAO **에서 OLE를** 포함 합니다 (해당 하는 경우). 그러나이 오류 코드로 작업 하는 것은 거의 필요 하지 않습니다. 일반적으로 다른 두 데이터 멤버에서 더 많은 정보를 사용할 수 있습니다. **값에 대 한 자세한 내용은** 데이터 멤버를 참조 하세요.

DAO 오류, DAO 오류 개체 형식 및 DAO Errors 컬렉션에 대 한 추가 정보는 클래스 [CDaoException](../mfc/reference/cdaoexception-class.md)에서 사용할 수 있습니다.

##  <a name="_core_a_database_exception.2d.handling_example"></a>데이터베이스 예외 처리 예제

다음 예에서는 **new** 연산자를 사용 하 여 힙에서 [CRecordset](../mfc/reference/crecordset-class.md)에서 파생 된 개체를 생성 한 다음 레코드 집합 (ODBC 데이터 원본 용)을 엽니다. DAO 클래스에 대 한 유사한 예제는 아래의 "DAO 예외 예제"를 참조 하십시오.

### <a name="odbc-exception-example"></a>ODBC 예외 예

[Open](../mfc/reference/crecordset-class.md#open) 멤버 함수는 ODBC 클래스에 대 한 [cdbexception](../mfc/reference/cdbexception-class.md) 형식의 예외를 throw 할 수 있으므로이 코드는 **try** 블록을 `Open` 사용 하 여 호출을 괄호로 묶습니다. 후속 **catch** 블록은를 `CDBException`catch 합니다. 이라는 `e`예외 개체 자체를 검사할 수도 있지만이 경우에는 레코드 집합을 만들 때 실패 한 것을 알 수 있습니다. **Catch** 블록은 메시지 상자를 표시 하 고 레코드 집합 개체를 삭제 하 여 정리 합니다.

[!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>DAO 예외 예

DAO 예제는 ODBC의 예제와 비슷하지만 일반적으로 더 많은 종류의 정보를 검색할 수 있습니다. 또한 다음 코드는 레코드 집합을 열려고 시도 합니다. 이 시도가 예외를 throw 하는 경우 예외 개체의 데이터 멤버를 검사 하 여 오류 정보를 확인할 수 있습니다. 이전 ODBC 예제와 마찬가지로, 레코드 집합을 만들 수 없습니다.

[!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

이 코드는 exception 개체의 [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) 멤버에서 오류 메시지 문자열을 가져옵니다. MFC는 예외를 throw 할 때이 멤버를 채웁니다.

`CDaoException` 개체에서 반환 되는 오류 정보에 대 한 자세한 내용은 [CDaoException](../mfc/reference/cdaoexception-class.md) 및 [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)클래스를 참조 하세요.

Microsoft Jet (.mdb) 데이터베이스를 사용 하는 경우와 대부분의 경우 ODBC를 사용 하 여 작업 하는 경우 오류 개체는 하나만 있습니다. 드문 경우 지만 ODBC 데이터 원본을 사용 하 고 여러 오류가 발생 하는 경우 [CDaoException:: GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount)에서 반환 된 오류 수를 기반으로 DAO의 errors 컬렉션을 반복할 수 있습니다. 루프를 통해 매번 [CDaoException:: geterrorinfo](../mfc/reference/cdaoexception-class.md#geterrorinfo) 를 호출 하 여 `m_pErrorInfo` 데이터 멤버를 다시 채워야 합니다.

## <a name="see-also"></a>참고자료

[예외 처리](../mfc/exception-handling-in-mfc.md)
