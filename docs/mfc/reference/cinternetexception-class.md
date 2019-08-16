---
title: CInternetException 클래스
ms.date: 11/04/2016
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
ms.openlocfilehash: c4f4c7a5b7594270aff9dfbc224e9a66ba09be3f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505916"
---
# <a name="cinternetexception-class"></a>CInternetException 클래스

인터넷 작업과 관련된 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CInternetException : public CException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CInternetException::CInternetException](#cinternetexception)|`CInternetException` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|Description|
|----------|-----------------|
|[CInternetException::m_dwContext](#m_dwcontext)|예외를 발생 시킨 작업과 관련 된 컨텍스트 값입니다.|
|[CInternetException::m_dwError](#m_dwerror)|예외를 발생 시킨 오류입니다.|

## <a name="remarks"></a>설명

클래스 `CInternetException` 에는 두 개의 공용 데이터 멤버가 포함 되어 있습니다. 하나는 예외와 연결 된 오류 코드를 포함 하 고 다른 하나는 오류와 연결 된 인터넷 응용 프로그램의 컨텍스트 식별자를 포함 합니다.

인터넷 응용 프로그램의 컨텍스트 식별자에 대 한 자세한 내용은 WinInet을 [사용한 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)문서를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

##  <a name="cinternetexception"></a>  CInternetException::CInternetException

이 멤버 함수는 개체를 `CInternetException` 만들 때 호출 됩니다.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>매개 변수

*dwError*<br/>
예외를 발생 시킨 오류입니다.

### <a name="remarks"></a>설명

CInternetException을 throw 하려면 [AFXTHROWINTERNETEXCEPTION](internet-url-parsing-globals.md#afxthrowinternetexception)MFC 전역 함수를 호출 합니다.

##  <a name="m_dwcontext"></a>  CInternetException::m_dwContext

관련 인터넷 작업과 관련 된 컨텍스트 값입니다.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>설명

컨텍스트 식별자는 원래 [Cinternetsession](../../mfc/reference/cinternetsession-class.md) 에 지정 되 고 MFC에서 [cinternetsession](../../mfc/reference/cinternetconnection-class.md)및 [cinternetsession](../../mfc/reference/cinternetfile-class.md)파생 클래스로 전달 됩니다. 이 기본값을 재정의 하 고 *Dwcontext* 매개 변수를 선택한 값으로 할당할 수 있습니다. *Dwcontext* 는 지정 된 개체의 모든 작업과 연결 됩니다. *Dwcontext* 는 [Cinternetsession:: onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)에서 반환 하는 작업의 상태 정보를 식별 합니다.

##  <a name="m_dwerror"></a>  CInternetException::m_dwError

예외를 발생 시킨 오류입니다.

```
DWORD m_dwError;
```

### <a name="remarks"></a>설명

이 오류 값은 WINERROR.H에 있는 시스템 오류 코드 일 수 있습니다. H 또는 WININET의 오류 값입니다. 넣기.

Win32 오류 코드 목록은 [오류 코드](/windows/win32/Debug/system-error-codes)를 참조 하세요. 인터넷 관련 오류 메시지 목록은을 참조 하십시오. 두 항목 모두 Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)
