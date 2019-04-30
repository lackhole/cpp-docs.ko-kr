---
title: CWinTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
ms.openlocfilehash: 840433ffb325a4f181848371306607b62373e75a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276785"
---
# <a name="cwintraits-class"></a>CWinTraits 클래스

이 클래스는 창 개체를 만들 때 사용 되는 스타일을 표준화 하는 방법을 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```

#### <a name="parameters"></a>매개 변수

*t_dwStyle*<br/>
기본 표준 창 스타일입니다.

*t_dwExStyle*<br/>
기본 확장된 창 스타일입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(정적) 에 대 한 확장된 스타일을 검색 합니다 `CWinTraits` 개체입니다.|
|[CWinTraits::GetWndStyle](#getwndstyle)|(정적) 표준 스타일을 검색 합니다 `CWinTraits` 개체입니다.|

## <a name="remarks"></a>설명

이렇게 [창 특성](../../atl/understanding-window-traits.md) 클래스는 ATL 창 개체 만들기에 사용 되는 스타일을 표준화 하는 간단한 방법을 제공 합니다. 이 클래스의 특수화를 사용 하 여 템플릿 매개 변수로 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 또는 다른 ATL의 창 클래스에 사용 된 기본 표준 및 확장 스타일을 지정 하는 창 클래스의 인스턴스.

기본 창 스타일 없음 다른 스타일에 대 한 호출에 지정 된 경우에 사용할 수 있도록 하려는 경우이 템플릿을 사용 하 여 [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)합니다.

ATL 창 스타일의 자주 사용 되는 조합에 대 한이 서식 파일의 세 가지 미리 정의 된 특수화를 제공합니다.

- `CControlWinTraits`

   표준 컨트롤 창을 위한 것입니다. 다음과 같은 표준 스타일 사용 됩니다. WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN, 및 WS_CLIPSIBLINGS 합니다. 확장 된 스타일이 없는 경우

- `CFrameWinTraits`

   표준 프레임 창을 위한 것입니다. 사용 하는 표준 스타일은 다음과 같습니다. WS_OVERLAPPEDWINDOW WS_CLIPCHILDREN, 하며 WS_CLIPSIBLINGS 합니다. 사용 된 확장된 스타일은 다음과 같습니다. WS_EX_APPWINDOW 및 WS_EX_WINDOWEDGE 합니다.

- `CMDIChildWinTraits`

   표준 MDI 자식 창을 위한 것입니다. 사용 하는 표준 스타일은 다음과 같습니다. WS_OVERLAPPEDWINDOW, WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN, 및 WS_CLIPSIBLINGS 합니다. 사용 된 확장된 스타일은 다음과 같습니다. WS_EX_MDICHILD.

인스턴스별 별로 설정할 다른 스타일을 허용 하는 창 클래스의 모든 인스턴스 사용에 대 한 특정 스타일 설정 되어 있는지 확인 하려는 경우 [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) 대신 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="getwndstyle"></a>  CWinTraits::GetWndStyle

표준 스타일을 검색 하려면이 함수를 호출 합니다 `CWinTraits` 개체입니다.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
창 만드는 데는 표준 스타일입니다. 하는 경우 *dwStyle* 가 0 이면 템플릿 스타일 값 (`t_dwStyle`)이 반환 됩니다. 하는 경우 *dwStyle* 는 0이 아니면 *dwStyle* 반환 됩니다.

### <a name="return-value"></a>반환 값

개체의 표준 창 스타일입니다.

##  <a name="getwndexstyle"></a>  CWinTraits::GetWndExStyle

확장된 스타일을 검색 하려면이 함수를 호출 합니다 `CWinTraits` 개체입니다.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
확장된 스타일 창 만들기에 사용 합니다. 하는 경우 *dwExStyle* 가 0 이면 템플릿 스타일 값 (`t_dwExStyle`)이 반환 됩니다. 하는 경우 *dwExStyle* 는 0이 아니면 *dwExStyle* 반환 됩니다.

### <a name="return-value"></a>반환 값

개체의 확장된 창 스타일입니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[창 특성 이해](../../atl/understanding-window-traits.md)
