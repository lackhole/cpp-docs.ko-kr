---
title: CRestrictions 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
helpviewer_keywords:
- CRestrictions class
- Open method
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
ms.openlocfilehash: 309bb7e707d649cf78528f3d0df6cf8e43201823
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040621"
---
# <a name="crestrictions-class"></a>CRestrictions 클래스

스키마 행 집합에 대 한 제한을 지정할 수 있는 제네릭 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <class T, short nRestrictions, const GUID* pguid>
class CRestrictions :
   public CSchemaRowset <T, nRestrictions>
```

### <a name="parameters"></a>매개 변수

*T*<br/>
접근자에 사용 되는 클래스입니다.

*nRestrictions*<br/>
스키마 행 집합에 대 한 제한 열의 수입니다.

*pguid*<br/>
스키마에 대 한 GUID에 대 한 포인터입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldbsch.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[열기](#open)|결과 사용자가 제공한 제한 사항에 따라 집합을 반환 합니다.|

## <a name="open"></a> Crestrictions:: Open

결과 사용자가 제공한 제한 사항에 따라 집합을 반환 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Open(const CSession& session,
   LPCTSTR lpszParam 1 = NULL,
   LPCTSTR lpszParam 2 = NULL,
   LPCTSTR lpszParam 3 = NULL,
   LPCTSTR lpszParam 4 = NULL,
   LPCTSTR lpszParam 5 = NULL,
   LPCTSTR lpszParam 6 = NULL,
   LPCTSTR lpszParam 7 = NULL,
   bool bBind = true);
```

#### <a name="parameters"></a>매개 변수

*session*<br/>
[in] 데이터 원본에 연결 하는 데 기존 세션 개체를 지정 합니다.

*lpszParam*<br/>
[in] 스키마 행 집합에는 제한을 지정합니다.

*bBind*<br/>
[in] 열 지도 자동으로 바인딩할 지 여부를 지정 합니다. 기본값은 **true**를 자동으로 바인딩할 열 지도 이르게 합니다. 설정 *bBind* 하 **false** 수동으로 바인딩할 수 있도록 열 맵의 자동 바인딩 방지 합니다. (수동 바인딩으로 OLAP 사용자에 게 특히 관심입니다.)

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

스키마 행 집합에서 최대 7 개의 제한 지정할 수 있습니다.

참조 [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) 각 스키마 행 집합에서 정의 된 제한에 대 한 정보에 대 한 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)