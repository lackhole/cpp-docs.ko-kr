---
title: db_param (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_param
helpviewer_keywords:
- db_param attribute
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
ms.openlocfilehash: 2de051b099da5f179a7634cddfb359d85f4b1f83
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328794"
---
# <a name="dbparam"></a>db_param

입력 또는 출력 매개 변수를 사용 하 여 지정 된 멤버 변수를 연결 하 고 변수를 구분 합니다.

## <a name="syntax"></a>구문

```cpp
[ db_param(ordinal, paramtype="DBPARAMIO_INPUT", dbtype, precision, scale, status, length) ]
```

### <a name="parameters"></a>매개 변수

*ordinal*<br/>
데이터를 바인딩할 행 집합의 필드에 해당 열 번호 (DBCOLUMNINFO 서 수).

*paramtype*<br/>
(선택 사항) 형식 매개 변수에 설정입니다. 공급자의 데이터 원본에서 지원 되는 매개 변수 I/O 형식만 지원 합니다. 형식은 하나 이상의 DBPARAMIOENUM 값을 조합 합니다.

- DBPARAMIO_INPUT 입력된 매개 변수입니다.

- DBPARAMIO_OUTPUT 출력 매개 변수입니다.

- DBPARAMIO_NOTPARAM 접근자 매개 변수가 없습니다. 설정 `eParamIO` 행에서이 값을 접근자 받으라는 매개 변수가 무시 됩니다.

*dbtype*<br/>
(선택 사항) OLE DB [유형 표시기](/previous-versions/windows/desktop/ms711251(v=vs.85)) 열 항목에 대 한 합니다.

*precision*<br/>
(선택 사항) 열 항목에 사용할 전체 자릿수입니다. 세부 정보에 대 한 설명을 참조 하세요 `bPrecision` 의 요소는 [DBBINDING 구조](/previous-versions/windows/desktop/ms716845(v=vs.85))

*scale*<br/>
(선택 사항) 열 항목에 사용할 소수 자릿수입니다. 세부 정보에 대 한 설명을 참조 하세요 `bScale` 의 요소는 [DBBINDING 구조](/previous-versions/windows/desktop/ms716845(v=vs.85))

*status*<br/>
(선택 사항) 이 칼럼의 상태를 저장 하는 데 사용 되는 멤버 변수입니다. 상태는 데이터 값 또는 NULL 등의 다른 값 열 값이 있는지 여부를 나타냅니다. 가능한 값을 참조 하세요 [상태](/previous-versions/windows/desktop/ms722617(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

*length*<br/>
(선택 사항) 멤버 변수 (바이트)에서 열의 크기를 보유 하는 데 사용 합니다.

## <a name="remarks"></a>설명

**db_param** 매개 변수를 정의 명령에서 사용할; 함께 사용할 따라서 `db_command`합니다. 예를 들어 사용할 수 있습니다 **db_param** SQL 쿼리 또는 저장된 프로시저의 매개 변수를 바인딩합니다. 물음표 (?)로 표시 되어 저장된 프로시저에서 매개 변수 및 매개 변수가 나타나는 순서 대로 데이터 멤버를 바인딩해야 합니다.

**db_param** OLE DB에 참여할 수 있는 멤버 데이터를 구분 `ICommandWithParameters`-바인딩을 기반으로 합니다. 매개 변수 형식 (입력 또는 출력), OLE DB 형식, 정밀도, 배율, 상태 및 지정된 된 매개 변수의 길이 설정 합니다. 이 특성에는 OLE DB 소비자 매크로 BEGIN_PARAM_MAP 삽입... END_PARAM_MAP. 각 멤버를 사용 하 여 표시 합니다 **db_param** 특성을 COLUMN_ENTRY 형식의 구조에 하나의 항목을 차지 합니다.

**db_param** 함께에서 사용 되는 [db_table](db-table.md) 또는 [db_command](db-command.md) 특성입니다.

소비자 특성 공급자가 클래스에 이 특성을 적용하는 경우 컴파일러는 클래스의 이름을 _\_*YourClassName*Accessor로 바꿉니다. 여기서 *YourClassName*은 클래스에 지정한 이름입니다. 컴파일러는 또한 \_*YourClassName*Accessor에서 파생되는 *YourClassName*이라는 클래스를 만듭니다.  클래스 뷰에 두 클래스 모두 표시됩니다.

## <a name="example"></a>예제

다음 예제에서는 Northwind 데이터베이스의 SalesbyYear 저장 프로시저를 기준으로 하는 명령 클래스를 만듭니다. 사용 하 여 저장된 프로시저의 첫 번째 매개 변수를 연결 하는 `m_RETURN_VALUE` 변수를 output 매개 변수로 정의 합니다. 마지막 두 (입력된) 매개 변수를 연결 `m_Beginning_Date` 고 `m_Ending_Date`입니다.

다음 예제에서는 연결 된 `nOutput` 출력 매개 변수를 사용 하 여 변수입니다.

```cpp
// db_param.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_source(L"my_connection_string"),
  db_command(L"{ ? = CALL dbo.\"Sales by Year\"(?,?) }")
]
struct CSalesbyYear {
   DBSTATUS m_dwShippedDateStatus;
   DBSTATUS m_dwOrderIDStatus;
   DBSTATUS m_dwSubtotalStatus;
   DBSTATUS m_dwYearStatus;

   DBLENGTH m_dwShippedDateLength;
   DBLENGTH m_dwOrderIDLength;
   DBLENGTH m_dwSubtotalLength;
   DBLENGTH m_dwYearLength;

   // Bind columns
   [ db_column("1", status="m_dwShippedDateStatus", length="m_dwShippedDateLength") ] DBTIMESTAMP m_ShippedDate;
   [ db_column("2", status="m_dwOrderIDStatus", length="m_dwOrderIDLength") ] LONG m_OrderID;
   [ db_column("3", status="m_dwSubtotalStatus", length="m_dwSubtotalLength") ] CURRENCY m_Subtotal;
   [ db_column("4", status="m_dwYearStatus", length="m_dwYearLength") ] TCHAR m_Year[31];

   // Bind parameters
   [ db_param("1", paramtype="DBPARAMIO_OUTPUT") ] LONG m_RETURN_VALUE;
   [ db_param("2", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Beginning_Date;
   [ db_param("3", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Ending_Date;
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**클래스**, **구조체**, 멤버, 메서드, 로컬|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 특성](ole-db-consumer-attributes.md)
