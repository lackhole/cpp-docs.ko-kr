---
title: CMFCDisableMenuAnimation 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
ms.openlocfilehash: bf8c598e9e105569e0a5676267e205b3d3939712
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345606"
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation 클래스

팝업 메뉴 애니메이션을 사용 하지 않도록 설정 합니다.

## <a name="syntax"></a>구문

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|`CMFCDisableMenuAnimation` 개체를 생성합니다.|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|[CMFCDisableMenuAnimation::Restore](#restore)|팝업 메뉴를 표시 하는 프레임 워크는 이전 애니메이션을 복원 합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|이름|설명|
|`CMFCDisableMenuAnimation::m_animType`|이전 팝업 메뉴 애니메이션 형식을 저장합니다.|

### <a name="remarks"></a>설명

이 도우미 클래스를 사용 하 여 일시적으로 (예: 마우스 또는 키보드 명령 처리 하는 경우) 팝업 메뉴 애니메이션을 사용 하지 않도록 설정 합니다.

`CMFCDisableMenuAnimation` 개체의 수명 동안 팝업 메뉴 애니메이션 사용 하지 않도록 설정 합니다. 생성자에서 현재 팝업 메뉴 애니메이션 형식을 저장 합니다 `m_animType` 필드 및 현재 애니메이션 형식 집합 `CMFCPopupMenu::NO_ANIMATION`합니다. 소멸자 이전 애니메이션 형식을 복원합니다.

만들 수는 `CMFCDisableMenuAnimation` 단일 함수 전체 팝업 메뉴 애니메이션을 사용 하지 않도록 설정 하기 위해 스택에서 개체입니다. 함수 간에 팝업 메뉴 애니메이션을 사용 하지 않도록 설정 하려는 경우 만들기는 `CMFCDisableMenuAnimation` 개체 힙에 대 한 다음 팝업 메뉴 애니메이션을 복원 하려는 경우 삭제 합니다.

## <a name="example"></a>예제

다음 예에서는 메뉴 애니메이션 일시적으로 사용 하지 않으려면 스택의 사용 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpopupmenu.h

##  <a name="restore"></a>  CMFCDisableMenuAnimation::Restore

팝업 메뉴를 표시 하는 프레임 워크는 이전 애니메이션을 복원 합니다.

```
void Restore ();
```

### <a name="remarks"></a>설명

이 메서드는 `CMFCDisableMenuAnimation` 소멸자는 팝업 메뉴를 표시 하는 프레임 워크는 이전 애니메이션을 복원 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md)
