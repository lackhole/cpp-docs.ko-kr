---
title: 복합 컨트롤 매크로
ms.date: 05/06/2019
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
ms.openlocfilehash: 685bf55910d4746463de30b17b71aa6d246db199
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221110"
---
# <a name="composite-control-macros"></a>복합 컨트롤 매크로

이러한 매크로 이벤트 싱크 맵 및 항목을 정의합니다.

|||
|-|-|
|[BEGIN_SINK_MAP](#begin_sink_map)|복합 컨트롤에 대 한 이벤트 싱크 맵의 시작을 표시 합니다.|
|[END_SINK_MAP](#end_sink_map)|복합 컨트롤에 대 한 이벤트 싱크 맵의 끝을 표시 합니다.|
|[SINK_ENTRY](#sink_entry)|이벤트 싱크 맵 항목입니다.|
|[SINK_ENTRY_EX](#sink_entry_ex)|추가 매개 변수를 사용 하 여 이벤트 싱크 맵 항목입니다.|
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017) Iid에 대 한 포인터를 소요 되는 점을 제외 하 고 SINK_ENTRY_EX 유사 합니다.|
|[SINK_ENTRY_INFO](#sink_entry_info)|항목을 사용 하 여 사용 하기 위해 수동으로 제공 된 형식 정보를 사용 하 여 이벤트 싱크 맵과 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)합니다.|
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017) Iid에 대 한 포인터를 소요 되는 점을 제외 하 고 SINK_ENTRY_INFO 유사 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="begin_sink_map"></a>  BEGIN_SINK_MAP

복합 컨트롤에 대 한 이벤트 싱크 맵의 시작 부분을 선언합니다.

```
BEGIN_SINK_MAP(_class)
```

### <a name="parameters"></a>매개 변수

*_class*<br/>
[in] 컨트롤을 지정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>설명

ActiveX 이벤트 싱크만 지 원하는 형식의 반환 값 HRESULT 또는 이벤트 처리기 메서드에서; void CE ATL 구현 다른 모든 반환 값 지원 되지 않으며 해당 동작이 정의 되지 않습니다.

##  <a name="end_sink_map"></a>  END_SINK_MAP

복합 컨트롤에 대 한 이벤트 싱크 맵의 끝을 선언합니다.

```
END_SINK_MAP()
```

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>설명

ActiveX 이벤트 싱크만 지 원하는 형식의 반환 값 HRESULT 또는 이벤트 처리기 메서드에서; void CE ATL 구현 다른 모든 반환 값 지원 되지 않으며 해당 동작이 정의 되지 않습니다.

##  <a name="sink_entry"></a>  SINK_ENTRY

처리기 함수 선언 (*fn*) 지정된 된 이벤트에 대 한 (*dispid*)에 의해 식별 된 컨트롤의 *id*합니다.

```
SINK_ENTRY( id, dispid, fn )
```

### <a name="parameters"></a>매개 변수

*ID*<br/>
[in] 컨트롤을 식별합니다.

*dispid*<br/>
[in] 지정된 된 이벤트를 식별합니다.

*fn*<br/>
[in] 이벤트 처리기 함수의 이름입니다. 이 함수를 사용 해야 합니다는 `_stdcall` 호출 규칙 및 적절 한 dispinterface 스타일 시그니처가 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>설명

ActiveX 이벤트 싱크만 지 원하는 형식의 반환 값 HRESULT 또는 이벤트 처리기 메서드에서; void CE ATL 구현 다른 모든 반환 값 지원 되지 않으며 해당 동작이 정의 되지 않습니다.

##  <a name="sink_entry_ex"></a>  SINK_ENTRY_EX 및 SINK_ENTRY_EX_P

처리기 함수 선언 (*fn*) 지정 된 이벤트 (*dispid*), 디스패치 인터페이스의 (*iid*), 식별 된 컨트롤에 대 한 *id*.

```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```

### <a name="parameters"></a>매개 변수

*ID*<br/>
[in] 컨트롤을 식별합니다.

*iid*<br/>
[in] 디스패치 인터페이스를 나타냅니다.

*piid*<br/>
[in] 디스패치 인터페이스에 대 한 포인터입니다.

*dispid*<br/>
[in] 지정된 된 이벤트를 식별합니다.

*fn*<br/>
[in] 이벤트 처리기 함수의 이름입니다. 이 함수를 사용 해야 합니다는 `_stdcall` 호출 규칙 및 적절 한 dispinterface 스타일 시그니처가 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]

### <a name="remarks"></a>설명

ActiveX 이벤트 싱크만 지 원하는 형식의 반환 값 HRESULT 또는 이벤트 처리기 메서드에서; void CE ATL 구현 다른 모든 반환 값 지원 되지 않으며 해당 동작이 정의 되지 않습니다.

##  <a name="sink_entry_info"></a>  SINK_ENTRY_INFO 및 SINK_ENTRY_INFO_P

이벤트 싱크 맵과 내 SINK_ENTRY_INFO 매크로 사용 하 여 필요한 정보를 제공 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) 관련 처리기 함수에 이벤트를 라우팅하도록 합니다.

```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```

### <a name="parameters"></a>매개 변수

*ID*<br/>
[in] 이벤트 소스를 식별 하는 부호 없는 정수입니다. 이 값과 일치 해야 합니다 *nID* 관련에 사용 되는 템플릿 매개 변수 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) 기본 클래스입니다.

*iid*<br/>
[in] 디스패치 인터페이스를 식별 하는 IID입니다.

*piid*<br/>
[in] 디스패치 인터페이스를 식별 하는 IID에 대 한 포인터입니다.

*dispid*<br/>
[in] DISPID를 지정된 된 이벤트를 식별 합니다.

*fn*<br/>
[in] 이벤트 처리기 함수의 이름입니다. 이 함수를 사용 해야 합니다는 `_stdcall` 호출 규칙 및 적절 한 dispinterface 스타일 시그니처가 있습니다.

*info*<br/>
[in] 이벤트 처리기 함수에 대 한 정보를 입력 합니다. 이 형식 정보에 대 한 포인터의 형태로 제공 됩니다는 `_ATL_FUNC_INFO` 구조입니다. CC_CDECL CALLCONV 필드에 대 한 Windows CE에서 지원 되는 유일한 옵션입니다는 `_ATL_FUNC_INFO` 구조입니다. 다른 값 지원 되지 않습니다. 따라서 해당 동작이 정의 되지 않았습니다.

### <a name="remarks"></a>설명

처음 네 개의 매크로 매개 변수는에 대 한 것과 동일 합니다 [SINK_ENTRY_EX](#sink_entry_ex) 매크로입니다. 마지막 매개 변수는 이벤트에 대 한 형식 정보를 제공 합니다. ActiveX 이벤트 싱크만 지 원하는 형식의 반환 값 HRESULT 또는 이벤트 처리기 메서드에서; void CE ATL 구현 다른 모든 반환 값 지원 되지 않으며 해당 동작이 정의 되지 않습니다.

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)<br/>
[복합 컨트롤 전역 함수](../../atl/reference/composite-control-global-functions.md)
