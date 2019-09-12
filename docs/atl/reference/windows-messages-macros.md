---
title: Windows 메시지 매크로
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
ms.openlocfilehash: 7bb5e2fa265c3a5dcabcc16d8343d5b86a4aaf42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275927"
---
# <a name="windows-messages-macros"></a>Windows 메시지 매크로

이 매크로 창 메시지를 전달합니다.

|||
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|사용 하 여 다른 창에 대 한 처리 창에서 수신 된 메시지를 전달 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="wm_forwardmsg"></a>  WM_FORWARDMSG

이 매크로 다른 창에 대 한 처리 창에서 수신 된 메시지를 전달 합니다.

```
WM_FORWARDMSG
```

### <a name="return-value"></a>반환 값

0이 아닌 메시지를 처리 하는 경우 그렇지 않은 경우에 0입니다.

### <a name="remarks"></a>설명

WM_FORWARDMSG를 사용 하 여 다른 창에 대 한 처리 창에서 수신 된 메시지를 전달 합니다. LPARAM 및 WPARAM 매개 변수를 다음과 같이 사용 됩니다.

|매개 변수|사용|
|---------------|-----------|
|WPARAM|사용자가 정의한 데이터|
|LPARAM|에 대 한 포인터를 `MSG` 메시지에 대 한 정보를 포함 하는 구조|

### <a name="example"></a>예제

다음 예에서 `m_hWndOther` 이 메시지를 수신 하는 다른 창을 나타냅니다.

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)
