---
title: CMFCDesktopAlertWndButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
helpviewer_keywords:
- CMFCDesktopAlertWndButton [MFC], IsCaptionButton
- CMFCDesktopAlertWndButton [MFC], IsCloseButton
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
ms.openlocfilehash: 639342e0a09a6e970478fce1b5aac629f03c2015
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776949"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton 클래스

단추를 바탕 화면 경고 대화 상자에 추가할 수 있습니다.

## <a name="syntax"></a>구문

```
class CMFCDesktopAlertWndButton : public CMFCButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|기본 생성자입니다.|
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|경고 대화 상자 캡션 영역에는 단추가 표시 되는지 여부를 결정 합니다.|
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|단추 경고 대화 상자를 닫고 있는지 여부를 결정 합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|이름|설명|
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|경고 대화 상자 캡션 영역에는 단추가 표시 되는지 여부를 지정 하는 부울 값입니다.|
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|단추 경고 대화 상자를 닫고 있는지 여부를 지정 하는 부울 값입니다.|

### <a name="remarks"></a>설명

생성자는 기본적으로 설정 합니다 `m_bIsCaptionButton` 및 `m_bIsCloseButton` FALSE로 데이터 멤버입니다. 부모 `CMFCDesktopAlertDialog` 개체 집합이 `m_bIsCaptionButton` 단추 경고 대화 상자 캡션 영역에 배치 하는 경우 TRUE로 합니다. `CMFCDesktopAlertDialog` 클래스를 만들고는 `CMFCDesktopAlertWndButton` 역할을 경고 대화 상자를 닫습니다는 단추가 상자를 설정 하는 개체 `m_bIsCloseButton` TRUE로 합니다.

추가 `CMFCDesktopAlertWndButton` 개체는 `CMFCDesktopAlertDialog` 단추를 추가 하는 개체입니다. 에 대 한 자세한 내용은 `CMFCDesktopAlertDialog`를 참조 하세요 [CMFCDesktopAlertDialog 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 사용 하는 방법에 설명 합니다 `SetImage` 의 메서드는 `CMFCDesktopAlertWndButton` 클래스입니다. 이 코드 조각은의 일부인 합니다 [바탕 화면 경고 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxdesktopalertwnd.h

##  <a name="iscaptionbutton"></a>  CMFCDesktopAlertWndButton::IsCaptionButton

경고 대화 상자 캡션 영역에는 단추가 표시 되는지 여부를 결정 합니다.

```
BOOL IsCaptionButton() const;
```

### <a name="return-value"></a>반환 값

단추는 경고 대화 상자 캡션 영역에 표시 되 면 0이 아닌 값 그렇지 않을 경우 0입니다.

##  <a name="isclosebutton"></a>  CMFCDesktopAlertWndButton::IsCloseButton

단추 경고 대화 상자를 닫고 있는지 여부를 결정 합니다.

```
BOOL IsCloseButton() const;
```

### <a name="return-value"></a>반환 값

단추는 경고 대화 상자를 닫으면 0이 아닌 값 그렇지 않을 경우 0입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertDialog 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)
