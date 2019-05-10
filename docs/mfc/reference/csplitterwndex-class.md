---
title: CSplitterWndEx 클래스
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: 8dedad4e99a37b13dc618859c8e6d8a83a65ea76
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339609"
---
# <a name="csplitterwndex-class"></a>CSplitterWndEx 클래스

사용자 지정된 분할자 창을 나타냅니다.

## <a name="syntax"></a>구문

```
class CSplitterWndEx : public CSplitterWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CSplitterWndEx::CSplitterWndEx`|기본 생성자입니다.|
|`CSplitterWndEx::~CSplitterWndEx`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|분할기 창 그리기 위해 프레임 워크에서 호출 됩니다. (재정의 [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|

## <a name="remarks"></a>설명

재정의 `OnDrawSplitter` 분할자 창 그래픽 구성 요소의 모양을 사용자 지정 하는 방법입니다.

`CSplitterWndEx` 클래스와 함께 사용 되는 [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox), 및 [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) 메서드를 시각화 관리자에서 구현 합니다. 응용 프로그램에서 창에 그릴 비주얼 관리자 시킬의 선언을 대체할 합니다 `CSplitterWnd` 클래스를 `CSplitterWndEx` 클래스. 프레임 창 응용 프로그램에 대 한 분할 창 클래스 mainfrm.h에 위치한 CMainFrame 클래스에 선언 됩니다. 예를 들어 참조 된 `OutlookDemo` 샘플 디렉터리에 샘플.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

[CSplitterWnd](csplitterwnd-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxsplitterwndex.h

##  <a name="ondrawsplitter"></a>  CSplitterWndEx::OnDrawSplitter

분할기 창 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다. 이 매개 변수가 NULL 인 경우 활성 창 프레임 워크를 다시 그립니다.

*nType*<br/>
[in] 중 하나는 `CSplitterWnd::ESplitType` 그릴 분할자 창 요소를 지정 하는 열거형 값입니다. 유효한 값은 `splitBox`, `splitBar`, `splitIntersection` 및 `splitBorder`입니다.

*rect*<br/>
[in] 크기와 지정 된 분할자 창 요소를 그릴 위치를 지정 하는 경계 사각형입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../hierarchy-chart.md)<br/>
[클래스](mfc-classes.md)<br/>
[CSplitterWnd 클래스](csplitterwnd-class.md)<br/>
[CMFCVisualManager 클래스](cmfcvisualmanager-class.md)
