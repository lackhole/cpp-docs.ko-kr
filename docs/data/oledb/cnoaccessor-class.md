---
title: CNoAccessor 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
ms.openlocfilehash: 0cf1b47cc03d1839ae5c547393c3c193dab439d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230466"
---
# <a name="cnoaccessor-class"></a>CNoAccessor 클래스

템플릿 인수로 사용할 수 있습니다 (`TAccessor`) 템플릿 클래스와 같은 `CCommand` 및 `CTable`, 접근자 클래스 인수를 필요로 하는 합니다.

## <a name="syntax"></a>구문

```cpp
class CNoAccessor
```

## <a name="remarks"></a>설명

사용 하 여 `CNoAccessor` 출력 열 또는 매개 변수를 지원 하도록 클래스를 원하지 않는 경우 템플릿 인수로 합니다.

`CNoAccessor` 각 메서드에 해당 하는 다른 접근자 클래스 다음 스텁 메서드를 구현 합니다.

- `BindColumns` -열 접근자를 바인딩합니다.

- `BindParameters` -열에 생성된 된 매개 변수를 바인딩합니다.

- `Bind` -바인딩을 만듭니다.

- `Close` -접근자를 닫습니다.

- `ReleaseAccessors` -클래스에 의해 만들어진 접근자를 해제 합니다.

- `FreeRecordMemory` -해제 해야 하는 현재 레코드의 모든 열을 해제 합니다.

- `GetColumnInfo` -열린된 행 집합에서 열 정보를 가져옵니다.

- `GetNumAccessors` -클래스에 의해 생성 되는 접근자의 수를 검색 합니다.

- `IsAutoAccessor` -True를 반환 하는 이동 작업 중 접근자에 대 한 데이터는 자동으로 검색 하는 경우.

- `GetHAccessor` -지정된 된 접근자의 접근자 핸들을 검색합니다.

- `GetBuffer` -책갈피 버퍼에 대 한 포인터를 검색합니다.

- `NoBindOnNullRowset` -빈 행 집합에 대해 데이터 바인딩을 하는 것을 금지 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)