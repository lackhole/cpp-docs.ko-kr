---
title: _ATL_FUNC_INFO 구조체
ms.date: 11/04/2016
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
ms.openlocfilehash: f6cf32bab86d741f3b0750c150c7bbc647b27ddc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62248695"
---
# <a name="atlfuncinfo-structure"></a>_ATL_FUNC_INFO 구조체

에 dispinterface 메서드 또는 속성을 설명 하는 데 사용 되는 형식 정보를 포함 합니다.

## <a name="syntax"></a>구문

```
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```

## <a name="members"></a>멤버

`cc`<br/>
호출 규칙. 이 구조를 사용 하는 경우는 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) 클래스를이 멤버는 CC_STDCALL 이어야 합니다. `CC_CDECL` Windows CE에서 지원 되는 유일한 옵션은는 `CALLCONV` 필드는 `_ATL_FUNC_INFO` 구조입니다. 다른 값 지원 되지 않습니다. 따라서 해당 동작이 정의 되지 않았습니다.

`vtReturn`<br/>
Variant 형식 함수 값을 반환 합니다.

`nParams`<br/>
함수 매개 변수의 수입니다.

`pVarTypes`<br/>
함수 매개 변수의 variant 형식의 배열입니다.

## <a name="remarks"></a>설명

내부적으로 ATL 형식 라이브러리에서 가져온 정보를 보관이 구조를 사용 합니다. 이벤트 처리기를 사용 하 여 사용에 대 한 형식 정보를 제공 하는 경우이 구조를 직접 조작 해야 합니다 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) 클래스 및 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) 매크로입니다.

## <a name="example"></a>예제

IDL에 정의 하는 dispinterface 메서드를 제공 합니다.

[!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]

정의 `_ATL_FUNC_INFO` 구조:

[!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]

## <a name="requirements"></a>요구 사항

헤더: atlcom.h

## <a name="see-also"></a>참고자료

[클래스 및 구조체](../../atl/reference/atl-classes.md)<br/>
[IDispEventSimpleImpl 클래스](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)
