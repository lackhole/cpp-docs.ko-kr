---
title: 출력 매개 변수
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
ms.openlocfilehash: 196c50ea62c3e3188b61a3b35a9e2752740c4ad5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283968"
---
# <a name="output-parameters"></a>출력 매개 변수

저장된 프로시저를 호출 하는 것을 SQL 명령을 실행 하는 것과 비슷합니다. 주요 차이가 저장된 프로시저 출력 매개 변수 (또는 "outparameter")를 사용 하 고 값을 반환 합니다.

저장 프로시저를 다음에서 첫 번째 '? '입니다. 반환 값 (전화) 및 두 번째'?' 입력 매개 변수 (이름):

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }"))
```

매개 변수 맵에서 입력 및 출력 매개 변수를 지정합니다.

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter
END_PARAM_MAP()
```

응용 프로그램에 저장된 프로시저에서 반환 되는 출력을 처리 해야 합니다. 다른 OLE DB 공급자는 출력 매개 변수를 반환 하 고 결과 처리 하는 동안 서로 다른 시간에 값을 반환 합니다. 예를 들어, Microsoft OLE DB 공급자 SQL Server (SQLOLEDB)에 대 한 출력 매개 변수를 제공 하지 않습니다 및 소비자가 검색 또는 저장된 프로시저가 반환한 결과 집합을 취소 한 후 반환 될 때까지 코드. 출력은 서버에서 마지막 TDS 패킷에서 반환 됩니다.

## <a name="row-count"></a>행 개수

OLE DB 소비자 템플릿을 사용 하 여 outparameter가 저장된 프로시저를 실행 하는 경우 행 수가 행 집합을 닫을 때까지 설정 되지 않았습니다.

예를 들어, 행 집합을 outparameter와 저장된 프로시저를 것이 좋습니다.

```sql
create procedure sp_test
   @_rowcount integer output
as
   select top 50 * from test
   @_rowcount = @@rowcount
return 0
```

`@_rowcount` outparameter 테스트 테이블에서 반환 된 행 수를 보고 합니다. 그러나이 저장된 프로시저를 50 행 수를 제한합니다. 예를 들어 테스트에 100 개 행이 있는 경우 행 개수가 50 (때문에이 코드는 상위 50 개 행만 검색)입니다. 테이블에서 30 개 행만 된 행 개수가 30 것입니다. 호출 해야 `Close` 또는 `CloseAll` 해당 값을 인출 하기 전에 outparameter를 채우려면.

## <a name="see-also"></a>참고자료

[저장 프로시저 사용](../../data/oledb/using-stored-procedures.md)