---
title: 프레임 창 제거
ms.date: 11/04/2016
f1_keywords:
- PostNcDestroy
helpviewer_keywords:
- Default method [MFC]
- DestroyWindow method [MFC]
- frame windows [MFC], destroying
- OnNcDestroy method, and frame windows
- document frame windows [MFC], destroying
- destroying frame windows
- MFC, frame windows
- windows [MFC], destroying
- OnClose method [MFC]
- PostNcDestroy method [MFC]
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
ms.openlocfilehash: b64298bd2b0f14c30c824d78947a17628adec8b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394639"
---
# <a name="destroying-frame-windows"></a>프레임 창 제거

MFC 프레임 워크는 프레임 워크 문서 및 뷰를 사용 하 여 연결 된 해당 창에 대 한 작성 뿐만 아니라 창 소멸을 관리 합니다. 추가 windows를 만든 있다면 제거 하는 일을 담당 합니다.

Framework에서 사용자가 창의 기본 프레임 창을 닫으면 [OnClose](../mfc/reference/cwnd-class.md#onclose) 처리기 호출 [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)합니다. Windows 창을 소멸 될 때 호출 되는 마지막 멤버 함수는 [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), 일부 정리를 수행 하는 호출을 [기본](../mfc/reference/cwnd-class.md#default) 멤버 Windows 정리를 수행 하도록 함수를 마지막으로 호출 합니다 가상 멤버 함수 [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy)합니다. 합니다 [CFrameWnd](../mfc/reference/cframewnd-class.md) 구현의 `PostNcDestroy` 삭제는 C++ 창 개체입니다. 에 절대 사용는 C++ **삭제** 프레임 창에는 연산자입니다. 대신 `DestroyWindow`를 사용하세요.

주 창의 닫을 때 응용 프로그램을 종료 합니다. 저장 되지 않은 문서 수정 되 면 프레임 워크 문서를 저장 해야 하는 경우 요청 메시지 상자를 표시 하 고 필요한 경우 적절 한 문서를 저장 된다는 보장 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>참고자료

[프레임 창 사용](../mfc/using-frame-windows.md)
