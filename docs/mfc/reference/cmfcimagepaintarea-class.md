---
title: CMFCImagePaintArea 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
ms.openlocfilehash: 37d975ace4d144cc6274b49a3406382f0fb300ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374183"
---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea 클래스

이미지 편집기 대화 상자에서 이미지를 수정 하는 데 사용할 수 있는 그림 영역을 제공 합니다.

## <a name="syntax"></a>구문

```
class CMFCImagePaintArea : public CButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|`CMFCImagePaintArea` 개체를 생성합니다.|
|`CMFCImagePaintArea::~CMFCImagePaintArea`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|[CMFCImagePaintArea::GetMode](#getmode)|현재 그리기 모드를 검색합니다.|
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|그림 영역에 대 한 비트맵 이미지를 설정합니다.|
|[CMFCImagePaintArea::SetColor](#setcolor)|현재 그리기 색을 설정합니다.|
|[CMFCImagePaintArea::SetMode](#setmode)|현재 그리기 모드를 설정합니다.|

### <a name="remarks"></a>설명

이 클래스는 코드에서 직접 사용할 수 없습니다.

프레임 워크는 이미지 편집기 대화 상자에서 그림 영역을 표시 하려면이 클래스를 사용 합니다. 이미지 편집기 대화 상자에 대 한 자세한 내용은 참조 하세요. [CMFCImageEditorDialog 클래스](../../mfc/reference/cmfcimageeditordialog-class.md)합니다.

## <a name="example"></a>예제

다음 예제에서는의 개체를 생성 하는 방법에 설명 합니다 `CMFCImagePaintArea` 클래스에서 현재 색을 그리는 현재 그리기 모드를 설정 하 고 그림 영역에 대 한 비트맵 이미지를 설정 합니다.

[!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afximagepaintarea.h

##  <a name="cmfcimagepaintarea"></a>  CMFCImagePaintArea::CMFCImagePaintArea

`CMFCImagePaintArea` 개체를 생성합니다.

```
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pParentDlg*|[in] 이미지 편집기의 부모인 대화 상자에 대 한 포인터입니다.|

##  <a name="getmode"></a>  CMFCImagePaintArea::GetMode

현재 그리기 모드를 검색합니다.

```
IMAGE_EDIT_MODE GetMode() const;
```

### <a name="return-value"></a>반환 값

[IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) 현재 그리기 모드를 지정 하는 값입니다.

##  <a name="setbitmap"></a>  CMFCImagePaintArea::SetBitmap

그림 영역에 대 한 비트맵 이미지를 설정합니다.

```
void SetBitmap(CBitmap* pBitmap);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pBitmap*|[in] 표시할 새 비트맵 이미지를 지정 합니다.|

### <a name="remarks"></a>설명

하는 경우 *pBitmap* 가 null 인 경우이 메서드는 수정할 수 있는 그리기 영역의 크기를 0으로 설정 합니다. 이 고, 그렇지 제공 된 비트맵 이미지의 크기를 수정할 수 있는 그리기 영역의 크기를 설정합니다.

##  <a name="setcolor"></a>  CMFCImagePaintArea::SetColor

현재 그리기 색을 설정합니다.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*color*|[in] 새 그리기 색입니다.|

### <a name="remarks"></a>설명

때 이미지 편집기 팔레트 막대에서 색을 선택 하거나 색 편집기 프레임 워크는 현재 그리기 색을 업데이트 하려면이 메서드를 호출 합니다. 초기 그리기 색이 검정색 (0 COLORREF 값).

그리기 색 IMAGE_EDIT_MODE_COLOR 제외 하 고 모든 그리기 모드에 대 한 이미지 편집기 대화 상자에서 사용 됩니다. 그리기 모드에 대 한 자세한 내용은 참조 하세요. [cmfcimagepaintarea:: Image_edit_mode 열거형](cmfcimagepaintarea-image-edit-mode-enumeration.md)합니다.

##  <a name="setmode"></a>  CMFCImagePaintArea::SetMode

현재 그리기 모드를 설정합니다.

```
void SetMode(IMAGE_EDIT_MODE mode);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*모드*|[in] [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) 현재 그리기 모드를 지정 하는 값입니다.|

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorDialog 클래스](../../mfc/reference/cmfcimageeditordialog-class.md)
