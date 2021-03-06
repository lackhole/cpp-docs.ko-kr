---
title: COleException 클래스
ms.date: 11/04/2016
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
ms.openlocfilehash: 96061f704d9df6cd788e362652b6ed22a7ffa999
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503941"
---
# <a name="coleexception-class"></a>COleException 클래스

OLE 작업과 관련된 예외 조건을 나타냅니다.

## <a name="syntax"></a>구문

```
class COleException : public CException
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleException::Process](#process)|Catch 된 예외를 OLE 반환 코드로 변환 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[COleException::m_sc](#m_sc)|예외에 대 한 이유를 나타내는 상태 코드를 포함 합니다.|

## <a name="remarks"></a>설명

클래스 `COleException` 에는 예외에 대 한 이유를 나타내는 상태 코드를 포함 하는 공용 데이터 멤버가 포함 되어 있습니다.

일반적으로 개체를 `COleException` 직접 만들지 마십시오. 대신 [AfxThrowOleException](exception-processing.md#afxthrowoleexception)를 호출 해야 합니다.

예외에 대 한 자세한 내용은 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md) 및 [예외 문서를 참조 하세요. OLE 예외](../../mfc/exceptions-ole-exceptions.md).

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleException`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

##  <a name="m_sc"></a>  COleException::m_sc

이 데이터 멤버는 예외의 원인을 나타내는 OLE 상태 코드를 포함 합니다.

```
SCODE m_sc;
```

### <a name="remarks"></a>설명

이 변수의 값은 [AfxThrowOleException](exception-processing.md#afxthrowoleexception)에 의해 설정 됩니다.

이에 대 한 자세한 내용은 Windows SDK의 [COM 오류 코드 구조](/windows/win32/com/structure-of-com-error-codes) 를 참조 하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]

##  <a name="process"></a>  COleException::Process

**Process** 멤버 함수를 호출 하 여 catch 된 예외를 OLE 상태 코드로 변환 합니다.

```
static SCODE PASCAL Process(const CException* pAnyException);
```

### <a name="parameters"></a>매개 변수

*pAnyException*<br/>
Catch 된 예외에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

OLE 상태 코드입니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  이 함수는 **정적**함수입니다.

이에 대 한 자세한 내용은 Windows SDK의 [COM 오류 코드 구조](/windows/win32/com/structure-of-com-error-codes) 를 참조 하십시오.

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[MFC 샘플 CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
