---
title: 인쇄 및 인쇄 미리 보기
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
ms.openlocfilehash: 70740922ec7f2030d14eebee72144a373550aacc
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768889"
---
# <a name="printing-and-print-preview"></a>인쇄 및 인쇄 미리 보기

MFC 클래스를 통해 프로그램의 문서에 대 한 인쇄 및 인쇄 미리 보기를 지 원하는 [CView](../mfc/reference/cview-class.md)합니다. 기본 인쇄 및 인쇄 미리 보기에 대 한 뷰 클래스를 재정의 하기만 [OnDraw](../mfc/reference/cview-class.md#ondraw) 멤버 함수를 계속 수행 해야 합니다. 해당 함수는 실제 프린터에 대 한 프린터 장치 컨텍스트를 화면에 보기 그리거나 화면에서 프린터를 시뮬레이션 하는 장치 컨텍스트에 대 수입니다.

또한 다중 페이지 문서 인쇄 및 페이지를 매기에 인쇄 된 문서에 머리글 및 바닥글을 추가 하려면 미리 보기를 관리 하는 코드를 추가할 수 있습니다.

다음이의 문서 인쇄가 Microsoft Foundation 클래스 라이브러리 (MFC)에서 구현 되는 방법 및 프레임 워크에 이미 기본 제공 인쇄 아키텍처를 활용 하는 방법을 설명 합니다. 문서는 또한 MFC 인쇄 미리 보기 기능을 쉽게 구현에서 지 원하는 방법 및 사용 하 여 해당 기능을 수정 하는 방법에 설명 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [인쇄](../mfc/printing.md)

- [인쇄 미리 보기 아키텍처](../mfc/print-preview-architecture.md)

- [샘플](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>참고자료

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
