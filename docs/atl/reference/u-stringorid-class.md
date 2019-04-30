---
title: _U_STRINGorID 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
ms.openlocfilehash: 4e6c086f9d2ff4061c6404444a3b4c61dd91fe1c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197119"
---
# <a name="ustringorid-class"></a>_U_STRINGorID 클래스

이 인수 어댑터 클래스에는 리소스 이름 (LPCTSTRs) 또는 리소스 Id (UINTs) 호출자 ID MAKEINTRESOURCE 매크로 사용 하 여 문자열로 변환할 필요 없이 함수에 전달할 수 있습니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class _U_STRINGorID
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|생성자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|리소스 식별자입니다.|

## <a name="remarks"></a>설명

이 클래스는 같은 Windows 리소스 관리 API에 대 한 래퍼를 구현 하는 것에 대 한 설계 되었습니다 합니다 [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea)를 [LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona), 및 [LoadMenu](/windows/desktop/api/winuser/nf-winuser-loadmenua) 허용 하는 함수 리소스의 이름 또는 ID 수 있는 LPCTSTR 인수

클래스는 두 개의 생성자 오버 로드를 정의 합니다: 하나 LPCTSTR 인수를 받아서 다른 UINT 인수를 수락 합니다. UINT 인수 MAKEINTRESOURCE 매크로 및 클래스의 단일 데이터 멤버에 저장 된 결과 사용 하 여 Windows 리소스 관리 함수를 사용 하 여 호환 가능한 리소스 형식으로 변환할 [m_lpstr](#_u_stringorid__m_lpstr)합니다. LPCTSTR 생성자의 인수는 변환 없이 직접 저장 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="_u_stringorid__m_lpstr"></a>  _U_STRINGorID::m_lpstr

클래스는 공용 LPCTSTR 데이터 멤버와 해당 생성자 중 하나에 전달 된 값을 보유 합니다.

```
LPCTSTR m_lpstr;
```

##  <a name="_u_stringorid___u_stringorid"></a>  _U_STRINGorID::_U_STRINGorID

UINT 생성자 인수로 MAKEINTRESOURCE 매크로 사용 하 여 Windows 리소스 관리 함수를 사용 하 여 호환 되는 리소스 종류를 변환한 결과 클래스의 단일 데이터 멤버에 저장 됩니다 [m_lpstr](#_u_stringorid__m_lpstr)합니다.

```
_U_STRINGorID(UINT nID);
_U_STRINGorID(LPCTSTR lpString);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
리소스 id입니다.

*lpString*<br/>
리소스 이름입니다.

### <a name="remarks"></a>설명

LPCTSTR 생성자의 인수는 변환 없이 직접 저장 됩니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
