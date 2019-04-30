---
title: CMFCDragFrameImpl 클래스
ms.date: 10/18/2018
f1_keywords:
- CMFCDragFrameImpl
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
ms.openlocfilehash: 05b4426da6bee0443a407cff583f47bee60262e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348616"
---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpl 클래스

`CMFCDragFrameImpl` 클래스 사용자가 표준 도킹 모드에서 창을 끌 때 나타나는 끌기 사각형을 그립니다.
더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

## <a name="syntax"></a>구문

```
class CMFCDragFrameImpl
```

## <a name="remarks"></a>설명

이 클래스의 개체는 각각에 포함 된 [CPane 클래스](../../mfc/reference/cpane-class.md) 개체입니다. 사용 하는 각 창에 따라서는 `CanFloat` 메서드는 사용자가이 끌 때 끌기 사각형을 표시 합니다.

사용 하 여 끌기 사각형의 두께 제어할 수 있습니다 [afx_global_data:: m_ndragframethicknessfloat](afx-global-data-structure.md#m_ndragframethicknessfloat) 하 고 [afx_global_data:: m_ndragframethicknessdock](afx-global-data-structure.md#m_ndragframethicknessdock)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxdragframeimpl.h

##  <a name="enddrawdragframe"></a>  CMFCDragFrameImpl::EndDrawDragFrame

```
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```

### <a name="parameters"></a>매개 변수

[in] *bClearInternalRects*<br/>

### <a name="remarks"></a>설명

##  <a name="init"></a>  CMFCDragFrameImpl::Init

```
void Init(CWnd* pDraggedWnd);
```

### <a name="parameters"></a>매개 변수

[in] *pDraggedWnd*<br/>

### <a name="remarks"></a>설명

##  <a name="movedragframe"></a>  CMFCDragFrameImpl::MoveDragFrame

```
void MoveDragFrame(BOOL bForceMove = FALSE);
```

### <a name="parameters"></a>매개 변수

[in] *bForceMove*<br/>

### <a name="remarks"></a>설명

##  <a name="placetabpredocking"></a>  CMFCDragFrameImpl::PlaceTabPreDocking

```
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,
    BOOL bFirstTime);

void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```

### <a name="parameters"></a>매개 변수

[in] *pTabbedBar*<br/>

[in] *bFirstTime*<br/>

[in] *pCBarToPlaceOn*<br/>

### <a name="remarks"></a>설명

##  <a name="removetabpredocking"></a>  CMFCDragFrameImpl::RemoveTabPreDocking

```
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```

### <a name="parameters"></a>매개 변수

[in] *pOldTargetBar*<br/>

### <a name="remarks"></a>설명

##  <a name="resetstate"></a>  CMFCDragFrameImpl::ResetState

```
void ResetState();
```

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CPane Class](../../mfc/reference/cpane-class.md)
