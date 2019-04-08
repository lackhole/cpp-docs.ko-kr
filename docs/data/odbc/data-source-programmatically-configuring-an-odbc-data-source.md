---
title: '데이터 소스: 프로그래밍 방식으로 ODBC 데이터 소스 구성'
ms.date: 11/04/2016
f1_keywords:
- SQLConfigDataSource
helpviewer_keywords:
- ODBC data sources, configuring
- SQLConfigDataSource method example
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
ms.openlocfilehash: 33269b65835812a6e1a03e091833831781d97b6d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037960"
---
# <a name="data-source-programmatically-configuring-an-odbc-data-source"></a>데이터 소스: 프로그래밍 방식으로 ODBC 데이터 소스 구성

이 항목에서는 프로그래밍 방식으로 데이터 원본 이름은 ODBC Open Database Connectivity ()를 구성 하는 방법을 설명 합니다. 이 방법을 사용 데이터에 액세스 하려면 사용자가 명시적으로 데이터 원본의 이름을 지정 하려면 ODBC 관리자나 다른 프로그램을 사용 하지 않고도.

일반적으로 사용자가 연결된 된 데이터베이스 관리 시스템 (DBMS)에서이 작업을 지 원하는 경우 데이터 원본을 만들려면 ODBC 관리자를 실행 합니다.

ODBC 관리자를 통해 Microsoft Access ODBC 데이터 소스를 만들 때 두 가지 선택 항목이 제공 됩니다: 기존의.mdb 파일을 선택 하거나 새.mdb 파일을 만들 수 있습니다. MFC ODBC 응용 프로그램에서.mdb 파일을 만드는 프로그래밍 방식으로 방법은 있습니다. 따라서 응용 프로그램에 Microsoft Access 데이터 소스 (.mdb 파일)에 데이터를 배치 하는 필요한 경우 사용 하거나 필요할 때마다 복사 하는 빈.mdb 파일 해야 할 가능성이 있습니다.

그러나 여러 Dbms 프로그래밍 방식으로 데이터 원본 만들기를 허용합니다. 일부 데이터 원본에는 데이터베이스에 대 한 디렉터리 사양을 유지 관리합니다. 즉, 디렉터리는 데이터 원본 및 데이터 소스 내의 각 테이블은 별도 파일에 저장 (dBASE의 경우 각 테이블은.dbf 파일). Microsoft Access 및 SQL Server와 같은 다른 ODBC 데이터베이스용 드라이버는 데이터 소스를 설정할 수 있습니다 사용 하기 전에 일부의 조건을 충족 해야 합니다. 예를 들어, SQL Server ODBC 드라이버를 사용 하는 경우 SQL Server 컴퓨터를 설정 해야 합니다.

##  <a name="_core_sqlconfigdatasource_example"></a> SQLConfigDataSource 예제

다음 예제에서는 `::SQLConfigDataSource` 새 Excel 데이터 원본을 만들려면 ODBC API 함수 호출 새 Excel 데이터 원본:

```
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",
                   "DSN=New Excel Data Source\0"
                   "Description=New Excel Data Source\0"
                   "FileType=Excel\0"
                   "DataDirectory=C:\\EXCELDIR\0"
                   "MaxScanRows=20\0");
```

데이터 소스는 실제로 디렉터리 (C:\EXCELDIR); 이 디렉터리가 있어야 합니다. Excel 드라이버는 디렉터리를 해당 데이터 원본 및 파일을 개별 테이블로 (.xls 파일 당 테이블 한 개).

테이블을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [데이터 원본: 프로그래밍 방식으로 ODBC 데이터 원본에서 테이블을 만들고](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md)합니다.

다음 정보를 전달 되는 매개 변수를 설명 합니다 `::SQLConfigDataSource` ODBC API 함수입니다. 사용할 `::SQLConfigDataSource`에 Odbcinst.h 헤더 파일을 포함 하 고 Odbcinst.lib 가져오기 라이브러리를 사용 해야 합니다. 또한 Odbccp32.dll 런타임 (또는 16 비트인 경우) 경로 여야 합니다.

ODBC 관리자 또는 유사한 유틸리티를 사용 하 여 ODBC 데이터 원본 이름을 만들 수 있습니다. 그러나이 적합 한 경우가 사용자가 별도 유틸리티를 실행 하도록 요구 하지 않고 액세스할 수 있는 응용 프로그램에서 직접 데이터 원본 이름을 만듭니다.

ODBC 관리자 (일반적으로 제어판에 설치)는 Windows 레지스트리에 (또는 16 비트인 경우 Odbc.ini 파일) 항목을 배치 하 여 새 데이터 원본을 만듭니다. ODBC 드라이버 관리자는이 파일을 데이터 원본에 대 한 필요한 정보를 쿼리 합니다. 것이 중요 정보에 대 한 호출을 사용 하 여 제공 해야 하므로 레지스트리에 배치 해야 합니다. 알아야 `::SQLConfigDataSource`합니다.

이 정보를 사용 하지 않고 레지스트리를 직접 작성할 수 있습니다 하지만 `::SQLConfigDataSource`,이 작업을 수행 하는 응용 프로그램은 드라이버 관리자를 사용 하 여 해당 데이터를 유지 관리 기술을 의존 합니다. 최신 ODBC 드라이버 관리자 구현 레코드를 다른 방식으로 데이터 원본에 대 한 유지 하면이 기술을 사용 하는 모든 응용 프로그램을 손상 되었습니다. 일반적으로 제공 되는 경우 API 함수를 사용 하는 것이 좋습니다. 예를 들어, 코드를 사용 하는 경우 32 비트를 16 비트에서 이식할는 `::SQLConfigDataSource` 함수는 Odbc.ini 파일 또는 레지스트리를 올바르게 작성 때문에 작동 합니다.

##  <a name="_core_sqlconfigdatasource_parameters"></a> SQLConfigDataSource 매개 변수

다음 설명의 매개 변수는 `::SQLConfigDataSource` 함수입니다. ODBC API에서 많은 정보를 가져옵니다 *프로그래머 참고 자료* Visual c + + 1.5 이상 버전을 사용 하 여 제공 합니다.

###  <a name="_core_function_prototype"></a> 함수 프로토타입

```
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);
```

### <a name="remarks"></a>설명

####  <a name="_core_parameters_and_usage"></a> 매개 변수 및 사용법

*hwndParent*<br/>
ODBC 드라이버 관리자나 특정 ODBC 드라이버를 만들고 새 데이터 원본에 대 한 사용자 로부터 추가 정보를 얻을 수 있는 대화 상자의 소유자로 지정 하는 창입니다. 경우는 *lpszAttributes* 매개 변수는 충분 한 정보를 제공 하지 않는, 대화 상자가 나타납니다. 합니다 *hwndParent* 매개 변수는 NULL 일 수 있습니다.

*lpszDriver*<br/>
드라이버 설명입니다. 실제 드라이버 이름 (DLL)가 아닌 사용자에 게 표시 이름입니다.

*lpszAttributes*<br/>
형식에서 특성 목록을 "keyname = value"입니다. 이러한 문자열이 목록의 끝에 두 개의 null 종결자를 사용 하 여 null 종결자로 구분 됩니다. 이러한 특성은 기본적으로 기본 드라이버 관련 항목을 새 데이터 원본에 대 한 레지스트리로 이동 합니다. 이 함수는 "DSN (데이터 원본 이름"), 새 데이터 원본의 이름을 지정 하는 ODBC API 참조에 언급 하지 않은 한 중요 한 키입니다. 항목의 나머지 부분을 새 데이터 원본에 대 한 드라이버와 관련이 있습니다. 종종 드라이버를 새 값에 대 한 대화 상자를 사용 하 여 사용자에 게 수 때문에 모든 항목을 제공 하는 데 필요한 아닙니다. (설정 *hwndParent* 로 null입니다.) 사용자에 게 묻지 않습니다 있도록 기본값을 명시적으로 지정할 수도 있습니다.

#### <a name="to-determine-the-description-of-a-driver-for-the-lpszdriver-parameter-using-odbc-administrator"></a>ODBC 관리자를 사용 하 여 lpszDriver 매개 변수에 대 한 드라이버 설명을 확인 하려면

1. ODBC 관리자를 실행 합니다.

1. **추가**를 클릭합니다.

이 설치 된 드라이버 및 해당 설명의 목록을 제공합니다. 이 설명으로 사용 합니다 *lpszDriver* 매개 변수입니다. 설명에 있는 경우 파일 이름 확장명 및 괄호를 포함 하 여 "Excel 파일 (*.xls)"와 같은 전체 설명을 사용 하는 note 합니다.

대신 레지스트리를 검사할 수 있습니다 (또는 16 비트에서는 Odbcinst.ini 파일)를 포함 하는 모든 드라이버 항목과 및 레지스트리 키 "ODBC Drivers" 아래의 설명을 (또는 Odbcinst.ini의 [ODBC Drivers] 섹션)의 목록.

키와 값을 찾을 수 합니다 *lpszAttributes* 매개 변수 (아마도 하나 ODBC 관리자에 의해 구성 된)를 이미 구성 된 데이터 원본에 대 한 Odbc.ini 파일을 검사 하는 것입니다.

#### <a name="to-find-keynames-and-values-for-the-lpszattributes-parameter"></a>LpszAttributes 매개 변수에 대 한 키 및 값을 찾으려면

1. Windows 레지스트리 편집기를 실행 하거나, 16 비트인 경우 Odbc.ini 파일을 엽니다.

1. 다음 중 하나를 사용 하 여 ODBC 데이터 원본 정보를 찾으려면

   - 32 비트에 대 한 키를 찾을 **HKEY_CURRENT_USER\Software\ODBC\ODBC 합니다. 데이터 원본 INI\ODBC** 왼쪽된 창에서.

      오른쪽 창에는 형식의 항목 나열: "pub: REG_SZ:*<data source name>*", 여기서 *<data source name>* 는 사용 하려는 드라이버에 대해 원하는 설정을 사용 하 여 이미 구성 된 데이터 원본입니다. 예를 들어, SQL Server에 데이터 원본을 선택 합니다. 문자열 다음의 항목 "pub:" 순서, 키 이름 및 값에서 사용 하는 사용자 *lpszAttributes* 매개 변수입니다.

   - 16 비트에 대 한 섹션을 표시 하는 Odbc.ini 파일에서 찾을 [*\<데이터 원본 이름 >*].

      형식입니다.이 줄을 다음 줄은 "keyname = value"입니다. 정확 하 게 항목에서 사용 하 여 *lpszAttributes* 매개 변수입니다.

사용 하려는 특정 드라이버에 대 한 설명서를 참조할 수도 있습니다. ODBC 관리자를 실행 하 여 액세스할 수 있는 드라이버에 대 한 온라인 도움말에서 유용한 정보를 찾을 수 있습니다. 일반적으로 이러한 도움말 파일 Windows NT, Windows 3.1의 경우, 또는 Windows 95 WINDOWS\SYSTEM 디렉터리에 배치 합니다.

#### <a name="to-obtain-online-help-for-your-odbc-driver"></a>ODBC 드라이버에 대 한 온라인 도움말을 보려면

1. ODBC 관리자를 실행 합니다.

1. **추가**를 클릭합니다.

1. 드라이버 이름을 선택 합니다.

1. **확인**을 클릭합니다.

해당 드라이버에 대 한 새 데이터 원본 만들기에 대 한 정보를 표시 하는 ODBC 관리자를 클릭 **도움말**합니다. 이 일반적으로 드라이버의 사용에 관한 중요 한 정보를 포함 하는 해당 특정 드라이버에 대 한 도움말 파일을 엽니다.

## <a name="see-also"></a>참고자료

[데이터 소스(ODBC)](../../data/odbc/data-source-odbc.md)
