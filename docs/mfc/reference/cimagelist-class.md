---
title: CImageList 클래스
ms.date: 11/04/2016
f1_keywords:
- CImageList
- AFXCMN/CImageList
- AFXCMN/CImageList::CImageList
- AFXCMN/CImageList::Add
- AFXCMN/CImageList::Attach
- AFXCMN/CImageList::BeginDrag
- AFXCMN/CImageList::Copy
- AFXCMN/CImageList::Create
- AFXCMN/CImageList::DeleteImageList
- AFXCMN/CImageList::DeleteTempMap
- AFXCMN/CImageList::Detach
- AFXCMN/CImageList::DragEnter
- AFXCMN/CImageList::DragLeave
- AFXCMN/CImageList::DragMove
- AFXCMN/CImageList::DragShowNolock
- AFXCMN/CImageList::Draw
- AFXCMN/CImageList::DrawEx
- AFXCMN/CImageList::DrawIndirect
- AFXCMN/CImageList::EndDrag
- AFXCMN/CImageList::ExtractIcon
- AFXCMN/CImageList::FromHandle
- AFXCMN/CImageList::FromHandlePermanent
- AFXCMN/CImageList::GetBkColor
- AFXCMN/CImageList::GetDragImage
- AFXCMN/CImageList::GetImageCount
- AFXCMN/CImageList::GetImageInfo
- AFXCMN/CImageList::GetSafeHandle
- AFXCMN/CImageList::Read
- AFXCMN/CImageList::Remove
- AFXCMN/CImageList::Replace
- AFXCMN/CImageList::SetBkColor
- AFXCMN/CImageList::SetDragCursorImage
- AFXCMN/CImageList::SetImageCount
- AFXCMN/CImageList::SetOverlayImage
- AFXCMN/CImageList::Write
- AFXCMN/CImageList::m_hImageList
helpviewer_keywords:
- CImageList [MFC], CImageList
- CImageList [MFC], Add
- CImageList [MFC], Attach
- CImageList [MFC], BeginDrag
- CImageList [MFC], Copy
- CImageList [MFC], Create
- CImageList [MFC], DeleteImageList
- CImageList [MFC], DeleteTempMap
- CImageList [MFC], Detach
- CImageList [MFC], DragEnter
- CImageList [MFC], DragLeave
- CImageList [MFC], DragMove
- CImageList [MFC], DragShowNolock
- CImageList [MFC], Draw
- CImageList [MFC], DrawEx
- CImageList [MFC], DrawIndirect
- CImageList [MFC], EndDrag
- CImageList [MFC], ExtractIcon
- CImageList [MFC], FromHandle
- CImageList [MFC], FromHandlePermanent
- CImageList [MFC], GetBkColor
- CImageList [MFC], GetDragImage
- CImageList [MFC], GetImageCount
- CImageList [MFC], GetImageInfo
- CImageList [MFC], GetSafeHandle
- CImageList [MFC], Read
- CImageList [MFC], Remove
- CImageList [MFC], Replace
- CImageList [MFC], SetBkColor
- CImageList [MFC], SetDragCursorImage
- CImageList [MFC], SetImageCount
- CImageList [MFC], SetOverlayImage
- CImageList [MFC], Write
- CImageList [MFC], m_hImageList
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
ms.openlocfilehash: 2fc92858f84826e2b953fcbc9de020741e97b007
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346368"
---
# <a name="cimagelist-class"></a>CImageList 클래스

Windows의 공용 이미지 목록 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CImageList : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CImageList::CImageList](#cimagelist)|`CImageList` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CImageList::Add](#add)|이미지 목록에 이미지 또는 이미지를 추가합니다.|
|[CImageList::Attach](#attach)|이미지 목록에 연결 된 `CImageList` 개체입니다.|
|[CImageList::BeginDrag](#begindrag)|이미지를 끌기 시작 합니다.|
|[CImageList::Copy](#copy)|내 이미지 복사를 `CImageList` 개체입니다.|
|[CImageList::Create](#create)|이미지 목록을 초기화 하 고 연결 하는 `CImageList` 개체입니다.|
|[CImageList::DeleteImageList](#deleteimagelist)|이미지 목록을 삭제합니다.|
|[CImageList::DeleteTempMap](#deletetempmap)|호출한 합니다 [CWinApp](../../mfc/reference/cwinapp-class.md) 임시를 삭제 하는 유휴 시간 처리기 `CImageList` 하 여 만든 개체 `FromHandle`합니다.|
|[CImageList::Detach](#detach)|이미지 목록 개체에서 분리를 `CImageList` 개체 및 이미지 목록에 대 한 핸들을 반환 합니다.|
|[CImageList::DragEnter](#dragenter)|끌기 작업 중 업데이트를 잠그고 지정된 된 위치에서 끌기 이미지를 표시 합니다.|
|[CImageList::DragLeave](#dragleave)|창의 잠금을 해제 하 고 창을 업데이트할 수 있도록 끌기 이미지를 숨깁니다.|
|[CImageList::DragMove](#dragmove)|끌어서 놓기 작업 중 끌고 있는 이미지를 이동 합니다.|
|[CImageList::DragShowNolock](#dragshownolock)|표시 하거나 창을 잠그지 않고 끌기 작업을 하는 동안 끌기 이미지를 숨깁니다.|
|[CImageList::Draw](#draw)|끌어서 놓기 작업 중 끌고 있는 이미지를 그립니다.|
|[CImageList::DrawEx](#drawex)|지정 된 디바이스 컨텍스트에서 이미지 목록 항목을 그립니다. 지정된 된 그리기 스타일을 사용 하 고 지정된 된 색을 사용 하 여 이미지를 혼합 합니다.|
|[CImageList::DrawIndirect](#drawindirect)|이미지 목록에서 이미지를 그립니다.|
|[CImageList::EndDrag](#enddrag)|끌기 작업을 종료합니다.|
|[CImageList::ExtractIcon](#extracticon)|이미지와 이미지 목록에 마스크를 기준으로 아이콘을 만듭니다.|
|[CImageList::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CImageList` 이미지 목록에 대 한 핸들을 지정 하는 경우 개체입니다. `CImageList` 개체가 핸들에 연결되지 않은 경우 임시 `CImageList` 개체를 만들어 연결합니다.|
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|에 대 한 포인터를 반환 합니다.는 `CImageList` 이미지 목록에 대 한 핸들을 지정 하는 경우 개체입니다. 경우는 `CImageList` 개체가 핸들에 연결 되지 않은, NULL이 반환 됩니다.|
|[CImageList::GetBkColor](#getbkcolor)|이미지 목록에 대 한 현재 배경색을 검색합니다.|
|[CImageList::GetDragImage](#getdragimage)|끌기를 위한 사용 되는 임시 이미지 목록을 가져옵니다.|
|[CImageList::GetImageCount](#getimagecount)|이미지 목록의 이미지 개수를 검색합니다.|
|[CImageList::GetImageInfo](#getimageinfo)|이미지에 대 한 정보를 검색합니다.|
|[CImageList::GetSafeHandle](#getsafehandle)|검색 `m_hImageList`합니다.|
|[CImageList::Read](#read)|보관 파일에서 이미지 목록을 읽습니다.|
|[CImageList::Remove](#remove)|이미지 목록에서 이미지를 제거합니다.|
|[CImageList::Replace](#replace)|이미지 목록의 이미지를 새 이미지로 대체합니다.|
|[CImageList::SetBkColor](#setbkcolor)|이미지 목록에 대 한 배경색을 설정 합니다.|
|[CImageList::SetDragCursorImage](#setdragcursorimage)|새 끌기 이미지를 만듭니다.|
|[CImageList::SetImageCount](#setimagecount)|이미지 목록의 이미지 개수를 다시 설정합니다.|
|[CImageList::SetOverlayImage](#setoverlayimage)|오버레이 마스크로 사용할 이미지 목록에 이미지의 인덱스를 추가 합니다.|
|[CImageList::Write](#write)|이미지 목록을 보관 파일에 씁니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CImageList::operator HIMAGELIST](#operator_himagelist)|반환 된 HIMAGELIST 연결할는 `CImageList`합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CImageList::m_hImageList](#m_himagelist)|이 개체에 연결 된 이미지 목록을 포함 하는 핸들입니다.|

## <a name="remarks"></a>설명

"이미지 목록" 컬렉션이 동일한 크기의 이미지를 각각 인덱스 0부터 시작 하 여 참조할 수 있습니다. 아이콘 또는 비트맵의 큰 집합을 효율적으로 관리 하는 이미지 목록 사용 됩니다. 모든 이미지는 이미지 목록에서 화면 장치 형태로 단일, 넓은 비트맵에 포함 됩니다. 이미지 목록에 마스크를 투명 하 게 이미지를 그리는 데 사용 (아이콘 스타일)를 포함 하는 단색 비트맵을 포함할 수도 있습니다. Microsoft Win32 응용 프로그래밍 인터페이스 (API) 이미지를 그릴, 만들기 및 이미지 목록 삭제, 추가 및 이미지를 제거, 이미지를 대체, 이미지를 병합 및 이미지를 끌어 데 사용할 수 있는 이미지 목록 기능을 제공 합니다.

이 컨트롤 (및 따라서는 `CImageList` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수 있습니다.

사용 하 여 대 한 자세한 내용은 `CImageList`를 참조 하세요 [컨트롤](../../mfc/controls-mfc.md) 하 고 [CImageList를 사용 하 여](../../mfc/using-cimagelist.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CImageList`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="add"></a>  CImageList::Add

이미지 목록에 하나 이상의 이미지 또는 아이콘을 추가 하려면이 함수를 호출 합니다.

```
int Add(
    CBitmap* pbmImage,
    CBitmap* pbmMask);

int Add(
    CBitmap* pbmImage,
    COLORREF crMask);

int Add(HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*pbmImage*<br/>
이미지 또는 이미지에 포함 된 비트맵에 대 한 포인터입니다. 이미지 수가 비트맵의 너비에서 유추 됩니다.

*pbmMask*<br/>
마스크가 포함 된 비트맵에 대 한 포인터입니다. 마스크가 없습니다 이미지 목록을 사용 하 여 사용 하는 경우이 매개 변수가 무시 됩니다.

*crMask*<br/>
마스크를 생성 하는 데 사용 하는 색입니다. 이 색 지정된 비트맵의 각 픽셀은 검정색으로 변경 된 하 고 해당 비트 마스크의 하나로 설정 됩니다.

*hIcon*<br/>
비트맵 및 새 이미지에 대 한 마스크를 포함 하는 아이콘의 핸들입니다.

### <a name="return-value"></a>반환 값

성공 하면 첫 번째 새 이미지의 0 기반 인덱스 그렇지 않으면-1입니다.

### <a name="remarks"></a>설명

이 사용 하 여 완료 되 면 아이콘 핸들 해제 책임이 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]

##  <a name="attach"></a>  CImageList::Attach

이미지 목록에 연결 하려면이 함수 호출을 `CImageList` 개체입니다.

```
BOOL Attach(HIMAGELIST hImageList);
```

### <a name="parameters"></a>매개 변수

*hImageList*<br/>
이미지 목록 개체에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

첨부 파일에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]

##  <a name="begindrag"></a>  CImageList::BeginDrag

이미지를 끌기 시작 하려면이 함수를 호출 합니다.

```
BOOL BeginDrag(
    int nImage,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
끌어 이미지의 0부터 시작 인덱스입니다.

*ptHotSpot*<br/>
시작 끌어서 위치 (일반적으로 커서 위치)의 좌표입니다. 좌표가 이미지의 왼쪽된 위 모퉁이 기준으로 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 끌어에 사용 되는 임시 이미지 목록을 만듭니다. 현재 커서를 사용 하 여 지정된 된 이미지 및 마스크를 결합 하는 이미지입니다. 후속 WM_MOUSEMOVE 메시지에 대 한 응답을 사용 하 여 끌기 이미지를 이동할 수는 `DragMove` 멤버 함수입니다. 끌기 작업을 종료 하려면 사용할 수는 `EndDrag` 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]

##  <a name="cimagelist"></a>  CImageList::CImageList

`CImageList` 개체를 생성합니다.

```
CImageList();
```

##  <a name="copy"></a>  CImageList::Copy

이 멤버 함수는 Win32 함수의 동작을 구현 [ImageList_Copy](/windows/desktop/api/commctrl/nf-commctrl-imagelist_copy)Windows SDK에 설명 된 대로 합니다.

```
BOOL Copy(
    int iDst,
    int iSrc,
    UINT uFlags = ILCF_MOVE);

BOOL Copy(
    int iDst,
    CImageList* pSrc,
    int iSrc,
    UINT uFlags = ILCF_MOVE);
```

### <a name="parameters"></a>매개 변수

*iDst*<br/>
복사 작업의 대상으로 사용할 이미지의 0부터 시작 하는 인덱스입니다.

*iSrc*<br/>
복사 작업의 원본으로 사용할 이미지의 0부터 시작 하는 인덱스입니다.

*uFlags*<br/>
복사 작업 수의 형식을 지정 하는 비트 플래그 값입니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|ILCF_MOVE|원본 이미지는 대상 이미지의 인덱스에 복사 됩니다. 이 작업은 지정된 된 이미지의 여러 인스턴스에서 발생합니다. ILCF_MOVE 기본값입니다.|
|ILCF_SWAP|원본 및 대상 이미지는 이미지 목록 내 위치를 교환합니다.|

*pSrc*<br/>
에 대 한 포인터를 `CImageList` 복사 작업의 대상이 되는 개체입니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]

##  <a name="create"></a>  CImageList::Create

이미지 목록을 초기화 하 고 연결 하는 [CImageList](../../mfc/reference/cimagelist-class.md) 개체입니다.

```
BOOL Create(
    int cx,
    int cy,
    UINT nFlags,
    int nInitial,
    int nGrow);

BOOL Create(
    UINT nBitmapID,
    int cx,
    int nGrow,
    COLORREF crMask);

BOOL Create(
    LPCTSTR lpszBitmapID,
    int cx,
    int nGrow,
    COLORREF crMask);

BOOL Create(
    CImageList& imagelist1,
    int nImage1,
    CImageList& imagelist2,
    int nImage2,
    int dx,
    int dy);

BOOL Create(CImageList* pImageList);
```

### <a name="parameters"></a>매개 변수

*cx*<br/>
크기 (픽셀 단위)의 각 이미지입니다.

*cy*<br/>
크기 (픽셀 단위)의 각 이미지입니다.

*nFlags*<br/>
만들려는 이미지 목록의 형식을 지정 합니다. 이 매개 변수는 다음 값의 조합일 수 있습니다 하지만 중 하나만 포함할 수는 `ILC_COLOR` 값입니다.

|값|의미|
|-----------|-------------|
|ILC_COLOR|지정 되지 않은 다른 ILC_COLOR * 플래그의 경우 기본 동작을 사용 합니다. 일반적으로 기본값은 ILC_COLOR4; 하지만 이전 디스플레이 드라이버에 대 한 기본값은 ILC_COLORDDB 합니다.|
|ILC_COLOR4|이미지 목록에 대 한 비트맵으로 4 비트 (16 색) 장치 독립적 비트맵 (DIB) 절을 사용 합니다.|
|ILC_COLOR8|8 비트 DIB 구역을 사용 합니다. 색 테이블에 사용 되는 색깔이 하프톤 팔레트와 동일한 색은입니다.|
|ILC_COLOR16|16 비트를 사용 하 여 (32/64 k 색) DIB 섹션입니다.|
|ILC_COLOR24|24 비트 DIB 구역을 사용 합니다.|
|ILC_COLOR32|32 비트 DIB 구역을 사용 합니다.|
|ILC_COLORDDB|장치 종속적 비트맵을 사용 합니다.|
|ILC_MASK|마스크를 사용 합니다. 이미지 목록은 단색 비트맵을 마스크로 사용 되는 두 비트맵을 포함 합니다. 이 값이 포함 되지 않은 경우 이미지 목록을 하나만 비트맵을 포함 합니다. 참조 [이미지 목록에서 이미지 그리기](../../mfc/drawing-images-from-an-image-list.md) 마스킹된 이미지에 대 한 자세한 내용은 합니다.|

*nInitial*<br/>
이미지 목록은 처음에 이미지의 수입니다.

*nGrow*<br/>
이미지는 시스템을 확보 하기 위해 새 이미지 목록의 크기를 조정 해야 하는 경우 이미지 목록을 증가할 수의 수입니다. 이 매개 변수는 크기가 조정 된 이미지 목록에 포함 될 수 있습니다 새 이미지의 수를 나타냅니다.

*nBitmapID*<br/>
이미지 목록과 연결 되도록 비트맵의 리소스 Id입니다.

*crMask*<br/>
마스크를 생성 하는 데 사용 하는 색입니다. 지정한 비트맵에서의이 색의 각 픽셀을 검정색으로, 변경 됩니다 하 고 해당 비트 마스크의 하나로 설정 됩니다.

*lpszBitmapID*<br/>
이미지의 리소스 Id를 포함 하는 문자열입니다.

*imagelist1*<br/>
`CImageList` 개체에 대한 참조입니다.

*nImage1*<br/>
첫 번째 기존 이미지의 인덱스입니다.

*imagelist2*<br/>
`CImageList` 개체에 대한 참조입니다.

*nImage2*<br/>
두 번째 기존 이미지의 인덱스입니다.

*dx*<br/>
픽셀 단위로 첫 번째 이미지에는 관계에서 두 번째 이미지의 x 축 오프셋입니다.

*dy*<br/>
픽셀 단위로 첫 번째 이미지에는 관계에서 두 번째 이미지의 y 축 오프셋입니다.

*pImageList*<br/>
`CImageList` 개체에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CImageList` 두 단계에서. 먼저 생성자를 호출 하 고 호출 `Create`, 이미지 목록을 만들고 연결 하는 `CImageList` 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]

##  <a name="deleteimagelist"></a>  CImageList::DeleteImageList

이미지 목록을 삭제 하려면이 함수를 호출 합니다.

```
BOOL DeleteImageList();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]

##  <a name="deletetempmap"></a>  CImageList::DeleteTempMap

자동으로 호출 합니다 `CWinApp` 유휴 시간 처리기 `DeleteTempMap` 임시 삭제 `CImageList` 개체에 의해 생성 [FromHandle](#fromhandle), 모든 핸들을 삭제 하지 않습니다 ( `hImageList`) 일시적으로 연결 사용 하 여는 `ImageList` 개체입니다.

```
static void PASCAL DeleteTempMap();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]

##  <a name="detach"></a>  CImageList::Detach

이미지 목록 개체를 분리 하려면이 함수 호출을 `CImageList` 개체입니다.

```
HIMAGELIST Detach();
```

### <a name="return-value"></a>반환 값

이미지 목록 개체에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 함수는 이미지 목록 개체에 대 한 핸들을 반환합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CImageList::Attach](#attach)합니다.

##  <a name="dragenter"></a>  CImageList::DragEnter

끌기 작업 중 지정 된 창에 대 한 업데이트를 잠급니다 *pWndLock* 에 지정 된 위치에서 끌기 이미지를 표시 하 고 *가리킨*합니다.

```
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWndLock*<br/>
끌기 이미지를 소유 하는 창에 대 한 포인터입니다.

*point*<br/>
끌기 이미지를 표시 하는 위치입니다. 클라이언트 영역이 아닌 창의 왼쪽된 위 모퉁이 기준으로 좌표는입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

좌표 창의 왼쪽된 위 모퉁이 기준으로 되므로 좌표를 지정 하는 경우 테두리, 제목 표시줄, 메뉴 모음 등의 창 요소의 너비에 대 한 보완 해야 합니다.

하는 경우 *pWndLock* 가 NULL이 고,이 함수는 데스크톱 창에 연결 된 표시 컨텍스트에서 이미지를 그립니다 좌표가 화면의 왼쪽된 위 모퉁이 기준으로 합니다.

이 함수는 끌기 작업 중 지정된 된 창에 대 한 다른 모든 업데이트를 잠급니다. 끌어온된 이미지를 사용 하 여 일시적으로 숨길 수 끌어서 놓기 작업의 대상 강조 표시 하는 등의 끌기 작업을 하는 동안에 그리기를 수행 해야 할 경우는 [CImageList::DragLeave](#dragleave) 함수입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CImageList::BeginDrag](#begindrag)합니다.

##  <a name="dragleave"></a>  CImageList::DragLeave

지정한 창과 잠금 해제 *pWndLock* 하 고 창을 업데이트할 수 있도록 끌기 이미지를 숨깁니다.

```
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```

### <a name="parameters"></a>매개 변수

*pWndLock*<br/>
끌기 이미지를 소유 하는 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CImageList::EndDrag](#enddrag)합니다.

##  <a name="dragmove"></a>  CImageList::DragMove

끌어서 놓기 작업 중 끌고 있는 이미지를 이동 하려면이 함수를 호출 합니다.

```
static BOOL PASCAL DragMove(CPoint pt);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
새 위치를 끕니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 WM_MOUSEMOVE 메시지에 대 한 응답으로 호출 됩니다. 끌기 작업을 시작 하려면 사용 된 `BeginDrag` 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]

##  <a name="dragshownolock"></a>  CImageList::DragShowNolock

표시 하거나 창을 잠그지 않고 끌기 작업을 하는 동안 끌기 이미지를 숨깁니다.

```
static BOOL PASCAL DragShowNolock(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
끌기 이미지 표시 여부를 지정 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

합니다 [CImageList::DragEnter](#dragenter) 함수 끌기 작업 도중 창에 모든 업데이트를 잠급니다. 그러나이 함수를 잠그지 않습니다 창.

##  <a name="draw"></a>  CImageList::Draw

끌어서 놓기 작업 중 끌고 있는 이미지를 그릴이 함수를 호출 합니다.

```
BOOL Draw(
    CDC* pDC,
    int nImage,
    POINT pt,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
대상 장치 컨텍스트에 대 한 포인터입니다.

*nImage*<br/>
그릴 이미지의 0부터 시작 인덱스입니다.

*pt*<br/>
지정 된 디바이스 컨텍스트 내에 그릴 위치입니다.

*nStyle*<br/>
그리기 스타일을 지정 하는 플래그입니다. 이러한 값 중 하나 이상을 수 있습니다.

|값|의미|
|-----------|-------------|
|ILD_BLEND25, ILD_FOCUS|시스템 강조 색을 사용 하 여 25% 혼합 이미지를 그립니다. 이미지 목록에 사용 되는 마스크 없는 경우에이 값 효과가 없습니다.|
|ILD_BLEND50, ILD_SELECTED, ILD_BLEND|시스템 강조 색을 사용 하 여 50%를 혼합 이미지를 그립니다. 이미지 목록에 사용 되는 마스크 없는 경우에이 값 효과가 없습니다.|
|ILD_MASK|마스크를 그립니다.|
|ILD_NORMAL|이미지 목록에 대 한 배경색을 사용 하 여 이미지를 그립니다. 배경색 CLR_NONE 값 이면 이미지 투명 하 게 마스크를 사용 하 여 그려집니다.|
|ILD_TRANSPARENT|투명 하 게 배경색에 관계 없이 마스크를 사용 하 여 이미지를 그립니다.|

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CImageList::SetOverlayImage](#setoverlayimage)합니다.

##  <a name="drawex"></a>  CImageList::DrawEx

지정 된 디바이스 컨텍스트에서 이미지 목록 항목을 그립니다.

```
BOOL DrawEx(
    CDC* pDC,
    int nImage,
    POINT pt,
    SIZE sz,
    COLORREF clrBk,
    COLORREF clrFg,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
대상 장치 컨텍스트에 대 한 포인터입니다.

*nImage*<br/>
그릴 이미지의 0부터 시작 인덱스입니다.

*pt*<br/>
지정 된 디바이스 컨텍스트 내에 그릴 위치입니다.

*sz*<br/>
이미지의 왼쪽 위 모퉁이 기준으로 그릴 이미지의 부분의 크기입니다. 참조 *dx* 하 고 *dy* 에서 [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK에 있습니다.

*clrBk*<br/>
이미지의 배경색입니다. 참조 *rgbBk* 에 [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK에 있습니다.

*clrFg*<br/>
이미지의 전경색입니다. 참조 *rgbFg* 에 [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK에 있습니다.

*nStyle*<br/>
그리기 스타일을 지정 하는 플래그입니다. 참조 *fStyle* 에 [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정된 된 그리기 스타일을 사용 하 고 지정된 된 색을 사용 하 여 이미지를 혼합 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]

##  <a name="drawindirect"></a>  CImageList::DrawIndirect

이미지 목록에서 이미지를 그리기 위해이 멤버 함수를 호출 합니다.

```
BOOL DrawIndirect(IMAGELISTDRAWPARAMS* pimldp);

BOOL DrawIndirect(
    CDC* pDC,
    int nImage,
    POINT pt,
    SIZE sz,
    POINT ptOrigin,
    UINT fStyle = ILD_NORMAL,
    DWORD dwRop = SRCCOPY,
    COLORREF rgbBack = CLR_DEFAULT,
    COLORREF rgbFore = CLR_DEFAULT,
    DWORD fState = ILS_NORMAL,
    DWORD Frame = 0,
    COLORREF crEffect = CLR_DEFAULT);
```

### <a name="parameters"></a>매개 변수

*pimldp*<br/>
에 대 한 포인터를 [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) 그리기 작업에 대 한 정보를 포함 하는 구조입니다.

*pDC*<br/>
대상 장치 컨텍스트에 대 한 포인터입니다. 이 삭제 해야 합니다 [CDC](../../mfc/reference/cdc-class.md) 되어 완료 되 면 개체입니다.

*nImage*<br/>
그릴 이미지의 0부터 시작 하는 인덱스입니다.

*pt*<br/>
A [지점](/previous-versions/dd162805\(v=vs.85\)) 의 x 좌표와 y-이미지를 그릴 위치를 포함 하는 구조체.

*sz*<br/>
A [크기](/windows/desktop/api/windef/ns-windef-tagsize) 그릴 이미지의 크기를 나타내는 구조입니다.

*ptOrigin*<br/>
A [지점](/previous-versions/dd162805\(v=vs.85\)) 포함 된 x 및 y 좌표 이미지 자체와 관련 하 여 그리기 작업의 왼쪽된 위 모퉁이 지정 하는 구조입니다. 이미지의 픽셀에 대 한 x-좌표 이상에 대 한 y-좌표는 왼쪽에 그려집니다.

*fStyle*<br/>
그리기 스타일을 필요에 따라 오버레이 이미지를 지정 하는 플래그입니다. 오버레이 이미지에 자세한 내용은 설명 섹션을 참조 합니다. MFC 기본 구현에서는 ILD_NORMAL, 이미지 목록에 대 한 배경색을 사용 하 여 이미지를 그립니다. 배경색 CLR_NONE 값 이면 이미지 투명 하 게 사용 되는 마스크를 사용 하 여 그려집니다.

다른 가능한 스타일에 설명 되어는 *fStyle* 의 멤버는 [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) 구조입니다.

*dwRop*<br/>
래스터 작업 코드를 지정 하는 값입니다. 이러한 코드는 최종 색을 달성 하기 위해 대상 사각형의 색 데이터를 사용 하 여 소스 사각형에 대 한 색 데이터를 결합 하는 방법을 정의 합니다. MFC의 기본 구현에서는 SRCCOPY, 대상 사각형에 직접 소스 사각형을 복사합니다. 이 매개 변수는 합니다 *fStyle* 매개 변수 ILD_ROP 플래그를 포함 되지 않습니다.

다른 가능한 값은 아래 설명 되어는 *dwRop* 의 멤버는 [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) 구조입니다.

*rgbBack*<br/>
CLR_DEFAULT 기본적으로 표시 되는 이미지 배경 색입니다. 이 매개 변수는 응용 프로그램 정의 RGB 값 또는 다음 값 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|CLR_DEFAULT|기본 배경색입니다. 이미지의 이미지 목록 배경색을 사용 하 여 그려집니다.|
|CLR_NONE|없는 배경색입니다. 이미지를 그릴 투명 하 게 합니다.|

*rgbFore*<br/>
이미지 전경색, CLR_DEFAULT 기본적입니다. 이 매개 변수는 응용 프로그램 정의 RGB 값 또는 다음 값 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|CLR_DEFAULT|기본 전경색입니다. 이미지는 시스템 강조 색을 사용 하 여 전경색으로 그려집니다.|
|CLR_NONE|Blend 색 없음입니다. 대상 장치 컨텍스트의 색과 혼합 됩니다.|

경우에이 매개 변수는 *fStyle* ILD_BLEND25 또는 ILD_BLEND50 플래그가 포함 됩니다.

*fState*<br/>
그리기 상태를 지정 하는 플래그입니다. 이 멤버는 하나 이상의 이미지 목록 상태 플래그를 포함할 수 있습니다.

*프레임*<br/>
Saturate 및 알파 혼합 효과의 동작을 영향을 줍니다.

ILS_SATURATE를 사용 하는 경우이 멤버는 아이콘에 있는 각 픽셀의 RGB 세 개 중 각 색 구성 요소에 추가 되는 값을 보유 합니다.

ILS_APLHA를 사용 하는 경우이 멤버는 알파 채널 값을 보유 합니다. 이 값은 0에서 255 사이의 0는 완전히 투명 하 고 255 완전히 불투명 수 있습니다.

*crEffect*<br/>
A [COLORREF](/windows/desktop/gdi/colorref) 광선 및 그림자 효과에 사용 되는 값입니다.

### <a name="return-value"></a>반환 값

TRUE 이면 성공적으로 이미지를 그릴; 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

Win32 구조를 직접 입력 하려는 경우 첫 번째 버전을 사용 합니다. 하나 이상의 MFC의 기본 인수를 활용 하거나 구조를 관리 하지 않도록 하려는 경우 두 번째 버전을 사용 합니다.

오버레이 이미지는 이미지에서이 멤버 함수에 지정 된 기본 이미지를 기반으로 그려지는 합니다 *nImage* 매개 변수입니다. 오버레이 마스크를 사용 하 여 그리기를 [그리기](#draw) 사용 하 여 지정 된 오버레이 마스크의 1부터 시작 인덱스를 사용 하 여 멤버 함수는 [INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) 매크로입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]

##  <a name="enddrag"></a>  CImageList::EndDrag

끌기 작업을 종료 하려면이 함수를 호출 합니다.

```
static void PASCAL EndDrag();
```

### <a name="remarks"></a>설명

끌기 작업을 시작 하려면 사용 된 `BeginDrag` 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]

##  <a name="extracticon"></a>  CImageList::ExtractIcon

이미지 및 이미지 목록에서 관련 된 마스크에 따라 아이콘을 만드는이 함수를 호출 합니다.

```
HICON ExtractIcon(int nImage);
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
이미지의 인덱스 0부터 시작 합니다.

### <a name="return-value"></a>반환 값

성공할 경우 아이콘의 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

이 방법은의 동작에 의존 합니다 [ImageList_ExtractIcon](/windows/desktop/api/commctrl/nf-commctrl-imagelist_extracticon) 아이콘을 만드는 매크로입니다. 참조 된 [ImageList_ExtractIcon](/windows/desktop/api/commctrl/nf-commctrl-imagelist_extracticon) 매크로 아이콘 만들기 및 정리에 대 한 자세한 내용은 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]

##  <a name="fromhandle"></a>  CImageList::FromHandle

에 대 한 포인터를 반환 합니다.는 `CImageList` 이미지 목록에 대 한 핸들을 지정 하는 경우 개체입니다.

```
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```

### <a name="parameters"></a>매개 변수

*hImageList*<br/>
이미지 목록을 지정합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CImageList` 성공 하면 NULL 개체입니다.

### <a name="remarks"></a>설명

경우는 `CImageList` 임시 핸들에 이미 연결 되지 않은 `CImageList` 개체를 만들어 연결 합니다. 이 임시 `CImageList` 개체는 임시 개체를 모두 삭제 됩니다 이때 다음에 응용 프로그램에 유휴 시간 이벤트 루프에서 될 때까지 유효 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]

##  <a name="fromhandlepermanent"></a>  CImageList::FromHandlePermanent

에 대 한 포인터를 반환 합니다.는 `CImageList` 이미지 목록에 대 한 핸들을 지정 하는 경우 개체입니다.

```
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```

### <a name="parameters"></a>매개 변수

*hImageList*<br/>
이미지 목록을 지정합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CImageList` 성공 하면 NULL 개체입니다.

### <a name="remarks"></a>설명

경우는 `CImageList` 개체가 핸들에 연결 되지 않은, NULL이 반환 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]

##  <a name="getbkcolor"></a>  CImageList::GetBkColor

이미지 목록에 대 한 현재 배경색을 검색 하려면이 함수를 호출 합니다.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>반환 값

RGB 색 값을 `CImageList` 배경 색 개체입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CImageList::SetBkColor](#setbkcolor)합니다.

##  <a name="getdragimage"></a>  CImageList::GetDragImage

끌기를 위한 사용 되는 임시 이미지 목록을 가져옵니다.

```
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,
    LPPOINT lpPointHotSpot);
```

### <a name="parameters"></a>매개 변수

*lpPoint*<br/>
주소를 [지점](/previous-versions/dd162805\(v=vs.85\)) 끌어 위치를 현재 수신 하는 구조입니다.

*lpPointHotSpot*<br/>
주소는 `POINT` 구조체 끌어서 위치를 기준으로 끌어 이미지의 오프셋입니다.

### <a name="return-value"></a>반환 값

성공 하면 임시 이미지에 대 한 포인터를 나열 하는 끌어;는 그렇지 않으면 NULL입니다.

##  <a name="getimagecount"></a>  CImageList::GetImageCount

이미지 목록의 이미지 개수를 검색 하려면이 함수를 호출 합니다.

```
int GetImageCount() const;
```

### <a name="return-value"></a>반환 값

이미지의 수입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CImageList::ExtractIcon](#extracticon)합니다.

##  <a name="getimageinfo"></a>  CImageList::GetImageInfo

이미지에 대 한 정보를 검색 하려면이 함수를 호출 합니다.

```
BOOL GetImageInfo(
    int nImage,
    IMAGEINFO* pImageInfo) const;
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
이미지의 인덱스 0부터 시작 합니다.

*pImageInfo*<br/>
에 대 한 포인터를 [IMAGEINFO](/windows/desktop/api/commctrl/ns-commctrl-_imageinfo) 이미지에 대 한 정보를 수신 하는 구조입니다. 이 구조에서 정보를 직접 이미지에 대 한 비트맵을 조작에 사용할 수 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`IMAGEINFO` 구조 이미지 목록의 이미지 정보를 포함 합니다.

##  <a name="getsafehandle"></a>  CImageList::GetSafeHandle

검색 하려면이 함수를 호출 합니다 `m_hImageList` 데이터 멤버입니다.

```
HIMAGELIST GetSafeHandle() const;
```

### <a name="return-value"></a>반환 값

첨부 된 이미지 목록에 대 한 핸들 그렇지 않은 경우 연결 된 개체가 없는 경우 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]

##  <a name="m_himagelist"></a>  CImageList::m_hImageList

이 개체에 연결 된 이미지 목록의 핸들입니다.

`HIMAGELIST m_hImageList;`

### <a name="remarks"></a>설명

`m_hImageList` 데이터 멤버는 HIMAGELIST 형식의 공용 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]

##  <a name="operator_himagelist"></a>  CImageList::operator HIMAGELIST

이 연산자를 사용 하 여 연결된 핸들을 가져오려면는 `CImageList` 개체입니다.

```
operator HIMAGELIST() const;
```

### <a name="return-value"></a>반환 값

경우 성공 이미지 목록에 핸들을 나타내는 `CImageList` 개체 고 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

이 연산자는 캐스팅 연산자를 HIMAGELIST 개체의 직접 사용을 지원 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]

##  <a name="read"></a>  CImageList::Read

보관 파일에서 이미지 목록의 읽을이 함수를 호출 합니다.

```
BOOL Read(CArchive* pArchive);
```

### <a name="parameters"></a>매개 변수

*pArchive*<br/>
에 대 한 포인터를 `CArchive` 이미지 목록의 읽을 개체입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]

##  <a name="remove"></a>  CImageList::Remove

이미지 목록 개체에서 이미지를 제거 하려면이 함수를 호출 합니다.

```
BOOL Remove(int nImage);
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
제거할 이미지의 0부터 시작 인덱스입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

다음 모든 항목 *nImage* 이제 한 단계 아래로 이동 합니다. 예를 들어 이미지 목록에 두 개의 항목이 포함 된 경우 첫 번째 항목을 삭제 하면 나머지 항목을 첫 번째 위치에 모두 포함 됩니다. *nImage*= 첫 번째 위치에서 항목의 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]

##  <a name="replace"></a>  CImageList::Replace

이미지 목록의 이미지를 새 이미지로 대체 하려면이 함수를 호출 합니다.

```
BOOL Replace(
    int nImage,
    CBitmap* pbmImage,
    CBitmap* pbmMask);

int Replace(
    int nImage,
    HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
교체 이미지의 0부터 시작 인덱스입니다.

*pbmImage*<br/>
이미지가 포함 된 비트맵에 대 한 포인터입니다.

*pbmMask*<br/>
마스크가 포함 된 비트맵에 대 한 포인터입니다. 마스크가 없습니다 이미지 목록을 사용 하 여 사용 하는 경우이 매개 변수가 무시 됩니다.

*hIcon*<br/>
비트맵 및 새 이미지에 대 한 마스크를 포함 하는 아이콘에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 반환 BOOL을 반환 하는 버전 그렇지 않으면 0입니다.

반환 되는 버전 **int** -성공할 경우 이미지의 0부터 시작 하는 인덱스를 반환 합니다. 1.

### <a name="remarks"></a>설명

이 멤버 함수를 호출한 후 호출 [SetImageCount](#setimagecount) 새에 할당 하려면 자리 표시자를 유효한 이미지 이미지 인덱스 번호입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CImageList::SetImageCount](#setimagecount)합니다.

##  <a name="setbkcolor"></a>  CImageList::SetBkColor

이미지 목록에 대 한 배경색을 설정 하려면이 함수를 호출 합니다.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>매개 변수

*cr*<br/>
배경색을 설정 합니다. CLR_NONE 수 있습니다. 이 경우 이미지 투명 하 게 마스크를 사용 하 여 그려집니다.

### <a name="return-value"></a>반환 값

성공할 경우 이전 배경색 그렇지 않으면 CLR_NONE 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]

##  <a name="setdragcursorimage"></a>  CImageList::SetDragCursorImage

현재 끌기 이미지를 사용 하 여 지정된 된 이미지 (일반적으로 마우스 커서 이미지)를 결합 하 여 새 끌기 이미지를 만듭니다.

```
BOOL SetDragCursorImage(
    int nDrag,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>매개 변수

*nDrag*<br/>
끌기 이미지와 함께 사용할 새 이미지의 인덱스입니다.

*ptHotSpot*<br/>
새 이미지 내에서 핫 스폿 위치입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

끌기 작업 중 새 이미지를 사용 하는 끌어 놓고 함수, 있으므로 Windows를 사용 해야 [ShowCursor](/windows/desktop/api/winuser/nf-winuser-showcursor) 함수를 호출한 후 실제 마우스 커서를 숨기려면 `CImageList::SetDragCursorImage`합니다. 이 고, 그렇지 시스템 끌기 작업의 기간에 대 한 두 마우스 커서를 표시할 수도 있습니다.

##  <a name="setimagecount"></a>  CImageList::SetImageCount

에 이미지 개수를 다시 설정 하려면이 멤버 함수 호출을 `CImageList` 개체입니다.

```
BOOL SetImageCount(UINT uNewCount);
```

### <a name="parameters"></a>매개 변수

*uNewCount*<br/>
이미지 목록에 새 이미지의 총 수를 지정 하는 값입니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이미지 목록의 이미지의 수를 늘리려면이 멤버 함수를 호출 하면 호출 [대체](#replace) 유효한 이미지에 새 인덱스를 할당할 추가 각 이미지에 대 한 합니다. 인덱스에 유효한 이미지 할당할 실패할 경우에 새 이미지 만들기는 그리기 작업을 예측할 수 없습니다.

이 함수를 사용 하 여 이미지 목록의 크기를 줄이는 잘린된 이미지 해제 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]

##  <a name="setoverlayimage"></a>  CImageList::SetOverlayImage

오버레이 마스크로 사용할 이미지의 목록에 이미지의 인덱스를 추가 하려면이 함수를 호출 합니다.

```
BOOL SetOverlayImage(
    int nImage,
    int nOverlay);
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
오버레이 마스크로 사용할 이미지의 0부터 시작 인덱스입니다.

*nOverlay*<br/>
오버레이 마스크의 1부터 시작 인덱스입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

목록에는 최대 4 개의 인덱스를 추가할 수 있습니다.

오버레이 마스크는 다른 이미지 위에 투명 하 게 그릴 이미지. 이미지 위에 오버레이 마스크를 사용 하 여 그리기를 [CImageList::Draw](#draw) INDEXTOOVERLAYMASK 매크로 사용 하 여 지정 된 오버레이 마스크의 1부터 시작 인덱스를 사용 하 여 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]

##  <a name="write"></a>  CImageList::Write

이미지 목록 개체를 보관 쓸이 함수를 호출 합니다.

```
BOOL Write(CArchive* pArchive);
```

### <a name="parameters"></a>매개 변수

*pArchive*<br/>
에 대 한 포인터를 `CArchive` 개체는 이미지 목록을 저장 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CListCtrl 클래스](../../mfc/reference/clistctrl-class.md)<br/>
[CTabCtrl 클래스](../../mfc/reference/ctabctrl-class.md)
