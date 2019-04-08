---
title: db_column (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_column
helpviewer_keywords:
- db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
ms.openlocfilehash: e0e2c873452884275e97663ae2d9d6df2f790ffd
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024844"
---
# <a name="dbcolumn"></a>db_column

행 집합의 변수를 지정된 된 열을 바인딩합니다.

## <a name="syntax"></a>구문

```cpp
[ db_column(ordinal, dbtype, precision, scale, status, length) ]
```

#### <a name="parameters"></a>매개 변수

*ordinal*<br/>
서 수 열 번호 (`DBCOLUMNINFO` 서 수) 또는 열 이름 (ANSI 또는 유니코드 문자열) 데이터를 바인딩할 행 집합의 필드에 해당 합니다. 숫자를 사용 하는 경우 연속 된 서 수를 건너뛸 수 있습니다 (예: 1, 2, 3, 5). 이름을 사용 하는 OLE DB 공급자에서 지 원하는 경우 공백을 포함할 수 있습니다. 예를 들어, 다음 형식 중 하나를 사용할 수 있습니다.

```cpp
[db_column("2")] TCHAR szCity[30];
[db_column(L"city_name")] TCHAR szCity[30];
```

*dbtype*<br/>
(선택 사항) OLE DB [유형 표시기](/previous-versions/windows/desktop/ms711251(v=vs.85)) 열 항목에 대 한 합니다.

*전체 자릿수*<br/>
(선택 사항) 열 항목에 사용할 전체 자릿수입니다. 자세한 내용은 설명을 참조는 `bPrecision` 의 요소는 [DBBINDING 구조](/previous-versions/windows/desktop/ms716845(v=vs.85))

*소수 자릿수*<br/>
(선택 사항) 열 항목에 사용할 소수 자릿수입니다. 세부 정보에 대 한 설명을 참조 하세요 `bScale` 의 요소는 [DBBINDING 구조](/previous-versions/windows/desktop/ms716845(v=vs.85))

*status*<br/>
(선택 사항) 이 칼럼의 상태를 저장 하는 데 사용 되는 멤버 변수입니다. 상태는 데이터 값 또는 NULL 등의 다른 값 열 값이 있는지 여부를 나타냅니다. 가능한 값을 참조 하세요 [상태](/previous-versions/windows/desktop/ms722617(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

*길이*<br/>
(선택 사항) 멤버 변수 (바이트)에서 열의 크기를 보유 하는 데 사용 합니다.

## <a name="remarks"></a>설명

**db_column** 행 집합의 변수에 지정 된 테이블 열을 바인딩합니다. OLE DB에 참여할 수 있는 멤버 데이터를 구분 `IAccessor`-바인딩을 기반으로 합니다. 이 특성이 설정 일반적으로 OLE DB 소비자 매크로 사용 하 여 정의 된 열 지도 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md), [END_COLUMN_MAP](../../data/oledb/end-column-map.md), 및 [COLUMN_ENTRY](../../data/oledb/column-entry.md)합니다. OLE DB를 조작 하는 이러한 [DBBINDING 구조](/previous-versions/windows/desktop/ms716845(v=vs.85)) 지정된 된 열을 바인딩합니다. 각 멤버를 사용 하 여 표시 합니다 **db_column** 특성 열 항목의 형태로 열 지도에서 하나의 항목을 차지 합니다. 따라서 호출이 특성 위치에 추가 하면 열 지도, 명령 또는 테이블 클래스입니다.

사용 하 여 **db_column** 함께에서 합니다 [db_table](db-table.md) 하거나 [db_command](db-command.md) 특성입니다.

소비자 특성 공급자가 클래스에 이 특성을 적용하는 경우 컴파일러는 클래스의 이름을 _\_*YourClassName*Accessor로 바꿉니다. 여기서 *YourClassName*은 클래스에 지정한 이름입니다. 컴파일러는 또한 \_*YourClassName*Accessor에서 파생되는 *YourClassName*이라는 클래스를 만듭니다.  클래스 뷰에 두 클래스 모두 표시됩니다.

응용 프로그램에서 사용 되는이 특성의 예제는 예제를 보려면 [AtlAgent](https://github.com/Microsoft/VCSamples), 및 [MultiRead](https://github.com/Microsoft/VCSamples)합니다.

## <a name="example"></a>예제

이 샘플 테이블의 열을 바인딩하는 **긴** 데이터 멤버 상태 및 길이 필드를 지정 합니다.

```cpp
// db_column_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_command(L"Select * from Products") ]
class CProducts {
   DBSTATUS m_dwProductIDStatus;
   DBLENGTH m_dwProductIDLength;

   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;
};
```

## <a name="example"></a>예제

이 샘플에는 네 개의 열을 바인딩하는 **긴**, 문자열, 타임 스탬프를 및 `DB_NUMERIC` 순서 대로 정수입니다.

```cpp
// db_column_2.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_command(L"Select * from Products") ]
class CProducts {
   [db_column("1")] LONG m_OrderID;
   [db_column("2")] TCHAR m_CustomerID[6];
   [db_column("4")] DB_NUMERIC m_OrderDate;
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**클래스**하십시오 **구조체**, 멤버, 메서드|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 특성](ole-db-consumer-attributes.md)<br/>
[클래스 특성](class-attributes.md)
