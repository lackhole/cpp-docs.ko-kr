---
title: CMFCRibbonContextCaption 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
ms.openlocfilehash: 26cc509db55bc95688123a7c6e673dcfc87c975b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237327"
---
# <a name="cmfcribboncontextcaption-class"></a>CMFCRibbonContextCaption 클래스

리본 범주 맨 위 또는 컨텍스트 범주에 나타나는 색 지정된 캡션을 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonContextCaption : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|`CMFCRibbonContextCaption::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFCRibbonContextCaption::GetColor](#getcolor)|캡션 색을 반환합니다.|
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||
|`CMFCRibbonContextCaption::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|

## <a name="remarks"></a>설명

이 클래스는 직접 인스턴스화할 수 없습니다. 합니다 [CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md) 클래스를 사용 하 여이 클래스 내부적으로 리본 범주에 색을 추가 합니다.

리본 범주에 대 한 색을 설정 하려면 호출 [cmfcribboncategory:: Settabcolor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)합니다. 컨텍스트 범주에 대 한 색을 설정 하려면 호출 [cmfcribbonbar:: Addcontextcategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonBar.h

##  <a name="getcolor"></a>  CMFCRibbonContextCaption::GetColor

캡션의 배경색을 반환합니다.

```
AFX_RibbonCategoryColor GetColor() const;
```

### <a name="return-value"></a>반환 값

반환된 된 값은 다음 열거형된 값 중 하나일 수 있습니다.

- `AFX_CategoryColor_None`

- `AFX_CategoryColor_Red`

- `AFX_CategoryColor_Orange`

- `AFX_CategoryColor_Yellow`

- `AFX_CategoryColor_Green`

- `AFX_CategoryColor_Blue`

- `AFX_CategoryColor_Indigo`

- `AFX_CategoryColor_Violet`

### <a name="remarks"></a>설명

캡션 색을 호출 하 여 설정할 수 있습니다 [cmfcribboncategory:: Settabcolor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) 하거나 [cmfcribbonbar:: Addcontextcategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)합니다.

##  <a name="getrighttabx"></a>  CMFCRibbonContextCaption::GetRightTabX

범주 리본 탭의 오른쪽 가장자리의 위치를 검색합니다.

```
int GetRightTabX() const;
```

### <a name="return-value"></a>반환 값

둘러싸는 사각형의 오른쪽 X 값을 반환 합니다 `CMFCRibbonCategory` 개체의 리본 탭 또는 탭 잘린 경우-1 값입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton 클래스](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonCategory 클래스](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md)
