---
title: CCachedDataPathProperty 클래스
ms.date: 11/04/2016
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
ms.openlocfilehash: e7394250c93bcc718d50f2ea9b3522256df7c820
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206784"
---
# <a name="ccacheddatapathproperty-class"></a>CCachedDataPathProperty 클래스

비동기적으로 전송되고 메모리 파일에 캐싱되는 OLE 컨트롤 속성을 구현합니다.

## <a name="syntax"></a>구문

```
class CCachedDataPathProperty : public CDataPathProperty
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|`CCachedDataPathProperty` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile` 데이터를 캐시 하는 개체입니다.|

## <a name="remarks"></a>설명

메모리 파일을 RAM 대신 디스크에 저장 됩니다 및 빠른 임시 전송에 유용 합니다.

와 함께 `CAysncMonikerFile` 하 고 `CDataPathProperty`, `CCachedDataPathProperty` OLE 컨트롤의 비동기 모니커를 사용 하기 위한 기능을 제공 합니다. 사용 하 여 `CCachedDataPathProperty` 개체를 통해 메모리 파일에 저장 하 고 URL 또는 파일 원본에서 데이터를 비동기적으로 전송 수는 `m_Cache` 공용 변수입니다. 모든 데이터의 메모리 파일에 저장 되 고 재정의 하지 않아도 됩니다 [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) 알림을 감시 하 고 대응 하는 경우가 있습니다. 예를 들어 큰를 전송 하는 경우. GIF 파일을 더 많은 데이터 도착을 자체 그리면 컨트롤에 알리기 위해 재정의 `OnDataAvailable` 알림을 확인 합니다.

클래스 `CCachedDataPathProperty` 에서 파생 된 `CDataPathProperty`합니다.

인터넷 응용 프로그램에서 비동기 모니커 및 ActiveX 컨트롤을 사용 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하세요.

- [인터넷 첫 번째 단계: ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md)

- [인터넷 첫 번째 단계: 비동기 모니커](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

`CCachedDataPathProperty`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

##  <a name="ccacheddatapathproperty"></a>  CCachedDataPathProperty::CCachedDataPathProperty

`CCachedDataPathProperty` 개체를 생성합니다.

```
CCachedDataPathProperty(COleControl* pControl = NULL);

CCachedDataPathProperty(
    LPCTSTR lpszPath,
    COleControl* pControl = NULL);
```

### <a name="parameters"></a>매개 변수

*pControl*<br/>
이 연결 될 ActiveX 컨트롤 개체에 대 한 포인터 `CCachedDataPathProperty` 개체입니다.

*lpszPath*<br/>
경로 절대 또는 상대 수 있는 속성의 절대 실제 위치를 참조 하는 비동기 모니커를 만드는 데 했습니다. `CCachedDataPathProperty` 하지 파일 이름, Url을 사용합니다. 원하는 경우는 `CCachedDataPathProperty` 파일에 대 한 개체, file:// 경로 앞에 추가 합니다.

### <a name="remarks"></a>설명

`COleControl` 가리키는 개체 *pControl* 에서 사용 됩니다 [열기](../../mfc/reference/cdatapathproperty-class.md#open) 파생된 클래스에서 검색 합니다. 하는 경우 *pControl* 가 null 인 경우 사용 하 여 사용 하는 컨트롤 `Open` 으로 설정 해야 [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol)합니다. 하는 경우 *lpszPath* 가 null 인 경우 경로 통해 전달할 수 있습니다 `Open` 사용 하 여 설정 하거나 [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath)합니다.

##  <a name="m_cache"></a>  CCachedDataPathProperty::m_Cache

데이터가 캐시 된 메모리 파일의 클래스 이름을 포함 합니다.

```
CMemFile m_Cache;
```

### <a name="remarks"></a>설명

메모리 파일을 RAM 대신 디스크에 저장 됩니다.

## <a name="see-also"></a>참고자료

[CDataPathProperty 클래스](../../mfc/reference/cdatapathproperty-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDataPathProperty 클래스](../../mfc/reference/cdatapathproperty-class.md)
