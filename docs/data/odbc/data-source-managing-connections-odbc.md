---
title: '데이터 소스: 연결 관리 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources [C++], multiuser environments
- generalizing connection strings
- ODBC [C++], disconnecting from data sources
- connection strings [C++], generalizing
- database connections [C++], creating
- GetDefaultConnect method
- connections [C++], data source
- ODBC connections [C++], configuring
- disconnecting from data sources
- databases [C++], connecting to
- ODBC connections [C++], disconnecting
- data sources [C++], connecting to
- ODBC connections [C++], connecting to data source
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
ms.openlocfilehash: 5b646ca0eb86d3addabaad59ca23f56cfe914114
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395952"
---
# <a name="data-source-managing-connections-odbc"></a>데이터 소스: 연결 관리 (ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

이 항목에 설명 합니다.

- [데이터 원본을 구성 하는 방법을](#_core_configuring_a_data_source)합니다.

- [다중 사용자 환경 데이터 소스와 그 레코드 집합에 미치는 영향](#_core_working_in_a_multiuser_environment)합니다.

- [데이터 원본에 연결 문자열을 일반화 하는 이유](#_core_generalizing_the_connection_string)합니다.

- [데이터 원본에 연결 하는 방법을](#_core_connecting_to_a_specific_data_source)합니다.

- [데이터 원본에서 분리 하는 방법](#_core_disconnecting_from_a_data_source)합니다.

- [CDatabase 개체 다시 사용 하는 방법을](#_core_reusing_a_cdatabase_object)합니다.

데이터 원본에 연결할 데이터에 액세스 하기 위해 DBMS와 통신을 설정 하는 것을 의미 합니다. ODBC 드라이버를 통해 응용 프로그램에서 데이터 원본에 연결 하면 로컬 또는 네트워크 드라이버를 연결을 만듭니다.

ODBC 드라이버는 권한이 있는 모든 데이터 원본에 연결할 수 있습니다. 응용 프로그램의 사용자에 해당 데이터 원본에 대 한 ODBC 드라이버를가지고 있어야 합니다. ODBC 드라이버 재배포 하는 방법에 대 한 자세한 내용은 참조 하세요. [고객에 게 ODBC 구성 요소 재배포](../../data/odbc/redistributing-odbc-components-to-your-customers.md)합니다.

##  <a name="_core_configuring_a_data_source"></a> 데이터 원본 구성

ODBC 관리자를 사용 하 여 데이터 원본을 구성 합니다. 데이터 원본이 추가 또는 제거 하려면 설치 후 ODBC 관리자를 사용할 수 있습니다. 응용 프로그램을 만들면 하거나 직접 데이터 소스를 추가할 수 있도록 ODBC 관리자를 사용자 또는 직접 ODBC 설치를 호출 하 여 응용 프로그램에이 기능을 빌드할 수 있습니다. 자세한 내용은 [ODBC 관리자](../../data/odbc/odbc-administrator.md)합니다.

데이터 원본으로 Excel 파일을 사용할 수 하 고 등록 하 고 나타나는 있도록 파일을 구성 해야 합니다 **데이터 원본 선택** 대화 상자.

#### <a name="to-use-an-excel-file-as-a-data-source"></a>데이터 원본으로 Excel 파일을 사용 하려면

1. ODBC 데이터 원본 관리자를 사용 하 여 파일을 구성 합니다.

1. 에 **파일 DSN** 탭을 클릭 **추가**합니다.

1. 에 **새 데이터 원본 만들기** 대화 상자에서 Excel 드라이버를 선택한 다음 클릭 **다음**합니다.

1. 클릭 **찾아보기**를 데이터 소스로 사용할 파일의 이름을 선택 합니다.

> [!NOTE]
>  선택 해야 할 수 있습니다 **모든 파일** .xls 파일을 보려면 드롭다운 메뉴에서.

1. **다음**을 클릭한 다음 **마침**을 클릭합니다.

1. 에 **ODBC Microsoft Excel 설정** 대화 상자에서 데이터베이스 버전 및 통합 문서를 선택 합니다.

##  <a name="_core_working_in_a_multiuser_environment"></a> 다중 사용자 환경에서 작업

여러 사용자가 데이터 원본에 연결 되어 있으면 레코드 집합에서 조작 하는 동안 데이터를 변경할 수 있습니다. 마찬가지로, 변경 내용을 다른 사용자의 영향을 줄 수 있습니다. 자세한 내용은 참조 하세요. [레코드 집합: 레코드 집합 업데이트 (ODBC)를 기록 하는 방법](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) 하 고 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.

##  <a name="_core_generalizing_the_connection_string"></a> 연결 문자열의 일반화

마법사는 데이터 원본에 연결할 기본 연결 문자열을 사용 합니다. 응용 프로그램을 개발 하는 동안 테이블 및 열을 보려면이 연결을 사용 합니다. 그러나이 기본 연결 문자열에 사용자가 응용 프로그램을 통해 데이터 원본에 연결에 대 한 적절 한 수 있습니다. 예를 들어, 데이터 원본 및 해당 위치의 경로를 응용 프로그램 개발에 사용 되는 다른 수 있습니다. 다시 구현 해야 경우에 [CRecordset::GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) 멤버 보다 일반적인 방식으로 작동 하 고 마법사 구현이 삭제 합니다. 예를 들어, 다음 방법 중 하나를 사용 합니다.

- 등록 하 고 ODBC 관리자를 사용 하 여 연결 문자열을 관리 합니다.

- 연결 문자열을 편집 하 고 데이터 원본 이름을 제거 합니다. 프레임 워크는 ODBC의 데이터 원본으로 제공 런타임 시 ODBC 데이터 원본 이름 및 기타 필요한 연결 정보를 묻는 대화 상자를 표시 합니다.

- 데이터 소스 이름만 제공 합니다. 필요한 경우 ODBC에서 사용자 ID 및 암호를 요청 합니다. 예를 들어 일반화 하기 전의 연결 문자열은 다음과 같습니다.

    ```cpp
    CString CApp1Set::GetDefaultConnect()
    {
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";
    }
    ```

   이 연결 문자열에는 Windows NT 통합 보안을 사용 하는 신뢰할 수 있는 연결을 지정 합니다. 암호를 하드 코딩 하지 않아야 하거나 주요 보안 취약점을 만들고 그렇게 하기 때문에 빈 암호를 지정 합니다. 대신 제공할 수 있습니다 `GetDefaultConnect` 새 연결 문자열에 있으므로 사용자 ID 및 암호를 쿼리 합니다.

    ```cpp
    // User must select data source and supply user ID and password:
        return "ODBC;";
    // User ID and password required:
        return "ODBC;DSN=mydb;";
    // Password required (myuserid must be replaced with a valid user ID):
        return "ODBC;DSN=mydb;UID=myuserid;";
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";
    ```

##  <a name="_core_connecting_to_a_specific_data_source"></a> 특정 데이터 원본에 연결

특정 데이터 원본에 연결할 데이터 원본에 이미 구성 해야 사용 하 여 [ODBC 관리자](../../data/odbc/odbc-administrator.md)합니다.

#### <a name="to-connect-to-a-specific-data-source"></a>특정 데이터 원본에 연결

1. 생성 된 `CDatabase` 개체입니다.

1. 호출 해당 `OpenEx` 또는 `Open` 멤버 함수입니다.

마법사를 사용 하 여 지정 된 것 이외의 경우 데이터 소스를 지정 하는 방법에 대 한 자세한 내용은 참조 하세요. [cdatabase:: Openex](../../mfc/reference/cdatabase-class.md#openex) 하거나 [cdatabase:: Open](../../mfc/reference/cdatabase-class.md#open) 에 *MFC 참조*합니다.

##  <a name="_core_disconnecting_from_a_data_source"></a> 데이터 원본에서 연결 끊기

호출 하기 전에 열린 모든 레코드 집합을 닫아야 합니다 `Close` 멤버 함수 `CDatabase`합니다. 관련 된 레코드 집합에는 `CDatabase` 보류 중인 종료 하려는 개체 `AddNew` 또는 `Edit` 문이 취소 되 고 보류 중인 모든 트랜잭션이 롤백됩니다.

#### <a name="to-disconnect-from-a-data-source"></a>데이터 원본에서 연결을 끊으려면

1. 호출 된 `CDatabase` 개체의 [닫기](../../mfc/reference/cdatabase-class.md#close) 멤버 함수입니다.

1. 다시 사용 하려는 경우가 아니면 개체를 삭제 합니다.

##  <a name="_core_reusing_a_cdatabase_object"></a> CDatabase 개체 다시 사용

다시 사용할 수는 `CDatabase` 동일한 데이터 소스에 다시 연결 하거나 다른 데이터 원본에 연결을 사용 하는지 여부를에서 연결을 끊은 후 개체입니다.

#### <a name="to-reuse-a-cdatabase-object"></a>CDatabase 개체 다시 사용

1. 개체의 원래 연결을 닫습니다.

1. 호출 개체를 삭제 하는 대신 해당 `OpenEx` 또는 `Open` 멤버 함수를 다시 합니다.

## <a name="see-also"></a>참고자료

[데이터 소스(ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[데이터 소스: 데이터 소스의 스키마 확인(ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)