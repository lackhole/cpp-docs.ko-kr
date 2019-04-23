---
title: OLE DB 공급자 템플릿 참조
ms.date: 11/04/2016
f1_keywords:
- vc.templates.ole
helpviewer_keywords:
- OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
ms.openlocfilehash: e1d6be9687085361edd9141d8fb471e21b6f6376
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038679"
---
# <a name="ole-db-provider-templates-reference"></a>OLE DB 공급자 템플릿 참조

클래스 및 OLE DB 공급자 템플릿에 대 한 인터페이스는 다음 범주로 그룹화 할 수 있습니다. 또한 참조 자료에 대 한 정보를 포함 합니다 [OLE DB 공급자 템플릿 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)합니다.

클래스에는 다음 명명 규칙을 사용 합니다: 패턴을 사용 하 여 라는 클래스 `IWidgetImpl` 인터페이스의 구현을 제공 `IWidget`합니다.

## <a name="session-classes"></a>세션 클래스

[IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)<br/>
데이터 원본 개체에서 새 세션을 만들고 새로 만들어진된 세션에서 요청된 된 인터페이스를 반환 합니다. 데이터 원본 개체에 필수 인터페이스입니다.

[ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)<br/>
속성 집합 맵에서 정의 되는 정적 함수를 호출 하 여 세션 속성을 구현 합니다. 세션 클래스의 속성 집합 지도 지정 해야 합니다. 세션에서 필수 인터페이스입니다.

## <a name="rowset-classes"></a>행 집합 클래스

[CRowsetImpl](../../data/oledb/crowsetimpl-class.md)

많은 구현 인터페이스의 여러 상속을 요구 하지 않고 표준 OLE DB 행 집합 구현을 제공 합니다. 구현은 제공 해야 하는 유일한 방법은 `Execute`합니다.

[CSimpleRow](../../data/oledb/csimplerow-class.md)<br/>
사용 되는 행 핸들에 대 한 기본 구현을 제공 합니다 `IRowsetImpl` 클래스입니다. 행 핸들은 논리적으로 결과 행에 대 한 고유 태그입니다. `IRowsetImpl` 새로 만듭니다 `CSimpleRow` 에서 요청 된 모든 행에 대 한 `IRowsetImpl::GetNextRows`합니다.

[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)<br/>
OLE DB 공급자를 구현할 필요는 `HACCESSOR`, 배열의 태그는 `DBBINDING` 구조입니다. 제공 `HACCESSOR`의 주소는 s는 `BindType` 구조입니다. 행 집합 및 명령에 대해 필수 항목입니다.

[IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)<br/>
공급자 열 맵에 정의 된 정적 함수 대리자입니다. 행 집합 및 명령에 필수 인터페이스입니다.

[IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)<br/>
명령 또는 행 집합에서 형식 변환의 가용성에 대 한 정보를 제공합니다. 명령, 행 집합 및 인덱스 행 집합에서 필수 항목입니다. 구현 된 `IConvertType` OLE DB에서 제공 된 변환 개체에 위임 하 여 인터페이스입니다.

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)<br/>
구현 된 `IDBSchemaRowset` 인터페이스 및 템플릿 화 된 작성자 함수 `CreateSchemaRowset`합니다.

[IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)<br/>
페이지를 열고 단일 기본 테이블 또는 인덱스에서 모든 행이 포함 된 행 집합을 반환 합니다. 세션 개체에 대 한 필수 인터페이스입니다.

[IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)<br/>
OLE DB 구현 [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) 행을 삭제 하 고 새 행을 삽입의 기존 행에 있는 열의 값으로 업데이트할 수 있도록 하는 인터페이스입니다.

[IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)<br/>
이 클래스에서 상속 [IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite) 재정의 [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite)합니다. `IRowsetCreatorImpl` 동일한 기능을 수행 `IObjectWithSite` 또한 OLE DB 속성을 사용 하지만 `DBPROPCANSCROLLBACKWARDS` 고 `DBPROPCANFETCHBACKWARDS`입니다.

[IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)<br/>
구현 된 `IRowsetIdentity` 인터페이스를 통해 두 개의 데이터 행 동일한 지 여부를 비교할 수 있습니다.

[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)<br/>
구현을 제공 합니다 `IRowset` 인터페이스는 기본 행 집합 인터페이스입니다.

[IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)<br/>
명령 클래스에 정의 된 지도 집합 하는 속성을 사용 하 여 행 집합 속성을 구현 합니다. 필수 행 집합 인터페이스입니다.

[IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)<br/>
OLE DB 구현 [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) 인터페이스 행 집합에서 임의의 행을 인출 합니다. 행 집합의 OLE DB 책갈피를 지원 하려면이 클래스에서 상속 하는 행 집합을 확인 합니다.

[IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)<br/>
구현 브로드캐스트 수신기 연결 지점에 advise 할 함수 `IID_IRowsetNotify` 행 집합의 내용 변경 합니다. 알림을 처리 하는 소비자 구현 [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85)) 하 고 해당 연결 지점에 등록 합니다.

[IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)<br/>
OLE DB 구현 [IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85)) 인터페이스를 사용 하 여 변경 내용 전송 지연 하는 소비자를 사용 하도록 설정 [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) 를 데이터 원본 및 전송 하기 전에 변경 내용을 취소 합니다.

## <a name="command-classes"></a>명령 클래스

[ICommandImpl](../../data/oledb/icommandimpl-class.md)<br/>
`ICommand` 인터페이스의 구현을 제공합니다. 이 인터페이스 표시 되지 않지만 의해 처리 됩니다 `ICommandTextImpl`합니다. 명령 개체에는 필수 인터페이스입니다.

[ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)<br/>
이 구현의 합니다 `ICommandProperties` 인터페이스가 정의한 정적 함수로 제공 됩니다는 `BEGIN_PROPSET_MAP` 매크로입니다. 명령에 대 한 필수 항목입니다.

[ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)<br/>
설정 하 고 저장 명령 텍스트를 반환 합니다. 명령에 대 한 필수 항목입니다.

[IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)<br/>
새 명령을 세션 개체를 만들고 새로 만든된 명령에 요청된 된 인터페이스를 반환 합니다. 세션 개체에 대 한 선택적 인터페이스입니다.

다른 명령 클래스는 `IColumnsInfoImpl` 고 `IAccessorImpl`위의 행 집합 클래스 섹션에서 설명 합니다.

## <a name="data-source-classes"></a>데이터 소스 클래스

[IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)<br/>
만들고 소비자와의 연결을 삭제 합니다. 데이터 원본 개체에서 열거자의 선택적 인터페이스에 필수 인터페이스입니다.

[IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)<br/>
`IDBProperties` 데이터 원본 개체에 대 한 필수 인터페이스 및 열거자에 대 한 선택적 인터페이스 이며 그러나 열거자를 노출 하는 경우 `IDBInitialize`를 노출 해야 `IDBProperties` (데이터 원본에는 속성).

[IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)<br/>
데이터 원본 개체에 대 한 인터페이스 포인터를 가져옵니다. 세션에서 필수 인터페이스입니다.

## <a name="other-classes"></a>다른 클래스

[CUtlProps](../../data/oledb/cutlprops-class.md)<br/>
다양 한 OLE DB 속성 인터페이스에 대 한 속성을 구현 (예를 들어 `IDBProperties`, `ISessionProperties`, 및 `IRowsetInfo`).

[IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)

OLE DB 구현 [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) 인터페이스 레코드를 추가 하 고 데이터 멤버에서 레코드를 검색 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[OLE DB 템플릿](../../data/oledb/ole-db-templates.md)