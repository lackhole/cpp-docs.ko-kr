---
title: CW2CWEX 클래스
ms.date: 11/04/2016
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
ms.openlocfilehash: d1f960f8ec94b8e573490d4e708d4240b894b5ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277154"
---
# <a name="cw2cwex-class"></a>CW2CWEX 클래스

이 클래스는 문자열 변환 매크로 CW2CTEX CT2CWEX, 및 CW2W typedef에서 사용 됩니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<int t_nBufferLength = 128>
class CW2CWEX
```

#### <a name="parameters"></a>매개 변수

*t_nBufferLength*<br/>
변환 프로세스에서 사용 되는 버퍼의 크기입니다. 기본 길이 128 바이트입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CW2CWEX::CW2CWEX](#cw2cwex)|생성자입니다.|
|[CW2CWEX::~CW2CWEX](#dtor)|소멸자입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CW2CWEX::operator LPCWSTR](#operator_lpcwstr)|변환 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CW2CWEX::m_psz](#m_psz)|소스 문자열을 저장 하는 데이터 멤버입니다.|

## <a name="remarks"></a>설명

추가 기능은 필요 하지 않으면 코드에서 CW2CTEX, CT2CWEX, 또는 CW2W을 사용 합니다.

이 클래스는 루프에서 사용 하기에 안전 하 고 스택이 오버플로되지 않습니다. 기본적으로 ATL 변환 클래스 및 매크로 변환에 대 한 현재 스레드의 ANSI 코드 페이지를 사용 합니다.

다음 매크로이 클래스를 기반으로 합니다.

- CW2CTEX

- CT2CWEX

다음 typedef는이 클래스를 기반으로 합니다.

- CW2W

이러한 텍스트 변환 매크로의 논의 참조 하세요 [ATL 및 MFC 문자열 변환 매크로](string-conversion-macros.md)합니다.

## <a name="example"></a>예제

참조 [ATL 및 MFC 문자열 변환 매크로](string-conversion-macros.md) 이러한 문자열 변환 매크로 사용의 예입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlconv.h

##  <a name="cw2cwex"></a>  CW2CWEX::CW2CWEX

생성자입니다.

```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2CWEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
변환할 텍스트 문자열입니다.

*nCodePage*<br/>
코드 페이지입니다. 이 클래스에서 사용 되지 않습니다.

### <a name="remarks"></a>설명

변환 프로세스에서 사용 되는 버퍼를 할당 합니다.

##  <a name="dtor"></a>  CW2CWEX::~CW2CWEX

소멸자입니다.

```
~CW2CWEX() throw();
```

### <a name="remarks"></a>설명

할당된 된 버퍼를 해제합니다.

##  <a name="m_psz"></a>  CW2CWEX::m_psz

소스 문자열을 저장 하는 데이터 멤버입니다.

```
LPCWSTR m_psz;
```

##  <a name="operator_lpcwstr"></a>  CW2CWEX::operator LPCWSTR

변환 연산자입니다.

```
operator LPCWSTR() const throw();
```

### <a name="return-value"></a>반환 값

LPCWSTR 입력할 텍스트 문자열을 반환 합니다.

## <a name="see-also"></a>참고자료

[CA2AEX 클래스](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX 클래스](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX 클래스](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX 클래스](../../atl/reference/cw2aex-class.md)<br/>
[CW2WEX 클래스](../../atl/reference/cw2wex-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
