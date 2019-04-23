---
title: OLE DB 소비자 템플릿 참조
ms.date: 11/04/2016
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc.templates.ole
- vc-attr.db_source
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
ms.openlocfilehash: fb0b24798b3f2682bbbec7624df34b40a2a9f4cc
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032273"
---
# <a name="ole-db-consumer-templates-reference"></a>OLE DB 소비자 템플릿 참조

OLE DB 소비자 템플릿은 다음 클래스를 포함 합니다. 에 대 한 참조 자료도 포함 되어 있습니다 항목의 [OLE DB 소비자 템플릿에 대 한 매크로](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)합니다.

## <a name="session-classes"></a>세션 클래스

[CDataConnection](../../data/oledb/cdataconnection-class.md)<br/>
데이터 소스를 사용 하 여 연결을 관리합니다. 필요한 개체 (데이터 소스 및 세션) 및 데이터 원본에 연결할 때 수행 해야 하는 작업을 캡슐화 하기 때문에 클라이언트를 만들기 위한 유용한 클래스입니다.

[CDataSource](../../data/oledb/cdatasource-class.md)<br/>
데이터 원본에 공급자를 통해 연결을 나타내는 OLE DB 데이터 원본 개체에 해당 합니다. 하나 이상의 데이터베이스 세션에서 각 표시는 `CSession` 개체, 단일 연결에서 발생할 수 있습니다.

[CEnumerator](../../data/oledb/cenumerator-class.md)<br/>
사용 가능한 데이터 원본에 대 한 행 집합 정보를 검색 하는 OLE DB 열거자 개체에 해당 합니다.

[CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)<br/>
사용한 `CEnumerator` 열거자 행 집합에서 데이터를 액세스할 수 있습니다. 이 행 집합은 데이터 원본 및 현재 열거자에서 표시 되는 열거자 구성 됩니다.

[CSession](../../data/oledb/csession-class.md)<br/>
단일 데이터베이스 액세스 세션을 나타냅니다. 하나 이상의 세션 상호 연결할 수 있습니다 `CDataSource` 개체입니다.

## <a name="accessor-classes"></a>접근자 클래스

[CAccessor](../../data/oledb/caccessor-class.md)<br/>
데이터 원본에 정적으로 바인딩된 레코드에 사용 됩니다. 데이터 원본의 구조를 파악 하는 경우이 접근자 클래스를 사용 합니다.

[CAccessorBase](../../data/oledb/caccessorbase-class.md)<br/>
모든 접근자 클래스에 대 한 기본 클래스입니다.

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
행 집합의 열 정보를 기반으로 런타임 시 만들 수 있는 접근자입니다. 데이터 원본의 구조 알 수 없는 경우 데이터를 검색할이 클래스를 사용 합니다.

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
명령 유형을 알 수 없는 경우 사용할 수 있는 접근자입니다. 호출 하 여 매개 변수 정보를 가져옵니다는 `ICommandWithParameters` 인터페이스, 공급자 인터페이스를 지원 합니다.

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
이 기능을 사용 하면 데이터베이스의 기본 구조 지식이 없는 경우 데이터 소스에 액세스할 수 있습니다.

[CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
유사한 `CDynamicStringAccessor` ANSI 문자열 데이터로 데이터 저장소에서 액세스 하는 데이터를 요청 하는이 클래스는 제외 합니다.

[CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
유사한 `CDynamicStringAccessor` 제외 하 고이 클래스는 유니코드 문자열 데이터를 데이터 저장소에서 액세스 하는 데이터를 요청 합니다.

[CManualAccessor](../../data/oledb/cmanualaccessor-class.md)<br/>
에 대 한 접근자 메서드를 사용 하 여 열 및 명령 매개 변수를 모두 처리 합니다. 이 클래스를 사용 하 여 공급자에는 형식으로 변환할 수 있다면 모든 데이터 형식에 사용할 수 있습니다.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
출력 열 또는 매개 변수를 지원 하도록 클래스를 원하지 않는 경우 템플릿 인수로 사용 수 있습니다.

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)<br/>
유사한 `CDynamicStringAccessor` 제외 하 고이 클래스는 XML 형식 (태그가 지정 된) 데이터로 데이터 저장소에서 액세스 하는 모든 데이터를 변환 합니다.

## <a name="rowset-classes"></a>행 집합 클래스

[CAccessorRowset](../../data/oledb/caccessorrowset-class.md)<br/>
행 집합 및 연결 된 해당 접근자를 캡슐화합니다.

[CArrayRowset](../../data/oledb/carrayrowset-class.md)<br/>
배열 구문을 사용 하 여 행 집합의 요소에 액세스 하는 데 사용 합니다.

[CBulkRowset](../../data/oledb/cbulkrowset-class.md)<br/>
인출 및 단일 호출으로 여러 행 핸들을 검색 하 여 대량에서 행을 조작 하는 데 사용 합니다.

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
명령 행 집합을 반환 하지 않는 경우 템플릿 인수로 사용할 수 있습니다.

[CRestrictions](../../data/oledb/crestrictions-class.md)<br/>
스키마 행 집합에 대 한 제한을 지정 하는 데 사용 합니다.

[CRowset](../../data/oledb/crowset-class.md)<br/>
조작를 설정 하 고 행 집합 데이터를 검색 하는 데 사용 합니다.

[CStreamRowset](../../data/oledb/cstreamrowset-class.md)<br/>
반환을 `ISequentialStream` 대신 행 집합 개체, 한 다음 사용할는 `Read` XML 형식으로 데이터를 검색 하는 방법입니다. (SQL Server 2000은 서식 지정 합니다;이 기능은 SQL Server 2000과만 작동)

[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)<br/>
더미 구현을 제공 `IRowsetNotify`에 대 한 빈 함수를 사용 하 여 합니다 `IRowsetNotify` 메서드 `OnFieldChange`를 `OnRowChange`, 및 `OnRowsetChange`합니다.

[스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)

OLE DB 템플릿은 OLE DB 스키마 행 집합에 해당 하는 클래스 집합을 제공 합니다.

## <a name="command-classes"></a>명령 클래스

[CCommand](../../data/oledb/ccommand-class.md)<br/>
설정 및 매개 변수 기반 OLE DB 명령을 실행 하는 데 사용 합니다. 단순 행 집합을 단순히 열을 사용 하 여 `CTable` 대신 합니다.

[CMultipleResults](../../data/oledb/cmultipleresults-class.md)<br/>
에 대 한 템플릿 인수를 받았던는 `CCommand` 서식 파일을 여러 결과 집합을 처리 하는 명령을 선택 합니다.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
와 같은 템플릿 클래스에 대 한 템플릿 인수로 사용 `CCommand` 및 `CTable`를 사용 하는 접근자 클래스 인수. 사용 하 여 `CNoAccessor` 출력 열 또는 매개 변수를 지원 하도록 클래스를 원하지 않는 경우.

[CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)<br/>
에 대 한 템플릿 인수를 받았던는 `CCommand` 서식 파일을 단일 행 집합을 처리 하는 명령을 선택 합니다. `CNoMultipleResults` 템플릿 인수에 대 한 기본값이입니다.

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
에 대 한 템플릿 인수를 받았던 `CCommand` 또는 `CTable` 명령 또는 테이블 행 집합을 반환 하지 않는 경우.

[CTable](../../data/oledb/ctable-class.md)<br/>
매개 변수가 없는 단순 행 집합에 액세스 하는 데 사용 합니다.

## <a name="property-classes"></a>속성 클래스

[CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)<br/>
속성 Id는 소비자가 속성 정보 배열을 전달 하는 데 사용 합니다. 속성 하나 속성 집합에 속합니다.

[CDBPropSet](../../data/oledb/cdbpropset-class.md)<br/>
공급자의 속성을 설정 하는 데 사용 합니다.

## <a name="bookmark-class"></a>책갈피 클래스

[CBookmark](../../data/oledb/cbookmark-class.md)<br/>
행 집합의 데이터에 액세스 하기 위한 인덱스로 사용 합니다.

## <a name="error-class"></a>Error 클래스

[CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)<br/>
OLE DB 오류 정보를 검색 하는 데 사용 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿 참조](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB 템플릿](../../data/oledb/ole-db-templates.md)