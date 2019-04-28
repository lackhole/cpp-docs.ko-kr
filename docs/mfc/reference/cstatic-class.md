---
title: CStatic 클래스
ms.date: 11/04/2016
f1_keywords:
- CStatic
- AFXWIN/CStatic
- AFXWIN/CStatic::CStatic
- AFXWIN/CStatic::Create
- AFXWIN/CStatic::DrawItem
- AFXWIN/CStatic::GetBitmap
- AFXWIN/CStatic::GetCursor
- AFXWIN/CStatic::GetEnhMetaFile
- AFXWIN/CStatic::GetIcon
- AFXWIN/CStatic::SetBitmap
- AFXWIN/CStatic::SetCursor
- AFXWIN/CStatic::SetEnhMetaFile
- AFXWIN/CStatic::SetIcon
helpviewer_keywords:
- CStatic [MFC], CStatic
- CStatic [MFC], Create
- CStatic [MFC], DrawItem
- CStatic [MFC], GetBitmap
- CStatic [MFC], GetCursor
- CStatic [MFC], GetEnhMetaFile
- CStatic [MFC], GetIcon
- CStatic [MFC], SetBitmap
- CStatic [MFC], SetCursor
- CStatic [MFC], SetEnhMetaFile
- CStatic [MFC], SetIcon
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
ms.openlocfilehash: 02e2f20cc568e8846923f7189da3ea45478fc289
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323871"
---
# <a name="cstatic-class"></a>CStatic 클래스

Windows 정적 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CStatic : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CStatic::CStatic](#cstatic)|`CStatic` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CStatic::Create](#create)|Windows 정적 컨트롤을 만들고에 연결 된 `CStatic` 개체입니다.|
|[CStatic::DrawItem](#drawitem)|소유자가 그린 정적 컨트롤 그리기를 재정의 합니다.|
|[CStatic::GetBitmap](#getbitmap)|이전에 사용 하 여 설정 하는 비트맵의 핸들을 검색 합니다 [SetBitmap](#setbitmap)합니다.|
|[CStatic::GetCursor](#getcursor)|커서 이미지의 핸들을 사용 하 여 이전에 설정 하는 검색 [SetCursor](#setcursor)합니다.|
|[CStatic::GetEnhMetaFile](#getenhmetafile)|이전에 설정 된 확장된 메타 파일의 핸들을 검색 [SetEnhMetaFile](#setenhmetafile)합니다.|
|[CStatic::GetIcon](#geticon)|이전에 사용 하 여 설정 아이콘의 핸들을 검색 합니다 [SetIcon](#seticon)합니다.|
|[CStatic::SetBitmap](#setbitmap)|정적 컨트롤에 표시할 비트맵을 지정 합니다.|
|[CStatic::SetCursor](#setcursor)|정적 컨트롤에 표시할 커서 이미지를 지정 합니다.|
|[CStatic::SetEnhMetaFile](#setenhmetafile)|정적 컨트롤에 표시할 확장된 메타 파일을 지정 합니다.|
|[CStatic::SetIcon](#seticon)|정적 컨트롤에 표시할 아이콘을 지정 합니다.|

## <a name="remarks"></a>설명

정적 컨트롤 텍스트 문자열, 상자, 사각형, 아이콘, 커서, 비트맵 또는 확장된 메타 파일을 표시합니다. 레이블, 상자 또는 다른 컨트롤을 별도 사용할 수 있습니다. 일반적으로 입력 하지 않고 및 출력이; 제공 정적 컨트롤 그러나 SS_NOTIFY 스타일을 사용 하 여 만들어진 경우 마우스 클릭의 부모를 알릴 수 있습니다.

2 단계를 거쳐에서 정적 컨트롤을 만듭니다. 먼저 생성 하는 생성자를 호출 합니다 `CStatic` 개체를 만든 다음 호출 합니다 [만들기](#create) 정적 컨트롤을 만들고 연결 하는 멤버 함수는 `CStatic` 개체.

만드는 경우는 `CStatic` (대화 상자 리소스의 경우)를 통해 대화 상자 내에서 개체를 `CStatic` 개체에는 사용자가 대화 상자를 닫으면 자동으로 제거 됩니다.

만드는 경우는 `CStatic` 창 내에서 개체 삭제 해야 합니다. `CStatic` 스택에 창 내에서 만든 개체는 자동으로 제거 됩니다. 만드는 경우는 `CStatic` 를 사용 하 여 힙에 있는 개체에는 **새** 를 호출 해야 함수를 **삭제** 되어 완료 되 면 제거할 개체의 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="create"></a>  CStatic::Create

Windows 정적 컨트롤을 만들고에 연결 된 `CStatic` 개체입니다.

```
virtual BOOL Create(
    LPCTSTR lpszText,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID = 0xffff);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
컨트롤에 배치할 텍스트를 지정 합니다. NULL 인 경우 텍스트가 표시 됩니다.

*dwStyle*<br/>
정적 컨트롤의 창 스타일을 지정합니다. 어떤 조합도 적용할 [정적 컨트롤 스타일](../../mfc/reference/styles-used-by-mfc.md#static-styles) 컨트롤입니다.

*rect*<br/>
정적 컨트롤의 크기와 위치를 지정합니다. 수 있습니다는 `RECT` 구조 또는 `CRect` 개체입니다.

*pParentWnd*<br/>
지정 된 `CStatic` 부모 창에 일반적으로 `CDialog` 개체입니다. NULL이 아니어야 합니다.

*nID*<br/>
정적 컨트롤의 컨트롤 ID를 지정 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CStatic` 두 단계로 개체입니다. 먼저 생성자를 호출 `CStatic`, 다음 호출 `Create`, Windows 정적 컨트롤을 만들고 연결 하는 `CStatic` 개체입니다.

다음 적용 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 정적 컨트롤에:

- WS_CHILD 항상

- WS_VISIBLE 일반적으로

- WS_DISABLED 거의

다음 중 하나를 적용 해야 정적 컨트롤에서 비트맵, 커서, 아이콘 또는 메타 파일을 표시 하려는 경우 [정적 스타일](../../mfc/reference/styles-used-by-mfc.md#static-styles):

- SS_BITMAP은 비트맵에 대 한이 스타일을 사용 합니다.

- SS_ICON 커서 및 아이콘에 대 한이 스타일을 사용 합니다.

- SS_ENHMETAFILE 향상 된 메타 파일에 대 한이 스타일을 사용 합니다.

커서, 비트맵, 아이콘에 대 한 다음 스타일을 사용할 수도 있습니다.

- 정적 컨트롤에서 이미지 가운데 SS_CENTERIMAGE 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

##  <a name="cstatic"></a>  CStatic::CStatic

`CStatic` 개체를 생성합니다.

```
CStatic();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

##  <a name="drawitem"></a>  CStatic::DrawItem

소유자가 그린 정적 컨트롤을 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
에 대 한 포인터를 [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) 구조입니다. 구조에 그릴 항목 및 필요한 그리기의 형식에 대 한 정보가 들어 있습니다.

### <a name="remarks"></a>설명

소유자가 그린 그리기를 구현 하려면이 함수를 재정의 `CStatic` (컨트롤에 스타일이 SS_OWNERDRAW) 하는 개체입니다.

##  <a name="getbitmap"></a>  CStatic::GetBitmap

사용 하 여 이전에 설정한 비트맵의 핸들을 가져옵니다 [SetBitmap](#setbitmap)되는 연결 된 `CStatic`합니다.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>반환 값

비트맵이 없습니다 설정 된 경우 NULL을 현재 비트맵 핸들입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="getcursor"></a>  CStatic::GetCursor

이전에 설정 된 커서의 핸들을 가져옵니다 [SetCursor](#setcursor)되는 연결 된 `CStatic`합니다.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>반환 값

커서가 없습니다 설정 된 경우 NULL을 현재 커서 핸들입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="getenhmetafile"></a>  CStatic::GetEnhMetaFile

이전에 설정 된 확장된 메타 파일의 핸들을 가져옵니다 [SetEnhMetafile](#setenhmetafile)되는 연결 된 `CStatic`합니다.

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>반환 값

확장된 메타 파일 없음 설정 된 경우 NULL을 현재 확장된 메타 파일 핸들입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="geticon"></a>  CStatic::GetIcon

아이콘을 사용 하 여 이전 설정의 핸들을 가져옵니다 [SetIcon](#seticon)되는 연결 된 `CStatic`합니다.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>반환 값

현재 아이콘 또는 없음 아이콘 설정 된 경우 NULL에 대 한 핸들입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

##  <a name="setbitmap"></a>  CStatic::SetBitmap

새 비트맵을 정적 컨트롤을 사용 하 여 연결합니다.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>매개 변수

*hBitmap*<br/>
정적 컨트롤에 그릴 비트맵의 핸들입니다.

### <a name="return-value"></a>반환 값

정적 컨트롤에 연결 된 비트맵이 없습니다 되었으면 NULL을 정적 컨트롤을 사용 하 여 이전에 연관 된 비트맵의 핸들입니다.

### <a name="remarks"></a>설명

비트맵을 정적 컨트롤에서 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 그려질 수 하 고 비트맵의 크기를 정적 컨트롤 크기가 조정 됩니다.

다양 한 창 및 다음을 비롯 한 정적 컨트롤 스타일을 사용할 수 있습니다.

- SS_BITMAP 비트맵에 항상이 스타일을 사용 합니다.

- 정적 컨트롤에서 이미지 가운데 SS_CENTERIMAGE 사용 합니다. 이미지는 정적 컨트롤 보다 크면 클리핑됩니다. 정적 컨트롤 보다 작은 경우 이미지 주위에 빈 공간이 비트맵의 왼쪽된 위 모퉁이에 있는 픽셀의 색으로 채워집니다.

- 클래스를 제공 하는 MFC `CBitmap`, 수행 보다 Win32 호출 보다 비트맵 이미지를 사용 하 여 작동 해야 할 경우 사용할 수 있는 `LoadBitmap`합니다. `CBitmap`협력 한 종류의 GDI 개체를 포함 하는 자주 사용 됩니다 `CStatic`에를 `CWnd` 정적 컨트롤로 그래픽 개체를 표시 하기 위해 사용 되는 클래스입니다.

`CImage` 더 많은 장치 독립적 비트맵이 DIB ()를 사용 하 여 쉽게 작업할 수 있도록 ATL/MFC 클래스가입니다. 자세한 내용은 [CImage 클래스](../../atl-mfc-shared/reference/cimage-class.md)합니다.

- 일반적인 사용법은 제공 `CStatic::SetBitmap` HBITMAP 운영자에 의해 반환 되는 GDI 개체를 `CBitmap` 또는 `CImage` 개체입니다. 이 작업을 수행 하는 코드에 다음 줄와 유사 합니다.

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```
다음 예제에서는 두 개의 `CStatic` 힙의 개체입니다. 사용 하 여 시스템 비트맵 로드 `CBitmap::LoadOEMBitmap` 사용 하 여 파일에서 다른 `CImage::Load`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="setcursor"></a>  CStatic::SetCursor

정적 컨트롤을 사용 하 여 새 커서 이미지를 연결합니다.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>매개 변수

*hCursor*<br/>
정적 컨트롤에 그릴 커서의 핸들입니다.

### <a name="return-value"></a>반환 값

이전에 커서가 없습니다 정적 컨트롤에 연결 된 경우 NULL을 정적 컨트롤을 사용 하 여 연결 된 커서의 핸들입니다.

### <a name="remarks"></a>설명

커서는 정적 컨트롤에서 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 그려질 수 하 고 커서의 크기를 정적 컨트롤 크기가 조정 됩니다.

다양 한 창 및 다음과 같은 정적 컨트롤 스타일을 사용할 수 있습니다.

- SS_ICON 커서 및 아이콘에 항상이 스타일을 사용 합니다.

- 정적 컨트롤의 가운데 SS_CENTERIMAGE 사용 합니다. 이미지는 정적 컨트롤 보다 크면 클리핑됩니다. 정적 컨트롤 보다 작은 경우 정적 컨트롤의 배경색을 사용 하 여 이미지 주위에 빈 공간이 채워집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="setenhmetafile"></a>  CStatic::SetEnhMetaFile

정적 컨트롤을 사용 하 여 새 확장된 메타 파일 이미지를 연결합니다.

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>매개 변수

*hMetaFile*<br/>
정적 컨트롤에 그릴 확장된 메타 파일의 핸들입니다.

### <a name="return-value"></a>반환 값

이전에 없는 확장된 메타 파일 정적 컨트롤에 연결 된 경우 NULL을 정적 컨트롤을 사용 하 여 연결 된 확장된 메타 파일의 핸들입니다.

### <a name="remarks"></a>설명

확장된 메타 파일 정적 컨트롤에서 자동으로 그려집니다. 확장된 메타 파일 정적 컨트롤의 크기에 맞게 크기가 조정 됩니다.

다양 한 창 및 다음과 같은 정적 컨트롤 스타일을 사용할 수 있습니다.

- 이 스타일은 항상 SS_ENHMETAFILE 사용에 대 한 메타 파일 향상.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="seticon"></a>  CStatic::SetIcon

정적 컨트롤을 사용 하 여 새 아이콘 이미지를 연결합니다.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*hIcon*<br/>
정적 컨트롤에 그릴 아이콘의 핸들입니다.

### <a name="return-value"></a>반환 값

이전에 아이콘이 없습니다 정적 컨트롤에 연결 된 경우 NULL을 정적 컨트롤을 사용 하 여 연결 된 아이콘의 핸들입니다.

### <a name="remarks"></a>설명

아이콘을 정적 컨트롤에서 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 그려질 수 하 고 정적 컨트롤 아이콘의 크기 조정 됩니다.

다양 한 창 및 다음과 같은 정적 컨트롤 스타일을 사용할 수 있습니다.

- SS_ICON 커서 및 아이콘에 항상이 스타일을 사용 합니다.

- 정적 컨트롤의 가운데 SS_CENTERIMAGE 사용 합니다. 이미지는 정적 컨트롤 보다 크면 클리핑됩니다. 정적 컨트롤 보다 작은 경우 정적 컨트롤의 배경색을 사용 하 여 이미지 주위에 빈 공간이 채워집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="see-also"></a>참고자료

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CListBox 클래스](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar 클래스](../../mfc/reference/cscrollbar-class.md)<br/>
[CDialog 클래스](../../mfc/reference/cdialog-class.md)
