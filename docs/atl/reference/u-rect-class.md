---
title: _U_RECT 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
ms.openlocfilehash: 306092a00a1e119263f4563eea181d7d3ee2b4b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274527"
---
# <a name="urect-class"></a>_U_RECT 클래스

이 인수 어댑터 클래스를 사용 하거나 `RECT` 포인터 또는 참조 포인터 측면에서 구현 되는 함수에 전달할 수 있습니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class _U_RECT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[_U_RECT::_U_RECT](#_u_rect___u_rect)|생성자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[_U_RECT::m_lpRect](#_u_rect__m_lprect)|에 대 한 포인터를 `RECT`입니다.|

## <a name="remarks"></a>설명

두 개의 생성자 오버 로드를 정의 하는 클래스: 습관이 **RECT &** 인수와 다른 허용는 `LPRECT` 인수입니다. 클래스의 단일 데이터 멤버에 대 한 참조 인수 주소를 저장 하는 첫 번째 생성자는 [m_lpRect](#_u_rect__m_lprect)합니다. 포인터 생성자의 인수는 변환 없이 직접 저장 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="_u_rect__m_lprect"></a>  _U_RECT::m_lpRect

클래스를 공용 생성자 중 하나에 전달 된 값을 보유 `LPRECT` 데이터 멤버입니다.

```
LPRECT m_lpRect;
```

##  <a name="_u_rect___u_rect"></a>  _U_RECT::_U_RECT

참조 인수 주소 클래스의 단일 데이터 멤버에 저장 됩니다 [m_lpRect](#_u_rect__m_lprect)합니다.

```
_U_RECT(RECT& rc);
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*rc*<br/>
`RECT` 참조 합니다.

*lpRect*<br/>
`RECT` 포인터입니다.

### <a name="remarks"></a>설명

포인터 생성자의 인수는 변환 없이 직접 저장 됩니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
