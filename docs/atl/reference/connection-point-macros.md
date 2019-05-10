---
title: 연결 지점 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
ms.openlocfilehash: cb8d6f696980ef91d7b43c960dc50289ea8500a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278204"
---
# <a name="connection-point-macros"></a>연결 지점 매크로

이러한 매크로 연결 지점 맵 및 항목을 정의합니다.

|||
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|연결 지점 맵 항목의 시작을 표시 합니다.|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|지도에 연결점을 입력합니다.|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017) CONNECTION_POINT_ENTRY 유사 하지만 iid에 대 한 포인터를 사용합니다.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|연결 지점 맵 항목의 끝을 표시 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="begin_connection_point_map"></a>  BEGIN_CONNECTION_POINT_MAP

연결 지점 맵 항목의 시작을 표시 합니다.

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 연결 지점을 포함 하는 클래스의 이름입니다.

### <a name="remarks"></a>설명

연결 지점 맵에 BEGIN_CONNECTION_POINT_MAP 매크로 사용 하 여 시작, 사용 하 여 연결 포인트의 각 항목을 추가 합니다 [CONNECTION_POINT_ENTRY](#connection_point_entry) 매크로 지도를 완료 하 고는 [END_CONNECTION_ POINT_MAP](#end_connection_point_map) 매크로입니다.

Atl에서 연결 지점에 대 한 자세한 내용은 문서 참조 [연결점](../../atl/atl-connection-points.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

##  <a name="connection_point_entry"></a>  CONNECTION_POINT_ENTRY 및 CONNECTION_POINT_ENTRY_P

액세스할 수 있도록 연결 지점 지도에 지정된 된 인터페이스에 대 한 연결 지점을 입력 합니다.

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 연결 지점 지도에 추가 되는 인터페이스의 GUID입니다.

*piid*<br/>
[in] Adde 되는 인터페이스의 GUID에 대 한 포인터입니다.

### <a name="remarks"></a>설명

사용 하는 연결 지점 항목 구조의 [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)합니다. 연결 지점 맵을 포함 하는 클래스에서 상속 해야 `IConnectionPointContainerImpl`합니다.

연결 지점 지도를 시작 합니다 [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) 매크로 각 CONNECTION_POINT_ENTRY 매크로 사용 하 여 연결 포인트에 대 한 항목을 추가 하 고 지도를 완료 합니다 [END_CONNECTION_ POINT_MAP](#end_connection_point_map) 매크로입니다.

Atl에서 연결 지점에 대 한 자세한 내용은 문서 참조 [연결점](../../atl/atl-connection-points.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

##  <a name="end_connection_point_map"></a>  END_CONNECTION_POINT_MAP

연결 지점 맵 항목의 끝을 표시 합니다.

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>설명

연결 지점 지도를 시작 합니다 [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) 매크로 사용 하 여 연결 포인트의 각 항목을 추가 [CONNECTION_POINT_ENTRY](#connection_point_entry) 매크로 지도 END_ 완료 하 고 CONNECTION_POINT_MAP 매크로입니다.

Atl에서 연결 지점에 대 한 자세한 내용은 문서 참조 [연결점](../../atl/atl-connection-points.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)<br/>
[연결 지점 전역 함수](../../atl/reference/connection-point-global-functions.md)
