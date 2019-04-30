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
ms.openlocfilehash: dedf8926f02dd36dc8d6ac8ab5ff4056b60dfc91
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345710"
---
# <a name="cinternetexception-class"></a>CInternetException 클래스

인터넷 작업과 관련된 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CInternetException : public CException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CInternetException::CInternetException](#cinternetexception)|`CInternetException` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CInternetException::m_dwContext](#m_dwcontext)|예외를 발생 시킨 작업과 연결 된 컨텍스트 값입니다.|
|[CInternetException::m_dwError](#m_dwerror)|예외를 발생 시킨 오류입니다.|

## <a name="remarks"></a>설명

`CInternetException` 클래스는 두 명의 public 데이터 멤버를 포함: 예외와 관련 된 오류 코드를 포함 하는 하나 및 다른 오류와 연결 된 인터넷 응용 프로그램의 컨텍스트 식별자를 포함 합니다.

인터넷 응용 프로그램에 대 한 컨텍스트 식별자에 대 한 자세한 내용은 문서를 참조 하세요 [WinInet을 사용 하 여 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

##  <a name="cinternetexception"></a>  CInternetException::CInternetException

이 멤버 함수를 호출 하는 경우는 `CInternetException` 개체가 만들어집니다.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>매개 변수

*dwError*<br/>
예외를 발생 시킨 오류입니다.

### <a name="remarks"></a>설명

CInternetException를 throw 하려면 MFC 전역 함수를 호출 [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception)합니다.

##  <a name="m_dwcontext"></a>  CInternetException::m_dwContext

인터넷 관련 작업과 연결 된 컨텍스트 값입니다.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>설명

컨텍스트 식별자에 원래 지정 된 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 및 MFC에서 전달한 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)-및 [CInternetFile](../../mfc/reference/cinternetfile-class.md)-클래스를 파생 합니다. 이 기본값을 재정의 하 고 할당할 수 있습니다 *dwContext* 매개 변수를 선택 해 값입니다. *dwContext* 지정된 된 개체의 모든 작업을 사용 하 여 연결 합니다. *dwContext* 반환한 작업의 상태 정보를 식별 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)합니다.

##  <a name="m_dwerror"></a>  CInternetException::m_dwError

예외를 발생 시킨 오류입니다.

```
DWORD m_dwError;
```

### <a name="remarks"></a>설명

오류 값이 시스템 수 WINERROR에 오류 코드입니다. H 또는 WININET에서 오류 값입니다. 8.

Win32 오류 코드 목록은 참조 하세요 [오류 코드](/windows/desktop/Debug/system-error-codes)합니다. 인터넷 관련 오류 메시지 목록을 참조 하세요. 두 항목은 Windows sdk에서입니다.

## <a name="see-also"></a>참고자료

[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)
