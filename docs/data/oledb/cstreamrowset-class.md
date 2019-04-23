---
title: CStreamRowset 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
- CStreamRowset::CStreamRowset
- CStreamRowset.CStreamRowset
- ATL.CStreamRowset.CStreamRowset
- ATL::CStreamRowset::CStreamRowset
- CStreamRowset
- CStreamRowset<TAccessor>::CStreamRowset
- ATL::CStreamRowset<TAccessor>::CStreamRowset
- CStreamRowset<TAccessor>.Close
- ATL.CStreamRowset<TAccessor>.Close
- CStreamRowset::Close
- CStreamRowset<TAccessor>::Close
- ATL::CStreamRowset::Close
- ATL.CStreamRowset.Close
- ATL::CStreamRowset<TAccessor>::Close
- CStreamRowset.Close
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
ms.openlocfilehash: b566ddab89d2198e3f6b24eb9a20c60747749d1a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022582"
---
# <a name="cstreamrowset-class"></a>CStreamRowset 클래스

에 사용 된 `CCommand` 또는 `CTable` 선언 합니다.

## <a name="syntax"></a>구문

```cpp
template <class TAccessor = CAccessorBase>
class CStreamRowset
```

### <a name="parameters"></a>매개 변수

*TAccessor*<br/>
접근자 클래스입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CStreamRowset](#cstreamrowset)|생성자입니다. 인스턴스화하고 초기화는 `CStreamRowset` 개체입니다.|
|[닫기](#close)|릴리스를 [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) 클래스에 대 한 인터페이스 포인터입니다.|

## <a name="remarks"></a>설명

사용 하 여 `CStreamRowset` 에 사용자 `CCommand` 또는 `CTable` 선언 예제:

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

또는

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute` 반환 합니다는 `ISequentialStream` 에 저장 된 포인터 `m_spStream`합니다. 그런 다음 사용은 `Read` XML 형식에서 (유니코드 문자열) 데이터를 검색 하는 방법. 예를 들어:

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000 XML 서식에서 수행 하 고 모든 열과 하나의 XML 문자열로 행 집합의 모든 행 반환 됩니다.

> [!NOTE]
>  이 기능은 SQL Server 2000과만 작동합니다.

## <a name="cstreamrowset"></a> CStreamRowset::CStreamRowset

인스턴스화하고 초기화는 `CStreamRowset` 개체입니다.

### <a name="syntax"></a>구문

```cpp
CStreamRowset();
```

## <a name="close"></a> CStreamRowset::Close

릴리스를 [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) 클래스에 대 한 인터페이스 포인터입니다.

### <a name="syntax"></a>구문

```cpp
void Close();
```

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)