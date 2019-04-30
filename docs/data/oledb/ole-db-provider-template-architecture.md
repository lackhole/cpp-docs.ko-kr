---
title: OLE DB 공급자 템플릿 구조
ms.date: 11/19/2018
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
ms.openlocfilehash: 65a7e5b8f169d06ca11d8d27ec99ce3db4b63014
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62284001"
---
# <a name="ole-db-provider-template-architecture"></a>OLE DB 공급자 템플릿 구조

## <a name="data-sources-and-sessions"></a>데이터 소스 및 세션

OLE DB 공급자 아키텍처에는 데이터 원본 개체 및 하나 이상의 세션이 포함 됩니다. 데이터 원본 개체에는 모든 공급자를 인스턴스화해야 하는 초기 개체가입니다. 소비자 응용 프로그램에서 데이터를 필요한 경우 공동 공급자를 시작 하려면 데이터 원본 개체를 만듭니다. 데이터 원본 개체에는 세션 개체를 만듭니다 (사용 하 여는 `IDBCreateSession` 인터페이스)를 통해 소비자는 데이터 원본 개체에 연결 합니다. ODBC 프로그래머에 게 데이터 원본 개체에 해당 하는 것으로 생각할 수 있습니다는 `HENV` 와 동등 하 게 세션 개체는 `HDBC`합니다.

![공급자 아키텍처](../../data/oledb/media/vc4twb1.gif "공급자 아키텍처")

만든 소스 파일과 함께 합니다 **OLE DB 공급자 마법사**, 데이터 원본 개체를 구현 하는 OLE DB 템플릿. OLE DB에 해당 하는 개체인 세션 `TSession`합니다.

## <a name="mandatory-and-optional-interfaces"></a>필수 및 선택적 인터페이스

OLE DB 공급자 템플릿에 필요한 모든 인터페이스에 대 한 미리 패키지 된 구현을 제공합니다. 필수 및 선택적 인터페이스는 여러 유형의 개체에 대 한 OLE DB에서 정의 됩니다.

- [데이터 원본](../../data/oledb/data-source-object-interfaces.md)

- [세션](../../data/oledb/session-object-interfaces.md)

- [행 집합](../../data/oledb/rowset-object-interfaces.md)

- [명령](../../data/oledb/command-object-interfaces.md)

- [트랜잭션](../../data/oledb/transaction-object-interfaces.md)

OLE DB 공급자 템플릿 행 및 저장소 개체를 구현 하지 않습니다.

다음 표에서 위에 나열 된 개체에 대 한 필수 및 선택적 인터페이스에 따라 합니다 [OLE DB 2.6 SDK 설명서](/previous-versions/windows/desktop/ms722784(v=vs.85))합니다.

|구성 요소|인터페이스|주석|
|---------------|---------------|-------------|
|[데이터 원본](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md))|[mandatory] `IDBCreateSession`<br /><br /> [mandatory] `IDBInitialize`<br /><br /> [mandatory] `IDBProperties`<br /><br /> [mandatory] `IPersist`<br /><br /> [optional] `IConnectionPointContainer`<br /><br /> [optional] `IDBAsynchStatus`<br /><br /> [optional] `IDBDataSourceAdmin`<br /><br /> [optional] `IDBInfo`<br /><br /> [optional] `IPersistFile`<br /><br /> [optional] `ISupportErrorInfo`|연결에서 소비자 공급자입니다. 개체 속성을 지정 하려면 사용자 ID, 암호 및 데이터 원본 이름과 같은 연결에서 사용 됩니다. 개체 데이터 원본 관리를 사용할 수도 있습니다 (만들기, 업데이트, 삭제, 테이블 및 등).|
|[세션](../../data/oledb/session-object-interfaces.md) ([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md))|[mandatory] `IGetDataSource`<br /><br /> [mandatory] `IOpenRowset`<br /><br /> [mandatory] `ISessionProperties`<br /><br /> [optional] `IAlterIndex`<br /><br /> [optional] `IAlterTable`<br /><br /> [optional] `IBindResource`<br /><br /> [optional] `ICreateRow`<br /><br /> [optional] `IDBCreateCommand`<br /><br /> [optional] `IDBSchemaRowset`<br /><br /> [optional] `IIndexDefinition`<br /><br /> [optional] `ISupportErrorInfo`<br /><br /> [optional] `ITableCreation`<br /><br /> [optional] `ITableDefinition`<br /><br /> [optional] `ITableDefinitionWithConstraints`<br /><br /> [optional] `ITransaction`<br /><br /> [optional] `ITransactionJoin`<br /><br /> [optional] `ITransactionLocal`<br /><br /> [optional] `ITransactionObject`|세션 개체는 소비자와 공급자 간의 단일 대화입니다. ODBC 비슷합니다 `HSTMT` 는 여러 동시 세션이 활성화 될 수 있습니다.<br /><br /> 세션 개체는 OLE DB 기능 페이지로 이동 하는 기본 연결 합니다. 명령, 트랜잭션 또는 행 집합 개체를 이동 하려면 세션 개체를 통해 이동 합니다.|
|[행 집합](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md))|[mandatory] `IAccessor`<br /><br /> [mandatory] `IColumnsInfo`<br /><br /> [mandatory] `IConvertType`<br /><br /> [mandatory] `IRowset`<br /><br /> [mandatory] `IRowsetInfo`<br /><br /> [optional] `IChapteredRowset`<br /><br /> [optional] `IColumnsInfo2`<br /><br /> [optional] `IColumnsRowset`<br /><br /> [optional] `IConnectionPointContainer`<br /><br /> [optional] `IDBAsynchStatus`<br /><br /> [optional] `IGetRow`<br /><br /> [optional] `IRowsetChange`<br /><br /> [optional] `IRowsetChapterMember`<br /><br /> [optional] `IRowsetCurrentIndex`<br /><br /> [optional] `IRowsetFind`<br /><br /> [optional] `IRowsetIdentity`<br /><br /> [optional] `IRowsetIndex`<br /><br /> [optional] `IRowsetLocate`<br /><br /> [optional] `IRowsetRefresh`<br /><br /> [optional] `IRowsetScroll`<br /><br /> [optional] `IRowsetUpdate`<br /><br /> [optional] `IRowsetView`<br /><br /> [optional] `ISupportErrorInfo`<br /><br /> [optional] `IRowsetBookmark`|행 집합 개체는 데이터 원본의 데이터입니다. 개체는 데이터 소스의 데이터 및 데이터에 대해 기본 작업 (업데이트, fetch, 이동 및 기타)에 사용 됩니다. 항상 행 집합 개체를 유지 하 고 데이터를 조작 해야 합니다.|
|[명령](../../data/oledb/command-object-interfaces.md) ([CCommand](ccommand-class.md))|[mandatory] `IAccessor`<br /><br /> [mandatory] `IColumnsInfo`<br /><br /> [mandatory] `ICommand`<br /><br /> [mandatory] `ICommandProperties`<br /><br /> [mandatory] `ICommandText`<br /><br /> [mandatory] `IConvertType`<br /><br /> [optional] `IColumnsRowset`<br /><br /> [optional] `ICommandPersist`<br /><br /> [optional] `ICommandPrepare`<br /><br /> [optional] `ICommandWithParameters`<br /><br /> [optional] `ISupportErrorInfo`<br /><br /> [optional] `ICommandStream`|명령 개체 쿼리와 같은 데이터에 대 한 작업을 처리합니다. 매개 변수가 있거나 매개 변수가 없는 문을 처리할 수 있습니다.<br /><br /> 명령 개체 매개 변수 및 출력 열에 대 한 바인딩을 처리를 담당 이기도 합니다. 바인딩에 행 집합에서 열을 검색 해야 하는 방법에 대 한 정보를 포함 하는 구조입니다. 서 수, 데이터 형식, 길이 및 상태와 같은 정보를 포함합니다.|
|[트랜잭션](../../data/oledb/transaction-object-interfaces.md) (선택 사항)|[mandatory] `IConnectionPointContainer`<br /><br /> [mandatory] `ITransaction`<br /><br /> [optional] `ISupportErrorInfo`|트랜잭션 개체는 데이터 소스에 대한 작업의 원자 단위를 정의하고 이러한 작업 단위가 서로 연관되는 방법을 결정합니다. 이 개체는 OLE DB 공급자 템플릿에 의해 직접 지원 되지 않습니다 (즉, 사용자 고유의 개체 만듭니다).|

자세한 내용은 다음 항목을 참조하세요.

- [속성 맵](../../data/oledb/property-maps.md)

- [사용자 레코드](../../data/oledb/user-record.md)

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 인터페이스](/previous-versions/windows/desktop/ms709709(v=vs.85))<br/>
