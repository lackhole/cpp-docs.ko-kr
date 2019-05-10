---
title: CMFCImageEditorPaletteBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::GetRowHeight
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable
helpviewer_keywords:
- CMFCImageEditorPaletteBar [MFC], GetRowHeight
- CMFCImageEditorPaletteBar [MFC], IsButtonExtraSizeAvailable
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
ms.openlocfilehash: 6812f3f425186484ef892d7f5c626c0dfce0f863
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378104"
---
# <a name="cmfcimageeditorpalettebar-class"></a>CMFCImageEditorPaletteBar 클래스

이미지 편집기 대화 상자에 색상표 모음 기능을 제공 합니다.

## <a name="syntax"></a>구문

```
class CMFCImageEditorPaletteBar : public CMFCToolBar
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|[CMFCImageEditorPaletteBar::GetRowHeight](#getrowheight)|도구 모음 단추의 높이 반환합니다. (재정의 [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|도구 모음 테두리 확장 하는 단추를 표시할 수 있는지 여부를 결정 합니다. (재정의 [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|

### <a name="remarks"></a>설명

이 클래스는 코드에서 직접 사용할 수 없습니다.

프레임 워크는이 클래스를 사용 하 여 이미지 편집기 대화 상자에 색상표 막대를 표시 합니다. 이미지 편집기 대화 상자에 대 한 자세한 내용은 참조 하세요. [CMFCImageEditorDialog 클래스](../../mfc/reference/cmfcimageeditordialog-class.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afximageeditordialog.h

##  <a name="getrowheight"></a>  CMFCImageEditorPaletteBar::GetRowHeight

도구 모음 단추의 높이 반환합니다.

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>반환 값

도구 모음에서 각 단추의 높이입니다.

##  <a name="isbuttonextrasizeavailable"></a>  CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable

도구 모음 테두리 확장 하는 단추를 표시할 수 있는지 여부를 결정 합니다.

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>반환 값

이 메서드는 FALSE를 반환합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorDialog 클래스](../../mfc/reference/cmfcimageeditordialog-class.md)
