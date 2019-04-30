---
title: 머리글 및 바닥글
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], multipage documents
- page headers [MFC], printing
- headers [MFC], printing
- footers [MFC], printing
- page footers [MFC], printing
- page headers [MFC]
- printing [MFC], headers and footers
- page footers [MFC]
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
ms.openlocfilehash: 1e2e57331ccbc7f0afd7b82dc035410af495abd8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297231"
---
# <a name="headers-and-footers"></a>머리글 및 바닥글

이 문서에는 인쇄 된 문서에 머리글 및 바닥글을 추가 하는 방법을 설명 합니다.

화면에서 문서를 볼 때 문서 및 문서의 현재 위치 이름 제목 표시줄 및 상태 표시줄에 일반적으로 표시 됩니다. 인쇄 문서 복사본을 보면 머리글 또는 바닥글에 표시 된 이름 및 페이지 수 있어야 유용 합니다. 이 어떻게 수행 하는 인쇄 및 화면 디스플레이에서 다를 프로그램도는 WYSIWYG에는 일반적인 방법입니다.

합니다 [OnPrint](../mfc/reference/cview-class.md#onprint) 멤버 함수는 각 페이지에 대 한 호출 되므로 및 화면 디스플레이 대 한 인쇄에 대해서만 호출 되므로 머리글이 나 바닥글을 인쇄 하는 적절 한 위치입니다. 머리글 또는 바닥글을 인쇄 하는 별도 함수를 정의 하 고 프린터 장치 컨텍스트를 전달할 수 `OnPrint`입니다. 원본 창 또는 호출 하기 전에 범위를 조정 해야 할 수 있습니다 [OnDraw](../mfc/reference/cview-class.md#ondraw) 본문의 머리글 또는 바닥글이 페이지 중복 되지 않도록 합니다. 수정할 수도 있습니다 `OnDraw` 적합 한 문서 페이지의 양을 줄일 수 있으므로 합니다.

머리글 또는 바닥글에서 수행한 영역을 사용 하는 것에 대 한 보정 하는 한 가지 방법은 합니다 **m_rectDraw** 소속 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)합니다. 페이지 인쇄 될 때마다가이 멤버는 페이지의 사용 가능한 영역을 사용 하 여 초기화 됩니다. 페이지의 본문을 인쇄 하기 전에 머리글 또는 바닥글을 인쇄 하는 경우에 저장 되는 사각형의 크기를 줄일 수 있습니다 **m_rectDraw** 머리글 또는 바닥글에서 수행한 영역에 대 한 계정에 있습니다. 그런 다음 `OnPrint` 참조할 수 있습니다 **m_rectDraw** 얼마나 많은 영역 페이지의 본문을 인쇄 하기 위해 계속 확인 합니다.

헤더 또는 다른 모든 항목을 인쇄할 수 없습니다 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)하기 전에 호출 되므로는 `StartPage` 멤버 함수 [CDC](../mfc/reference/cdc-class.md) 가 호출 되었습니다. 이 시점에서 프린터 장치 컨텍스트는 페이지 경계에 간주 됩니다. 에서만 인쇄를 수행할 수 있습니다는 `OnPrint` 멤버 함수입니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [다중 페이지 문서 인쇄](../mfc/multipage-documents.md)

- [인쇄용 GDI 리소스 할당](../mfc/allocating-gdi-resources.md)

## <a name="see-also"></a>참고자료

[인쇄](../mfc/printing.md)
