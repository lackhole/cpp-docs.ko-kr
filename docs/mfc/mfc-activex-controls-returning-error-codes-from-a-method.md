---
title: 'MFC ActiveX 컨트롤: 메서드에서 오류 코드를 반환합니다.'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
ms.openlocfilehash: 0800c1827c636dd81e2928e33c0ee2afde4c94ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324274"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX 컨트롤: 메서드에서 오류 코드를 반환합니다.

이 문서에서는 ActiveX 컨트롤 메서드에서 오류 코드를 반환 하는 방법을 설명 합니다.

메서드 내에서 오류가 발생 했음을 알리는를 사용 해야 합니다 [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) 매개 변수로 SCODE (상태 코드)를 사용 하는 멤버 함수입니다. 미리 정의 된 SCODE를 사용 하거나 자신만 정의 수 있습니다.

> [!NOTE]
>  `ThrowError` 속성의 Get 또는 Set 내에서 오류를 반환 하는 수단 으로만 사용 하려는 함수 또는 메서드를 자동화 합니다. 이 스택에 적절 한 예외 처리기 수 있는 시간이 존재 합니다.

도우미 함수는 가장 일반적인 같은 미리 정의 된 SCODEs에 대 한 존재 [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported)하십시오 [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), 및 [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).

목록을 미리 정의 된 SCODEs 및 사용자 지정 SCODEs 정의 대 한 지침 섹션을 참조 하세요 [Your ActiveX 컨트롤의 오류 처리](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX 컨트롤에서: 고급 항목입니다.

코드의 다른 영역에서 예외를 보고 하는 방법은 참조 하세요 [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) 및 섹션 [Your ActiveX 컨트롤의 오류 처리](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX 컨트롤에서: 고급 항목입니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
