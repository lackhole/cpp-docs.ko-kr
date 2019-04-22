---
title: COleDispatchException 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
ms.openlocfilehash: 2d5b9d2a0dc1e716ea8cb20f0d0dcb4c5d765079
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769058"
---
# <a name="coledispatchexception-class"></a>COleDispatchException 클래스

OLE 자동화의 핵심인 OLE `IDispatch` 인터페이스에만 해당하는 예외를 처리합니다.

## <a name="syntax"></a>구문

```
class COleDispatchException : public CException
```

## <a name="members"></a>멤버

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|오류에 대 한 도움말 컨텍스트입니다.|
|[COleDispatchException::m_strDescription](#m_strdescription)|구두 오류 설명입니다.|
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|파일을 사용 하는 데 도움이 `m_dwHelpContext`합니다.|
|[COleDispatchException::m_strSource](#m_strsource)|예외를 생성 하는 응용 프로그램입니다.|
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-특정 오류 코드입니다.|

## <a name="remarks"></a>설명

같은 다른 예외 클래스에서 파생 된 `CException` 기본 클래스 `COleDispatchException` THROW, THROW_LAST, TRY, CATCH, AND_CATCH, 및 END_CATCH 매크로 사용 하 여 사용할 수 있습니다.

일반적으로 호출 해야 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) 만들고 throw 하는 `COleDispatchException` 개체입니다.

예외에 대 한 자세한 내용은 문서를 참조 하세요 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md) 고 [예외: OLE 예외](../../mfc/exceptions-ole-exceptions.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleDispatchException`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

##  <a name="m_dwhelpcontext"></a>  COleDispatchException::m_dwHelpContext

응용 프로그램의 도움말의 도움말 컨텍스트를 식별 (합니다. HLP) 파일입니다.

```
DWORD m_dwHelpContext;
```

### <a name="remarks"></a>설명

이 멤버 함수에 의해 설정 됩니다 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) 때 예외가 throw 됩니다.

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)에 대한 예제를 참조하세요.

##  <a name="m_strdescription"></a>  COleDispatchException::m_strDescription

"디스크 꽉 참."와 같은 일반 언어로 된 오류 설명을 포함합니다.

```
CString m_strDescription;
```

### <a name="remarks"></a>설명

이 멤버 함수에 의해 설정 됩니다 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) 때 예외가 throw 됩니다.

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)에 대한 예제를 참조하세요.

##  <a name="m_strhelpfile"></a>  COleDispatchException::m_strHelpFile

프레임 워크 응용 프로그램의 도움말 파일의 이름으로이 문자열을 채웁니다.

```
CString m_strHelpFile;
```

##  <a name="m_strsource"></a>  COleDispatchException::m_strSource

프레임 워크 예외를 생성 하는 응용 프로그램의 이름으로이 문자열을 채웁니다.

```
CString m_strSource;
```

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)에 대한 예제를 참조하세요.

##  <a name="m_wcode"></a>  COleDispatchException::m_wCode

응용 프로그램에 특정 오류 코드를 포함 합니다.

```
WORD m_wCode;
```

### <a name="remarks"></a>설명

이 멤버 함수에 의해 설정 됩니다 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) 때 예외가 throw 됩니다.

## <a name="see-also"></a>참고자료

[CALCDRIV MFC 샘플](../../overview/visual-cpp-samples.md)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDispatchDriver 클래스](../../mfc/reference/coledispatchdriver-class.md)<br/>
[COleException 클래스](../../mfc/reference/coleexception-class.md)
