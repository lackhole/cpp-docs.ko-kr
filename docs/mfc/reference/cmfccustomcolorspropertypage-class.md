---
title: CMFCCustomColorsPropertyPage 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
ms.openlocfilehash: b28711991835dd14929e5387709046c3867c715e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403700"
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage 클래스

색 대화 상자에서 사용자 지정 색을 선택할 수 있는 속성 페이지를 나타냅니다.

## <a name="syntax"></a>구문

```
class CMFCCustomColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|`CMFCCustomColorsPropertyPage::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCCustomColorsPropertyPage::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|[CMFCCustomColorsPropertyPage::Setup](#setup)|속성 페이지의 색 구성 요소를 설정합니다.|

### <a name="remarks"></a>설명

`CMFCColorDialog` 클래스는 사용자 지정 색 속성 페이지를 표시 하려면이 클래스를 사용 합니다. 에 대 한 자세한 내용은 `CMFCColorDialog`를 참조 하세요 [CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 생성 하는 방법에 설명 된 `CMFCCustomColorsPropertyPage` 개체 및 속성 페이지의 색 구성 요소를 설정 합니다.

[!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxcustomcolorspropertypage.h

##  <a name="setup"></a>  CMFCCustomColorsPropertyPage::Setup

속성 페이지의 색 구성 요소를 설정합니다.

```
void Setup(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*R*|[in] RGB 값의 빨강 구성 요소입니다.|
|*G*|[in] RGB 값의 녹색 구성 요소입니다.|
|*B*|[in] RGB 값의 파랑 구성 요소입니다.|

### <a name="remarks"></a>설명

이 메서드는 현재 RGB 및 연결된 된 HLS (hue, 밝기 및 채도) 색 값의 속성 페이지를 업데이트합니다. 합니다 [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) 메서드는 프레임 워크 색 대화 상자를 초기화 하거나 사용자가 마우스 왼쪽된 단추를 누를 때이 메서드를 호출 합니다. 에 대 한 자세한 내용은 `CMFCColorDialog`를 참조 하세요 [CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md)합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CMFCStandardColorsPropertyPage 클래스](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
