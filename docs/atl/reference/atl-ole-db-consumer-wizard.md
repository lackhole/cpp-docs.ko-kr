---
title: ATL OLE DB 소비자 마법사
ms.date: 08/31/2018
f1_keywords:
- vc.codewiz.class.atl.consumer.overview
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- connection strings [C++], OLE DB consumers
- ATL OLE DB Consumer Wizard
ms.assetid: dcb68ed1-2224-422f-9f7b-108a74864204
ms.openlocfilehash: 59ad635f62ab7a20a31de7255ec4522136e102ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261262"
---
# <a name="atl-ole-db-consumer-wizard"></a>ATL OLE DB 소비자 마법사

이 마법사를 설정 하는 OLE DB 소비자 클래스 데이터 바인딩을 사용 하 여 지정 된 OLE DB 공급자를 통해 지정 된 데이터 원본에 액세스 하는 데 필요한 합니다.

> [!NOTE]
> 이 마법사를 사용 하면 클릭 해야 합니다 **데이터 원본** 의 이름을 입력 하기 전에 데이터 원본을 선택 하려면 단추를 `Class` 및 **.h 파일** 필드입니다.

## <a name="uielement-list"></a>UI 요소 목록

- **데이터 원본**

   합니다 **데이터 원본** 단추 지정된 된 OLE DB 공급자를 사용 하 여 지정 된 데이터 소스를 설정할 수 있습니다. 이 단추를 클릭 합니다 **데이터 연결 속성** 대화 상자가 나타납니다. 연결 문자열을 작성 하는 방법은 하며 **데이터 연결 속성** 대화 상자, 참조 [데이터 링크 API 개요](/previous-versions/windows/desktop/ms718102) Windows SDK 설명서의 합니다.

   다음과 같은 추가 정보는 탭에 설명 합니다 **데이터 연결 속성** 대화 상자.

   - **공급자** 탭

      데이터 원본에 대 한 연결을 관리 하기 위한 적절 한 공급자를 선택 합니다. 공급자의 형식은 일반적으로 연결 되어 데이터베이스의 형식에 의해 결정 됩니다. 클릭 합니다 **다음** 단추를 클릭 하거나 합니다 **연결** 탭 합니다.

   - **연결** 탭

      이 탭의 내용을 선택한 공급자에 따라 달라 집니다. 이 섹션에서는 두 개의 연결을 설명 하지만 다양 한 유형의 공급자가 가장 일반적인: SQL 및 ODBC 데이터입니다. 나머지는 여기에 설명 된 필드에 비슷한 변형입니다.

      SQL 데이터의 경우

      1. **선택 하거나 서버 이름을 입력 합니다.** 네트워크의 모든 등록 된 데이터 서버를 표시 하려면 드롭다운 목록에서 메뉴를 클릭 하 고 하나를 선택 합니다.

      1. **서버 로그온 정보를 입력 합니다.** 사용자 이름 및 데이터 서버에 로그온 하는 암호를 입력 합니다.

         > [!NOTE]
         > 데이터 연결 속성 대화 상자의 "암호 저장 허용" 기능을 사용 하 여 보안 문제가 있습니다. 입력 "정보" 서버에 로그온 할 라디오 단추를 두 가지 있습니다.
         >
         > - **Windows NT 통합 보안 사용**
         > - **특정 사용자 이름 및 암호 사용**
         >
         > 그러나 선택 하는 경우 **특정 사용자 이름 및 암호를 사용 하 여**,이 옵션은 안전 하지 않으면 ("암호 저장 허용"에 대 한 확인란을 사용 합니다.) 암호를 저장할 수 있습니다. 선택 하는 것이 좋습니다 **사용 하 여 Windows NT 통합 보안**; 암호를 암호화 하기 때문에이 옵션은 안전 합니다.
         > "암호 저장 허용 합니다."를 선택 하려는 경우가 있을 수 있습니다. 예를 들어 개인 데이터베이스 솔루션을 사용 하 여 라이브러리를 해제 하는 경우는 데이터베이스에 직접 액세스 해도 (원하는 인증 체계)를 통해 사용자를 확인 한 다음 종류의 데이터를 제한 하는 중간 계층 응용 프로그램을 대신 사용 사용자에 게 사용할 수 있습니다.

      1. **서버에서 데이터베이스를 선택 합니다.** 데이터 서버에 등록 된 모든 데이터베이스를 표시 하려면 드롭다운 목록에서 메뉴를 클릭 하 고 하나를 선택 합니다.

         \- 또는 -

         **데이터베이스 이름으로 데이터베이스 파일을 첨부 합니다.** 데이터베이스로 사용할 파일 지정 명시적 경로 입력 합니다.

      ODBC 데이터의 경우

      1. **데이터의 원본을 지정 합니다.** 데이터 원본 이름 또는 연결 문자열을 사용할 수 있습니다.

         **데이터 원본 이름을 사용 합니다.** 이 드롭다운 목록에는 컴퓨터에서 등록 된 데이터 원본 표시 됩니다. ODBC 데이터 원본 관리자를 사용 하 여 미리 데이터 원본을 설정할 수 있습니다.

         \- 또는 -

         **연결 문자열을 사용 합니다.** 이미가지고 또는 클릭 하면 연결 문자열을 입력 하거나 합니다 **빌드** ; 단추를 **데이터 원본 선택** 대화 상자가 나타납니다. 파일 또는 시스템 데이터 원본을 선택 하 고 클릭 **확인**합니다.

         > [!NOTE]
         > 기존 연결의 속성을 확인 하 여 연결 문자열을 가져올 수 있습니다 **서버 탐색기**, 또는 두 번 클릭 하 여 연결을 만들 수 있습니다 **연결 추가** 에서 **서버 탐색기**합니다.

      1. **서버 로그온 정보를 입력 합니다.** 사용자 이름 및 데이터 서버에 로그온 하는 암호를 입력 합니다.

      1. 초기 카탈로그를 사용 하 여 입력 합니다.

      1. 클릭 **연결 테스트**테스트가 성공 하는 경우 클릭 **확인**합니다. 그렇지 않은 경우 로그온 정보를 확인, 다른 데이터베이스 또는 다른 데이터 서버를 시도 합니다.

   - **고급** 탭

      **네트워크 설정:** 지정 된 **가장 수준이** (서버에서 클라이언트를 가장할 때 사용할 수; RPC 가장 수준에 직접적으로 해당 하는 가장 수준) 및 **보호 수준을** ( 클라이언트와 서버 간에 전송 되는 데이터의 보호 수준 해당 직접 RPC 보호 수준).

      **기타:** **연결 제한 시간**, 시간 초과가 발생 하기 전에 허용 되는 유휴 시간 (초) 수를 지정 합니다. **액세스 권한을**, 데이터 연결에 대 한 액세스 권한을 지정 합니다.

      고급 초기화 속성에 대 한 자세한 내용은 각 특정 OLE DB 공급자와 함께 제공 되는 설명서를 참조 하십시오.

   - **모든** 탭

      이 탭에는 데이터 원본 및 사용자가 지정한 연결에 대 한 초기화 속성의 요약이 표시 됩니다. 이러한 값을 편집할 수 있습니다.

      클릭 **확인** 완료 합니다. 합니다 **데이터베이스 개체 선택** 대화 상자가 나타납니다. 이 대화 상자에서 테이블, 뷰 또는 소비자가 사용할 저장된 프로시저를 선택 합니다.

- **클래스**

   데이터 원본을 선택 하면이 상자는 테이블 또는 선택한 저장된 프로시저에 따라 기본 클래스 이름으로 채워집니다 (참조 **데이터 원본을 선택** 아래). 클래스 이름을 편집할 수 있습니다.

- **.h 파일**

   데이터 원본을 선택 하면이 상자는 테이블 또는 선택한 저장된 프로시저에 따라 기본 헤더 클래스 이름으로 채워집니다 (참조 **데이터 원본을 선택** 아래). 헤더 파일의 이름을 편집 하거나 기존 헤더 파일을 선택할 수 있습니다.

- **특성 사용**

   이 옵션은 특성 또는 템플릿 선언을 사용 하 여 소비자 클래스를 만들 여부를 지정 합니다. 이 옵션을 선택 하면 마법사 (이것이 기본 옵션) 템플릿 선언 대신 특성을 사용 합니다. 이 옵션의 선택을 취소 하면 특성 대신 템플릿 선언이 사용 합니다.

   - 소비자를 선택 하면 **형식** 의 **테이블**, 마법사를 사용 하는 `db_source` 및 `db_table` 특성을 클래스 선언에서 테이블 및 테이블 접근자를 만들기 및 사용 하 여 `db_column` 를 열 지도를 만듭니다. 예를 들어이 맵에서 생성 됩니다.

        ```cpp
        // Inject table class and table accessor class declarations
        [db_source("<initialization_string>"), db_table("dbo.Orders")]
        ...
        // Column map
        [ db_column(1, status=m_dwOrderIDStatus, length=m_dwOrderIDLength) ] LONG m_OrderID;
        [ db_column(2, status=m_dwCustomerIDStatus, length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];
        ...
        ```

      사용 하는 대신는 `CTable` 테이블 및 테이블 접근자 클래스 및이 예제와 같이 열 지도 만들려면 BEGIN_COLUMN_MAP 및 END_COLUMN_MAP 매크로 선언 하는 템플릿 클래스:

        ```cpp
        // Table accessor class
            class COrdersAccessor; // Table class
            class COrders : public CTable<CAccessor<COrdersAccessor>>;
        // ...
        // Column map
            BEGIN_COLUMN_MAP(COrderDetailsAccessor)
                COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID, m_dwOrderIDLength, m_dwOrderIDStatus)
                COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID, m_dwCustomerIDLength, m_dwCustomerIDStatus)
                // ...
            END_COLUMN_MAP()
        ```

   - 소비자를 선택 하면 **형식** 의 **명령**, 마법사를 사용 하는 `db_source` 및 `db_command` 특성을 사용 하 여 `db_column` 열 지도를 만듭니다. 예를 들어이 맵에서 생성 됩니다.

        ```cpp
        [db_source("<initialization_string>"), db_command("SQL_command")]
        ...
        // Column map using db_column is the same as for consumer type of 'table'
        ```

      명령 및 명령 접근자를 사용 하는 대신 클래스 선언을 명령 클래스의.h 파일의 예를 들어:

        ```cpp
        // Command accessor class:
            class CListOrdersAccessor;
        // Command class:
            class CListOrders : public CCommand<CAccessor<CListOrdersAccessor>>;
        // ...
        // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as
        // for consumer type of 'table'
        ```

      참조 [특성의 기본 메커니즘](../../windows/basic-mechanics-of-attributes.md) 자세한 내용은 합니다.

- **Type**

   소비자 클래스에서 파생 될 지 여부를 지정 하려면이 라디오 단추 중 하나를 선택 `CTable` 또는 `CCommand` (기본값).

   - **Table**

      사용 하려는 경우이 옵션을 선택 `CTable` 또는 `db_table` 테이블 및 테이블 접근자 클래스 선언을 만들려면.

   - **명령**

      사용 하려는 경우이 옵션을 선택 `CCommand` 또는 `db_command` 명령 및 명령 접근자 클래스 선언을 만들려면. 이 옵션이 기본 옵션입니다.

- **지원**

   (기본값은 none) 소비자에서 지원 되는 데 업데이트 종류를 지정 하는 확인란을 선택 합니다. 설정이 다음 각 [DBPROP_IRowsetChange](/previous-versions/windows/desktop/ms715892) 와 적절 한 항목을 [DBPROP_UPDATABILITY](/previous-versions/windows/desktop/ms722676) 속성에서 지도 설정 합니다.

   - **변경 내용**

      소비자 행 집합의 행 데이터의 업데이트는 지원 하도록 지정 합니다.

   - **삽입**

      소비자가 행 집합에 행 삽입 지를 지정 합니다.

   - **삭제**

      소비자 행 집합에서 행을 삭제 지를 지정 합니다.

## <a name="see-also"></a>참고자료

[ATL OLE DB 소비자](../../atl/reference/adding-an-atl-ole-db-consumer.md)<br/>
[코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[연결 문자열 및 데이터 링크 (OLE DB)](/previous-versions/windows/desktop/ms718376)
