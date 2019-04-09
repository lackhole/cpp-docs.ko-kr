---
title: COleDataSource 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDataSource
- AFXOLE/COleDataSource
- AFXOLE/COleDataSource::COleDataSource
- AFXOLE/COleDataSource::CacheData
- AFXOLE/COleDataSource::CacheGlobalData
- AFXOLE/COleDataSource::DelayRenderData
- AFXOLE/COleDataSource::DelayRenderFileData
- AFXOLE/COleDataSource::DelaySetData
- AFXOLE/COleDataSource::DoDragDrop
- AFXOLE/COleDataSource::Empty
- AFXOLE/COleDataSource::FlushClipboard
- AFXOLE/COleDataSource::GetClipboardOwner
- AFXOLE/COleDataSource::OnRenderData
- AFXOLE/COleDataSource::OnRenderFileData
- AFXOLE/COleDataSource::OnRenderGlobalData
- AFXOLE/COleDataSource::OnSetData
- AFXOLE/COleDataSource::SetClipboard
helpviewer_keywords:
- COleDataSource [MFC], COleDataSource
- COleDataSource [MFC], CacheData
- COleDataSource [MFC], CacheGlobalData
- COleDataSource [MFC], DelayRenderData
- COleDataSource [MFC], DelayRenderFileData
- COleDataSource [MFC], DelaySetData
- COleDataSource [MFC], DoDragDrop
- COleDataSource [MFC], Empty
- COleDataSource [MFC], FlushClipboard
- COleDataSource [MFC], GetClipboardOwner
- COleDataSource [MFC], OnRenderData
- COleDataSource [MFC], OnRenderFileData
- COleDataSource [MFC], OnRenderGlobalData
- COleDataSource [MFC], OnSetData
- COleDataSource [MFC], SetClipboard
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
ms.openlocfilehash: 37de6fd74f1e9210dcd9b9a356719436814c0c7f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776832"
---
# <a name="coledatasource-class"></a>COleDataSource 클래스

애플리케이션이 데이터를 넣어 두었다 클립보드 또는 끌어 놓기 작업과 같은 데이터 전송 작업에서 해당 데이터를 제공하는 캐시의 역할을 합니다.

## <a name="syntax"></a>구문

```
class COleDataSource : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleDataSource::COleDataSource](#coledatasource)|`COleDataSource` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleDataSource::CacheData](#cachedata)|데이터를 사용 하 여 지정 된 형식 제공을 `STGMEDIUM` 구조입니다.|
|[COleDataSource::CacheGlobalData](#cacheglobaldata)|HGLOBAL를 사용 하 여 지정 된 형식으로 데이터를 제공 합니다.|
|[COleDataSource::DelayRenderData](#delayrenderdata)|지연 된 렌더링을 사용 하 여 지정 된 형식으로 데이터를 제공 합니다.|
|[COleDataSource::DelayRenderFileData](#delayrenderfiledata)|지정 된 형식으로 데이터를 제공 된 `CFile` 포인터입니다.|
|[COleDataSource::DelaySetData](#delaysetdata)|지원 되는 모든 형식에 대 한 호출 `OnSetData`합니다.|
|[COleDataSource::DoDragDrop](#dodragdrop)|데이터 소스를 사용 하 여 끌어서 놓기 작업을 수행합니다.|
|[COleDataSource::Empty](#empty)|비우고는 `COleDataSource` 개체 데이터입니다.|
|[COleDataSource::FlushClipboard](#flushclipboard)|모든 데이터를 클립보드에 렌더링합니다.|
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|클립보드에 데이터를 여전히 인지 확인 합니다.|
|[COleDataSource::OnRenderData](#onrenderdata)|지연 된 렌더링의 일부로 데이터를 검색합니다.|
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|데이터를 검색 한 `CFile` 지연 된 렌더링의 일부로.|
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|지연 된 렌더링의 일부로 HGLOBAL에 데이터를 검색합니다.|
|[COleDataSource::OnSetData](#onsetdata)|데이터를 대체 하기 위해 호출 된 `COleDataSource` 개체입니다.|
|[COleDataSource::SetClipboard](#setclipboard)|위치는 `COleDataSource` 클립보드에는 개체입니다.|

## <a name="remarks"></a>설명

OLE 데이터 소스를 직접 만들 수 있습니다. 또는 합니다 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 및 [COleServerItem](../../mfc/reference/coleserveritem-class.md) 클래스에 대 한 응답에서 OLE 데이터 원본을 만들고 해당 `CopyToClipboard` 및 `DoDragDrop` 멤버 함수입니다. 참조 [COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) 에 대해 간략하게 설명 합니다. 재정의 `OnGetClipboardData` OLE 데이터 소스의 데이터에 추가 클립보드 형식을 추가 하려면 클라이언트 항목 또는 서버 항목 클래스의 멤버 함수에 대해 생성 된 `CopyToClipboard` 또는 `DoDragDrop` 멤버 함수입니다.

전송 데이터를 준비 하려고 할 때마다이 클래스의 개체를 만들고 데이터에 대 한 가장 적절 한 메서드를 사용 하 여 데이터를 사용 하 여 입력 해야 합니다. 데이터 소스에 삽입 된 방식으로 데이터를 즉시 제공 했는지 여부를 직접적인 영향 (즉시 렌더링) 또는 요청 시 (지연 된 렌더링). 제공 하는 데이터 사용 되는 클립보드 형식을 전달 하 여 모든 클립보드 형식에 대 한 (및 선택적 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 구조)를 호출 [DelayRenderData](#delayrenderdata)합니다.

데이터 원본 및 데이터 전송에 대 한 자세한 내용은 문서 참조 [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md)합니다. 또한이 문서 [클립보드 항목](../../mfc/clipboard.md) OLE 클립보드 메커니즘을 설명 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDataSource`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

##  <a name="cachedata"></a>  COleDataSource::CacheData

데이터는 제공 되는 동안 데이터 전송 작업 형식을 지정 하려면이 함수를 호출 합니다.

```
void CacheData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 제공 하려면의 클립보드 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환한 값 중 하나일 수 있습니다 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) 함수입니다.

*lpStgMedium*<br/>
가리키는 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) 지정 된 형식의 데이터가 포함 된 구조입니다.

*lpFormatEtc*<br/>
가리키는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 데이터 제공 해야 하는 형식을 설명 하는 구조입니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우 *cfFormat*합니다. 다른 필드에 대 한 기본값이 사용 됩니다 NULL 인 경우는 `FORMATETC` 구조입니다.

### <a name="remarks"></a>설명

이 함수는 즉시 렌더링을 사용 하 여 제공 하기 때문에 데이터를 제공 해야 합니다. 데이터는 필요할 때까지 캐시 됩니다.

사용 하 여 데이터를 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) 구조입니다. 사용할 수도 있습니다는 `CacheGlobalData` 데이터의 양을 제공 하는 경우 멤버 함수는는 HGLOBAL를 사용 하 여 효율적으로 전송할 수 있을 만큼 적습니다.

호출한 후 `CacheData` 를 `ptd` 소속 `lpFormatEtc` 의 내용과 *lpStgMedium* 호출자가 아니라 데이터 개체에 의해 소유 됩니다.

지연 된 렌더링을 사용 하려면 호출을 [DelayRenderData](#delayrenderdata) 하거나 [DelayRenderFileData](#delayrenderfiledata) 멤버 함수입니다. 자세한 내용은 지연 된 렌더링 MFC에서 처리 된 것으로 문서를 참조 하세요. [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.

자세한 내용은 참조는 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) 및 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK에는 구조입니다.

자세한 내용은 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK에 있습니다.

##  <a name="cacheglobaldata"></a>  COleDataSource::CacheGlobalData

데이터는 제공 되는 동안 데이터 전송 작업 형식을 지정 하려면이 함수를 호출 합니다.

```
void CacheGlobalData(
    CLIPFORMAT cfFormat,
    HGLOBAL hGlobal,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 제공 하려면의 클립보드 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환한 값 중 하나일 수 있습니다 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) 함수입니다.

*hGlobal*<br/>
지정 된 형식의 데이터가 포함 된 전역 메모리 블록에 대 한 핸들입니다.

*lpFormatEtc*<br/>
가리키는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 데이터 제공 해야 하는 형식을 설명 하는 구조입니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우 *cfFormat*합니다. 다른 필드에 대 한 기본값이 사용 됩니다 NULL 인 경우는 `FORMATETC` 구조입니다.

### <a name="remarks"></a>설명

이 함수를 사용 하 여 즉시 렌더링; 함수를 호출할 때 데이터를 제공 해야 하므로 데이터를 제공 합니다. 데이터는 필요할 때까지 캐시 됩니다. 사용 된 `CacheData` 멤버 함수는 많은 양의 데이터 또는 구조화 된 저장소 매체 필요한 경우 제공 하는 경우.

지연 된 렌더링을 사용 하려면 호출을 [DelayRenderData](#delayrenderdata) 하거나 [DelayRenderFileData](#delayrenderfiledata) 멤버 함수입니다. 자세한 내용은 지연 된 렌더링 MFC에서 처리 된 것으로 문서를 참조 하세요. [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.

자세한 내용은 참조는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK에는 구조입니다.

자세한 내용은 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK에 있습니다.

##  <a name="coledatasource"></a>  COleDataSource::COleDataSource

`COleDataSource` 개체를 생성합니다.

```
COleDataSource();
```

##  <a name="delayrenderdata"></a>  COleDataSource::DelayRenderData

데이터는 제공 되는 동안 데이터 전송 작업 형식을 지정 하려면이 함수를 호출 합니다.

```
void DelayRenderData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 제공 하려면의 클립보드 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환한 값 중 하나일 수 있습니다 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) 함수입니다.

*lpFormatEtc*<br/>
가리키는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 데이터 제공 해야 하는 형식을 설명 하는 구조입니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우 *cfFormat*합니다. 다른 필드에 대 한 기본값이 사용 됩니다 NULL 인 경우는 `FORMATETC` 구조입니다.

### <a name="remarks"></a>설명

이 함수를 사용 하 여 지연 된 렌더링 데이터를 즉시 제공 되지 않은 데이터를 제공 합니다. 합니다 [OnRenderData](#onrenderdata) 하거나 [OnRenderGlobalData](#onrenderglobaldata) 멤버 함수가 호출 되어 데이터를 요청 합니다.

통해 데이터를 제공 하려는 경우이 함수를 사용 하 여를 `CFile` 개체입니다. 통해 데이터를 제공 하려는 경우는 `CFile` 개체를 호출 합니다 [DelayRenderFileData](#delayrenderfiledata) 멤버 함수입니다. 자세한 내용은 지연 된 렌더링 MFC에서 처리 된 것으로 문서를 참조 하세요. [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.

즉시 렌더링을 사용 하려면 호출을 [CacheData](#cachedata) 하거나 [CacheGlobalData](#cacheglobaldata) 멤버 함수입니다.

자세한 내용은 참조는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK에는 구조입니다.

자세한 내용은 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK에 있습니다.

##  <a name="delayrenderfiledata"></a>  COleDataSource::DelayRenderFileData

데이터는 제공 되는 동안 데이터 전송 작업 형식을 지정 하려면이 함수를 호출 합니다.

```
void DelayRenderFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 제공 하려면의 클립보드 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환한 값 중 하나일 수 있습니다 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) 함수입니다.

*lpFormatEtc*<br/>
가리키는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 데이터 제공 해야 하는 형식을 설명 하는 구조입니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우 *cfFormat*합니다. 다른 필드에 대 한 기본값이 사용 됩니다 NULL 인 경우는 `FORMATETC` 구조입니다.

### <a name="remarks"></a>설명

이 함수를 사용 하 여 지연 된 렌더링 데이터를 즉시 제공 되지 않은 데이터를 제공 합니다. 합니다 [OnRenderFileData](#onrenderfiledata) 멤버 함수가 호출 되어 데이터를 요청 합니다.

사용 하려는 경우이 함수를 사용 하 여를 `CFile` 개체 데이터를 제공 합니다. 사용 하지 않을 경우는 `CFile` 개체를 호출 합니다 [DelayRenderData](#delayrenderdata) 멤버 함수입니다. 자세한 내용은 지연 된 렌더링 MFC에서 처리 된 것으로 문서를 참조 하세요. [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.

즉시 렌더링을 사용 하려면 호출을 [CacheData](#cachedata) 하거나 [CacheGlobalData](#cacheglobaldata) 멤버 함수입니다.

자세한 내용은 참조는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK에는 구조입니다.

자세한 내용은 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK에 있습니다.

##  <a name="delaysetdata"></a>  COleDataSource::DelaySetData

데이터 원본의 내용을 변경 작업을 지원 하려면이 함수를 호출 합니다.

```
void DelaySetData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 배치할의 클립보드 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 네이티브 Windows에서 반환한 값 중 하나일 수 있습니다 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) 함수입니다.

*lpFormatEtc*<br/>
가리키는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 데이터를 교체의 형식을 설명 하는 구조입니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우 *cfFormat*합니다. 다른 필드에 대 한 기본값이 사용 됩니다 NULL 인 경우는 `FORMATETC` 구조입니다.

### <a name="remarks"></a>설명

[OnSetData](#onsetdata) 이런 때 프레임 워크에서 호출 됩니다. 프레임 워크에서 데이터 원본을 반환 될 때만 사용 됩니다 [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource)합니다. 하는 경우 `DelaySetData` 를 호출 하지 않으면 프로그램 `OnSetData` 함수 호출 되지 것입니다. `DelaySetData` 각 클립보드를 호출 해야 합니다 또는 `FORMATETC` 형식을 지원 합니다.

자세한 내용은 참조는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK에는 구조입니다.

자세한 내용은 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK에 있습니다.

##  <a name="dodragdrop"></a>  COleDataSource::DoDragDrop

호출 된 `DoDragDrop` 멤버 함수에서 일반적으로이 데이터 원본에 대 한 끌어서 놓기 작업을 수행 하는 [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) 처리기입니다.

```
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,
    LPCRECT lpRectStartDrag = NULL,
    COleDropSource* pDropSource = NULL);
```

### <a name="parameters"></a>매개 변수

*dwEffects*<br/>
끌어서 놓기 작업 허용 되는이 데이터 원본에 있습니다. 다음 중 하나 이상의 수 있습니다.

- DROPEFFECT_COPY는 복사 작업을 수행할 수 있습니다.

- DROPEFFECT_MOVE 이동 작업을 수행할 수 있습니다.

- DROPEFFECT_LINK 링크에서 끌어 놓은 데이터를 원본 데이터를 설정할 수 없습니다.

- DROPEFFECT_SCROLL 나타냅니다 끌기 스크롤 작업이 발생할 수 있습니다.

*lpRectStartDrag*<br/>
끌기 실제로 시작 위치를 정의 하는 사각형에 대 한 포인터입니다. 자세한 내용은 아래 설명 부분을 참조하십시오.

*pDropSource*<br/>
놓기 소스를 가리킵니다. 경우 NULL 이면 기본 구현의 [COleDropSource](../../mfc/reference/coledropsource-class.md) 사용 됩니다.

### <a name="return-value"></a>반환 값

끌어서 놓기 작업에서 생성 하는 효과 삭제 합니다. 그렇지 않으면 DROPEFFECT_NONE 사용자 제공 된 사각형을 벗어나기 전에 마우스 단추를 놓을 때문에 작업을 시작 하는 경우.

### <a name="remarks"></a>설명

끌어서 놓기 작업이 즉시 시작 되지 않습니다. 마우스 커서가 지정 된 사각형에서 벗어날 때까지 기다렸다가 *lpRectStartDrag* 또는 지정 된 기간 (밀리초)이 경과한 때까지 합니다. 하는 경우 *lpRectStartDrag* 가 null 인 경우 사각형의 크기는 1 픽셀입니다.

레지스트리 키 설정 지연 시간 지정 됩니다. 호출 하 여 지연 시간을 변경할 수 있습니다 [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) 하거나 [cwinapp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)합니다. 지연 시간을 지정 하지 않으면 기본값은 200 시간 (밀리초)이 사용 됩니다. 끌어서 지연 시간을 다음과 같이 저장 됩니다.

- Windows NT 끌어서 지연 시간 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay에 저장 됩니다.

- Windows 3.x 끌어서 지연 시간 WIN에 저장 됩니다. INI 파일 [Windows} 섹션입니다.

- Windows 95/98 끌어서 지연 시간 WIN의 캐시 된 버전에 저장 됩니다. INI 합니다.

지연 정보 중 하나는 레지스트리에 저장 된 방법에 대 한 자세한 내용은 끌어에 대 한 또는 합니다. INI 파일을 참조 하세요 [WriteProfileString](/windows/desktop/api/winbase/nf-winbase-writeprofilestringa) Windows SDK에 있습니다.

자세한 내용은 문서를 참조 하세요. [끌어다 놓습니다. 놓기 소스 구현](../../mfc/drag-and-drop-implementing-a-drop-source.md)합니다.

##  <a name="empty"></a>  COleDataSource::Empty

비어 있는 것으로이 함수를 호출 합니다 `COleDataSource` 개체 데이터입니다.

```
void Empty();
```

### <a name="remarks"></a>설명

둘 다가 캐시 하 고 지연 렌더링 형식을 다시 사용할 수 있도록 비워질 됩니다.

자세한 내용은 [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) Windows SDK에 있습니다.

##  <a name="flushclipboard"></a>  COleDataSource::FlushClipboard

에 있는 클립보드를 사용 하면 응용 프로그램이 종료 된 후 클립보드의에서 데이터를 붙여 넣습니다. 데이터를 렌더링 합니다.

```
static void PASCAL FlushClipboard();
```

### <a name="remarks"></a>설명

사용 하 여 [SetClipboard](#setclipboard) 를 클립보드에 데이터를 저장 합니다.

##  <a name="getclipboardowner"></a>  COleDataSource::GetClipboardOwner

클립보드의 데이터를 이후 변경 되었는지 여부를 결정 [SetClipboard](#setclipboard) 가 마지막으로 호출 하 고 그렇다면 현재 소유자를 식별 합니다.

```
static COleDataSource* PASCAL GetClipboardOwner();
```

### <a name="return-value"></a>반환 값

데이터를 클립보드에 현재 원본 또는 클립보드에 없는 경우 또는 호출 응용 프로그램에서 클립보드를 소유 하지 않은 경우 NULL입니다.

##  <a name="onrenderdata"></a>  COleDataSource::OnRenderData

지정 된 형식의 데이터를 검색 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
가리키는 합니다 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 정보가 요청 된 형식을 지정 하는 구조입니다.

*lpStgMedium*<br/>
가리키는 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) 구조는 데이터가 반환 됩니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정 된 형식은 이전에 하나를 `COleDataSource` 를 사용 하 여 개체를 [DelayRenderData](#delayrenderdata) 또는 [DelayRenderFileData](#delayrenderfiledata) 지연 된 렌더링에 대 한 멤버 함수입니다. 이 함수의 기본 구현이 호출 됩니다 [OnRenderFileData](#onrenderfiledata) 하거나 [OnRenderGlobalData](#onrenderglobaldata) 경우 제공 되는 저장소 미디어 파일 또는 메모리, 각각. 이러한 형식은 모두 제공 그런 다음 기본 구현에서는 0을 반환 하 고 아무 작업도 수행 됩니다. 자세한 내용은 지연 된 렌더링 MFC에서 처리 된 것으로 문서를 참조 하세요. [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.

경우 *lpStgMedium*-> *tymed* TYMED_NULL, 되는 `STGMEDIUM` 할당 되 고 지정 된 대로 입력 해야 *lpFormatEtc tymed->* 합니다. TYMED_NULL, 없는 경우는 `STGMEDIUM` 데이터를 채워야 합니다.

이 고급 재정의할 수 있습니다. 요청 된 형식 및 미디어 데이터를 제공 하려면이 함수를 재정의 합니다. 데이터에 따라 대신이 함수의 다른 버전 중 하나를 재정의 하는 것이 좋습니다. 데이터가 작고 크기가 고정 되어 있으면 재정의 `OnRenderGlobalData`합니다. 데이터 파일에는 가변 크기의 경우 재정의 `OnRenderFileData`합니다.

자세한 내용은 참조는 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) 및 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 구조는 [TYMED](/windows/desktop/api/objidl/ne-objidl-tagtymed) 열거형 형식 및 [있음](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK입니다.

##  <a name="onrenderfiledata"></a>  COleDataSource::OnRenderFileData

지정 된 저장 미디어 파일인 경우 지정 된 형식의 데이터를 검색 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
가리키는 합니다 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 정보가 요청 된 형식을 지정 하는 구조입니다.

*pFile*<br/>
가리키는 [CFile](../../mfc/reference/cfile-class.md) 개체는 데이터를 렌더링할 수 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정 된 형식은 이전에 하나를 `COleDataSource` 를 사용 하 여 개체를 [DelayRenderData](#delayrenderdata) 지연 된 렌더링에 대 한 멤버 함수입니다. 이 함수의 기본 구현은 단순히 FALSE를 반환합니다.

이 고급 재정의할 수 있습니다. 요청 된 형식 및 미디어 데이터를 제공 하려면이 함수를 재정의 합니다. 데이터에 따라 대신이 함수의 다른 버전 중 하나를 재정의 하는 것이 좋습니다. 여러 저장소 미디어를 처리 하려는 경우 재정의할 [OnRenderData](#onrenderdata)합니다. 데이터 파일에는 가변 크기의 경우 재정의 `OnRenderFileData`합니다. 자세한 내용은 지연 된 렌더링 MFC에서 처리 된 것으로 문서를 참조 하세요. [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.

자세한 내용은 참조는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 구조 및 [있음](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK의 합니다.

##  <a name="onrenderglobaldata"></a>  COleDataSource::OnRenderGlobalData

지정 된 저장소 미디어가 전역 메모리 때 지정 된 형식의 데이터를 검색 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
가리키는 합니다 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 정보가 요청 된 형식을 지정 하는 구조입니다.

*phGlobal*<br/>
반환 될 데이터는 전역 메모리 핸들을 가리킵니다. 하나는 아직 할당 되지 경우이 매개 변수는 NULL 일 수 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정 된 형식은 이전에 하나를 `COleDataSource` 를 사용 하 여 개체를 [DelayRenderData](#delayrenderdata) 지연 된 렌더링에 대 한 멤버 함수입니다. 이 함수의 기본 구현은 단순히 FALSE를 반환합니다.

하는 경우 *phGlobal* 가 NULL 이면 새 HGLOBAL 할당 되 고 반환 해야 *phGlobal*합니다. 여는 HGLOBAL 지정 하는 고, 그렇지 *phGlobal* 데이터로 채워야 합니다. HGLOBAL에 배치 하는 데이터의 양이 메모리 블록의 현재 크기를 초과할 수 없습니다. 또한 더 큰 크기로 블록 다시 할당할 수 없습니다.

이 고급 재정의할 수 있습니다. 요청 된 형식 및 미디어 데이터를 제공 하려면이 함수를 재정의 합니다. 데이터에 따라 대신이 함수의 다른 버전 중 하나를 재정의 하는 것이 좋습니다. 여러 저장소 미디어를 처리 하려는 경우 재정의할 [OnRenderData](#onrenderdata)합니다. 데이터 파일에는 가변 크기의 경우 재정의 [OnRenderFileData](#onrenderfiledata)합니다. 자세한 내용은 지연 된 렌더링 MFC에서 처리 된 것으로 문서를 참조 하세요. [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.

자세한 내용은 참조는 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 구조 및 [있음](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK의 합니다.

##  <a name="onsetdata"></a>  COleDataSource::OnSetData

설정 하거나 데이터를 바꾸기 위해 프레임 워크에서 호출 된 `COleDataSource` 지정 된 형식의 개체입니다.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
가리키는 합니다 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 구조 데이터를 대체 형식을 지정 합니다.

*lpStgMedium*<br/>
가리키는 합니다 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) 의 현재 내용을 대체 하는 데이터를 포함 하는 구조는 `COleDataSource` 개체입니다.

*bRelease*<br/>
함수 호출을 완료 한 후 저장소 미디어의 소유권을 권한이 있는 사용자를 나타냅니다. 호출자가 저장소 매체를 대신 하 여 할당 된 리소스를 해제 하기 위해 담당자 결정 합니다. 호출자에 게가 작업을 설정 하 여 수행 *bRelease*합니다. 하는 경우 *bRelease* 는 0이 아닌 경우 데이터 소스는 소유권을 사용 하 여를 마쳤을 때 미디어를 해제 합니다. 때 *bRelease* 0 호출자에 게 소유권을 보유 하 고 데이터 원본을 호출 기간에만 저장 미디어를 사용할 수 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

데이터 소스는 성공적으로 가져온이 될 때까지 데이터의 소유권을 사용 하지 않습니다. 즉,이 소유권을 가져올 경우 `OnSetData` 0을 반환 합니다. 호출 하 여 저장소 매체 소유권을 사용 하는 데이터 원본의 경우 해제 합니다 [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) 함수입니다.

기본 구현은 아무 작업도 수행하지 않습니다. 지정 된 형식의 데이터를 대체 하려면이 함수를 재정의 합니다. 이 고급 재정의할 수 있습니다.

자세한 내용은 참조는 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) 하 고 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 구조 및 [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) 및 [있음](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK의 함수입니다.

##  <a name="setclipboard"></a>  COleDataSource::SetClipboard

에 포함 된 데이터는 `COleDataSource` 다음 함수 중 하나를 호출한 후 클립보드에 개체: [CacheData](#cachedata)하십시오 [CacheGlobalData](#cacheglobaldata), [DelayRenderData](#delayrenderdata), 또는 [DelayRenderFileData](#delayrenderfiledata)합니다.

```
void SetClipboard();
```

## <a name="see-also"></a>참고자료

[MFC 샘플 HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDataObject 클래스](../../mfc/reference/coledataobject-class.md)
