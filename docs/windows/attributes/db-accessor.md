---
title: db_accessor (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_accessor
helpviewer_keywords:
- db_accessor attribute
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
ms.openlocfilehash: bfb287261fce4ebf189801c308f57513f2c9f113
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148252"
---
# <a name="dbaccessor"></a>db_accessor

그룹 `db_column` 에 참여 하는 특성 `IAccessor`-바인딩을 기반으로 합니다.

## <a name="syntax"></a>구문

```cpp
[ db_accessor(num, auto) ]
```

#### <a name="parameters"></a>매개 변수

*num*<br/>
접근자 수 (0부터 시작 하는 정수 인덱스)를 지정합니다. 오름차순 접근자 숫자 순서를 정수 또는 정의 된 값을 지정 해야 합니다.

*auto*<br/>
접근자는 자동으로 검색할지 (TRUE) 여부를 지정 하는 부울 값 (FALSE)를 검색 합니다.

## <a name="remarks"></a>설명

**db_accessor** 에 대 한 기본 OLE DB 접근자를 정의 합니다. 후속 `db_column` 고 `db_param` 동일한 클래스 또는 함수 내에서 특성입니다. **db_accessor** 사용 가능한 수준 멤버에는 그룹에 `db_column` OLE DB에 참여 하는 특성 `IAccessor`-기반 바인딩을 합니다. 함께에서 사용 되는 `db_table` 또는 `db_command` 특성입니다. 이 특성을 호출 하는 것은 호출 비슷합니다는 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.

**db_accessor** 행 집합을 생성 하 고 해당 접근자 맵은에 바인딩합니다. 호출 하지 마십시오 **db_accessor**0 접근자가 자동으로 생성 하 고 모든 열 바인딩이 접근자 블록에 매핑됩니다.

**db_accessor** 그룹 데이터베이스 열 하나 이상의 접근자 바인딩이 있습니다. 여러 접근자를 사용 해야 하는 시나리오의 자세한 내용은 참조 하세요. [행 집합에서 여러 접근자 사용](../../data/oledb/using-multiple-accessors-on-a-rowset.md)합니다. "사용자 레코드 지원에 대 한 여러 접근자"에서 참조 하세요 [사용자 레코드](../../data/oledb/user-records.md)합니다.

소비자 특성 공급자가 클래스에 이 특성을 적용하는 경우 컴파일러는 클래스의 이름을 _\_*YourClassName*Accessor로 바꿉니다. 여기서 *YourClassName*은 클래스에 지정한 이름입니다. 컴파일러는 또한 \_*YourClassName*Accessor에서 파생되는 *YourClassName*이라는 클래스를 만듭니다.  클래스 뷰에 두 클래스 모두 표시됩니다.

## <a name="example"></a>예제

다음 예제에서는 **db_accessor** 두 접근자에 Northwind 데이터베이스의 Orders 테이블의 열을 그룹에 있습니다. 접근자 0은 자동 접근자 및 접근자 1입니다.

```cpp
// cpp_attr_ref_db_accessor.cpp
// compile with: /LD /link /OPT:NOREF
#define _ATL_ATTRIBUTES
#include <atlbase.h>
#include <atldbcli.h>

[ db_command(L"SELECT LastName, FirstName FROM Orders") ]
class CEmployees {
public:
   [ db_accessor(0, TRUE) ];
   [ db_column("1") ] LONG m_OrderID;
   [ db_column("2") ] TCHAR m_CustomerID[6];
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;

   [ db_accessor(1, FALSE) ];
   [ db_column("8") ] CURRENCY m_Freight;
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|특성 블록|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 특성](ole-db-consumer-attributes.md)