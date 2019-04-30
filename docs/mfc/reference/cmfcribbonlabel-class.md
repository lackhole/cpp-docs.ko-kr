---
title: CMFCRibbonLabel 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
ms.openlocfilehash: b79d6191d2deb0a295e81da1150cc7b38fd81232
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388412"
---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel 클래스

리본에 대해 클릭할 수 없는 텍스트 레이블을 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|생성 하 고 초기화를 `CMFCRibbonLabel` 지정된 된 텍스트 문자열을 사용 하 여 개체입니다.|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCRibbonLabel::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|[CMFCRibbonLabel::SetACCData](#setaccdata)|현재 리본 label 요소에 대 한 내게 필요한 옵션 데이터를 결정합니다. (재정의 [cmfcribbonbutton:: Setaccdata](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

### <a name="remarks"></a>설명

리본 레이블입니다를 만든 후 추가 패널에 호출한 [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)합니다.

빠른 실행 도구 모음 리본 레이블을 추가할 수 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonLabel.h

##  <a name="cmfcribbonlabel"></a>  CMFCRibbonLabel::CMFCRibbonLabel

생성 하 고 초기화 된 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) 지정된 된 텍스트 문자열을 표시 하는 개체입니다.

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
[in] 레이블에 표시할 텍스트입니다.

*bIsMultiLine*<br/>
[in] TRUE 레이블 여러 줄 레이블을; 임을 지정 하려면 그렇지 않으면 FALSE입니다.

##  <a name="setaccdata"></a>  CMFCRibbonLabel::SetACCData

현재 리본 label 요소에 대 한 내게 필요한 옵션 데이터를 결정합니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
[in] 현재 리본 레이블의 부모 창을 나타냅니다.

*data*<br/>
[out] 형식의 개체 `CAccessibilityData` 현재 리본 레이블의 내게 필요한 옵션 데이터는 채워집니다.

### <a name="return-value"></a>반환 값

TRUE 이면 합니다 *데이터* FALSE 매개 변수를 성공적으로 현재 리본 레이블의 내게 필요한 옵션 데이터를 사용 하 여 채워진 고, 그렇지 않으면입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton 클래스](../../mfc/reference/cmfcribbonbutton-class.md)
