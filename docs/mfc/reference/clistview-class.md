---
title: CListView 클래스
ms.date: 11/04/2016
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
ms.openlocfilehash: 698e37b2853a2ca3698ee0a426c8ded688c99c58
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58776624"
---
# <a name="clistview-class"></a>CListView 클래스

및 목록 컨트롤의 사용을 간소화 [CListCtrl](../../mfc/reference/clistctrl-class.md), MFC의 문서 뷰 아키텍처를 사용 하 여 목록 컨트롤 기능을 캡슐화 하는 클래스입니다.

## <a name="syntax"></a>구문

```
class CListView : public CCtrlView
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CListView::CListView](#clistview)|`CListView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CListView::GetListCtrl](#getlistctrl)|뷰와 연결 된 목록 컨트롤을 반환 합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CListView::RemoveImageList](#removeimagelist)|목록 보기에서 지정 된 이미지 목록을 제거합니다.|

## <a name="remarks"></a>설명

이 아키텍처에 대 한 자세한 내용은 참조에 대 한 개요는 [CView](../../mfc/reference/cview-class.md) 클래스 및 있습니다 언급 상호 참조 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>요구 사항

**헤더:** afxcview.h

##  <a name="clistview"></a>  CListView::CListView

`CListView` 개체를 생성합니다.

```
CListView();
```

##  <a name="getlistctrl"></a>  CListView::GetListCtrl

뷰와 연결 된 목록 컨트롤에 대 한 참조를 가져오려면이 함수를 호출 합니다.

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>반환 값

뷰와 연결 된 목록 컨트롤에 대 한 참조입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

##  <a name="removeimagelist"></a>  CListView::RemoveImageList

목록 보기에서 지정 된 이미지 목록을 제거합니다.

```
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>매개 변수

*nImageList*<br/>
제거할 이미지의 0부터 시작 하는 인덱스입니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 ROWLIST](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)
