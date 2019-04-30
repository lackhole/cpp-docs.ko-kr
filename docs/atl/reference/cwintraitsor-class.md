---
title: CWinTraitsOR 클래스
ms.date: 11/04/2016
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
ms.openlocfilehash: ec628fcde40d3cc4601d6b6ddf49fa5599ac5a86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276733"
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR 클래스

이 클래스는 창 개체를 만들 때 사용 되는 스타일을 표준화 하는 방법을 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0,
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```

#### <a name="parameters"></a>매개 변수

*t_dwStyle*<br/>
기본 창 스타일입니다.

*t_dwExStyle*<br/>
기본 확장된 창 스타일입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|에 대 한 확장된 스타일을 검색 합니다 `CWinTraitsOR` 개체입니다.|
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|표준 스타일을 검색 합니다 `CWinTraitsOR` 개체입니다.|

## <a name="remarks"></a>설명

이렇게 [창 특성](../../atl/understanding-window-traits.md) 클래스는 ATL 창 개체 만들기에 사용 되는 스타일을 표준화 하는 간단한 방법을 제공 합니다. 이 클래스의 특수화를 사용 하 여 템플릿 매개 변수로 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 또는 다른 ATL의 창 클래스에 사용 되는 표준 및 확장 된 스타일의 최소 집합을 지정 하는 창 클래스의 인스턴스.

특정 스타일 설정 되어 있는지 확인 창 클래스의 모든 인스턴스에 대 한 다른 스타일을 허용 하는 동안에 대 한 호출에서 인스턴스별 기준 설정 하려는 경우이 템플릿의 특수화를 사용 하 여 [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)합니다.

기본 창 스타일 없음 다른 스타일에 대 한 호출에 지정 된 경우에 사용할 수 있도록 하려는 경우 `CWindowImpl::Create`를 사용 하 여 [CWinTraits](../../atl/reference/cwintraits-class.md) 대신 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="getwndstyle"></a>  CWinTraitsOR::GetWndStyle

표준 스타일의 조합 (논리적 OR 연산자 사용)를 검색 하려면이 함수를 호출 합니다 `CWinTraits` 개체와 지정 된 기본 스타일 *t_dwStyle*합니다.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
창의 생성에 사용 되는 스타일입니다.

### <a name="return-value"></a>반환 값

에 전달 되는 스타일의 조합을 *dwStyle* 하 여 지정 된 기본 `t_dwStyle`, 논리적 OR 연산자를 사용 합니다.

##  <a name="getwndexstyle"></a>  CWinTraitsOR::GetWndExStyle

확장 된 스타일의 조합 (논리적 OR 연산자 사용)를 검색 하려면이 함수를 호출 합니다 `CWinTraits` 개체와 지정 된 기본 스타일 `t_dwStyle`합니다.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
확장된 스타일 창 만들기에 사용 합니다.

### <a name="return-value"></a>반환 값

에 전달 되는 확장 된 스타일의 조합을 *dwExStyle* 하 여 지정 된 기본 `t_dwExStyle`, 논리 OR 연산자를 사용 하 여

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[창 특성 이해](../../atl/understanding-window-traits.md)
