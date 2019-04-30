---
title: COM 맵 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
ms.openlocfilehash: 75d081674fa4b63e66f1296834d3de305665ab9a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258418"
---
# <a name="com-map-global-functions"></a>COM 맵 전역 함수

이러한 함수는 COM 맵에 대 한 지원을 제공 `IUnknown` 구현 합니다.

|||
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|위임 된 `IUnknown` 집계 개체.|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|인터페이스에 대 한 비교를 위한 효율적인 코드 생성 `IUnknown`합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="atlinternalqueryinterface"></a>  AtlInternalQueryInterface

요청된 인터페이스에 대한 포인터를 검색합니다.

```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*pThis*<br/>
[in] 에 노출 된 인터페이스의 COM 맵에 포함 된 개체에 대 한 포인터 `QueryInterface`합니다.

*pEntries*<br/>
[in] 배열을 `_ATL_INTMAP_ENTRY` 맵을 사용할 수 있는 인터페이스에 액세스 하는 구조입니다.

*iid*<br/>
[in] 요청 된 인터페이스의 GUID입니다.

*ppvObject*<br/>
[out] 에 지정 된 인터페이스 포인터에 대 한 포인터 *iid*, 또는 인터페이스를 찾을 수 없으면 NULL입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

`AtlInternalQueryInterface`에서는 COM 맵 테이블의 인터페이스만 처리됩니다. 개체를 집계 하는 경우 `AtlInternalQueryInterface` 알 수 없는 외부를 위임 하지 않습니다. 매크로 사용 하 여 COM 맵 테이블에 인터페이스를 입력할 수 있습니다 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) 또는 해당 변형 중 하나입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

##  <a name="inlineisequaliunknown"></a>  InlineIsEqualIUnknown

에 대 한 테스트의 특별 한 경우이 함수를 호출 `IUnknown`합니다.

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>매개 변수

*rguid1*<br/>
[in] 비교할 GUID `IID_IUnknown`합니다.

## <a name="see-also"></a>참고자료

[함수](../../atl/reference/atl-functions.md)<br/>
[COM 맵 매크로](../../atl/reference/com-map-macros.md)
