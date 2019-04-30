---
title: CA2CAEX 클래스
ms.date: 11/04/2016
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
ms.openlocfilehash: 88389d4fe913a31fce43e3c8cc95605f99701695
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261197"
---
# <a name="ca2caex-class"></a>CA2CAEX 클래스

이 클래스는 문자열 변환 매크로 CA2CTEX CT2CAEX, 및 CA2CA typedef에서 사용 됩니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<int t_nBufferLength = 128>
class CA2CAEX
```

#### <a name="parameters"></a>매개 변수

*t_nBufferLength*<br/>
변환 프로세스에서 사용 되는 버퍼의 크기입니다. 기본 길이 128 바이트입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CA2CAEX::CA2CAEX](#ca2caex)|생성자입니다.|
|[CA2CAEX::~CA2CAEX](#dtor)|소멸자입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CA2CAEX::operator LPCSTR](#operator_lpcstr)|변환 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CA2CAEX::m_psz](#m_psz)|소스 문자열을 저장 하는 데이터 멤버입니다.|

## <a name="remarks"></a>설명

추가 기능이 필요한 경우가 아니면 사용자 고유의 코드에서 CA2CTEX, CT2CAEX, 또는 CA2CA을 사용 합니다.

이 클래스는 루프에서 사용 하기에 안전 하 고 스택이 오버플로되지 않습니다. 기본적으로 ATL 변환 클래스와 매크로는 현재 스레드의 ANSI 코드 페이지를 변환에 사용합니다.

다음 매크로이 클래스를 기반으로 합니다.

- CA2CTEX

- CT2CAEX

다음 typedef는이 클래스를 기반으로 합니다.

- CA2CA

이러한 텍스트 변환 매크로의 논의 참조 하세요 [ATL 및 MFC 문자열 변환 매크로](string-conversion-macros.md)합니다.

## <a name="example"></a>예제

참조 [ATL 및 MFC 문자열 변환 매크로](string-conversion-macros.md) 이러한 문자열 변환 매크로 사용의 예입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlconv.h

##  <a name="ca2caex"></a>  CA2CAEX::CA2CAEX

생성자입니다.

```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
변환할 텍스트 문자열입니다.

*nCodePage*<br/>
이 클래스에서 사용 되지 않습니다.

### <a name="remarks"></a>설명

번역에 필요한 버퍼를 만듭니다.

##  <a name="dtor"></a>  CA2CAEX::~CA2CAEX

소멸자입니다.

```
~CA2CAEX() throw();
```

### <a name="remarks"></a>설명

할당된 된 버퍼를 해제합니다.

##  <a name="m_psz"></a>  CA2CAEX::m_psz

소스 문자열을 저장 하는 데이터 멤버입니다.

```
LPCSTR m_psz;
```

##  <a name="operator_lpcstr"></a>  CA2CAEX::operator LPCSTR

변환 연산자입니다.

```
operator LPCSTR() const throw();
```

### <a name="return-value"></a>반환 값

LPCSTR 입력할 텍스트 문자열을 반환 합니다.

## <a name="see-also"></a>참고자료

[CA2AEX 클래스](../../atl/reference/ca2aex-class.md)<br/>
[CA2WEX 클래스](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX 클래스](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX 클래스](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX 클래스](../../atl/reference/cw2wex-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
