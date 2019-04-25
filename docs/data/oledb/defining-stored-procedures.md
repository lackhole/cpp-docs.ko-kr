---
title: 저장 프로시저 정의
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
ms.openlocfilehash: 0f4c4ad84abf2a5de2cdf09e7064396ea01eeebe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176397"
---
# <a name="defining-stored-procedures"></a>저장 프로시저 정의

저장된 프로시저를 호출 하기 전에 먼저 정의 해야 하지만 사용 하 여 [DEFINE_COMMAND](../../data/oledb/define-command.md) 매크로입니다. 명령을 정의할 때 매개 변수 표식으로 물음표 (?)를 사용 하 여 매개 변수를 표기 합니다.

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{INSERT {name, phone} INTO shippers (?,?)}"))
```

이 항목의 코드 예제에서 사용 된 구문 (괄호 및 등의 사용)는 SQL Server와 관련이 있습니다. 저장된 프로시저에 사용 하는 구문을 사용 하는 공급자에 따라 달라질 수 있습니다.

다음으로, 매개 변수 맵을 명령에서 발생 하는 순서 대로 매개 변수를 나열 하는 명령에서 사용 하는 매개 변수를 지정 합니다.

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param
END_PARAM_MAP()
```

앞의 예제 때 저장된 프로시저를 정의 합니다. 일반적으로 코드의 효율적인 재사용에 대 한 데이터베이스 집합이 포함 되어 이름의 미리 정의 된 저장된 프로시저와 같은 `Sales by Year` 또는 `dt_adduserobject`합니다. SQL Server 엔터프라이즈 관리자를 사용 하 여 해당 정의 볼 수 있습니다. 다음과 같이 호출 (배치를 *?* 매개 변수는 저장된 프로시저 인터페이스에 종속).

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }"))
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }"))
```

다음으로 명령 클래스를 선언 합니다.

```cpp
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>
```

마지막으로 저장된 프로시저 호출 `OpenRowset` 다음과 같습니다.

```cpp
CSession m_session;

HRESULT OpenRowset()
{
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);
}
```

또한 데이터베이스 특성을 사용 하 여 저장된 프로시저를 정의할 수는 참고 [db_command](../../windows/db-command.md) 다음과 같습니다.

```cpp
db_command("{ ? = CALL dbo.dt_adduserobject }")
```

## <a name="see-also"></a>참고자료

[저장 프로시저 사용](../../data/oledb/using-stored-procedures.md)