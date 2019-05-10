---
title: CMFCStandardColorsPropertyPage 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- CMFCStandardColorsPropertyPage class [MFC]
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
ms.openlocfilehash: 91cfa609c31e83c02cce8b2a474a9b66ec3ba56f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388633"
---
# <a name="cmfcstandardcolorspropertypage-class"></a>CMFCStandardColorsPropertyPage 클래스

색 대화 상자에서 표준 색을 선택 하는 데 사용할 속성 페이지를 나타냅니다.

## <a name="syntax"></a>구문

```
class CMFCStandardColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|`CMFCStandardColorsPropertyPage::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCStandardColorsPropertyPage::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|

### <a name="remarks"></a>설명

`CMFCColorDialog` 클래스는 표준 색 속성 페이지를 표시 하려면이 클래스를 사용 합니다. 에 대 한 자세한 내용은 `CMFCColorDialog`를 참조 하세요 [CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxstandardcolorspropertypage.h

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CMFCCustomColorsPropertyPage 클래스](../../mfc/reference/cmfccustomcolorspropertypage-class.md)
