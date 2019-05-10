---
title: XML 데이터 액세스
ms.date: 10/18/2018
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
ms.openlocfilehash: b5704c10393026a14ac66b632559fc376f008f8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62284520"
---
# <a name="accessing-xml-data"></a>XML 데이터 액세스

데이터 원본의 XML 데이터를 검색 하는 별도 메서드를 두 가지: 사용 [CStreamRowset](../../data/oledb/cstreamrowset-class.md) 및 다른 용도로 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)합니다.

|기능|CStreamRowset|CXMLAccessor|
|-------------------|-------------------|------------------|
|전송 된 데이터 양|한 번에 모든 열과 행에서 데이터를 검색합니다.|모든 열에서 데이터를 검색 하지만 한 번에 한 행만 합니다. 와 같은 메서드를 사용 하 여 행을 이동 해야 `MoveNext`합니다.|
|문자열의 서식을 지정|SQL Server XML 문자열의 형식을 지정 하 고 소비자에 게 보냅니다.|행 집합 형식으로 데이터를 네이티브 (공급자 유니코드 문자열로 전송 요청)을 검색 하 고 XML 형식으로 데이터를 보유 하는 문자열을 빌드합니다.|
|형식 제어|몇 가지 수준의 일부 SQL Server 2000 관련 속성을 설정 하 여 XML 문자열의 서식 지정 하는 방법을 제어 해야 합니다.|생성된 된 XML 문자열의 형식 제어할 수 없거나 해야합니다.|

하지만 `CStreamRowset` 제공을 보다 효과적으로 XML 형식으로 데이터를에서 검색 하는 SQL Server 2000 에서만 지원 됩니다.

## <a name="retrieving-xml-data-using-cstreamrowset"></a>CStreamRowset를 사용 하 여 XML 데이터를 검색 합니다.

지정할 [CStreamRowset](../../data/oledb/cstreamrowset-class.md) 에서 행 집합 형식으로 프로그램 `CCommand` 또는 `CTable` 선언 합니다. 사용할 수 있습니다 고유한 접근자 또는 없는 접근자를 사용 하 여 예를 들어:

```cpp
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;
```

또는

```cpp
CCommand<CNoAccessor, CStreamRowset> myCmd;
```

정상적으로 호출 하는 경우 `CCommand::Open` (예를 들어, 지정 `CRowset` 으로 `TRowset` 클래스)를 가져옵니다는 `IRowset` 포인터. `ICommand::Execute` 반환 합니다는 `IRowset` 에 저장 된 포인터를 `m_spRowset` 의 멤버는 `CRowset` 개체. 와 같은 메서드와 `MoveFirst`, `MoveNext`, 및 `GetData` 해당 포인터를 사용 하 여 데이터를 검색 합니다.

반면, 호출 하는 경우 `CCommand::Open` (지정 `CStreamRowset` 으로 `TRowset` 클래스), `ICommand::Execute` 반환는 `ISequentialStream` 에 저장 된 포인터를 `m_spStream` 데이터 멤버의 [CStreamRowset](../../data/oledb/cstreamrowset-class.md). 그런 다음 사용은 `Read` XML 형식에서 (유니코드 문자열) 데이터를 검색 하는 방법. 예를 들어:

```cpp
myCmd.m_spStream->Read()
```

SQL Server 2000에서는 XML 서식 지정 하 고 모든 열과 하나의 XML 문자열로 행 집합의 모든 행을 반환 합니다.

사용 하는 예제는 `Read` 메서드를 참조 하세요 **소비자에 게 XML 지원 추가** 에서 [단순 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md)합니다.

> [!NOTE]
> XML을 사용 하 여 지원 `CStreamRowset` SQL Server 2000 에서만 작동 하 고 SQL Server 2000 (MDAC를 사용 하 여 설치 됨)에 대 한 OLE DB 공급자가 있어야 합니다.

## <a name="retrieving-xml-data-using-cxmlaccessor"></a>CXMLAccessor를 사용 하 여 XML 데이터를 검색 합니다.

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) 데이터 저장소의 스키마에 대 한 지식이 없는 경우 데이터 원본에서 문자열 데이터로 액세스할 수 있습니다. `CXMLAccessor` 처럼 작동 `CDynamicStringAccessorW` 전자 (태그가 지정 된) 데이터를 XML 형식으로 데이터 저장소에서 액세스 하는 모든 데이터를 변환 한다는 점이 다릅니다. XML 태그 이름 데이터 저장소의 열 이름과 최대한 가깝게 일치합니다.

사용 하 여 `CXMLAccessor` 다른 접근자 클래스와 마찬가지로, 템플릿 매개 변수로 전달 `CCommand` 또는 `CTable`:

```cpp
CTable<CXMLAccessor, CRowset> rs;
```

사용 하 여 [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) 한 번에 하나의 테이블 행에서 데이터를 검색 하 고와 같은 메서드를 사용 하 여 행을 이동 하려면 `MoveNext`예를 들어:

```cpp
// Open data source, session, and rowset
hr = rs.MoveFirst();

while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
{
    CStringW strRowData;
    myCmd.GetXMLRowData(strRowData);

    printf_s( "%S\n", strRowData );

    hr = rs.MoveNext();
}
```

사용할 수 있습니다 [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) XML 형식의 문자열 데이터로 열 (데이터 형식) 정보를 검색할 수 있습니다.

## <a name="see-also"></a>참고자료

[접근자 사용](../../data/oledb/using-accessors.md)