---
title: CMFCSpinButtonCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
ms.openlocfilehash: 60808359c11604368493031e1b6f4573b3b2026f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410102"
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl 클래스

`CMFCSpinButtonCtrl` 클래스 스핀 단추 컨트롤을 그리는 비주얼 관리자를 지원 합니다.

## <a name="syntax"></a>구문

```
class CMFCSpinButtonCtrl : public CSpinButtonCtrl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|기본 생성자입니다.|
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|현재 스핀 단추 컨트롤을 다시 그립니다.|

## <a name="remarks"></a>설명

응용 프로그램에서 스핀 단추 컨트롤을 그릴 비주얼 관리자를 사용 하려면 모든 인스턴스를 대체 합니다 `CSpinButtonCtrl` 클래스는 `CMFCSpinButtonCtrl` 클래스입니다.

## <a name="example"></a>예제

다음 예제에는 개체를 만드는 방법을 보여 줍니다 합니다 `CMFCSpinButtonCtrl` 클래스 및 사용 하 여 해당 `Create` 메서드.

[!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)

[CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxspinbuttonctrl.h

##  <a name="ondraw"></a>  CMFCSpinButtonCtrl::OnDraw

현재 스핀 단추 컨트롤을 다시 그립니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

프레임 워크 호출을 `CMFCSpinButtonCtrl::OnPaint` 처리 하는 메서드를 [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) 메시지 및 메서드가 다시 호출 하는이 `CMFCSpinButtonCtrl::OnDraw` 메서드. 프레임 워크 spin button 컨트롤을 그리는 방법을 사용자 지정 하려면이 메서드를 재정의 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager 클래스](../../mfc/reference/cmfcvisualmanager-class.md)
