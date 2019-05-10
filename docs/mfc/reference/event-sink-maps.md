---
title: 이벤트 싱크 맵
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.maps
helpviewer_keywords:
- event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
ms.openlocfilehash: 8e33636253b269692f87f99980b9da0cd60867ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322360"
---
# <a name="event-sink-maps"></a>이벤트 싱크 맵

포함 된 OLE 컨트롤에 이벤트가 발생 하는 경우 컨트롤의 컨테이너는 이벤트 싱크 맵"," MFC에서 제공 하 라고 하는 메커니즘을 사용 하 여 이벤트를 받습니다. 이 이벤트 싱크 맵과 해당 이벤트의 매개 변수 뿐만 아니라 각 특정 이벤트에 대 한 처리기 함수를 지정합니다. 이벤트 싱크 맵에 대 한 자세한 내용은 문서 참조 [ActiveX 컨트롤 컨테이너](../../mfc/activex-control-containers.md)합니다.

### <a name="event-sink-maps"></a>이벤트 싱크 맵

|||
|-|-|
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|이벤트 싱크 맵과의 정의 시작합니다.|
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|이벤트 싱크 맵과 선언합니다.|
|[END_EVENTSINK_MAP](#end_eventsink_map)|이벤트 싱크 맵과의 정의 종료합니다.|
|[ON_EVENT](#on_event)|특정 이벤트에 대 한 이벤트 처리기를 정의합니다.|
|[ON_EVENT_RANGE](#on_event_range)|OLE 컨트롤 집합에서 발생 하는 특정 이벤트에 대 한 이벤트 처리기를 정의 합니다.|
|[ON_EVENT_REFLECT](#on_event_reflect)|컨트롤의 컨테이너에 의해 처리 됩니다 전에 컨트롤에서 발생 하는 이벤트를 받습니다.|
|[ON_PROPNOTIFY](#on_propnotify)|OLE 컨트롤에서 속성 알림을 처리 하는 것에 대 한 처리기를 정의 합니다.|
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|OLE 컨트롤 집합에서 속성 알림을 처리 하는 것에 대 한 처리기를 정의 합니다.|
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|컨트롤의 컨테이너에 의해 처리 됩니다 전에 컨트롤에서 전송 된 속성 알림을 수신 합니다.|

##  <a name="begin_eventsink_map"></a>  BEGIN_EVENTSINK_MAP

이벤트 싱크 맵의 정의 시작 합니다.

```
BEGIN_EVENTSINK_MAP(theClass, baseClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 인 이벤트 싱크에 매핑할 컨트롤 클래스의 이름을 지정 합니다.

*baseClass*<br/>
기본 클래스의 이름을 지정 *theClass*합니다.

### <a name="remarks"></a>설명

클래스의 멤버 함수를 정의 하는 구현 (.cpp) 파일에서 이벤트 싱크 맵 BEGIN_EVENTSINK_MAP 매크로 사용 하 여 시작 후의 알림을 받으려면 각 이벤트에 대해 매크로 항목을 추가 하 고 END_EVENTSINK_MAP 매크로와 이벤트 싱크 맵을 완료 합니다.

이벤트 싱크 맵 및 OLE 컨트롤 컨테이너에 대 한 자세한 내용은 문서 참조 [ActiveX 컨트롤 컨테이너](../../mfc/activex-control-containers.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="declare_eventsink_map"></a>  DECLARE_EVENTSINK_MAP

OLE 컨테이너를 컨테이너의 알림이 이벤트를 지정 하는 이벤트 싱크 맵을 제공할 수 있습니다.

```
DECLARE_EVENTSINK_MAP()
```

### <a name="remarks"></a>설명

클래스 선언의 끝 DECLARE_EVENTSINK_MAP 매크로 사용 합니다. 그런 다음 합니다. 클래스의 멤버 함수를 정의 하는 CPP 파일의 알림을 받을 이벤트 및 이벤트 싱크 목록의 끝을 선언 하려면 END_EVENTSINK_MAP 매크로 각각에 대해 매크로 항목을 BEGIN_EVENTSINK_MAP 매크로 사용 합니다.

이벤트 싱크 맵에 대 한 자세한 내용은 문서 참조 [ActiveX 컨트롤 컨테이너](../../mfc/activex-control-containers.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="end_eventsink_map"></a>  END_EVENTSINK_MAP

이벤트 싱크 맵의 정의 종료합니다.

```
END_EVENTSINK_MAP()
```

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="on_event"></a>  ON_EVENT

ON_EVENT 매크로 사용 하 여 OLE 컨트롤에 의해 발생 하는 이벤트에 대 한 이벤트 처리기 함수를 정의 합니다.

```
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵 속해 있는 클래스입니다.

*ID*<br/>
OLE 컨트롤의 컨트롤 ID입니다.

*dispid*<br/>
컨트롤에서 발생 한 이벤트의 디스패치 ID입니다.

*pfnHandler*<br/>
이벤트를 처리 하는 멤버 함수에 대 한 포인터입니다. 이 함수는 BOOL 유형 및 이벤트의 매개 변수와 일치 하는 매개 변수 형식을 반환 해야 합니다. (참조 *vtsParams*). 함수를 나타내는 이벤트가 처리 되었으면 TRUE를 반환 해야 그렇지 않으면 FALSE입니다.

*vtsParams*<br/>
시퀀스로 **VTS_** 이벤트에 대 한 매개 변수의 형식을 지정 하는 상수입니다. 이들은 DISP_FUNCTION 같은 디스패치 맵 항목에 사용 되는 동일한 상수입니다.

### <a name="remarks"></a>설명

*vtsParams* 인수는 공백으로 구분 된 목록에서 값을 **VTS_** 상수입니다. 공백 (쉼표가 아님)으로 구분 된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정 합니다. 예를 들어:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

BOOL 뒤에 정수 (short)이 포함 된 목록을 지정 합니다.

목록은 합니다 **VTS_** 상수를 참조 하십시오 [EVENT_CUSTOM](event-maps.md#event_custom)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="on_event_range"></a>  ON_EVENT_RANGE

ON_EVENT_RANGE 매크로 사용 하 여 연속 Id 범위 내에서 컨트롤 ID를 가진 모든 OLE 컨트롤에서 발생 하는 이벤트에 대 한 이벤트 처리기 함수를 정의 합니다.

```
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵 속해 있는 클래스입니다.

*idFirst*<br/>
범위에서 첫 번째 OLE 컨트롤의 컨트롤 ID입니다.

*idLast*<br/>
범위에서 마지막 OLE 컨트롤의 컨트롤 ID입니다.

*dispid*<br/>
컨트롤에서 발생 한 이벤트의 디스패치 ID입니다.

*pfnHandler*<br/>
이벤트를 처리 하는 멤버 함수에 대 한 포인터입니다. 이 함수는 BOOL 유형, 이벤트의 매개 변수와 일치 하는 추가 매개 변수 형식과 형식 UINT (컨트롤 ID의 경우)에 대 한 첫 번째 매개 변수를 반환 해야 합니다. (참조 *vtsParams*). 함수를 나타내는 이벤트가 처리 되었으면 TRUE를 반환 해야 그렇지 않으면 FALSE입니다.

*vtsParams*<br/>
시퀀스로 **VTS_** 이벤트에 대 한 매개 변수의 형식을 지정 하는 상수입니다. 첫 번째 상수는 컨트롤 id VTS_I4, 형식이 여야 합니다. 이들은 DISP_FUNCTION 같은 디스패치 맵 항목에 사용 되는 동일한 상수입니다.

### <a name="remarks"></a>설명

*vtsParams* 인수는 공백으로 구분 된 목록에서 값을 **VTS_** 상수입니다. 공백 (쉼표가 아님)으로 구분 된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정 합니다. 예를 들어:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

BOOL 뒤에 정수 (short)이 포함 된 목록을 지정 합니다.

목록은 합니다 **VTS_** 상수를 참조 하십시오 [EVENT_CUSTOM](event-maps.md#event_custom)합니다.

### <a name="example"></a>예제

다음 예제에서는 세 가지 컨트롤에 대 한 구현 MouseDown 이벤트에 대 한 이벤트 처리기를 보여 줍니다 (IDC_MYCTRL1 IDC_MYCTRL3 통해). 이벤트 처리기 함수를 `OnRangeMouseDown`, 대화 상자 클래스의 헤더 파일에서 선언 됩니다 ( `CMyDlg`)으로:

[!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]

아래 코드는 대화 상자 클래스의 구현 파일에서 정의 됩니다.

[!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="on_event_reflect"></a>  ON_EVENT_REFLECT

ON_EVENT_REFLECT 매크로 사용 이벤트 싱크 맵 OLE 컨트롤의 래퍼 클래스의 경우 컨트롤의 컨테이너에 의해 처리 됩니다 전에 컨트롤에서 발생 하는 이벤트를 받습니다.

```
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵 속해 있는 클래스입니다.

*dispid*<br/>
컨트롤에서 발생 한 이벤트의 디스패치 ID입니다.

*pfnHandler*<br/>
이벤트를 처리 하는 멤버 함수에 대 한 포인터입니다. 이 함수는 BOOL 반환 형식 및 이벤트의 매개 변수와 일치 하는 매개 변수 형식에 있어야 합니다 (참조 *vtsParams*). 함수를 나타내는 이벤트가 처리 되었으면 TRUE를 반환 해야 그렇지 않으면 FALSE입니다.

*vtsParams*<br/>
시퀀스로 **VTS_** 이벤트에 대 한 매개 변수의 형식을 지정 하는 상수입니다. 이들은 DISP_FUNCTION 같은 디스패치 맵 항목에 사용 되는 동일한 상수입니다.

### <a name="remarks"></a>설명

*vtsParams* 인수는 공백으로 구분 된 목록에서 값을 **VTS_** 상수입니다.

공백 (쉼표가 아님)으로 구분 된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정 합니다. 예를 들어:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

BOOL 뒤에 정수 (short)이 포함 된 목록을 지정 합니다.

목록은 합니다 **VTS_** 상수를 참조 하십시오 [EVENT_CUSTOM](event-maps.md#event_custom)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="on_propnotify"></a>  ON_PROPNOTIFY

ON_PROPNOTIFY 매크로 사용 하 여 OLE 컨트롤에서 속성 알림을 처리 하기 위한 이벤트 싱크 맵 항목을 정의 합니다.

```
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵 속해 있는 클래스입니다.

*ID*<br/>
OLE 컨트롤의 컨트롤 ID입니다.

*dispid*<br/>
알림 영역에서 관련 된 속성의 디스패치 ID입니다.

*pfnRequest*<br/>
처리 하는 멤버 함수에 대 한 포인터를 `OnRequestEdit` 이 속성에 대 한 알림입니다. 이 함수는 BOOL 반환 형식이 있어야 합니다. 및 **BOOL** <strong>\*</strong> 매개 변수입니다. 이 함수는 속성을 변경 하도록 허용 하려면 TRUE를 허용 하지 않으려면 FALSE 매개 변수를 설정 해야 합니다. 함수는 알림을 처리 된; 나타내려면 TRUE를 반환 해야 그렇지 않으면 FALSE입니다.

*pfnChanged*<br/>
처리 하는 멤버 함수에 대 한 포인터를 `OnChanged` 이 속성에 대 한 알림입니다. 함수는 BOOL 유형 및 UINT 매개 변수를 반환 해야 합니다. 함수는 알림 처리 되었으면 TRUE를 반환 해야 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

*vtsParams* 인수는 공백으로 구분 된 목록에서 값을 **VTS_** 상수입니다. 공백 (쉼표가 아님)으로 구분 된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정 합니다. 예를 들어:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

BOOL 뒤에 정수 (short)이 포함 된 목록을 지정 합니다.

목록은 합니다 **VTS_** 상수를 참조 하십시오 [EVENT_CUSTOM](event-maps.md#event_custom)합니다.

##  <a name="on_propnotify_range"></a>  ON_PROPNOTIFY_RANGE

ON_PROPNOTIFY_RANGE 매크로 사용 하 여 연속 Id 범위 내에서 컨트롤 ID를 가진 OLE 컨트롤에서 속성 알림을 처리 하기 위한 이벤트 싱크 맵 항목을 정의 합니다.

```

ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵 속해 있는 클래스입니다.

*idFirst*<br/>
범위에서 첫 번째 OLE 컨트롤의 컨트롤 ID입니다.

*idLast*<br/>
범위에서 마지막 OLE 컨트롤의 컨트롤 ID입니다.

*dispid*<br/>
알림 영역에서 관련 된 속성의 디스패치 ID입니다.

*pfnRequest*<br/>
처리 하는 멤버 함수에 대 한 포인터를 `OnRequestEdit` 이 속성에 대 한 알림입니다. 이 함수에 있어야 합니다는 `BOOL` 형식을 반환 하 고 `UINT` 및 `BOOL*` 매개 변수입니다. 함수는 속성을 변경 하도록 허용 하려면 TRUE를 허용 하지 않으려면 FALSE 매개 변수를 설정 해야 합니다. 함수는 알림 처리 되었으면 TRUE를 반환 해야 그렇지 않으면 FALSE입니다.

*pfnChanged*<br/>
처리 하는 멤버 함수에 대 한 포인터를 `OnChanged` 이 속성에 대 한 알림입니다. 함수에 있어야 합니다는 `BOOL` 반환 형식 및 `UINT` 매개 변수입니다. 함수는 알림 처리 되었으면 TRUE를 반환 해야 그렇지 않으면 FALSE입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="on_propnotify_reflect"></a>  ON_PROPNOTIFY_REFLECT

ON_PROPNOTIFY_REFLECT 매크로 사용 이벤트 싱크 맵 OLE 컨트롤의 래퍼 클래스의 경우에 컨트롤의 컨테이너에 의해 처리 됩니다 전에 컨트롤에서 전송 하는 속성 알림을 수신 합니다.

```

ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵 속해 있는 클래스입니다.

*dispid*<br/>
알림 영역에서 관련 된 속성의 디스패치 ID입니다.

*pfnRequest*<br/>
처리 하는 멤버 함수에 대 한 포인터를 `OnRequestEdit` 이 속성에 대 한 알림입니다. 이 함수는 BOOL 반환 형식이 있어야 합니다. 및 **BOOL** <strong>\*</strong> 매개 변수입니다. 이 함수는 속성을 변경 하도록 허용 하려면 TRUE를 허용 하지 않으려면 FALSE 매개 변수를 설정 해야 합니다. 함수는 알림을 처리 된; 나타내려면 TRUE를 반환 해야 그렇지 않으면 FALSE입니다.

*pfnChanged*<br/>
처리 하는 멤버 함수에 대 한 포인터를 `OnChanged` 이 속성에 대 한 알림입니다. 함수 반환 형식 및 매개 변수 없이 BOOL 있어야 합니다. 함수는 알림을 처리 된; 나타내려면 TRUE를 반환 해야 그렇지 않으면 FALSE입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
