---
title: 연결 맵
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.maps
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
ms.openlocfilehash: cbd993e7172ca9a25f25db18d5d0fa042db847b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373299"
---
# <a name="connection-maps"></a>연결 맵

OLE 컨트롤 다른 응용 프로그램에 대 한 인터페이스를 노출할 수 있습니다. 이러한 인터페이스를 제어 하는 컨테이너에서의 액세스만을 허용 합니다. OLE 컨트롤에서 다른 OLE 개체의 외부 인터페이스에 액세스 하려는 경우 연결점을 설정 해야 합니다. 이 연결점에는 나가는 이벤트 맵 또는 알림 함수와 같은 외부 디스패치 맵에 대 한 액세스를 제어할 수 있습니다.

Microsoft Foundation Class 라이브러리는 연결점을 지 원하는 프로그래밍 모델을 제공 합니다. 이 모델에서 "연결 매핑됩니다" 인터페이스 또는 OLE 컨트롤에 대 한 연결점을 지정 하는 데 사용 됩니다. 연결 맵 각 연결 지점에 대 한 매크로 포함 합니다. 연결 맵에 대 한 자세한 내용은 참조는 [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) 클래스입니다.

일반적으로 컨트롤에서 지원 되 두 연결 지점: 이벤트 및 속성 알림을 하나입니다. 이러한 구현한는 `COleControl` 기본 클래스 및 컨트롤 작성기에 의해 추가 작업이 필요 합니다. 클래스에서 구현 하려는 모든 추가 연결 지점은 수동으로 추가 해야 합니다. 연결 맵 및 포인트를 지원 하려면 MFC 다음 매크로 제공 합니다.

### <a name="connection-map-declaration-and-demarcation"></a>연결 맵 선언 및 구분

|||
|-|-|
|[BEGIN_CONNECTION_PART](#begin_connection_part)|(클래스 선언에서 사용 해야 합니다)는 추가 연결 지점을 구현 하는 포함 된 클래스를 선언 합니다.|
|[END_CONNECTION_PART](#end_connection_part)|(클래스 선언에서 사용 해야 합니다) 연결 지점의 선언을 종료 합니다.|
|[CONNECTION_IID](#connection_iid)|컨트롤의 연결 지점의 인터페이스 ID를 지정합니다.|
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|연결 맵이 (클래스 선언에서 사용 해야 합니다) 클래스에서 사용 되는 선언 합니다.|
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|(클래스 구현에 사용 해야 합니다) 연결 맵의 정의 시작 합니다.|
|[END_CONNECTION_MAP](#end_connection_map)|(클래스 구현에 사용 해야 합니다) 연결 맵의 정의 종료 합니다.|
|[CONNECTION_PART](#connection_part)|컨트롤의 연결 구조의 연결점을 지정합니다.|

다음 함수를 설정 하 고 연결 지점을 사용 하 여 연결을 끊기 싱크 지원:

### <a name="initializationtermination-of-connection-points"></a>연결 지점의 초기화/종료

|||
|-|-|
|[AfxConnectionAdvise](#afxconnectionadvise)|원본 및 싱크 간에 연결을 설정 합니다.|
|[AfxConnectionUnadvise](#afxconnectionunadvise)|원본 및 싱크 간의 연결을 중단합니다.|

##  <a name="begin_connection_part"></a>  BEGIN_CONNECTION_PART

BEGIN_CONNECTION_PART 매크로 사용 하 여 추가 연결 지점 속성과 이벤트 알림 연결 지점 외의 정의 시작 합니다.

```
BEGIN_CONNECTION_PART(theClass, localClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 연결점 컨트롤 클래스의 이름을 지정 합니다.

*localClass*<br/>
연결 지점을 구현하는 로컬 클래스의 이름을 지정합니다.

### <a name="remarks"></a>설명

클래스 멤버 함수를 정의 하는 선언 (.h) 파일에서 연결점 BEGIN_CONNECTION_PART 매크로 사용 하 여 다음 CONNECTION_IID 매크로 및 다른 멤버 함수를 구현 하려는 모든 추가 시작한 연결 완료 END_CONNECTION_PART 매크로 사용 하 여 지도 가리킵니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="end_connection_part"></a>  END_CONNECTION_PART

연결 지점의 선언을 종료합니다.

```
END_CONNECTION_PART(localClass)
```

### <a name="parameters"></a>매개 변수

*localClass*<br/>
연결 지점을 구현하는 로컬 클래스의 이름을 지정합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="connection_iid"></a>  CONNECTION_IID

BEGIN_CONNECTION_PART 사이의 END_CONNECTION_PART 매크로 정의에 사용할 OLE 컨트롤에서 지 원하는 연결 지점의 인터페이스 ID.

```
CONNECTION_IID(iid)
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
연결 지점에서 호출 하는 인터페이스의 인터페이스 ID입니다.

### <a name="remarks"></a>설명

합니다 *iid* 인수 ID에 연결 된 해당 싱크 연결점은 호출 하는 인터페이스를 식별 하는 데 인터페이스입니다. 예를 들어:

[!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]

호출 되는 연결 지점을 지정 합니다 `ISinkInterface` 인터페이스입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="declare_connection_map"></a>  DECLARE_CONNECTION_MAP

각 `COleControl`-프로그램에서 파생 된 클래스에는 컨트롤을 지 원하는 추가 연결 지점을 지정 하기 위해 연결 맵을 제공할 수 있습니다.

```
DECLARE_CONNECTION_MAP()
```

### <a name="remarks"></a>설명

컨트롤 추가 요소를 지 원하는 경우 클래스 선언의 끝 DECLARE_CONNECTION_MAP 매크로 사용 합니다. 그런 다음 클래스의 멤버 함수를 정의 하는.cpp 파일에서 사용 BEGIN_CONNECTION_MAP 매크로, 각 컨트롤의 연결 지점에 대 한 CONNECTION_PART 매크로 및 END_CONNECTION_MAP 매크로 연결 맵 종료를 선언 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="begin_connection_map"></a>  BEGIN_CONNECTION_MAP

프로그램에서 각 `COleControl` 파생 클래스는 컨트롤을 지원하는 연결 포인트를 지정하기 위해 연결 맵을 제공할 수 있습니다.

```
BEGIN_CONNECTION_MAP(theClass, theBase)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 연결을 매핑할 컨트롤 클래스의 이름을 지정합니다.

*theBase*<br/>
기본 클래스의 이름을 지정 *theClass*합니다.

### <a name="remarks"></a>설명

구현에서 (합니다. 클래스에 대 한 cpp) 멤버를 정의 하는 함수, BEGIN_CONNECTION_MAP 매크로 사용 하 여 연결 맵을 시작한 다음 각 연결 포인트를 사용 하 여에 대해 매크로 항목을 추가 합니다 [CONNECTION_PART](#connection_part) 매크로입니다. 마지막으로 사용 하 여 연결 맵을 완료 합니다 [END_CONNECTION_MAP](#end_connection_map) 매크로입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="end_connection_map"></a>  END_CONNECTION_MAP

연결 맵의 정의를 끝냅니다.

```
END_CONNECTION_MAP()
```

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="connection_part"></a>  CONNECTION_PART

OLE 컨트롤에 대 한 연결 지점을 ID로 매핑합니다.는 특정 인터페이스

```
CONNECTION_PART(theClass, iid, localClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 연결점 컨트롤 클래스의 이름을 지정 합니다.

*iid*<br/>
연결 지점에서 호출 하는 인터페이스의 인터페이스 ID입니다.

*localClass*<br/>
연결 지점을 구현하는 로컬 클래스의 이름을 지정합니다.

### <a name="remarks"></a>설명

예를 들어:

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]

호출 하는 연결점을 사용 하 여 연결 맵을 구현 하는 `IID_ISinkInterface` 인터페이스입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="afxconnectionadvise"></a>  AfxConnectionAdvise

지정 된 소스, 사이의 연결을 설정 하려면이 함수를 호출 *pUnkSrc*, 및 지정 된 싱크가 *pUnkSink*합니다.

```
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD FAR* pdwCookie);
```

### <a name="parameters"></a>매개 변수

*pUnkSrc*<br/>
인터페이스를 호출 하는 개체에 대 한 포인터입니다.

*pUnkSink*<br/>
인터페이스를 구현 하는 개체에 대 한 포인터입니다.

*iid*<br/>
연결의 인터페이스 ID입니다.

*bRefCount*<br/>
TRUE 이면 연결을 만드는 참조 횟수를 인해 해야 함을 *pUnkSink* 증가 수입니다. FALSE 이면 참조 횟수를 증가 하지는 합니다.

*pdwCookie*<br/>
연결 식별자를이 반환 하는 DWORD에 대 한 포인터입니다. 이 값으로 전달 해야 합니다 *dwCookie* 매개 변수를 `AfxConnectionUnadvise` 연결 연결을 끊을 때.

### <a name="return-value"></a>반환 값

연결이 설정 된; 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

##  <a name="afxconnectionunadvise"></a>  AfxConnectionUnadvise

지정 된 소스, 간의 연결을 끊거나이 함수를 호출 *pUnkSrc*, 및 지정 된 싱크가 *pUnkSink*합니다.

```
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD dwCookie);
```

### <a name="parameters"></a>매개 변수

*pUnkSrc*<br/>
인터페이스를 호출 하는 개체에 대 한 포인터입니다.

*pUnkSink*<br/>
인터페이스를 구현 하는 개체에 대 한 포인터입니다.

*iid*<br/>
연결 지점 인터페이스의 인터페이스 ID입니다.

*bRefCount*<br/>
TRUE 이면 연결 끊기 참조 횟수를 인해 해야 함을 *pUnkSink* 감소 됩니다. FALSE는 참조 횟수는 감소 되지 않습니다 나타냅니다.

*dwCookie*<br/>
반환 된 연결 식별자 `AfxConnectionAdvise`합니다.

### <a name="return-value"></a>반환 값

0이 아닌 경우 연결의 연결이 해제 되었습니다. 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
