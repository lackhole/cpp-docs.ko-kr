---
title: CInvalidArgException 클래스
ms.date: 11/04/2016
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
ms.openlocfilehash: d2df9b482fe95ad0a13a85a51037a4cbbc28d057
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392623"
---
# <a name="cinvalidargexception-class"></a>CInvalidArgException 클래스

이 클래스는 잘못된 인수 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CInvalidArgException : public CSimpleException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CInvalidArgException::CInvalidArgException](#cinvalidargexception)|생성자입니다.|

## <a name="remarks"></a>설명

`CInvalidArgException` 개체는 잘못 된 인수 예외 상태를 나타냅니다.

예외 처리에 대 한 자세한 내용은 참조는 [CException 클래스](../../mfc/reference/cexception-class.md) 항목 및 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="cinvalidargexception"></a>  CInvalidArgException::CInvalidArgException

생성자입니다.

```
CInvalidArgException();
```

### <a name="remarks"></a>설명

이 생성자를 직접 사용 하지 마십시오 전역 함수를 호출 **AfxThrowInvalidArgException**합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CSimpleException 클래스](../../mfc/reference/csimpleexception-class.md)
