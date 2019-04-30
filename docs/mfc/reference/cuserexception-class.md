---
title: CUserException 클래스
ms.date: 11/04/2016
f1_keywords:
- CUserException
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
ms.openlocfilehash: 72d8537616792859a2b00a1a5cd880ce5eb452bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323439"
---
# <a name="cuserexception-class"></a>CUserException 클래스

최종 사용자 작업을 중지하도록 throw됩니다.

## <a name="syntax"></a>구문

```
class CUserException : public CSimpleException
```

## <a name="remarks"></a>설명

사용 하 여 `CUserException` 응용 프로그램별 예외 throw/catch 예외 메커니즘을 사용 하려는 경우. 클래스 이름에 "user" 와"내 사용자 예외를 처리 해야 하는 것입니다." 해석 될 수 있습니다.

A `CUserException` 전역 함수를 호출한 후 일반적으로 예외가 `AfxMessageBox` 작업에 실패 한 사용자에 게 알릴 합니다. 예외 처리기를 작성할 때 사용자 일반적으로 이미 보고 된 오류 때문에 특별히 예외를 처리 합니다. 일부 경우에서이 예외를 throw 하는 프레임 워크입니다. Throw 하는 `CUserException` 사용자가 직접 사용자 알림 및 전역 함수를 호출할 `AfxThrowUserException`합니다.

아래 예제에서 실패할 수 있는 작업을 포함 하는 함수는 사용자 경고 및 throw를 `CUserException`입니다. 호출 함수는 예외를 catch 하 고 특수 처리:

[!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]

사용 하 여 대 한 자세한 내용은 `CUserException`, 문서를 참조 하세요 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CUserException`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)
